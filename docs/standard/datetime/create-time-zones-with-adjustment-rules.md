---
title: 如何：创建带有调整规则的时区
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], creating
- time zones [.NET Framework], and adjustment rules
- adjustment rule [.NET Framework]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
ms.openlocfilehash: 4ef3d93746c5688dc15fc7e45d9be054dcfba4c8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132555"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a>如何：创建带有调整规则的时区

由于以下几个原因，应用程序所需的确切时区信息在特定系统上可能不存在：

- 本地系统的注册表中从未定义过该时区。

- 已修改或删除注册表中有关时区的数据。

- 对于特定的历史时间段，时区没有有关时区调整的准确信息。

在这些情况下，可以调用 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 方法来定义应用程序所需的时区。 您可以使用此方法的重载来创建具有或不带调整规则的时区。 如果时区支持夏令时，则可以用固定或浮动调整规则定义调整。 （有关这些术语的定义，请参阅时区[概述](../../../docs/standard/datetime/time-zone-overview.md)中的 "时区术语" 部分。）

> [!IMPORTANT]
> 通过调用 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 方法创建的自定义时区不会添加到注册表中。 相反，它们只能通过 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 方法调用返回的对象引用进行访问。

本主题说明如何创建具有调整规则的时区。 若要创建不支持夏令时调整规则的时区，请参阅[如何：创建不带调整规则的时区](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)。

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a>创建具有浮动调整规则的时区

1. 对于每个调整（即，每次从一个特定时间间隔转换到标准时间时），请执行以下操作：

    1. 定义时区调整的开始转换时间。

       您必须调用 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> 方法，并向其传递一个定义转换时间的 <xref:System.DateTime> 值、一个定义转换月份的整数值、一个整数值（用于定义转换发生的周）以及一个用于定义的 <xref:System.DayOfWeek> 值发生转换的一周中的哪一天。 此方法调用将实例化一个 <xref:System.TimeZoneInfo.TransitionTime> 对象。

    2. 为时区调整定义结束转换时间。 这需要对 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> 方法的另一次调用。 此方法调用将实例化第二个 <xref:System.TimeZoneInfo.TransitionTime> 对象。

    3. 调用 <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> 方法，并向其传递调整的有效开始日期和结束日期、定义转换中时间量的 <xref:System.TimeSpan> 对象和两个 <xref:System.TimeZoneInfo.TransitionTime> 对象，这些对象定义在夏令时发生转换的时间。 此方法调用将实例化一个 <xref:System.TimeZoneInfo.AdjustmentRule> 对象。

    4. 将 <xref:System.TimeZoneInfo.AdjustmentRule> 对象分配给 <xref:System.TimeZoneInfo.AdjustmentRule> 对象的数组。

2. 定义时区的显示名称。 显示名称采用相当标准的格式，在此格式中，时区与协调世界时（UTC）的偏移量括在括号中，后面跟有标识时区的字符串、时区中的一个或多个城市，或者一个或多个 cou时区中的 ntries 或区域。

3. 定义时区标准时间的名称。 通常，此字符串还用作时区的标识符。

4. 定义时区的夏令时的名称。

5. 如果要使用不同于时区的标准名称的标识符，请定义时区标识符。

6. 实例化定义时区与 UTC 的偏移量的 <xref:System.TimeSpan> 对象。 时间时区晚于 UTC 的时区具有正偏移量。 其时间早于 UTC 的时区具有负偏移量。

7. 调用 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> 方法来实例化新时区。

## <a name="example"></a>示例

下面的示例为美国定义了一个中部标准时区，其中包括从1918到当前时间间隔内的各种时间间隔的调整规则。

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

在此示例中创建的时区具有多个调整规则。 必须小心，以确保任何调整规则的有效开始日期和结束日期不会与另一个调整规则的日期重叠。 如果有重叠，则会引发 <xref:System.InvalidTimeZoneException>。

对于浮点调整规则，将值5传递到 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 方法的 `week` 参数，以指示在特定月份的最后一周发生转换。

在创建要在 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> 方法调用中使用的 <xref:System.TimeZoneInfo.AdjustmentRule> 对象数组时，代码可以将数组初始化为要为时区创建的调整数所需的大小。 相反，此代码示例调用 <xref:System.Collections.Generic.List%601.Add%2A> 方法，将每个调整规则添加到 <xref:System.TimeZoneInfo.AdjustmentRule> 对象的泛型 <xref:System.Collections.Generic.List%601> 集合。 然后，该代码调用 <xref:System.Collections.Generic.List%601.CopyTo%2A> 方法将此集合的成员复制到数组中。

该示例还使用 <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> 方法定义固定日期调整。 这类似于调用 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 方法，但它只要求转换参数的时间、月份和日期。

可以使用如下所示的代码测试该示例：

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a>编译代码

此示例需要：

- 导入以下命名空间：

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>请参阅

- [日期、时间和时区](../../../docs/standard/datetime/index.md)
- [时区概述](../../../docs/standard/datetime/time-zone-overview.md)
- [如何：创建不含调整规则的时区](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)

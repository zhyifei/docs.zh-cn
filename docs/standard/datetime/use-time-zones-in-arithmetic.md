---
title: 如何：在日期和时间算术中使用时区
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], adding and subtracting
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 417d8f00c9323f096a2d6228e853a55b1573f48c
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106718"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a>如何：在日期和时间算术中使用时区

通常, 当您使用<xref:System.DateTime>或<xref:System.DateTimeOffset>值执行日期和时间算术运算时, 结果将不反映任何时区调整规则。 即使日期和时间值的时区清晰标识 (例如, 当<xref:System.DateTime.Kind%2A>属性设置为<xref:System.DateTimeKind.Local>时), 也是如此。 本主题演示如何对属于特定时区的日期和时间值执行算术运算。 算术运算的结果将反映时区调整规则。

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a>将调整规则应用到日期和时间运算

1. 采取措施将日期和时间值与其所属时区紧密耦合。 例如声明同时包含日期和时间值及其时区的结构。 下面的示例使用此方法将<xref:System.DateTime>值与其时区链接。

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. 通过调用<xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>方法<xref:System.TimeZoneInfo.ConvertTime%2A>或方法, 将时间转换为协调世界时 (UTC)。

3. 对 UTC 时间执行算术运算。

4. 通过调用<xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>方法将时间从 UTC 转换为原始时间的关联时区。

## <a name="example"></a>示例

下方示例向中部标准时间 2008 年 3 月 9 日凌晨 1:30 添加了 2 小时 30 分钟。 30 分钟后（即 2008 年 3 月 9 日凌晨 2:00） 会发生到夏时令的时区转换。 由于该示例遵从了上一部分中列出的四个步骤，因此它将最终时间正确地报告为 2008 年 3 月 9 日凌晨 2:00。

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

<xref:System.DateTime> 和<xref:System.DateTimeOffset>值都与它们所属的任何时区解除关联。 只有能够立即识别任意日期和时间所属的时区，才能在执行日期和时间运算时自动应用时区调整规则。 这意味着，日期和时间及其关联时区必须紧密耦合。 可通过方法进行此操作，其中包括：

- 假设应用程序中使用的所有时间均属于某个特定时区。 尽管在某些情况下适用，但此方法的灵活性和可移植性有限。

- 在类型字段中包括日期和时间及其关联时区，定义将二者紧密耦合的类型。 代码示例中使用了此方法，定义了将日期和时间以及时区存储在两个成员字段中的结构。

该示例演示如何对<xref:System.DateTime>值执行算术运算, 以便将时区调整规则应用到结果。 但是, <xref:System.DateTimeOffset>可以轻松地使用值。 下面的示例演示了如何调整原始示例中的代码, <xref:System.DateTimeOffset> <xref:System.DateTime>而不是使用值。

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

请注意, 如果此加法只是对<xref:System.DateTimeOffset>值执行, 而不是先将其转换为 UTC, 则结果将反映正确的时间点, 但其偏移量不反映指定时区的时间。

## <a name="compiling-the-code"></a>编译代码

此示例需要：

- 该命名空间将`using`与语句一起导入 (在C#代码中是必需的)。 <xref:System>

## <a name="see-also"></a>请参阅

- [日期、时间和时区](../../../docs/standard/datetime/index.md)
- [使用日期和时间执行算术运算](../../../docs/standard/datetime/performing-arithmetic-operations.md)

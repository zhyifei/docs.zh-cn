---
title: 在各时区之间转换时间
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], converting
- time zones [.NET Framework], conversions
- UTC times, converting
- converting times
- local time conversions
ms.assetid: a51e1a3b-c983-4320-b31a-1f9fa3cf824a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5b78e3985169954d71b479aa2e8a034f61afc01
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106969"
---
# <a name="converting-times-between-time-zones"></a>在各时区之间转换时间

对任何使用日期和时间的应用程序而言，处理各时区之间的差异变得愈发重要。 应用程序不能再假设所有时间都能用本地时间表示, 这是从<xref:System.DateTime>结构中可用的时间。 例如，显示美国东部当前时间的网页对东亚客户而言缺乏可信度。 本主题介绍如何将时间从一个时区转换到另一个时区, 以及如何转换<xref:System.DateTimeOffset>具有时区感知限制的值。

## <a name="converting-to-coordinated-universal-time"></a>转换为协调世界时

协调世界时 (UTC) 是一项高精度的原子时标准。 世界的时区表示为相对于 UTC 的正/负偏移量。 因此，UTC 提供一种无时区或中间时区的时间。 如果日期和时间在计算机之间的可移植性非常重要，则建议使用 UTC 时间。 (有关使用日期和时间的详细信息和其他最佳做法, 请参阅在[.NET Framework 中使用 DateTime 的编码最佳做法](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973825(v=msdn.10))。)通过将各个时区转换为 UTC，可以简化时间的比较。

> [!NOTE]
> 您还可以对<xref:System.DateTimeOffset>结构进行序列化以明确表示单个时间点。 由于<xref:System.DateTimeOffset>对象会存储日期和时间值以及其相对于 utc 的偏移量, 因此, 它们始终表示与 utc 的关系中的特定时间点。

将时间转换为 UTC 的最简单方法是调用`static` (`Shared`在 Visual Basic) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType>方法。 方法所执行的确切转换取决于`dateTime`参数的<xref:System.DateTime.Kind%2A>属性的值, 如下表所示。

| `DateTime.Kind`            | 转换                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | 将本地时间转换为 UTC。                                                    |
| `DateTimeKind.Unspecified` | 假定 `dateTime` 参数为本地时间并将本地时间转换为 UTC。 |
| `DateTimeKind.Utc`         | 返回未更改的 `dateTime` 参数。                                    |

以下代码可将当前本地时间转换为 UTC，并将结果显示在控制台上。

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

如果日期和时间值不表示本地时间或 UTC, 则该<xref:System.DateTime.ToUniversalTime%2A>方法可能会返回错误的结果。 但是, 您可以使用<xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType>方法来转换指定时区的日期和时间。 (有关检索<xref:System.TimeZoneInfo>表示目标时区的对象的详细信息, 请参阅[查找本地系统上定义的时区](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)。)下面的代码使用<xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType>方法将东部标准时间转换为 UTC。

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

请注意, <xref:System.ArgumentException> <xref:System.DateTime>如果对象的<xref:System.DateTime.Kind%2A>属性与时区不匹配, 此方法将引发。 <xref:System.DateTime.Kind%2A>如果属性为<xref:System.DateTimeKind.Utc?displayProperty=nameWithType> <xref:System.DateTime.Kind%2A> ,但对象不<xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType>表示本地时区, 或者属性为但对象不相等,则会发生不匹配。<xref:System.TimeZoneInfo> <xref:System.TimeZoneInfo> <xref:System.DateTimeKind.Local?displayProperty=nameWithType>

所有这些方法<xref:System.DateTime>都将值作为参数, 并返回<xref:System.DateTime>一个值。 对于<xref:System.DateTimeOffset>值<xref:System.DateTimeOffset.ToUniversalTime%2A> , 结构具有实例方法, 该方法可将当前实例的日期和时间转换为 UTC。 <xref:System.DateTimeOffset> 下面的示例调用<xref:System.DateTimeOffset.ToUniversalTime%2A>方法, 将本地时间和几个其他时间转换为协调世界时 (UTC)。

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>将 UTC 转换为指定的时区

若要将 UTC 转换为本地时间, 请参阅后面的 "将 UTC 转换为本地时间" 一节。 若要将 UTC 转换为任何指定时区中的时间, 请调用<xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>方法。 该方法采用两个参数：

- 要转换的 UTC。 这必须是<xref:System.DateTime>其<xref:System.DateTime.Kind%2A>属性设置为`Unspecified`或`Utc`的值。

- UTC 要转换的目标时区。

以下代码可将 UTC 转换为中部标准时间。

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>将 UTC 转换为本地时间

若要将 UTC 转换为本地时间, <xref:System.DateTime.ToLocalTime%2A>请调用要<xref:System.DateTime>转换其时间的对象的方法。 此方法的确切行为取决于对象的<xref:System.DateTime.Kind%2A>属性值, 如下表所示。

| `DateTime.Kind`            | 转换                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | 返回未<xref:System.DateTime>更改的值。                                      |
| `DateTimeKind.Unspecified` | <xref:System.DateTime>假定值为 utc 并将 utc 转换为本地时间。 |
| `DateTimeKind.Utc`         | <xref:System.DateTime>将值转换为本地时间。                                 |

> [!NOTE]
> 此<xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType>方法的行为`DateTime.ToLocalTime`与方法相同。 它采用单个参数, 即要转换的日期和时间值。

你还可以使用`static` (`Shared`在 Visual Basic) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType>方法将任何指定时区中的时间转换为本地时间。 下一节将讨论此方法。

## <a name="converting-between-any-two-time-zones"></a>在任意两个时区之间转换

您可以通过使用`static` <xref:System.TimeZoneInfo>类的以下两个 (`Shared`在 Visual Basic 中) 方法之一在任意两个时区之间进行转换:

- <xref:System.TimeZoneInfo.ConvertTime%2A>

  此方法的参数是要转换的日期和时间值、 `TimeZoneInfo`表示日期和时间值的时区的对象, `TimeZoneInfo`以及表示将日期和时间值转换为的时区的对象。

- <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  此方法的参数是要转换的日期和时间值、日期和时间值的时区的标识符, 以及要将日期和时间值转换为的时区的标识符。

这两种方法都<xref:System.DateTime.Kind%2A>要求要转换的日期和时间值的属性<xref:System.TimeZoneInfo> , 以及表示其时区的对象或时区标识符彼此对应。 否则会引发 <xref:System.ArgumentException>。 例如, 如果`Kind`日期和时间值的属性为`DateTimeKind.Local`, 则当作为`TimeZoneInfo.Local`参数传递给方法的`TimeZoneInfo`对象不等于时, 将引发异常。 如果作为参数传递给该方法的标识符不等于`TimeZoneInfo.Local.Id`, 则也会引发异常。

下面的<xref:System.TimeZoneInfo.ConvertTime%2A>示例使用方法将夏威夷标准时间转换为本地时间。

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>转换 DateTimeOffset 值

<xref:System.DateTimeOffset>对象所表示的日期和时间值不能完全识别时区, 因为在实例化对象时, 对象与其时区无关。 但是，大多数情况下，应用程序仅需根据两种相对于 UTC 的偏移量，而不是特定时区的时间来转换日期和时间。 若要执行此转换, 可以调用当前实例的<xref:System.DateTimeOffset.ToOffset%2A>方法。 该方法的单个参数是此方法要返回的新日期和时间值的偏移量。

例如，如果用户所请求网页的日期和时间已知，并且已被序列化为 MM/dd/yyyy hh:mm:ss zzzz 格式的字符串，以下 `ReturnTimeOnServer` 方法会将此日期和时间值转换为 Web 服务器上的日期和时间。

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)] 

如果向该方法传递字符串“9/1/2007 5:32:07 -05:00”（表示比 UTC 早五个小时的时区中的日期和时间），则对处于美国太平洋标准时区中的服务器，太平洋标准时区运行。

类还包含<xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>方法的重载, 该重载使用<xref:System.DateTimeOffset.ToOffset(System.TimeSpan)>值执行时区转换。 <xref:System.TimeZoneInfo> 此方法的参数是一个<xref:System.DateTimeOffset>值和一个对要将时间转换到的时区的引用。 方法调用将返回一个<xref:System.DateTimeOffset>值。 例如, 可以按`ReturnTimeOnServer`如下所示重写上一示例中的方法, 以<xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29>调用方法。

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>请参阅

- <xref:System.TimeZoneInfo>
- [日期、时间和时区](../../../docs/standard/datetime/index.md)
- [查找本地系统上定义的时区](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)

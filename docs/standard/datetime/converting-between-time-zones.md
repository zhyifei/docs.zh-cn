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
ms.openlocfilehash: 7547f0c2dd3651e478bb52106640a7b4525afc29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="converting-times-between-time-zones"></a>在各时区之间转换时间

对任何使用日期和时间的应用程序而言，处理各时区之间的差异变得愈发重要。 应用程序可以不再假定所有时间可以都表示的本地时间，即的时间可从<xref:System.DateTime>结构。 例如，显示美国东部当前时间的网页对东亚客户而言缺乏可信度。 本主题说明如何将时间从一个时区转换到另一个字符串，以及如何将转换<xref:System.DateTimeOffset>具有有限的时区感知的值。

## <a name="converting-to-coordinated-universal-time"></a>转换为协调世界时

协调世界时 (UTC) 是一项高精度的原子时标准。 世界的时区表示为相对于 UTC 的正/负偏移量。 因此，UTC 提供一种无时区或中间时区的时间。 如果日期和时间在计算机之间的可移植性非常重要，则建议使用 UTC 时间。 (有关详细信息和其他使用日期和时间的最佳实践，请参阅[编码在.NET Framework 中使用日期时间的最佳做法](https://msdn.microsoft.com/library/ms973825.aspx)。)通过将各个时区转换为 UTC，可以简化时间的比较。

> [!NOTE]
> 您还可以序列化<xref:System.DateTimeOffset>结构，以明确地表示的时间的单一点。 因为<xref:System.DateTimeOffset>对象存储以及其相对于 UTC 的偏移量的日期和时间值，它们始终为 UTC 表示的某个特定点关系中的时间。

将时间转换为 UTC 的最简单方法是调用`static`(`Shared`在 Visual Basic 中)<xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType>方法。 确切转换执行的方法取决于值`dateTime`参数的<xref:System.DateTime.Kind%2A>属性，如下表所示。

| `DateTime.Kind`            | 转换                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | 将本地时间转换为 UTC。                                                    |
| `DateTimeKind.Unspecified` | 假定 `dateTime` 参数为本地时间并将本地时间转换为 UTC。 |
| `DateTimeKind.Utc`         | 返回未更改的 `dateTime` 参数。                                    |

以下代码可将当前本地时间转换为 UTC，并将结果显示在控制台上。

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

> [!NOTE]
> <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType>方法不一定会生成相同的结果<xref:System.TimeZone.ToUniversalTime%2A?displayProperty=nameWithType>和<xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType>方法。 如果主机系统的本地时区包括多个调整规则，<xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType>将相应的规则应用于特定日期和时间。 其他两种方法始终应用最新调整规则。

如果日期和时间值不表示本地时间还是 UTC，<xref:System.DateTime.ToUniversalTime%2A>方法可能会返回错误结果。 但是，你可以使用<xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType>方法将从指定的时区的日期和时间。 (有关详细信息检索<xref:System.TimeZoneInfo>对象，表示目标时区，请参阅[查找本地系统上定义的时区](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)。)下面的代码使用<xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType>方法将东部标准时间转换为 UTC。

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

请注意，此方法将引发<xref:System.ArgumentException>如果<xref:System.DateTime>对象的<xref:System.DateTime.Kind%2A>属性与时区不匹配。 如果出现不匹配<xref:System.DateTime.Kind%2A>属性是<xref:System.DateTimeKind?displayProperty=nameWithType>但<xref:System.TimeZoneInfo>对象不表示本地时区，或者如果<xref:System.DateTime.Kind%2A>属性是<xref:System.DateTimeKind?displayProperty=nameWithType>但<xref:System.TimeZoneInfo>对象不等于<xref:System.DateTimeKind?displayProperty=nameWithType>。

所有这些方法采用<xref:System.DateTime>值作为参数并返回<xref:System.DateTime>值。 有关<xref:System.DateTimeOffset>值，<xref:System.DateTimeOffset>结构具有<xref:System.DateTimeOffset.ToUniversalTime%2A>实例将日期和时间的当前实例转换为 UTC 的方法。 下面的示例调用<xref:System.DateTimeOffset.ToUniversalTime%2A>方法将本地时间和几个其他时间转换为协调世界时 (UTC)。

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a>将 UTC 转换为指定的时区

若要将 UTC 转换为本地时间，请参阅"将转换 UTC 转换为本地时间"下一节。 若要将 UTC 转换为在你指定任何时区中的时间，调用<xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>方法。 该方法采用两个参数：

* 要转换的 UTC。 这必须是<xref:System.DateTime>值其<xref:System.DateTime.Kind%2A>属性设置为`Unspecified`或`Utc`。

* UTC 要转换的目标时区。

以下代码可将 UTC 转换为中部标准时间。

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a>将 UTC 转换为本地时间

若要转换为本地时间的 UTC，调用<xref:System.DateTime.ToLocalTime%2A>方法<xref:System.DateTime>对象要转换的时间。 方法的确切行为取决于对象的值<xref:System.DateTime.Kind%2A>属性，如下表所示。

| `DateTime.Kind`            | 转换                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | 返回<xref:System.DateTime>值保持不变。                                      |
| `DateTimeKind.Unspecified` | 假定<xref:System.DateTime>值为 UTC 并将 UTC 转换为本地时间。 |
| `DateTimeKind.Utc`         | 将转换<xref:System.DateTime>为本地时间的值。                                 |

> [!NOTE]
> <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType>方法的行为相同与`DateTime.ToLocalTime`方法。 它采用单个参数，这是要转换的日期和时间值。

你还可以将任何指定时区中的时间通过转换为本地时间`static`(`Shared`在 Visual Basic 中)<xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType>方法。 此方法将在下一部分中讨论。

## <a name="converting-between-any-two-time-zones"></a>在任意两个时区之间转换

你可使用以下两个任一任意两个时区之间转换`static`(`Shared`在 Visual Basic 中) 的方法<xref:System.TimeZoneInfo>类：

* <xref:System.TimeZoneInfo.ConvertTime%2A>

  此方法的参数是要转换的日期和时间值`TimeZoneInfo`表示时区的日期和时间值的对象和一个`TimeZoneInfo`对象，表示要转换的日期和时间值的时区。

* <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  此方法的参数是要转换到的日期和时间值中日期和要转换的时间值、 的日期和时间值的时区，标识符和时区的标识符。

这两种方法需要<xref:System.DateTime.Kind%2A>要转换的日期和时间值的属性和<xref:System.TimeZoneInfo>对象或时区标识符表示其所在的时区对应于另一个。 否则会引发 <xref:System.ArgumentException>。 例如，如果`Kind`的日期和时间值的属性是`DateTimeKind.Local`，如果引发异常`TimeZoneInfo`作为参数传递给方法的对象是否不等于`TimeZoneInfo.Local`。 如果作为参数传递给方法的标识符是否不等于，也会引发异常`TimeZoneInfo.Local.Id`。

下面的示例使用<xref:System.TimeZoneInfo.ConvertTime%2A>方法将从夏威夷标准时间转换为本地时间。

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a>转换 DateTimeOffset 值

所表示的日期和时间值<xref:System.DateTimeOffset>对象不是完全时区感知因为对象不再关联时从其时区时实例化。 但是，大多数情况下，应用程序仅需根据两种相对于 UTC 的偏移量，而不是特定时区的时间来转换日期和时间。 若要执行此转换，可以调用当前实例的<xref:System.DateTimeOffset.ToOffset%2A>方法。 该方法的单个参数是新的日期和时间的方法是返回的值的偏移量。

例如，如果用户所请求网页的日期和时间已知，并且已被序列化为 MM/dd/yyyy hh:mm:ss zzzz 格式的字符串，以下 `ReturnTimeOnServer` 方法会将此日期和时间值转换为 Web 服务器上的日期和时间。

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)] 

如果向该方法传递字符串“9/1/2007 5:32:07 -05:00”（表示比 UTC 早五个小时的时区中的日期和时间），则对处于美国太平洋标准时区中的服务器，太平洋标准时区运行。

<xref:System.TimeZoneInfo>类还进行了的重载<xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>执行使用的时区转换方法<xref:System.DateTimeOffset.ToOffset(System.TimeSpan)>值。 方法的参数<xref:System.DateTimeOffset>值和时区的时间是要转换的引用。 方法调用返回<xref:System.DateTimeOffset>值。 例如，`ReturnTimeOnServer`上一示例中的方法可重写，如下所示调用<xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29>方法。

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a>请参阅

<xref:System.TimeZoneInfo>
[日期、 时间和时区](../../../docs/standard/datetime/index.md)
[查找本地系统上定义的时区](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)

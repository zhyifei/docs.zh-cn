---
title: 使用日期和时间执行算术运算
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], arithmetic operations
- dates [.NET Framework], arithmetic operations
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], comparing
- DateTime structure, arithmetic operations
- DateTimeOffset structure, arithmetic operations
ms.assetid: 87c7ddf2-f15e-48af-8602-b3642237e6d0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bbd5afb89d2b992e06583c7427c1a25a5b8f273
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33577540"
---
# <a name="performing-arithmetic-operations-with-dates-and-times"></a>使用日期和时间执行算术运算

尽管同时<xref:System.DateTime>和<xref:System.DateTimeOffset>结构提供对它们的值执行算术运算的成员，算术运算的结果有很大不同。 本主题检查这些差异、 与之关联的日期和时间数据中的时区感知度和讨论如何执行完全使用日期和时间数据的时区感知操作。

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a>比较和带有 DateTime 值的算术运算

<xref:System.DateTime.Kind%2A?displayProperty=nameWithType>属性允许<xref:System.DateTimeKind>要分配给以指示它是表示本地时间、 协调世界时 (UTC) 或在未指定时区的时间的日期和时间值。 此有限的时区信息时比较或执行日期和时间运算上，但是，将忽略<xref:System.DateTimeKind>值。 以下示例通过比较当前本地时间与当前 UTC 时间，对此进行了阐释。

[!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]

<xref:System.DateTime.CompareTo%28System.DateTime%29>方法，则报告本地时间早于 (或小于) 的 UTC 时间和减法运算指示在美国 UTC 系统的本地时间之间的差异其 UTC 时间与本地时间之间的时差是 7 小时。 但由于这两个值提供的单个时间点的表现形式有所不同，因此从本例中可清楚得知，此时间间隔完全是由本地时区与 UTC 之间的时差所致。

一般来说，<xref:System.DateTime.Kind%2A?displayProperty=nameWithType>属性不会影响返回的结果<xref:System.DateTime.Kind>比较和算术方法 （如所示的两个相同时间点进行比较），尽管它可能会影响这些结果的解释。 例如：

* 对两个日期和时间值的任何算术运算的结果执行其<xref:System.DateTime.Kind%2A?displayProperty=nameWithType>属性都等于<xref:System.DateTimeKind>反映两个值之间的实际时间间隔。 同样，对两个日期和时间值进行比较可精确反映出时间之间的关系。

* 对两个日期和时间值的任何算术或比较操作的结果执行其<xref:System.DateTime.Kind%2A?displayProperty=nameWithType>属性都等于<xref:System.DateTimeKind>或对具有不同的两个日期和时间值<xref:System.DateTime.Kind%2A?displayProperty=nameWithType>属性值反映时钟时间差异之间的两个值。

* 对本地日期和时间值执行的算术或比较运算不考虑某个特定值是否不明确或无效，也不考虑任何调整规则（因本地时区与夏令时的来回转换）的影响。

* 任何比较或计算 UTC 与本地时间之差的运算所得出的结果中都包含一个时间间隔，它等于本地时区与 UTC 之间的时差。

* 任何比较或计算未指定时间与 UTC 或本地时间的运算都反映简单的时钟时间。 时区差异未纳入考虑范围，且结果不会反映是否应用了时区调整规则。

* 任何比较或计算两个未指定时间之差的运算都可能包含一个未知间隔，它反映两个不同时区内的时间之差。

许多方案中的时区差异不会影响日期和时间计算 (其中的某些类的讨论，请参阅[DateTime、 DateTimeOffset、 TimeSpan 和 TimeZoneInfo 之间进行选择](../../../docs/standard/datetime/choosing-between-datetime.md)) 或在其中上下文日期和时间数据定义比较或算术运算的含义。

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a>比较和 DateTimeOffset 值的算术运算

A<xref:System.DateTimeOffset>值不仅包括包括日期和时间，还明确定义该日期和时间相对于 UTC 的偏移量。 这样能来定义的方式稍有不同的相等性<xref:System.DateTimeOffset>值。 而<xref:System.DateTime>值是否相等，如果它们具有相同的日期和时间值<xref:System.DateTimeOffset>值是否相等，如果它们都在时间中引用相同的点。 这使得<xref:System.DateTimeOffset>值更精确，因而需要进行解释时和确定两个日期和时间之间的间隔的大多数算术运算比较中使用较少。 以下示例中，这是<xref:System.DateTimeOffset>等效于前面的示例比较本地与 UTC<xref:System.DateTimeOffset>值、 阐释了这种行为差异。

[!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]

在此示例中，<xref:System.DateTimeOffset.CompareTo%2A>方法指示当前的本地时间与当前的 UTC 时间是否相等和的减法<xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)>值指示这两个时间之间的差异是<xref:System.TimeSpan.Zero?displayProperty=nameWithType>。

使用的主要限制<xref:System.DateTimeOffset>中日期和时间运算的值是，尽管<xref:System.DateTimeOffset>值具有某些时区识别能力，但不完全时区感知。 尽管<xref:System.DateTimeOffset>值的偏移量反映相对于 UTC 的时区偏移量时<xref:System.DateTimeOffset>变量首先分配一个值，它将成为与解除关联时区之后。 由于不再直接与可识别时间关联，日期和时间间隔的相加和相减将不会考虑时区调整规则。

举例说明，美国中部标准时区的夏令时转换发生于  2008 年 3 月 9 日凌晨 2:00。 这意味着，向中部标准时间 2008 年 3 月 9 日凌晨 1:30 增加两个半小时的间隔， 得出的日期和时间应为  2008 年 3 月 9 日凌晨 5:00。 但是，如下面的示例所示，加法运算得出的结果却是  2008 年 3 月 9 日凌晨 4:00。 请注意，此运算结果并不表示正确的时间点，它也不是我们所关注的时区的时间（也就是说，运算未得出预期的时区时差）。

[!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]

## <a name="arithmetic-operations-with-times-in-time-zones"></a>中的时区的时间的算术运算

<xref:System.TimeZoneInfo>类包括大量在它们将时间从一个时区转换到另一个时自动应用调整的转换方法。 其中包括：

* <xref:System.TimeZoneInfo.ConvertTime%2A>和<xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>任意两个时区之间转换时间的方法。

* <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>和<xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>方法，它们将特定时区的时间转换为 UTC，或将 UTC 转换为特定时区中的时间。

有关详细信息，请参阅[时区之间转换时间](../../../docs/standard/datetime/converting-between-time-zones.md)。

<xref:System.TimeZoneInfo.ConvertTimeToUtc(System.DateTime)>类不提供任何在执行日期和时间运算时自动应用的调整规则的方法。 但是可以通过将某一时区内的时间转换为 UTC，执行算术运算，然后再将 UTC 转换回该时区内的时间，来实现此目的。 有关详细信息，请参阅[如何： 在日期和时间运算中使用时区](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)。

例如，以下代码类似于之前向 2008 年 3 月 9 日凌晨 2:00 增加 两个半小时的代码。 但是，由于其在执行日期和时间算术前将中部标准时间转换为 UTC，然后将 UTC 结果转换回中部标准时间，所以得出的时间反映的是中部标准时区转换为夏令时。

[!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]

## <a name="see-also"></a>请参阅

[日期、 时间和时区](../../../docs/standard/datetime/index.md)
[如何： 在日期和时间运算中使用时区](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)

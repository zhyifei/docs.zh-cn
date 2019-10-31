---
title: 在 DateTime 与 DateTimeOffset 之间进行转换
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime structure, converting
- time zones [.NET Framework], conversions
- UTC times, converting
- DateTimeOffset structure, converting
- converting DateTimeOffset and DateTime values
- dates [.NET Framework], converting
- converting times
- Date data type, converting
- local time conversions
ms.assetid: b605ff97-0c45-4c24-833f-4c6a3e8be64c
ms.openlocfilehash: 428553f75db2cca6705ac72873e86e120e94d134
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132591"
---
# <a name="converting-between-datetime-and-datetimeoffset"></a>在 DateTime 与 DateTimeOffset 之间进行转换

尽管 <xref:System.DateTimeOffset> 结构比 <xref:System.DateTime> 结构提供更高的时区感知度，<xref:System.DateTime> 参数在方法调用中更常见。 因此，将 <xref:System.DateTimeOffset> 值转换为 <xref:System.DateTime> 值，反之亦然。 本主题说明如何以保留尽可能多的时区信息的方式执行这些转换。

> [!NOTE]
> <xref:System.DateTime> 和 <xref:System.DateTimeOffset> 类型在表示时区中的时间时有一些限制。 通过其 <xref:System.DateTime.Kind%2A> 属性，<xref:System.DateTime> 可以仅反映协调世界时（UTC）和系统的本地时区。 <xref:System.DateTimeOffset> 反映了相对于 UTC 的时间偏移量，但它不反映该偏移量所属的实际时区。 有关时间值和时区支持的详细信息，请参阅[在 DateTime、DateTimeOffset、TimeSpan 和 TimeZoneInfo 之间进行选择](../../../docs/standard/datetime/choosing-between-datetime.md)。

## <a name="conversions-from-datetime-to-datetimeoffset"></a>从 DateTime 转换为 DateTimeOffset

<xref:System.DateTimeOffset> 结构提供两种等效方法来执行 <xref:System.DateTime>，以实现适用于大多数转换的 <xref:System.DateTimeOffset> 转换：

- <xref:System.DateTimeOffset.%23ctor%2A> 构造函数，该构造函数根据 <xref:System.DateTime> 值创建新 <xref:System.DateTimeOffset> 对象。

- 隐式转换运算符，该运算符允许向 <xref:System.DateTimeOffset> 对象分配 <xref:System.DateTime> 值。

对于 UTC 和本地 <xref:System.DateTime> 值，生成的 <xref:System.DateTimeOffset> 值的 <xref:System.DateTimeOffset.Offset%2A> 属性将准确反映 UTC 或本地时区偏移量。 例如，以下代码将 UTC 时间转换为其等效的 <xref:System.DateTimeOffset> 值。

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

在本例中，`utcTime2` 变量的偏移量为 00:00。 同样，以下代码将本地时间转换为其等效的 <xref:System.DateTimeOffset> 值。

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

但对于 <xref:System.DateTime.Kind%2A> 属性 <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType><xref:System.DateTime> 值，这两种转换方法会生成一个 <xref:System.DateTimeOffset> 值，其偏移量为本地时区的偏移量。 下面的示例对此进行了演示，该示例使用美国太平洋标准时区。

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

如果 <xref:System.DateTime> 值反映了本地时区或 UTC 以外的日期和时间，则可以通过调用重载的 <xref:System.DateTimeOffset.%23ctor%2A> 构造函数将其转换为 <xref:System.DateTimeOffset> 值，并保留其时区信息。 例如，以下示例实例化反映中部标准时间的 <xref:System.DateTimeOffset> 对象。

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

此构造函数重载的第二个参数（表示与 UTC 之间的时差的 <xref:System.TimeSpan> 对象）应通过调用时间相应时区的 <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> 方法来检索。 该方法的单个参数是 <xref:System.DateTime> 值，该值表示要转换的日期和时间。 如果时区支持夏令时，此参数允许方法为该特定日期和时间确定适当偏移量。

## <a name="conversions-from-datetimeoffset-to-datetime"></a>从 DateTimeOffset 转换为 DateTime

<xref:System.DateTimeOffset.DateTime%2A> 属性最常用于执行 <xref:System.DateTimeOffset> <xref:System.DateTime> 转换。 但是，它将返回一个 <xref:System.DateTime.Kind%2A> 属性 <xref:System.DateTimeKind.Unspecified>的 <xref:System.DateTime> 值，如下面的示例所示。

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

这意味着，在使用 <xref:System.DateTimeOffset.DateTime%2A> 属性时，转换将丢失有关 <xref:System.DateTimeOffset> 值与 UTC 的关系的任何信息。 这会影响对应于 UTC 时间或系统本地时间的 <xref:System.DateTimeOffset> 值，因为 <xref:System.DateTimeOffset.DateTime%2A> 结构仅在其 <xref:System.DateTime.Kind%2A> 属性中反映这两个时区。

若要在将 <xref:System.DateTimeOffset> 转换为 <xref:System.DateTime> 值时保留尽可能多的时区信息，可以使用 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> 和 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 属性。

### <a name="converting-a-utc-time"></a>转换 UTC 时间

若要指示转换 <xref:System.DateTimeOffset.DateTime%2A> 值为 UTC 时间，可以检索 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> 属性的值。 它在以下两个方面与 <xref:System.DateTimeOffset.DateTime%2A> 属性不同：

- 它将返回其 <xref:System.DateTime.Kind%2A> 属性 <xref:System.DateTimeKind.Utc>的 <xref:System.DateTime> 值。

- 如果 <xref:System.DateTimeOffset.Offset%2A> 属性值不等于 <xref:System.TimeSpan.Zero?displayProperty=nameWithType>，则它会将时间转换为 UTC。

> [!NOTE]
> 如果应用程序要求转换 <xref:System.DateTime> 值明确标识单个时间点，应考虑使用 <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> 属性来处理所有 <xref:System.DateTimeOffset> <xref:System.DateTime> 转换。

下面的代码使用 <xref:System.DateTimeOffset.UtcDateTime%2A> 属性将其 offset 等于 <xref:System.TimeSpan.Zero?displayProperty=nameWithType> 的 <xref:System.DateTimeOffset> 值转换为 <xref:System.DateTime> 值。

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

下面的代码使用 <xref:System.DateTimeOffset.UtcDateTime%2A> 属性对 <xref:System.DateTimeOffset> 值执行时区转换和类型转换。

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a>转换本地时间

若要指示 <xref:System.DateTimeOffset> 值表示本地时间，可以将 <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> 属性返回的 <xref:System.DateTime> 值传递到`Shared` 方法中的 `static` （Visual Basic）。 方法返回作为第一个参数传递给它的日期和时间，但将 <xref:System.DateTime.Kind%2A> 属性设置为其第二个参数指定的值。 以下代码在转换 <xref:System.DateTimeOffset> 值（其偏移量对应于本地时区的偏移量）时使用 <xref:System.DateTime.SpecifyKind%2A> 方法。

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

你还可以使用 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 属性将 <xref:System.DateTimeOffset> 值转换为本地 <xref:System.DateTime> 值。 返回的 <xref:System.DateTime> 值的 <xref:System.DateTime.Kind%2A> 属性是 <xref:System.DateTimeKind.Local>。 以下代码在转换 <xref:System.DateTimeOffset> 值（其偏移量对应于本地时区的偏移量）时使用 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 属性。 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

使用 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 属性检索 <xref:System.DateTime> 值时，该属性的 `get` 访问器首先将 <xref:System.DateTimeOffset> 值转换为 UTC，然后通过调用 <xref:System.DateTimeOffset.ToLocalTime%2A> 方法将其转换为本地时间。 这意味着，可以从 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 属性检索值，以便在执行类型转换的同时执行时区转换。 还意味着在执行转换期间应用本地时区的调整规则。 下面的代码演示如何使用 <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> 属性同时执行类型和时区转换。

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a>通用转换方法

下面的示例定义了一个名为 `ConvertFromDateTimeOffset` 的方法，该方法将 <xref:System.DateTimeOffset> 值转换为 <xref:System.DateTime> 值。 根据其偏移量，它确定 <xref:System.DateTimeOffset> 值是 UTC 时间、本地时间还是其他时间，并相应地定义返回的日期和时间值的 <xref:System.DateTime.Kind%2A> 属性。

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

下面的示例调用 `ConvertFromDateTimeOffset` 方法来转换<xref:System.DateTimeOffset> 值，这些值表示 UTC 时间、本地时间和美国中部标准时区的时间。

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

请注意，此代码根据应用程序及其日期和时间值的来源所作的两种假设不一定始终有效：

- 它假定偏移量为 <xref:System.TimeSpan.Zero?displayProperty=nameWithType> 的日期和时间值表示 UTC。 事实上，UTC 并不是特定时区中的时间，而是世界时区中的时间相对于它进行标准化的时间。 时区还可以有 <xref:System.TimeSpan.Zero>的偏移量。

- 假定偏移量等于本地时区偏移量的日期和时间表示本地时区。 由于日期和时间值已从其原始时区解除关联，因此这可能不成立；日期和时间可能源自具有相同偏移量的其他时区。

## <a name="see-also"></a>请参阅

- [日期、时间和时区](../../../docs/standard/datetime/index.md)

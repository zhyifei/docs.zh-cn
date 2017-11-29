---
title: "在 DateTime 与 DateTimeOffset 之间进行转换"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35923fb89d6ca2edb3453db61386f0cd23047278
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="converting-between-datetime-and-datetimeoffset"></a><span data-ttu-id="6bc39-102">在 DateTime 与 DateTimeOffset 之间进行转换</span><span class="sxs-lookup"><span data-stu-id="6bc39-102">Converting between DateTime and DateTimeOffset</span></span>

<span data-ttu-id="6bc39-103">尽管<xref:System.DateTimeOffset>结构可提供更高程度的时区识别能力比<xref:System.DateTime>结构，<xref:System.DateTime>更常见的方法调用中使用参数。</span><span class="sxs-lookup"><span data-stu-id="6bc39-103">Although the <xref:System.DateTimeOffset> structure provides a greater degree of time zone awareness than the <xref:System.DateTime> structure, <xref:System.DateTime> parameters are used more commonly in method calls.</span></span> <span data-ttu-id="6bc39-104">因此，可以在转换<xref:System.DateTimeOffset>值复制到<xref:System.DateTime>值并，反之亦然，这样就显得尤为重要。</span><span class="sxs-lookup"><span data-stu-id="6bc39-104">Because of this, the ability to convert <xref:System.DateTimeOffset> values to <xref:System.DateTime> values and vice versa is particularly important.</span></span> <span data-ttu-id="6bc39-105">本主题演示如何保留尽可能时区信息的方式执行这些转换。</span><span class="sxs-lookup"><span data-stu-id="6bc39-105">This topic shows how to perform these conversions in a way that preserves as much time zone information as possible.</span></span>

> [!NOTE]
> <span data-ttu-id="6bc39-106">同时<xref:System.DateTime>和<xref:System.DateTimeOffset>类型表示时区中的时间时有一些限制。</span><span class="sxs-lookup"><span data-stu-id="6bc39-106">Both the <xref:System.DateTime> and the <xref:System.DateTimeOffset> types have some limitations when representing times in time zones.</span></span> <span data-ttu-id="6bc39-107">使用其<xref:System.DateTime.Kind%2A>属性，<xref:System.DateTime>能够反映仅协调世界时 (UTC) 和系统的本地时区。</span><span class="sxs-lookup"><span data-stu-id="6bc39-107">With its <xref:System.DateTime.Kind%2A> property, <xref:System.DateTime> is able to reflect only Coordinated Universal Time (UTC) and the system's local time zone.</span></span> <span data-ttu-id="6bc39-108"><xref:System.DateTimeOffset>反映时间的 UTC 偏移量，但它不反映该偏移量实际时区所属。</span><span class="sxs-lookup"><span data-stu-id="6bc39-108"><xref:System.DateTimeOffset> reflects a time's offset from UTC, but it does not reflect the actual time zone to which that offset belongs.</span></span> <span data-ttu-id="6bc39-109">有关时间值和时区的支持的详细信息，请参阅[选择之间 DateTime、 DateTimeOffset、 TimeSpan 和 TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)。</span><span class="sxs-lookup"><span data-stu-id="6bc39-109">For details about time values and support for time zones, see [Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).</span></span>

## <a name="conversions-from-datetime-to-datetimeoffset"></a><span data-ttu-id="6bc39-110">从 DateTime 转换为 DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="6bc39-110">Conversions from DateTime to DateTimeOffset</span></span>

<span data-ttu-id="6bc39-111"><xref:System.DateTimeOffset>结构提供了两个等效的方法来执行<xref:System.DateTime>到<xref:System.DateTimeOffset>适合于大多数转换的转换：</span><span class="sxs-lookup"><span data-stu-id="6bc39-111">The <xref:System.DateTimeOffset> structure provides two equivalent ways to perform <xref:System.DateTime> to <xref:System.DateTimeOffset> conversion that are suitable for most conversions:</span></span>

* <span data-ttu-id="6bc39-112"><xref:System.DateTimeOffset.%23ctor%2A>构造函数，创建一个新<xref:System.DateTimeOffset>对象基于<xref:System.DateTime>值。</span><span class="sxs-lookup"><span data-stu-id="6bc39-112">The <xref:System.DateTimeOffset.%23ctor%2A> constructor, which creates a new <xref:System.DateTimeOffset> object based on a <xref:System.DateTime> value.</span></span>

* <span data-ttu-id="6bc39-113">隐式转换运算符，可用于分配<xref:System.DateTime>值赋给<xref:System.DateTimeOffset>对象。</span><span class="sxs-lookup"><span data-stu-id="6bc39-113">The implicit conversion operator, which allows you to assign a <xref:System.DateTime> value to a <xref:System.DateTimeOffset> object.</span></span>

<span data-ttu-id="6bc39-114">对于 UTC 和本地<xref:System.DateTime>值，<xref:System.DateTimeOffset.Offset%2A>属性生成<xref:System.DateTimeOffset>值准确地反映 UTC 或本地时间的时区偏移量。</span><span class="sxs-lookup"><span data-stu-id="6bc39-114">For UTC and local <xref:System.DateTime> values, the <xref:System.DateTimeOffset.Offset%2A> property of the resulting <xref:System.DateTimeOffset> value accurately reflects the UTC or local time zone offset.</span></span> <span data-ttu-id="6bc39-115">例如，下面的代码将 UTC 时间转换为它的等效项<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="6bc39-115">For example, the following code converts a UTC time to its equivalent <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]

<span data-ttu-id="6bc39-116">在本例中，`utcTime2` 变量的偏移量为 00:00。</span><span class="sxs-lookup"><span data-stu-id="6bc39-116">In this case, the offset of the `utcTime2` variable is 00:00.</span></span> <span data-ttu-id="6bc39-117">同样，下面的代码将本地时间转换为它的等效项<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="6bc39-117">Similarly, the following code converts a local time to its equivalent <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]

<span data-ttu-id="6bc39-118">但是，对于<xref:System.DateTime>值其<xref:System.DateTime.Kind%2A>属性是<xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>，这两个转换方法生成<xref:System.DateTimeOffset>其偏移量为本地时区的值。</span><span class="sxs-lookup"><span data-stu-id="6bc39-118">However, for <xref:System.DateTime> values whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, these two conversion methods produce a <xref:System.DateTimeOffset> value whose offset is that of the local time zone.</span></span> <span data-ttu-id="6bc39-119">以下示例对此进行了演示，该示例在美国太平洋标准时区运行。</span><span class="sxs-lookup"><span data-stu-id="6bc39-119">This is shown in the following example, which is run in the U.S. Pacific Standard Time zone.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]

<span data-ttu-id="6bc39-120">如果<xref:System.DateTime>值反映的日期和一些内容以外的本地时区或 utc 格式的时间，你可以将其转换为<xref:System.DateTimeOffset>值并通过调用重载保留其所在的时区信息<xref:System.DateTimeOffset.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="6bc39-120">If the <xref:System.DateTime> value reflects the date and time in something other than the local time zone or UTC, you can convert it to a <xref:System.DateTimeOffset> value and preserve its time zone information by calling the overloaded <xref:System.DateTimeOffset.%23ctor%2A> constructor.</span></span> <span data-ttu-id="6bc39-121">例如，下面的示例实例化<xref:System.DateTimeOffset>反映中部标准时间的对象。</span><span class="sxs-lookup"><span data-stu-id="6bc39-121">For example, the following example instantiates a <xref:System.DateTimeOffset> object that reflects Central Standard Time.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]

<span data-ttu-id="6bc39-122">为此构造函数重载，第二个参数<xref:System.TimeSpan>对象表示的时间的偏移量相对于 UTC，应通过调用检索<xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType>方法的时间对应的时间区域。</span><span class="sxs-lookup"><span data-stu-id="6bc39-122">The second parameter to this constructor overload, a <xref:System.TimeSpan> object that represents the time's offset from UTC, should be retrieved by calling the <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=nameWithType> method of the time's corresponding time zone.</span></span> <span data-ttu-id="6bc39-123">该方法的单个参数是<xref:System.DateTime>值，该值表示要转换的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="6bc39-123">The method's single parameter is the <xref:System.DateTime> value that represents the date and time to be converted.</span></span> <span data-ttu-id="6bc39-124">如果时区支持夏令时，此参数允许方法为该特定日期和时间确定适当偏移量。</span><span class="sxs-lookup"><span data-stu-id="6bc39-124">If the time zone supports daylight saving time, this parameter allows the method to determine the appropriate offset for that particular date and time.</span></span>

## <a name="conversions-from-datetimeoffset-to-datetime"></a><span data-ttu-id="6bc39-125">从 DateTimeOffset 转换为 DateTime</span><span class="sxs-lookup"><span data-stu-id="6bc39-125">Conversions from DateTimeOffset to DateTime</span></span>

<span data-ttu-id="6bc39-126"><xref:System.DateTimeOffset.DateTime%2A>属性通常用于执行<xref:System.DateTimeOffset>到<xref:System.DateTime>转换。</span><span class="sxs-lookup"><span data-stu-id="6bc39-126">The <xref:System.DateTimeOffset.DateTime%2A> property is most commonly used to perform <xref:System.DateTimeOffset> to <xref:System.DateTime> conversion.</span></span> <span data-ttu-id="6bc39-127">但是，它将返回<xref:System.DateTime>值其<xref:System.DateTime.Kind%2A>属性是<xref:System.DateTimeKind.Unspecified>，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="6bc39-127">However, it returns a <xref:System.DateTime> value whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified>, as the following example illustrates.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]

<span data-ttu-id="6bc39-128">这意味着，任何信息有关<xref:System.DateTimeOffset>为 UTC 值的关系丢失由转换时<xref:System.DateTimeOffset.DateTime%2A>使用属性。</span><span class="sxs-lookup"><span data-stu-id="6bc39-128">This means that any information about the <xref:System.DateTimeOffset> value's relationship to UTC is lost by the conversion when the <xref:System.DateTimeOffset.DateTime%2A> property is used.</span></span> <span data-ttu-id="6bc39-129">这会影响<xref:System.DateTimeOffset>值对应于 UTC 时间或系统的本地时间，因为<xref:System.DateTimeOffset.DateTime%2A>结构反映了仅这两个时区中其<xref:System.DateTime.Kind%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="6bc39-129">This affects <xref:System.DateTimeOffset> values that correspond to UTC time or to the system's local time because the <xref:System.DateTimeOffset.DateTime%2A> structure reflects only those two time zones in its <xref:System.DateTime.Kind%2A> property.</span></span>

<span data-ttu-id="6bc39-130">在转换时保留可能一样多的时区信息<xref:System.DateTimeOffset>到<xref:System.DateTime>值，可以使用<xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType>和<xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="6bc39-130">To preserve as much time zone information as possible when converting a <xref:System.DateTimeOffset> to a <xref:System.DateTime> value, you can use the <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> and <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> properties.</span></span>

### <a name="converting-a-utc-time"></a><span data-ttu-id="6bc39-131">UTC 时间转换</span><span class="sxs-lookup"><span data-stu-id="6bc39-131">Converting a UTC time</span></span>

<span data-ttu-id="6bc39-132">指示已转换<xref:System.DateTimeOffset.DateTime%2A>值为 UTC 时间，则可以检索的值<xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="6bc39-132">To indicate that a converted <xref:System.DateTimeOffset.DateTime%2A> value is the UTC time, you can retrieve the value of the <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="6bc39-133">它不同于<xref:System.DateTimeOffset.DateTime%2A>两种方式的属性：</span><span class="sxs-lookup"><span data-stu-id="6bc39-133">It differs from the <xref:System.DateTimeOffset.DateTime%2A> property in two ways:</span></span>

* <span data-ttu-id="6bc39-134">它将返回<xref:System.DateTime>值其<xref:System.DateTime.Kind%2A>属性是<xref:System.DateTimeKind.Utc>。</span><span class="sxs-lookup"><span data-stu-id="6bc39-134">It returns a <xref:System.DateTime> value whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Utc>.</span></span>

* <span data-ttu-id="6bc39-135">如果<xref:System.DateTimeOffset.Offset%2A>属性值不等于<xref:System.TimeSpan.Zero?displayProperty=nameWithType>，它将时间转换为 UTC。</span><span class="sxs-lookup"><span data-stu-id="6bc39-135">If the <xref:System.DateTimeOffset.Offset%2A> property value does not equal <xref:System.TimeSpan.Zero?displayProperty=nameWithType>, it converts the time to UTC.</span></span>

> [!NOTE]
> <span data-ttu-id="6bc39-136">如果你的应用程序需要转换<xref:System.DateTime>值明确标识单个点时间，您应该考虑使用<xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType>属性来处理所有<xref:System.DateTimeOffset>到<xref:System.DateTime>转换。</span><span class="sxs-lookup"><span data-stu-id="6bc39-136">If your application requires that converted <xref:System.DateTime> values unambiguously identify a single point in time, you should consider using the <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=nameWithType> property to handle all <xref:System.DateTimeOffset> to <xref:System.DateTime> conversions.</span></span>

<span data-ttu-id="6bc39-137">下面的代码使用<xref:System.DateTimeOffset.UtcDateTime%2A>要转换的属性<xref:System.DateTimeOffset>值其偏移量等于<xref:System.TimeSpan.Zero?displayProperty=nameWithType>到<xref:System.DateTime>值。</span><span class="sxs-lookup"><span data-stu-id="6bc39-137">The following code uses the <xref:System.DateTimeOffset.UtcDateTime%2A> property to convert a <xref:System.DateTimeOffset> value whose offset equals <xref:System.TimeSpan.Zero?displayProperty=nameWithType> to a <xref:System.DateTime> value.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]

<span data-ttu-id="6bc39-138">下面的代码使用<xref:System.DateTimeOffset.UtcDateTime%2A>属性在上执行的时区转换和类型转换<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="6bc39-138">The following code uses the <xref:System.DateTimeOffset.UtcDateTime%2A> property to perform both a time zone conversion and a type conversion on a <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]

### <a name="converting-a-local-time"></a><span data-ttu-id="6bc39-139">本地时间转换</span><span class="sxs-lookup"><span data-stu-id="6bc39-139">Converting a local time</span></span>

<span data-ttu-id="6bc39-140">若要指示<xref:System.DateTimeOffset>值表示本地时间，可以将传递<xref:System.DateTime>返回值<xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType>属性`static`(`Shared`在 Visual Basic 中)<xref:System.DateTime.SpecifyKind%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="6bc39-140">To indicate that a <xref:System.DateTimeOffset> value represents the local time, you can pass the <xref:System.DateTime> value returned by the <xref:System.DateTimeOffset.DateTime%2A?displayProperty=nameWithType> property to the `static` (`Shared` in Visual Basic) <xref:System.DateTime.SpecifyKind%2A> method.</span></span> <span data-ttu-id="6bc39-141">该方法返回的日期和时间作为其第一个参数传递给它，但设置<xref:System.DateTime.Kind%2A>通过其第二个参数指定的值的属性。</span><span class="sxs-lookup"><span data-stu-id="6bc39-141">The method returns the date and time passed to it as its first parameter, but sets the <xref:System.DateTime.Kind%2A> property to the value specified by its second parameter.</span></span> <span data-ttu-id="6bc39-142">下面的代码使用<xref:System.DateTime.SpecifyKind%2A>方法转换时<xref:System.DateTimeOffset>其偏移量对应的本地时区的值。</span><span class="sxs-lookup"><span data-stu-id="6bc39-142">The following code uses the <xref:System.DateTime.SpecifyKind%2A> method when converting a <xref:System.DateTimeOffset> value whose offset corresponds to that of the local time zone.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]

<span data-ttu-id="6bc39-143">你还可以使用<xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType>要转换的属性<xref:System.DateTimeOffset>本地值<xref:System.DateTime>值。</span><span class="sxs-lookup"><span data-stu-id="6bc39-143">You can also use the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property to convert a <xref:System.DateTimeOffset> value to a local <xref:System.DateTime> value.</span></span> <span data-ttu-id="6bc39-144"><xref:System.DateTime.Kind%2A>属性返回<xref:System.DateTime>值是<xref:System.DateTimeKind.Local>。</span><span class="sxs-lookup"><span data-stu-id="6bc39-144">The <xref:System.DateTime.Kind%2A> property of the returned <xref:System.DateTime> value is <xref:System.DateTimeKind.Local>.</span></span> <span data-ttu-id="6bc39-145">下面的代码使用<xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType>属性转换时<xref:System.DateTimeOffset>其偏移量对应的本地时区的值。</span><span class="sxs-lookup"><span data-stu-id="6bc39-145">The following code uses the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property when converting a <xref:System.DateTimeOffset> value whose offset corresponds to that of the local time zone.</span></span> 

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]

<span data-ttu-id="6bc39-146">当检索<xref:System.DateTime>值使用<xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType>属性，该属性的`get`访问器首先将转换<xref:System.DateTimeOffset>值为 UTC，然后将其转换为本地时间通过调用<xref:System.DateTimeOffset.ToLocalTime%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="6bc39-146">When you retrieve a <xref:System.DateTime> value using the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property, the property's `get` accessor first converts the <xref:System.DateTimeOffset> value to UTC, then converts it to local time by calling the <xref:System.DateTimeOffset.ToLocalTime%2A> method.</span></span> <span data-ttu-id="6bc39-147">这意味着你可以检索一个值从<xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType>属性来执行在同一时间执行类型转换的时区转换。</span><span class="sxs-lookup"><span data-stu-id="6bc39-147">This means that you can retrieve a value from the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property to perform a time zone conversion at the same time that you perform a type conversion.</span></span> <span data-ttu-id="6bc39-148">还意味着在执行转换期间应用本地时区的调整规则。</span><span class="sxs-lookup"><span data-stu-id="6bc39-148">It also means that the local time zone's adjustment rules are applied in performing the conversion.</span></span> <span data-ttu-id="6bc39-149">下面的代码演示如何使用<xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType>属性来执行类型和时区转换。</span><span class="sxs-lookup"><span data-stu-id="6bc39-149">The following code illustrates the use of the <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=nameWithType> property to perform both a type and a time zone conversion.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]

### <a name="a-general-purpose-conversion-method"></a><span data-ttu-id="6bc39-150">一般用途的转换方法</span><span class="sxs-lookup"><span data-stu-id="6bc39-150">A general-purpose conversion method</span></span>

<span data-ttu-id="6bc39-151">下面的示例定义一个名为方法`ConvertFromDateTimeOffset`，用于将转换<xref:System.DateTimeOffset>值复制到<xref:System.DateTime>值。</span><span class="sxs-lookup"><span data-stu-id="6bc39-151">The following example defines a method named `ConvertFromDateTimeOffset` that converts <xref:System.DateTimeOffset> values to <xref:System.DateTime> values.</span></span> <span data-ttu-id="6bc39-152">根据其偏移量，它确定是否<xref:System.DateTimeOffset>值是 UTC 时间、 本地时间或其他时间，并定义对返回的日期和时间值的<xref:System.DateTime.Kind%2A>属性相应地。</span><span class="sxs-lookup"><span data-stu-id="6bc39-152">Based on its offset, it determines whether the <xref:System.DateTimeOffset> value is a UTC time, a local time, or some other time, and defines the returned date and time value's <xref:System.DateTime.Kind%2A> property accordingly.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]

<span data-ttu-id="6bc39-153">下面的示例调用`ConvertFromDateTimeOffset`方法将转换<xref:System.DateTimeOffset>值表示 UTC 时间、 本地时间和在美国的时间中部标准时区的时间。</span><span class="sxs-lookup"><span data-stu-id="6bc39-153">The follow example calls the `ConvertFromDateTimeOffset` method to convert <xref:System.DateTimeOffset> values that represent a UTC time, a local time, and a time in the U.S. Central Standard Time zone.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
[!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]

<span data-ttu-id="6bc39-154">请注意，此代码根据应用程序及其日期和时间值的来源所作的两种假设不一定始终有效：</span><span class="sxs-lookup"><span data-stu-id="6bc39-154">Note that this code makes two assumptions that, depending on the application and the source of its date and time values, may not always be valid:</span></span>

* <span data-ttu-id="6bc39-155">它假定日期和时间值的偏移量是<xref:System.TimeSpan.Zero?displayProperty=nameWithType>表示 UTC。</span><span class="sxs-lookup"><span data-stu-id="6bc39-155">It assumes that a date and time value whose offset is <xref:System.TimeSpan.Zero?displayProperty=nameWithType> represents UTC.</span></span> <span data-ttu-id="6bc39-156">事实上，UTC 并不是特定时区中的时间，而是世界时区中的时间相对于它进行标准化的时间。</span><span class="sxs-lookup"><span data-stu-id="6bc39-156">In fact, UTC is not a time in a particular time zone, but the time in relation to which the times in the world's time zones are standardized.</span></span> <span data-ttu-id="6bc39-157">此外可以偏移量为时区<xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="6bc39-157">Time zones can also have an offset of <xref:System.TimeSpan.Zero>.</span></span>

* <span data-ttu-id="6bc39-158">假定偏移量等于本地时区偏移量的日期和时间表示本地时区。</span><span class="sxs-lookup"><span data-stu-id="6bc39-158">It assumes that a date and time whose offset equals that of the local time zone represents the local time zone.</span></span> <span data-ttu-id="6bc39-159">由于日期和时间值已从其原始时区解除关联，因此这可能不成立；日期和时间可能源自具有相同偏移量的其他时区。</span><span class="sxs-lookup"><span data-stu-id="6bc39-159">Because date and time values are disassociated from their original time zone, this may not be the case; the date and time can have originated in another time zone with the same offset.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bc39-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bc39-160">See also</span></span>

[<span data-ttu-id="6bc39-161">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="6bc39-161">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)

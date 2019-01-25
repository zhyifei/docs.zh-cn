---
title: 实例化 DateTimeOffset 对象
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
- DateTimeOffset structure, converting to DateTime
- DateTimeOffset structure, instantiating
ms.assetid: 9648375f-d368-4373-a976-3332ece00c0a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11f62b8fe8a28d6fe6401d53dac4b9bc1c45b21d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554592"
---
# <a name="instantiating-a-datetimeoffset-object"></a><span data-ttu-id="73890-102">实例化 DateTimeOffset 对象</span><span class="sxs-lookup"><span data-stu-id="73890-102">Instantiating a DateTimeOffset object</span></span>

<span data-ttu-id="73890-103"><xref:System.DateTimeOffset> 结构提供了多种创建新 <xref:System.DateTimeOffset> 值的方法。</span><span class="sxs-lookup"><span data-stu-id="73890-103">The <xref:System.DateTimeOffset> structure offers a number of ways to create new <xref:System.DateTimeOffset> values.</span></span> <span data-ttu-id="73890-104">其中的许多直接对应于实例化新的可用方法<xref:System.DateTime>值，包含允许您指定的日期和时间值的偏移量从协调世界时 (UTC) 的增强功能。</span><span class="sxs-lookup"><span data-stu-id="73890-104">Many of them correspond directly to the methods available for instantiating new <xref:System.DateTime> values, with enhancements that allow you to specify the date and time value's offset from Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="73890-105">具体而言，您可以实例化<xref:System.DateTimeOffset>值按以下方式：</span><span class="sxs-lookup"><span data-stu-id="73890-105">In particular, you can instantiate a <xref:System.DateTimeOffset> value in the following ways:</span></span>

* <span data-ttu-id="73890-106">通过使用日期和时间文字。</span><span class="sxs-lookup"><span data-stu-id="73890-106">By using a date and time literal.</span></span>

* <span data-ttu-id="73890-107">通过调用<xref:System.DateTimeOffset>构造函数。</span><span class="sxs-lookup"><span data-stu-id="73890-107">By calling a <xref:System.DateTimeOffset> constructor.</span></span>

* <span data-ttu-id="73890-108">通过隐式转换到的值<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="73890-108">By implicitly converting a value to <xref:System.DateTimeOffset> value.</span></span>

* <span data-ttu-id="73890-109">分析日期和时间的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="73890-109">By parsing the string representation of a date and time.</span></span>

<span data-ttu-id="73890-110">本主题提供了更高版本的详细信息和代码示例，展示了这些方法的实例化新<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="73890-110">This topic provides greater detail and code examples that illustrate these methods of instantiating new <xref:System.DateTimeOffset> values.</span></span>

## <a name="date-and-time-literals"></a><span data-ttu-id="73890-111">日期和时间文本</span><span class="sxs-lookup"><span data-stu-id="73890-111">Date and time literals</span></span>

<span data-ttu-id="73890-112">语言的支持，实例化的最常见方式之一<xref:System.DateTime>值是提供的日期和时间作为硬编码文本值。</span><span class="sxs-lookup"><span data-stu-id="73890-112">For languages that support it, one of the most common ways to instantiate a <xref:System.DateTime> value is to provide the date and time as a hard-coded literal value.</span></span> <span data-ttu-id="73890-113">例如，以下 Visual Basic 代码创建<xref:System.DateTime>对象，其值是 2008 年 1 月 1 日，上午 10:00。</span><span class="sxs-lookup"><span data-stu-id="73890-113">For example, the following Visual Basic code creates a <xref:System.DateTime> object whose value is January 1, 2008, at 10:00 AM.</span></span>

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#1)]

<span data-ttu-id="73890-114"><xref:System.DateTimeOffset> 此外可以使用支持的语言时使用日期和时间文本初始化值<xref:System.DateTime>原义字符。</span><span class="sxs-lookup"><span data-stu-id="73890-114"><xref:System.DateTimeOffset> values can also be initialized using date and time literals when using languages that support <xref:System.DateTime> literals.</span></span> <span data-ttu-id="73890-115">例如，以下 Visual Basic 代码创建<xref:System.DateTimeOffset>对象。</span><span class="sxs-lookup"><span data-stu-id="73890-115">For example, the following Visual Basic code creates a <xref:System.DateTimeOffset> object.</span></span>

[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#2)]

<span data-ttu-id="73890-116">如控制台输出所示，<xref:System.DateTimeOffset>以这种方式创建的值分配的本地时区偏移量。</span><span class="sxs-lookup"><span data-stu-id="73890-116">As the console output shows, the <xref:System.DateTimeOffset> value created in this way is assigned the offset of the local time zone.</span></span> <span data-ttu-id="73890-117">这意味着，<xref:System.DateTimeOffset>分配使用的字符文本值不会标识单个时间点的代码运行不同的计算机上。</span><span class="sxs-lookup"><span data-stu-id="73890-117">This means that a <xref:System.DateTimeOffset> value assigned using a character literal does not identify a single point of time if the code is run on different computers.</span></span>

## <a name="datetimeoffset-constructors"></a><span data-ttu-id="73890-118">DateTimeOffset 构造函数</span><span class="sxs-lookup"><span data-stu-id="73890-118">DateTimeOffset constructors</span></span>

<span data-ttu-id="73890-119"><xref:System.DateTimeOffset>类型定义了六个构造函数。</span><span class="sxs-lookup"><span data-stu-id="73890-119">The <xref:System.DateTimeOffset> type defines six constructors.</span></span> <span data-ttu-id="73890-120">其中四个直接对应<xref:System.DateTime>带有类型的其他参数的构造函数<xref:System.TimeSpan>定义日期和时间的 UTC 偏移量。</span><span class="sxs-lookup"><span data-stu-id="73890-120">Four of them correspond directly to <xref:System.DateTime> constructors, with an additional parameter of type <xref:System.TimeSpan> that defines the date and time's offset from UTC.</span></span> <span data-ttu-id="73890-121">这些规则可以定义<xref:System.DateTimeOffset>值基于其单独的日期和时间组件的值。</span><span class="sxs-lookup"><span data-stu-id="73890-121">These allow you to define a <xref:System.DateTimeOffset> value based on the value of its individual date and time components.</span></span> <span data-ttu-id="73890-122">例如，以下代码使用以下四个构造函数实例化<xref:System.DateTimeOffset>对象具有相同的值，2008 年 7 月 1 日的上午 12:05 + 01:00。</span><span class="sxs-lookup"><span data-stu-id="73890-122">For example, the following code uses these four constructors to instantiate <xref:System.DateTimeOffset> objects with identical values of 7/1/2008 12:05 AM +01:00.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#3)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#3)]

<span data-ttu-id="73890-123">请注意，当的值<xref:System.DateTimeOffset>对象实例化使用<xref:System.Globalization.PersianCalendar>对象作为其构造函数的自变量之一显示到控制台，它将表示为公历而不是波斯历的日期。</span><span class="sxs-lookup"><span data-stu-id="73890-123">Note that, when the value of the <xref:System.DateTimeOffset> object instantiated using a <xref:System.Globalization.PersianCalendar> object as one of the arguments to its constructor is displayed to the console, it is expressed as a date in the Gregorian rather than the Persian calendar.</span></span> <span data-ttu-id="73890-124">若要输出使用波斯历的日期，请参阅中的示例<xref:System.Globalization.PersianCalendar>主题。</span><span class="sxs-lookup"><span data-stu-id="73890-124">To output a date using the Persian calendar, see the example in the <xref:System.Globalization.PersianCalendar> topic.</span></span>

<span data-ttu-id="73890-125">其他两个构造函数创建<xref:System.DateTimeOffset>对象从<xref:System.DateTime>值。</span><span class="sxs-lookup"><span data-stu-id="73890-125">The other two constructors create a <xref:System.DateTimeOffset> object from a <xref:System.DateTime> value.</span></span> <span data-ttu-id="73890-126">其中第一个具有一个参数，<xref:System.DateTime>值将转换为<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="73890-126">The first of these has a single parameter, the <xref:System.DateTime> value to convert to a <xref:System.DateTimeOffset> value.</span></span> <span data-ttu-id="73890-127">所生成的偏移量<xref:System.DateTimeOffset>值取决于<xref:System.DateTime.Kind%2A>构造函数的单个参数的属性。</span><span class="sxs-lookup"><span data-stu-id="73890-127">The offset of the resulting <xref:System.DateTimeOffset> value depends on the <xref:System.DateTime.Kind%2A> property of the constructor's single parameter.</span></span> <span data-ttu-id="73890-128">如果其值为<xref:System.DateTimeKind.Utc?displayProperty=nameWithType>，偏移量设置为等于<xref:System.TimeSpan.Zero?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="73890-128">If its value is <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, the offset is set equal to <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.</span></span> <span data-ttu-id="73890-129">否则，会将其时差设置为等于本地时区的时差。</span><span class="sxs-lookup"><span data-stu-id="73890-129">Otherwise, its offset is set equal to that of the local time zone.</span></span> <span data-ttu-id="73890-130">下面的示例演示如何使用此构造函数实例化<xref:System.DateTimeOffset>表示 UTC 和本地时区对象：</span><span class="sxs-lookup"><span data-stu-id="73890-130">The following example illustrates the use of this constructor to instantiate <xref:System.DateTimeOffset> objects representing UTC and the local time zone:</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#4)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#4)]

> [!NOTE]
> <span data-ttu-id="73890-131">调用的重载<xref:System.DateTimeOffset>构造函数具有单个<xref:System.DateTime>参数等效于执行的隐式转换<xref:System.DateTime>值设为<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="73890-131">Calling the overload of the <xref:System.DateTimeOffset> constructor that has a single <xref:System.DateTime> parameter is equivalent to performing an implicit conversion of a <xref:System.DateTime> value to a <xref:System.DateTimeOffset> value.</span></span>

<span data-ttu-id="73890-132">创建第二个构造函数<xref:System.DateTimeOffset>对象从<xref:System.DateTime>值具有两个参数：<xref:System.DateTime>要转换值，和一个<xref:System.TimeSpan>值，该值表示的日期和时间的 UTC 偏移量。</span><span class="sxs-lookup"><span data-stu-id="73890-132">The second constructor that creates a <xref:System.DateTimeOffset> object from a <xref:System.DateTime> value has two parameters: the <xref:System.DateTime> value to convert, and a <xref:System.TimeSpan> value representing the date and time's offset from UTC.</span></span> <span data-ttu-id="73890-133">此偏移量的值必须对应于<xref:System.DateTime.Kind%2A>构造函数的第一个参数的属性或<xref:System.ArgumentException>引发。</span><span class="sxs-lookup"><span data-stu-id="73890-133">This offset value must correspond to the <xref:System.DateTime.Kind%2A> property of the constructor's first parameter or an <xref:System.ArgumentException> is thrown.</span></span> <span data-ttu-id="73890-134">如果<xref:System.DateTime.Kind%2A>属性的第一个参数是<xref:System.DateTimeKind.Utc?displayProperty=nameWithType>，第二个参数的值必须为<xref:System.TimeSpan.Zero?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="73890-134">If the <xref:System.DateTime.Kind%2A> property of the first parameter is <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, the value of the second parameter must be <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.</span></span> <span data-ttu-id="73890-135">如果<xref:System.DateTime.Kind%2A>属性的第一个参数是<xref:System.DateTimeKind.Local?displayProperty=nameWithType>，第二个参数的值必须是本地系统时区的偏移量。</span><span class="sxs-lookup"><span data-stu-id="73890-135">If the <xref:System.DateTime.Kind%2A> property of the first parameter is <xref:System.DateTimeKind.Local?displayProperty=nameWithType>, the value of the second parameter must be the offset of the local system's time zone.</span></span> <span data-ttu-id="73890-136">如果<xref:System.DateTime.Kind%2A>属性的第一个参数是<xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>，那么时差可以是任何有效的值。</span><span class="sxs-lookup"><span data-stu-id="73890-136">If the <xref:System.DateTime.Kind%2A> property of the first parameter is <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, the offset can be any valid value.</span></span> <span data-ttu-id="73890-137">下面的代码演示如何调用此构造函数将转换<xref:System.DateTime>到<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="73890-137">The following code illustrates calls to this constructor to convert <xref:System.DateTime> to <xref:System.DateTimeOffset> values.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#5)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#5)]

## <a name="implicit-type-conversion"></a><span data-ttu-id="73890-138">隐式类型转换</span><span class="sxs-lookup"><span data-stu-id="73890-138">Implicit type conversion</span></span>

<span data-ttu-id="73890-139"><xref:System.DateTimeOffset>类型支持一次隐式类型转换： 从<xref:System.DateTime>值设为<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="73890-139">The <xref:System.DateTimeOffset> type supports one implicit type conversion: from a <xref:System.DateTime> value to a <xref:System.DateTimeOffset> value.</span></span> <span data-ttu-id="73890-140">隐式类型转换是指从一种类型转换为另一种类型，而无需显示转换（通过 C# 或 Visual Basic）且不会丢失信息。</span><span class="sxs-lookup"><span data-stu-id="73890-140">(An implicit type conversion is a conversion from one type to another that does not require an explicit cast (in C#) or conversion (in Visual Basic) and that does not lose information.</span></span> <span data-ttu-id="73890-141">它可以实现如下代码。</span><span class="sxs-lookup"><span data-stu-id="73890-141">It makes code like the following possible.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#6)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#6)]

<span data-ttu-id="73890-142">所生成的偏移量<xref:System.DateTimeOffset>值取决于<xref:System.DateTime.Kind%2A?displayProperty=nameWithType>属性值。</span><span class="sxs-lookup"><span data-stu-id="73890-142">The offset of the resulting <xref:System.DateTimeOffset> value depends on the <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> property value.</span></span> <span data-ttu-id="73890-143">如果其值为<xref:System.DateTimeKind.Utc?displayProperty=nameWithType>，偏移量设置为等于<xref:System.TimeSpan.Zero?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="73890-143">If its value is <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>, the offset is set equal to <xref:System.TimeSpan.Zero?displayProperty=nameWithType>.</span></span> <span data-ttu-id="73890-144">如果其值为<xref:System.DateTimeKind.Local?displayProperty=nameWithType>或<xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>，偏移量设置为等于本地时区。</span><span class="sxs-lookup"><span data-stu-id="73890-144">If its value is either <xref:System.DateTimeKind.Local?displayProperty=nameWithType> or <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>, the offset is set equal to that of the local time zone.</span></span>

## <a name="parsing-the-string-representation-of-a-date-and-time"></a><span data-ttu-id="73890-145">分析日期和时间的字符串表示形式</span><span class="sxs-lookup"><span data-stu-id="73890-145">Parsing the string representation of a date and time</span></span>

<span data-ttu-id="73890-146"><xref:System.DateTimeOffset>类型支持四种方法，可用于转换的字符串表示形式的日期和时间入<xref:System.DateTimeOffset>值：</span><span class="sxs-lookup"><span data-stu-id="73890-146">The <xref:System.DateTimeOffset> type supports four methods that allow you to convert the string representation of a date and time into a <xref:System.DateTimeOffset> value:</span></span>

* <span data-ttu-id="73890-147"><xref:System.DateTimeOffset.Parse%2A>它尝试将转换的字符串表示形式的日期和时间为<xref:System.DateTimeOffset>值则会引发异常，如果转换失败。</span><span class="sxs-lookup"><span data-stu-id="73890-147"><xref:System.DateTimeOffset.Parse%2A>, which tries to convert the string representation of a date and time to a <xref:System.DateTimeOffset> value and throws an exception if the conversion fails.</span></span>

* <span data-ttu-id="73890-148"><xref:System.DateTimeOffset.TryParse%2A>它尝试将转换的字符串表示形式的日期和时间为<xref:System.DateTimeOffset>值并返回`false`如果转换失败。</span><span class="sxs-lookup"><span data-stu-id="73890-148"><xref:System.DateTimeOffset.TryParse%2A>, which tries to convert the string representation of a date and time to a <xref:System.DateTimeOffset> value and returns `false` if the conversion fails.</span></span>

* <span data-ttu-id="73890-149"><xref:System.DateTimeOffset.ParseExact%2A>尝试将日期和时间的指定格式的字符串表示形式转换<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="73890-149"><xref:System.DateTimeOffset.ParseExact%2A>, which tries to convert the string representation of a date and time in a specified format to a <xref:System.DateTimeOffset> value.</span></span> <span data-ttu-id="73890-150">如果转换失败，该方法将引发异常。</span><span class="sxs-lookup"><span data-stu-id="73890-150">The method throws an exception if the conversion fails.</span></span>

* <span data-ttu-id="73890-151"><xref:System.DateTimeOffset.TryParseExact%2A>尝试将日期和时间的指定格式的字符串表示形式转换<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="73890-151"><xref:System.DateTimeOffset.TryParseExact%2A>, which tries to convert the string representation of a date and time in a specified format to a <xref:System.DateTimeOffset> value.</span></span> <span data-ttu-id="73890-152">如果转换失败，该方法将返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="73890-152">The method returns `false` if the conversion fails.</span></span>

<span data-ttu-id="73890-153">下面的示例演示对每个四个字符串转换方法的调用来实例化<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="73890-153">The following example illustrates calls to each of these four string conversion methods to instantiate a <xref:System.DateTimeOffset> value.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/cs/Instantiate.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual.Instantiate#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Instantiate/vb/Instantiate.vb#7)]

## <a name="see-also"></a><span data-ttu-id="73890-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="73890-154">See also</span></span>

- [<span data-ttu-id="73890-155">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="73890-155">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)

---
title: 如何：从特定日期中提取星期几
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET Framework], dates
- DateTime.DayOfWeek property
- DateTime.ToString method
- dates [.NET Framework], retrieving week information
- DateTimeOffset.DayOfWeek property
- dates [.NET Framework], day of week
- Weekday function
- day of week [.NET Framework]
- extracting day of week
- weekday names
- WeekdayName function
- numbers [.NET Framework], day of week
- formatting [.NET Framework], time
- DateTimeOffset.ToString method
- full weekday names
ms.assetid: 1c9bef76-5634-46cf-b91c-9b9eb72091d7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bd4066fe0a2d9f26505976c13ac80e03554e0aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575722"
---
# <a name="how-to-extract-the-day-of-the-week-from-a-specific-date"></a><span data-ttu-id="40b28-102">如何：从特定日期中提取星期几</span><span class="sxs-lookup"><span data-stu-id="40b28-102">How to: Extract the Day of the Week from a Specific Date</span></span>
<span data-ttu-id="40b28-103">利用 .NET Framework，可以很容易地确定某个特定日期是星期几，以及显示某个特定日期的本地化星期几名称。</span><span class="sxs-lookup"><span data-stu-id="40b28-103">The .NET Framework makes it easy to determine the ordinal day of the week for a particular date, and to display the localized weekday name for a particular date.</span></span> <span data-ttu-id="40b28-104">指示与特定日期相对应的星期几的枚举值可以从 <xref:System.DateTime.DayOfWeek%2A> 或 <xref:System.DateTimeOffset.DayOfWeek%2A> 属性中获取。</span><span class="sxs-lookup"><span data-stu-id="40b28-104">An enumerated value that indicates the day of the week corresponding to a particular date is available from the <xref:System.DateTime.DayOfWeek%2A> or <xref:System.DateTimeOffset.DayOfWeek%2A> property.</span></span> <span data-ttu-id="40b28-105">与此不同的是，检索星期几名称是一项格式化操作，可通过调用格式化方法来执行，例如日期和时间值的 `ToString` 方法或 <xref:System.String.Format%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="40b28-105">In contrast, retrieving the weekday name is a formatting operation that can be performed by calling a formatting method, such as a date and time value's `ToString` method or the <xref:System.String.Format%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="40b28-106">本主题演示如何执行这些格式化操作。</span><span class="sxs-lookup"><span data-stu-id="40b28-106">This topic shows how to perform these formatting operations.</span></span>  
  
### <a name="to-extract-a-number-indicating-the-day-of-the-week-from-a-specific-date"></a><span data-ttu-id="40b28-107">从特定日期中提取指示星期几的数字</span><span class="sxs-lookup"><span data-stu-id="40b28-107">To extract a number indicating the day of the week from a specific date</span></span>  
  
1.  <span data-ttu-id="40b28-108">如果要使用日期的字符串表示形式，请使用静态 <xref:System.DateTime> 或 <xref:System.DateTimeOffset> 方法将其转换为 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> 或 <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> 值。</span><span class="sxs-lookup"><span data-stu-id="40b28-108">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="40b28-109">使用 <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> 或 <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> 属性检索指示星期几的 <xref:System.DayOfWeek> 值。</span><span class="sxs-lookup"><span data-stu-id="40b28-109">Use the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> property to retrieve a <xref:System.DayOfWeek> value that indicates the day of the week.</span></span>  
  
3.  <span data-ttu-id="40b28-110">如有必要，可将 <xref:System.DayOfWeek> 值强制转换（在 C# 中）或转换（在 Visual Basic 中）为整数。</span><span class="sxs-lookup"><span data-stu-id="40b28-110">If necessary, cast (in C#) or convert (in Visual Basic) the <xref:System.DayOfWeek> value to an integer.</span></span>  
  
 <span data-ttu-id="40b28-111">下面的示例将显示一个整数，用于表示特定日期的星期几。</span><span class="sxs-lookup"><span data-stu-id="40b28-111">The following example displays an integer that represents the day of the week of a specific date.</span></span>  
  
 [!code-csharp[Formatting.Howto.WeekdayName#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/weekdaynumber7.cs#7)]
 [!code-vb[Formatting.Howto.WeekdayName#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/weekdaynumber7.vb#7)]  
  
### <a name="to-extract-the-abbreviated-weekday-name-from-a-specific-date"></a><span data-ttu-id="40b28-112">从特定日期中提取缩写的星期几名称</span><span class="sxs-lookup"><span data-stu-id="40b28-112">To extract the abbreviated weekday name from a specific date</span></span>  
  
1.  <span data-ttu-id="40b28-113">如果要使用日期的字符串表示形式，请使用静态 <xref:System.DateTime> 或 <xref:System.DateTimeOffset> 方法将其转换为 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> 或 <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> 值。</span><span class="sxs-lookup"><span data-stu-id="40b28-113">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="40b28-114">你可以提取当前区域性或特定区域性的缩写的星期几名称：</span><span class="sxs-lookup"><span data-stu-id="40b28-114">You can extract the abbreviated weekday name of the current culture or of a specific culture:</span></span>  
  
    1.  <span data-ttu-id="40b28-115">若要提取当前区域性的缩写的星期几名称，请调用日期和时间值的 <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> 或 <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> 实例方法，并以 `format` 参数的形式传递字符串“ddd”。</span><span class="sxs-lookup"><span data-stu-id="40b28-115">To extract the abbreviated weekday name for the current culture, call the date and time value's <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> instance method, and pass the string "ddd" as the `format` parameter.</span></span> <span data-ttu-id="40b28-116">下面的示例演示 <xref:System.DateTime.ToString%28System.String%29> 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="40b28-116">The following example illustrates the call to the <xref:System.DateTime.ToString%28System.String%29> method.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname1.cs#1)]
         [!code-vb[Formatting.Howto.WeekdayName#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname1.vb#1)]  
  
    2.  <span data-ttu-id="40b28-117">若要提取特定区域性的缩写的星期几名称，请调用日期和时间值的 <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> 或 <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> 实例方法。</span><span class="sxs-lookup"><span data-stu-id="40b28-117">To extract the abbreviated weekday name for a specific culture, call the date and time value’s <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="40b28-118">同时以 `format` 参数形式传递字符串“ddd”。</span><span class="sxs-lookup"><span data-stu-id="40b28-118">Pass the string "ddd" as the `format` parameter.</span></span> <span data-ttu-id="40b28-119">以 <xref:System.Globalization.CultureInfo> 参数的形式传递表示要检索其星期几名称的区域性的 <xref:System.Globalization.DateTimeFormatInfo> 或 `provider` 对象。</span><span class="sxs-lookup"><span data-stu-id="40b28-119">Pass either a <xref:System.Globalization.CultureInfo> or a <xref:System.Globalization.DateTimeFormatInfo> object that represents the culture whose weekday name you want to retrieve as the `provider` parameter.</span></span> <span data-ttu-id="40b28-120">下面的代码阐释如何使用表示 fr-FR 区域性的 <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> 对象调用 <xref:System.Globalization.CultureInfo> 方法。</span><span class="sxs-lookup"><span data-stu-id="40b28-120">The following code illustrates a call to the <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> method using a <xref:System.Globalization.CultureInfo> object that represents the fr-FR culture.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname2.cs#2)]
         [!code-vb[Formatting.Howto.WeekdayName#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname2.vb#2)]  
  
### <a name="to-extract-the-full-weekday-name-from-a-specific-date"></a><span data-ttu-id="40b28-121">从特定日期中提取完整的星期几名称</span><span class="sxs-lookup"><span data-stu-id="40b28-121">To extract the full weekday name from a specific date</span></span>  
  
1.  <span data-ttu-id="40b28-122">如果要使用日期的字符串表示形式，请使用静态 <xref:System.DateTime> 或 <xref:System.DateTimeOffset> 方法将其转换为 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> 或 <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> 值。</span><span class="sxs-lookup"><span data-stu-id="40b28-122">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="40b28-123">你可以提取当前区域性或特定区域性的完整的星期几名称：</span><span class="sxs-lookup"><span data-stu-id="40b28-123">You can extract the full weekday name of the current culture or of a specific culture:</span></span>  
  
    1.  <span data-ttu-id="40b28-124">若要提取当前区域性的缩写的星期几名称，请调用日期和时间值的 <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> 或 <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> 实例方法，并以 `format` 参数的形式传递字符串“dddd”。</span><span class="sxs-lookup"><span data-stu-id="40b28-124">To extract the weekday name for the current culture, call the date and time value’s <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> instance method, and pass the string "dddd" as the `format` parameter.</span></span> <span data-ttu-id="40b28-125">下面的示例演示 <xref:System.DateTime.ToString%28System.String%29> 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="40b28-125">The following example illustrates the call to the <xref:System.DateTime.ToString%28System.String%29> method.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname4.cs#4)]
         [!code-vb[Formatting.Howto.WeekdayName#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname4.vb#4)]  
  
    2.  <span data-ttu-id="40b28-126">若要提取特定区域性的星期几名称，请调用日期和时间值的 <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> 或 <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> 实例方法。</span><span class="sxs-lookup"><span data-stu-id="40b28-126">To extract the weekday name for a specific culture, call the date and time value’s <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="40b28-127">同时以 `format` 参数形式传递字符串“dddd”。</span><span class="sxs-lookup"><span data-stu-id="40b28-127">Pass the string "dddd" as the `format` parameter.</span></span> <span data-ttu-id="40b28-128">以 <xref:System.Globalization.CultureInfo> 参数的形式传递表示要检索其星期几名称的区域性的 <xref:System.Globalization.DateTimeFormatInfo> 或 `provider` 对象。</span><span class="sxs-lookup"><span data-stu-id="40b28-128">Pass either a <xref:System.Globalization.CultureInfo> or a <xref:System.Globalization.DateTimeFormatInfo> object that represents the culture whose weekday name you want to retrieve as the `provider` parameter.</span></span> <span data-ttu-id="40b28-129">下面的代码阐释如何使用表示 es-ES 区域性的 <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> 对象调用 <xref:System.Globalization.CultureInfo> 方法。</span><span class="sxs-lookup"><span data-stu-id="40b28-129">The following code illustrates a call to the <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> method using a <xref:System.Globalization.CultureInfo> object that represents the es-ES culture.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname5.cs#5)]
         [!code-vb[Formatting.Howto.WeekdayName#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname5.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="40b28-130">示例</span><span class="sxs-lookup"><span data-stu-id="40b28-130">Example</span></span>  
 <span data-ttu-id="40b28-131">该示例演示如何调用 <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> 和 <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> 属性以及 <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> 和 <xref:System.DateTimeOffset.ToString%2A?displayProperty=nameWithType> 方法，以检索特定日期中表示星期几的数字、缩写的星期几名称和完整的星期几名称。</span><span class="sxs-lookup"><span data-stu-id="40b28-131">The example illustrates calls to the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> and <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> properties and the <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> and <xref:System.DateTimeOffset.ToString%2A?displayProperty=nameWithType> methods to retrieve the number that represents the day of the week, the abbreviated weekday name, and the full weekday name for a particular date.</span></span>  
  
 [!code-csharp[Formatting.Howto.WeekdayName#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/example6.cs#6)]
 [!code-vb[Formatting.Howto.WeekdayName#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example6.vb#6)]  
  
 <span data-ttu-id="40b28-132">个别语言可能提供与 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 所提供的功能相同或互为补充的功能。</span><span class="sxs-lookup"><span data-stu-id="40b28-132">Individual languages may provide functionality that duplicates or supplements the functionality provided by the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="40b28-133">例如，Visual Basic 包括这样的两个函数：</span><span class="sxs-lookup"><span data-stu-id="40b28-133">For example, Visual Basic includes two such functions:</span></span>  
  
-   <span data-ttu-id="40b28-134">`Weekday`，它返回指示特定日期中表示星期几的数字。</span><span class="sxs-lookup"><span data-stu-id="40b28-134">`Weekday`, which returns a number that indicates the day of the week of a particular date.</span></span> <span data-ttu-id="40b28-135">此函数将一周中第一天的序数值视为一，而 <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> 属性却将其视为零。</span><span class="sxs-lookup"><span data-stu-id="40b28-135">It considers the ordinal value of the first day of the week to be one, whereas the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> property considers it to be zero.</span></span>  
  
-   <span data-ttu-id="40b28-136">`WeekdayName`，它返回当前区域性中与特定星期几相对应的周的名称。</span><span class="sxs-lookup"><span data-stu-id="40b28-136">`WeekdayName`, which returns the name of the week in the current culture that corresponds to a particular weekday number.</span></span>  
  
 <span data-ttu-id="40b28-137">下面的示例演示了 Visual Basic `Weekday` 和 `WeekdayName` 函数的用法。</span><span class="sxs-lookup"><span data-stu-id="40b28-137">The following example illustrates the use of the Visual Basic `Weekday` and `WeekdayName` functions.</span></span>  
  
 [!code-vb[Formatting.HowTo.WeekdayName#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example9.vb#9)]  
  
 <span data-ttu-id="40b28-138">也可以使用 <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> 属性返回的值检索特定日期的星期几名称。</span><span class="sxs-lookup"><span data-stu-id="40b28-138">You can also use the value returned by the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> property to retrieve the weekday name of a particular date.</span></span> <span data-ttu-id="40b28-139">此过程只需对 <xref:System.Enum.ToString%2A> 属性返回的值调用 <xref:System.DayOfWeek> 方法。</span><span class="sxs-lookup"><span data-stu-id="40b28-139">This requires only a call to the <xref:System.Enum.ToString%2A> method on the <xref:System.DayOfWeek> value returned by the property.</span></span> <span data-ttu-id="40b28-140">但是，此技术并不生成当前区域性的本地化星期几名称，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="40b28-140">However, this technique does not produce a localized weekday name for the current culture, as the following example illustrates.</span></span>  
  
 [!code-csharp[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/Howto1.cs#8)]
 [!code-vb[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/Howto1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="40b28-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="40b28-141">See Also</span></span>  
 [<span data-ttu-id="40b28-142">执行格式设置操作</span><span class="sxs-lookup"><span data-stu-id="40b28-142">Performing Formatting Operations</span></span>](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [<span data-ttu-id="40b28-143">标准日期和时间格式字符串</span><span class="sxs-lookup"><span data-stu-id="40b28-143">Standard Date and Time Format Strings</span></span>](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)  
 [<span data-ttu-id="40b28-144">自定义日期和时间格式字符串</span><span class="sxs-lookup"><span data-stu-id="40b28-144">Custom Date and Time Format Strings</span></span>](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)

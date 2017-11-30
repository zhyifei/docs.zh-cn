---
title: "如何：用非公历日历显示日期"
ms.custom: 
ms.date: 03/30/2017
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
- formatting [.NET Framework], dates
- dates [.NET Framework], formatting
- calendars [.NET Framework], displaying dates
- displaying date and time data
ms.assetid: ed324eff-4aff-4a76-b6c0-04e6c0d8f5a9
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a79860091e549dcf4eaa7090947f9506eceb6119
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-dates-in-non-gregorian-calendars"></a><span data-ttu-id="c4612-102">如何：用非公历日历显示日期</span><span class="sxs-lookup"><span data-stu-id="c4612-102">How to: Display Dates in Non-Gregorian Calendars</span></span>
<span data-ttu-id="c4612-103"><xref:System.DateTime>和<xref:System.DateTimeOffset>类型使用它们的默认日历为公历。</span><span class="sxs-lookup"><span data-stu-id="c4612-103">The <xref:System.DateTime> and <xref:System.DateTimeOffset> types use the Gregorian calendar as their default calendar.</span></span> <span data-ttu-id="c4612-104">这意味着，调用日期和时间值的 `ToString` 方法会用公历日历显示该日期和时间的字符串表示形式，即使该日期和时间是使用其他日历创建的。</span><span class="sxs-lookup"><span data-stu-id="c4612-104">This means that calling a date and time value's `ToString` method displays the string representation of that date and time in the Gregorian calendar, even if that date and time was created using another calendar.</span></span> <span data-ttu-id="c4612-105">这一点在以下示例中，使用两种不同方式与波斯历，创建日期和时间值，但仍在公历日历显示这些日期和时间值时，它调用<xref:System.DateTime.ToString%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="c4612-105">This is illustrated in the following example, which uses two different ways to create a date and time value with the Persian calendar, but still displays those date and time values in the Gregorian calendar when it calls the <xref:System.DateTime.ToString%2A> method.</span></span> <span data-ttu-id="c4612-106">此示例对于用特定日历显示日期，反映了两种常用但不正确的方法。</span><span class="sxs-lookup"><span data-stu-id="c4612-106">This example reflects two commonly used but incorrect techniques for displaying the date in a particular calendar.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Calendar#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#1)]
 [!code-vb[Formatting.HowTo.Calendar#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#1)]  
  
 <span data-ttu-id="c4612-107">两种不同的方法可以用于以特定日历显示日期。</span><span class="sxs-lookup"><span data-stu-id="c4612-107">Two different techniques can be used to display the date in a particular calendar.</span></span> <span data-ttu-id="c4612-108">第一种方法要求日历是特定区域性的默认日历。</span><span class="sxs-lookup"><span data-stu-id="c4612-108">The first requires that the calendar be the default calendar for a particular culture.</span></span> <span data-ttu-id="c4612-109">第二种方法可以与任何日历一起使用。</span><span class="sxs-lookup"><span data-stu-id="c4612-109">The second can be used with any calendar.</span></span>  
  
### <a name="to-display-the-date-for-a-cultures-default-calendar"></a><span data-ttu-id="c4612-110">针对区域性默认日历显示日期</span><span class="sxs-lookup"><span data-stu-id="c4612-110">To display the date for a culture's default calendar</span></span>  
  
1.  <span data-ttu-id="c4612-111">实例化日历对象派生自<xref:System.Globalization.Calendar>类，表示要使用的日历。</span><span class="sxs-lookup"><span data-stu-id="c4612-111">Instantiate a calendar object derived from the <xref:System.Globalization.Calendar> class that represents the calendar to be used.</span></span>  
  
2.  <span data-ttu-id="c4612-112">实例化<xref:System.Globalization.CultureInfo>对象表示的区域性的格式设置将用于显示日期。</span><span class="sxs-lookup"><span data-stu-id="c4612-112">Instantiate a <xref:System.Globalization.CultureInfo> object representing the culture whose formatting will be used to display the date.</span></span>  
  
3.  <span data-ttu-id="c4612-113">调用<xref:System.Array.Exists%2A?displayProperty=nameWithType>方法来确定日历对象是否为返回的数组的成员<xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="c4612-113">Call the <xref:System.Array.Exists%2A?displayProperty=nameWithType> method to determine whether the calendar object is a member of the array returned by the <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="c4612-114">这表示日历可用作的默认日历<xref:System.Globalization.CultureInfo>对象。</span><span class="sxs-lookup"><span data-stu-id="c4612-114">This indicates that the calendar can serve as the default calendar for the <xref:System.Globalization.CultureInfo> object.</span></span> <span data-ttu-id="c4612-115">如果它不是数组的成员，请按照“用任何日历显示日期”部分中的说明执行。</span><span class="sxs-lookup"><span data-stu-id="c4612-115">If it is not a member of the array, follow the instructions in the "To Display the Date in Any Calendar" section.</span></span>  
  
4.  <span data-ttu-id="c4612-116">日历将对象分配给<xref:System.Globalization.DateTimeFormatInfo.Calendar%2A>属性<xref:System.Globalization.DateTimeFormatInfo>返回对象<xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="c4612-116">Assign the calendar object to the <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A> property of the <xref:System.Globalization.DateTimeFormatInfo> object returned by the <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4612-117"><xref:System.Globalization.CultureInfo>类还具有<xref:System.Globalization.CultureInfo.Calendar%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="c4612-117">The <xref:System.Globalization.CultureInfo> class also has a <xref:System.Globalization.CultureInfo.Calendar%2A> property.</span></span> <span data-ttu-id="c4612-118">但是，它是只读的和常量;它不会更改以反映新的默认日历分配给<xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="c4612-118">However, it is read-only and constant; it does not change to reflect the new default calendar assigned to the <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> property.</span></span>  
  
5.  <span data-ttu-id="c4612-119">调用<xref:System.DateTime.ToString%2A>或<xref:System.DateTime.ToString%2A>方法，并将其传递<xref:System.Globalization.CultureInfo>对象在上一步中修改了其默认日历。</span><span class="sxs-lookup"><span data-stu-id="c4612-119">Call either the <xref:System.DateTime.ToString%2A> or the <xref:System.DateTime.ToString%2A> method, and pass it the <xref:System.Globalization.CultureInfo> object whose default calendar was modified in the previous step.</span></span>  
  
### <a name="to-display-the-date-in-any-calendar"></a><span data-ttu-id="c4612-120">用任何日历显示日期</span><span class="sxs-lookup"><span data-stu-id="c4612-120">To display the date in any calendar</span></span>  
  
1.  <span data-ttu-id="c4612-121">实例化日历对象派生自<xref:System.Globalization.Calendar>类，表示要使用的日历。</span><span class="sxs-lookup"><span data-stu-id="c4612-121">Instantiate a calendar object derived from the <xref:System.Globalization.Calendar> class that represents the calendar to be used.</span></span>  
  
2.  <span data-ttu-id="c4612-122">确定应在日期和时间值的字符串表示形式中出现的日期和时间元素。</span><span class="sxs-lookup"><span data-stu-id="c4612-122">Determine which date and time elements should appear in the string representation of the date and time value.</span></span>  
  
3.  <span data-ttu-id="c4612-123">对于每个你想要显示的日期和时间元素，调用日历对象`Get`...</span><span class="sxs-lookup"><span data-stu-id="c4612-123">For each date and time element that you want to display, call the calendar object's `Get`…</span></span> <span data-ttu-id="c4612-124">方法。</span><span class="sxs-lookup"><span data-stu-id="c4612-124">method.</span></span> <span data-ttu-id="c4612-125">有以下方法可用：</span><span class="sxs-lookup"><span data-stu-id="c4612-125">The following methods are available:</span></span>  
  
    -   <span data-ttu-id="c4612-126"><xref:System.Globalization.Calendar.GetYear%2A>将年份显示以适当的日历。</span><span class="sxs-lookup"><span data-stu-id="c4612-126"><xref:System.Globalization.Calendar.GetYear%2A>, to display the year in the appropriate calendar.</span></span>  
  
    -   <span data-ttu-id="c4612-127"><xref:System.Globalization.Calendar.GetMonth%2A>显示相应的日历中的月。</span><span class="sxs-lookup"><span data-stu-id="c4612-127"><xref:System.Globalization.Calendar.GetMonth%2A>, to display the month in the appropriate calendar.</span></span>  
  
    -   <span data-ttu-id="c4612-128"><xref:System.Globalization.Calendar.GetDayOfMonth%2A>若要显示的每月天数数以适当的日历。</span><span class="sxs-lookup"><span data-stu-id="c4612-128"><xref:System.Globalization.Calendar.GetDayOfMonth%2A>, to display the number of the day of the month in the appropriate calendar.</span></span>  
  
    -   <span data-ttu-id="c4612-129"><xref:System.Globalization.Calendar.GetHour%2A>在适当的日历中显示的时间。</span><span class="sxs-lookup"><span data-stu-id="c4612-129"><xref:System.Globalization.Calendar.GetHour%2A>, to display the hour of the day in the appropriate calendar.</span></span>  
  
    -   <span data-ttu-id="c4612-130"><xref:System.Globalization.Calendar.GetMinute%2A>以显示在相应的日历中的小时分钟。</span><span class="sxs-lookup"><span data-stu-id="c4612-130"><xref:System.Globalization.Calendar.GetMinute%2A>, to display the minutes in the hour in the appropriate calendar.</span></span>  
  
    -   <span data-ttu-id="c4612-131"><xref:System.Globalization.Calendar.GetSecond%2A>若要以适当的日历分钟内显示秒数。</span><span class="sxs-lookup"><span data-stu-id="c4612-131"><xref:System.Globalization.Calendar.GetSecond%2A>, to display the seconds in the minute in the appropriate calendar.</span></span>  
  
    -   <span data-ttu-id="c4612-132"><xref:System.Globalization.Calendar.GetMilliseconds%2A>以在相应的日历中的第二个显示毫秒数。</span><span class="sxs-lookup"><span data-stu-id="c4612-132"><xref:System.Globalization.Calendar.GetMilliseconds%2A> , to display the milliseconds in the second in the appropriate calendar.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4612-133">示例</span><span class="sxs-lookup"><span data-stu-id="c4612-133">Example</span></span>  
 <span data-ttu-id="c4612-134">该示例使用两个不同日历显示日期。</span><span class="sxs-lookup"><span data-stu-id="c4612-134">The example displays a date using two different calendars.</span></span> <span data-ttu-id="c4612-135">它在将回历定义为 ar-JO 区域性的默认日历之后显示日期，并使用波斯日历（fa-IR 区域性不支持将它作为可选日历）显示日期。</span><span class="sxs-lookup"><span data-stu-id="c4612-135">It displays the date after defining the Hijri calendar as the default calendar for the ar-JO culture, and displays the date using the Persian calendar, which is not supported as an optional calendar by the fa-IR culture.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Calendar#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#2)]
 [!code-vb[Formatting.HowTo.Calendar#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#2)]  
  
 <span data-ttu-id="c4612-136">每个<xref:System.Globalization.CultureInfo>对象都可以支持一个或多个日历，由指示<xref:System.Globalization.CultureInfo.OptionalCalendars%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="c4612-136">Each <xref:System.Globalization.CultureInfo> object can support one or more calendars, which are indicated by the <xref:System.Globalization.CultureInfo.OptionalCalendars%2A> property.</span></span> <span data-ttu-id="c4612-137">以下方法之一指定为区域性的默认日历，并且返回的只读的<xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="c4612-137">One of these is designated as the culture's default calendar and is returned by the read-only <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="c4612-138">另一个可选日历可以被指定为默认值通过分配<xref:System.Globalization.Calendar>对象，表示日历<xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType>属性返回<xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="c4612-138">Another of the optional calendars can be designated as the default by assigning a <xref:System.Globalization.Calendar> object that represents that calendar to the <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType> property returned by the <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="c4612-139">但是，某些日历，由表示波斯历如<xref:System.Globalization.PersianCalendar>类中，不能作为任何区域性的可选日历。</span><span class="sxs-lookup"><span data-stu-id="c4612-139">However, some calendars, such as the Persian calendar represented by the <xref:System.Globalization.PersianCalendar> class, do not serve as optional calendars for any culture.</span></span>  
  
 <span data-ttu-id="c4612-140">该示例定义了一个可重用的日历实用工具类 `CalendarUtility`，用于处理有关使用特定日历生成日期的字符串表示形式的许多详细信息。</span><span class="sxs-lookup"><span data-stu-id="c4612-140">The example defines a reusable calendar utility class, `CalendarUtility`, to handle many of the details of generating the string representation of a date using a particular calendar.</span></span> <span data-ttu-id="c4612-141">`CalendarUtility` 类包含以下成员：</span><span class="sxs-lookup"><span data-stu-id="c4612-141">The `CalendarUtility` class has the following members:</span></span>  
  
-   <span data-ttu-id="c4612-142">其单个参数是参数化构造函数<xref:System.Globalization.Calendar>对象是用来表示日期。</span><span class="sxs-lookup"><span data-stu-id="c4612-142">A parameterized constructor whose single parameter is a <xref:System.Globalization.Calendar> object in which a date is to be represented.</span></span> <span data-ttu-id="c4612-143">这会分配给类的私有字段。</span><span class="sxs-lookup"><span data-stu-id="c4612-143">This is assigned to a private field of the class.</span></span>  
  
-   <span data-ttu-id="c4612-144">`CalendarExists`返回一个布尔值，该值表示日历的私有方法`CalendarUtility`对象受<xref:System.Globalization.CultureInfo>传递给方法作为参数的对象。</span><span class="sxs-lookup"><span data-stu-id="c4612-144">`CalendarExists`, a private method that returns a Boolean value indicating whether the calendar represented by the `CalendarUtility` object is supported by the <xref:System.Globalization.CultureInfo> object that is passed to the method as a parameter.</span></span> <span data-ttu-id="c4612-145">该方法包装对的调用<xref:System.Array.Exists%2A?displayProperty=nameWithType>方法，向其传递<xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>数组。</span><span class="sxs-lookup"><span data-stu-id="c4612-145">The method wraps a call to the <xref:System.Array.Exists%2A?displayProperty=nameWithType> method, to which it passes the <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType> array.</span></span>  
  
-   <span data-ttu-id="c4612-146">`HasSameName`分配给一个私有方法<xref:System.Predicate%601>，传入作为参数传递给委托<xref:System.Array.Exists%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="c4612-146">`HasSameName`, a private method assigned to the <xref:System.Predicate%601> delegate that is passed as a parameter to the <xref:System.Array.Exists%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c4612-147">数组的每个成员都会传递给该方法，直到该方法返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="c4612-147">Each member of the array is passed to the method until the method returns `true`.</span></span> <span data-ttu-id="c4612-148">该方法确定可选日历的名称是否与 `CalendarUtility` 对象表示的日历相同。</span><span class="sxs-lookup"><span data-stu-id="c4612-148">The method determines whether the name of an optional calendar is the same as the calendar represented by the `CalendarUtility` object.</span></span>  
  
-   <span data-ttu-id="c4612-149">`DisplayDate`传递两个参数的重载的公共方法： 请<xref:System.DateTime>或<xref:System.DateTimeOffset>值，用以在所表示的日历`CalendarUtility`对象和要使用其格式设置规则的区域性。</span><span class="sxs-lookup"><span data-stu-id="c4612-149">`DisplayDate`, an overloaded public method that is passed two parameters: either a <xref:System.DateTime> or <xref:System.DateTimeOffset> value to express in the calendar represented by the `CalendarUtility` object; and the culture whose formatting rules are to be used.</span></span> <span data-ttu-id="c4612-150">它在返回日期的字符串表示形式时的行为取决于要使用其格式设置规则的区域性是否支持目标日历。</span><span class="sxs-lookup"><span data-stu-id="c4612-150">Its behavior in returning the string representation of a date depends on whether the target calendar is supported by the culture whose formatting rules are to be used.</span></span>  
  
 <span data-ttu-id="c4612-151">无论用于创建日历<xref:System.DateTime>或<xref:System.DateTimeOffset>在此示例中，该值通常表示为公历日期的值。</span><span class="sxs-lookup"><span data-stu-id="c4612-151">Regardless of the calendar used to create a <xref:System.DateTime> or <xref:System.DateTimeOffset> value in this example, that value is typically expressed as a Gregorian date.</span></span> <span data-ttu-id="c4612-152">这是因为<xref:System.DateTime>和<xref:System.DateTimeOffset>类型并不保留任何日历信息。</span><span class="sxs-lookup"><span data-stu-id="c4612-152">This is because the <xref:System.DateTime> and <xref:System.DateTimeOffset> types do not preserve any calendar information.</span></span> <span data-ttu-id="c4612-153">它们在内部表示自 0001 年 1 月 1 日午夜以来所经历的时钟周期数。</span><span class="sxs-lookup"><span data-stu-id="c4612-153">Internally, they are represented as the number of ticks that have elapsed since midnight of January 1, 0001.</span></span> <span data-ttu-id="c4612-154">该数字的解释取决于日历。</span><span class="sxs-lookup"><span data-stu-id="c4612-154">The interpretation of that number depends on the calendar.</span></span> <span data-ttu-id="c4612-155">对于大多数区域性，默认日历是公历。</span><span class="sxs-lookup"><span data-stu-id="c4612-155">For most cultures, the default calendar is the Gregorian calendar.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c4612-156">编译代码</span><span class="sxs-lookup"><span data-stu-id="c4612-156">Compiling the Code</span></span>  
 <span data-ttu-id="c4612-157">此示例需要对 System.Core.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="c4612-157">This example requires a reference to System.Core.dll.</span></span>  
  
 <span data-ttu-id="c4612-158">在命令行上使用 csc.exe 或 vb.exe 代码编译。</span><span class="sxs-lookup"><span data-stu-id="c4612-158">Compile the code at the command line using csc.exe or vb.exe.</span></span> <span data-ttu-id="c4612-159">若要编译中的代码[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，将其放入控制台应用程序项目模板。</span><span class="sxs-lookup"><span data-stu-id="c4612-159">To compile the code in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], put it in a console application project template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4612-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4612-160">See Also</span></span>  
 [<span data-ttu-id="c4612-161">执行格式设置操作</span><span class="sxs-lookup"><span data-stu-id="c4612-161">Performing Formatting Operations</span></span>](../../../docs/standard/base-types/performing-formatting-operations.md)

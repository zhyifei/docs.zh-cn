---
title: "使用日期和时间执行算术运算"
description: "使用日期和时间执行算术运算"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 589ac5ec-8365-4a0d-bc38-72183718110c
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: b872cc4c2b799ddafc9df263795d860754d1ec17
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="performing-arithmetic-operations-with-dates-and-times"></a><span data-ttu-id="98cd0-104">使用日期和时间执行算术运算</span><span class="sxs-lookup"><span data-stu-id="98cd0-104">Performing arithmetic operations with dates and times</span></span>

<span data-ttu-id="98cd0-105">尽管 [System.DateTime](xref:System.DateTime) 和 [System.DateTimeOffset](xref:System.DateTimeOffset) 结构都可提供对其值执行算术运算的成员，但算术运算的结果却大不相同。</span><span class="sxs-lookup"><span data-stu-id="98cd0-105">Although both the [System.DateTime](xref:System.DateTime) and the [System.DateTimeOffset](xref:System.DateTimeOffset) structures provide members that perform arithmetic operations on their values, the results of arithmetic operations are very different.</span></span> <span data-ttu-id="98cd0-106">本文将分析这些差异、将这些差异与日期和时间数据形式的时区感知程度联系起来，并介绍如何使用日期和时间数据完整地执行时区感知运算。</span><span class="sxs-lookup"><span data-stu-id="98cd0-106">This article examines those differences, relates them to degrees of time zone awareness in date and time data, and discusses how to perform fully time zone aware operations using date and time data.</span></span>

## <a name="comparisons-and-arithmetic-operations-with-datetime-values"></a><span data-ttu-id="98cd0-107">DateTime 值的比较和算术运算</span><span class="sxs-lookup"><span data-stu-id="98cd0-107">Comparisons and Arithmetic Operations with DateTime Values</span></span>

<span data-ttu-id="98cd0-108">[System.DateTime](xref:System.DateTime) 值具有一定程度的时区感知。</span><span class="sxs-lookup"><span data-stu-id="98cd0-108">[System.DateTime](xref:System.DateTime) values possess a limited degree of time zone awareness.</span></span> <span data-ttu-id="98cd0-109">通过 [DateTime.Kind](xref:System.DateTime.Kind) 属性可将 [System.DateTimeKind](xref:System.DateTimeKind) 值分配到日期和时间，以指示其表示的是本地时间、协调世界时 (UTC) 还是未指定时区中的时间。</span><span class="sxs-lookup"><span data-stu-id="98cd0-109">The [DateTime.Kind](xref:System.DateTime.Kind) property allows a [System.DateTimeKind](xref:System.DateTimeKind) value to be assigned to the date and time to indicate whether it represents local time, Coordinated Universal Time (UTC), or the time in an unspecified time zone.</span></span> <span data-ttu-id="98cd0-110">但是对 [DateTime](xref:System.DateTime) 值进行比较或执行日期和时间算术算法时，会忽略此有限的时区信息。</span><span class="sxs-lookup"><span data-stu-id="98cd0-110">However, this limited time zone information is ignored when comparing or performing date and time arithmetic on [DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="98cd0-111">以下示例通过比较当前本地时间与当前 UTC 时间，对此进行了阐释。</span><span class="sxs-lookup"><span data-stu-id="98cd0-111">The following example, which compares the current local time with the current UTC time, illustrates this.</span></span>

```csharp
using System;

public enum TimeComparison
{
   EarlierThan = -1,
   TheSameAs = 0,
   LaterThan = 1
}

public class DateManipulation
{
   public static void Main()
   {
      DateTime localTime = DateTime.Now;
      DateTime utcTime = DateTime.UtcNow;

      Console.WriteLine("Difference between {0} and {1} time: {2}:{3} hours", 
                        localTime.Kind.ToString(), 
                        utcTime.Kind.ToString(), 
                        (localTime - utcTime).Hours, 
                        (localTime - utcTime).Minutes);
      Console.WriteLine("The {0} time is {1} the {2} time.", 
                        localTime.Kind.ToString(), 
                        Enum.GetName(typeof(TimeComparison), localTime.CompareTo(utcTime)), 
                        utcTime.Kind.ToString());  
   }
}
// If run in the U.S. Pacific Standard Time zone, the example displays 
// the following output to the console:
//    Difference between Local and Utc time: -7:0 hours
//    The Local time is EarlierThan the Utc time.
```

```vb
Public Enum TimeComparison As Integer
   EarlierThan = -1
   TheSameAs = 0
   LaterThan = 1
End Enum

Module DateManipulation
   Public Sub Main()
      Dim localTime As Date = Date.Now
      Dim utcTime As Date = Date.UtcNow

      Console.WriteLine("Difference between {0} and {1} time: {2}:{3} hours", _
                        localTime.Kind.ToString(), _
                        utcTime.Kind.ToString(), _
                        (localTime - utcTime).Hours, _
                        (localTime - utcTime).Minutes)
      Console.WriteLine("The {0} time is {1} the {2} time.", _
                        localTime.Kind.ToString(), _ 
                        [Enum].GetName(GetType(TimeComparison), localTime.CompareTo(utcTime)), _
                        utcTime.Kind.ToString())  
      ' If run in the U.S. Pacific Standard Time zone, the example displays 
      ' the following output to the console:
      '    Difference between Local and Utc time: -7:0 hours
      '    The Local time is EarlierThan the Utc time.                                                    
   End Sub
End Module
```

<span data-ttu-id="98cd0-112">[DateTime.CompareTo(DateTime, DateTime)](xref:System.DateTime.Compare(System.DateTime,System.DateTime)) 方法报告本地时间早于（小于）UTC 时间，并且减法运算指示，对于美国太平洋标准时区内的系统，其 UTC 时间与本地时间之间的时差是&7; 小时。</span><span class="sxs-lookup"><span data-stu-id="98cd0-112">The [DateTime.CompareTo(DateTime, DateTime)](xref:System.DateTime.Compare(System.DateTime,System.DateTime)) method reports that the local time is earlier than (or less than) the UTC time, and the subtraction operation indicates that the difference between UTC and the local time for a system in the U.S. Pacific Standard Time zone is seven hours.</span></span> <span data-ttu-id="98cd0-113">但由于这两个值提供的单个时间点的表现形式有所不同，因此从本例中可清楚得知，此时间间隔完全是由本地时区与 UTC 之间的时差所致。</span><span class="sxs-lookup"><span data-stu-id="98cd0-113">But because these two values provide different representations of a single point in time, it is clear in this case that this time interval is completely attributable to the local time zone's offset from UTC.</span></span> 

<span data-ttu-id="98cd0-114">一般来说，[DateTimeKind](xref:System.DateTimeKind) 属性不会影响 [DateTime](xref:System.DateTime) 比较和算术方法返回的结果（如两个相同时间点所指示那样），只会影响对这些结果的解释。</span><span class="sxs-lookup"><span data-stu-id="98cd0-114">More generally, the [DateTimeKind](xref:System.DateTimeKind) property does not affect the results returned by [DateTime](xref:System.DateTime) comparison and arithmetic methods (as the comparison of two identical points in time indicates), although it can affect the interpretation of those results.</span></span> <span data-ttu-id="98cd0-115">例如: </span><span class="sxs-lookup"><span data-stu-id="98cd0-115">For example:</span></span>

* <span data-ttu-id="98cd0-116">对 [DateTimeKind](xref:System.DateTimeKind) 属性均等于 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) 的两个日期和时间值执行的任何算术运算所得出的结果可反映两个值之间的实际时间间隔。</span><span class="sxs-lookup"><span data-stu-id="98cd0-116">The result of any arithmetic operation performed on two date and time values whose [DateTimeKind](xref:System.DateTimeKind) properties both equal [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) reflects the actual time interval between the two values.</span></span> <span data-ttu-id="98cd0-117">同样，对两个日期和时间值进行比较可精确反映出时间之间的关系。</span><span class="sxs-lookup"><span data-stu-id="98cd0-117">Similarly, the comparison of two such date and time values accurately reflects the relationship between times.</span></span>

* <span data-ttu-id="98cd0-118">对 [DateTimeKind](xref:System.DateTimeKind) 属性均等于 [DateTimeKind.Local](xref:System.DateTimeKind.Local) 或 [DateTimeKind](xref:System.DateTimeKind) 属性值不同的两个日期和时间值执行的任何算术或比较运算所得出的结果可反映两个值之间的时钟时间差。</span><span class="sxs-lookup"><span data-stu-id="98cd0-118">The result of any arithmetic or comparison operation performed on two date and time values whose [DateTimeKind](xref:System.DateTimeKind) properties both equal [DateTimeKind.Local](xref:System.DateTimeKind.Local) or on two date and time values with different [DateTimeKind](xref:System.DateTimeKind) property values reflects the difference in clock time between the two values.</span></span> 

* <span data-ttu-id="98cd0-119">对本地日期和时间值执行的算术或比较运算不考虑某个特定值是否不明确或无效，也不考虑任何调整规则（因本地时区与夏令时的来回转换）的影响。</span><span class="sxs-lookup"><span data-stu-id="98cd0-119">Arithmetic or comparison operations on local date and time values do not consider whether a particular value is ambiguous or invalid, nor do they take account of the effect of any adjustment rules that result from the local time zone's transition to or from daylight saving time.</span></span>

* <span data-ttu-id="98cd0-120">任何比较或计算 UTC 与本地时间之差的运算所得出的结果中都包含一个时间间隔，它等于本地时区与 UTC 之间的时差。</span><span class="sxs-lookup"><span data-stu-id="98cd0-120">Any operation that compares or calculates the difference between UTC and a local time includes a time interval equal to the local time zone's offset from UTC in the result.</span></span> 

* <span data-ttu-id="98cd0-121">任何比较或计算未指定时间与 UTC 或本地时间的运算都反映简单的时钟时间。</span><span class="sxs-lookup"><span data-stu-id="98cd0-121">Any operation that compares or calculates the difference between an unspecified time and either UTC or the local time reflects simple clock time.</span></span> <span data-ttu-id="98cd0-122">时区差异未纳入考虑范围，且结果不会反映是否应用了时区调整规则。</span><span class="sxs-lookup"><span data-stu-id="98cd0-122">Time zone differences are not considered, and the result does not reflect the application of time zone adjustment rules.</span></span> 

* <span data-ttu-id="98cd0-123">任何比较或计算两个未指定时间之差的运算都可能包含一个未知间隔，它反映两个不同时区内的时间之差。</span><span class="sxs-lookup"><span data-stu-id="98cd0-123">Any operation that compares or calculates the difference between two unspecified times may include an unknown interval that reflects the difference between the time in two different time zones.</span></span>

<span data-ttu-id="98cd0-124">在很多情况下，时区差异不会影响日期和时间计算，或是日期和时间数据上下文会定义比较或算术运算的含义。</span><span class="sxs-lookup"><span data-stu-id="98cd0-124">There are many scenarios in which time zone differences do not affect date and time calculations or in which the context of the date and time data defines the meaning of comparison or arithmetic operations.</span></span> <span data-ttu-id="98cd0-125">有关其中一些场景的介绍，请参阅[在 DateTime、DateTimeOffset、TimeSpan 和 TimeZoneInfo 之间进行选择](choosing-between-datetime.md)。</span><span class="sxs-lookup"><span data-stu-id="98cd0-125">For a discussion of some of these, see [Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](choosing-between-datetime.md).</span></span>

## <a name="comparisons-and-arithmetic-operations-with-datetimeoffset-values"></a><span data-ttu-id="98cd0-126">DateTimeOffset 值的比较和算术运算</span><span class="sxs-lookup"><span data-stu-id="98cd0-126">Comparisons and Arithmetic Operations with DateTimeOffset Values</span></span>

<span data-ttu-id="98cd0-127">[System.DateTimeOffset](xref:System.DateTimeOffset) 值不仅包括日期和时间，还包括明确定义相对 UTC 的日期和时间的时差。</span><span class="sxs-lookup"><span data-stu-id="98cd0-127">A [System.DateTimeOffset](xref:System.DateTimeOffset) value includes not only a date and time, but also an offset that unambiguously defines that date and time relative to UTC.</span></span> <span data-ttu-id="98cd0-128">因此，可以定义与 [System.DateTime](xref:System.DateTime) 值有些许不同的等式。</span><span class="sxs-lookup"><span data-stu-id="98cd0-128">This makes it possible to define equality somewhat differently than for [System.DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="98cd0-129">如果它们具有相同的日期和时间值，则 [DateTime](xref:System.DateTime) 值相同；如果它们表示相同的时间点，则 [DateTimeOffset](xref:System.DateTimeOffset) 值相同。</span><span class="sxs-lookup"><span data-stu-id="98cd0-129">Whereas [DateTime](xref:System.DateTime) values are equal if they have the same date and time value, [DateTimeOffset](xref:System.DateTimeOffset) values are equal if they both refer to the same point in time.</span></span> <span data-ttu-id="98cd0-130">这使得在确定两个日期和时间之间的间隔的比较和大多数算术运算中使用时，[DateTimeOffset](xref:System.DateTimeOffset) 值更加准确，且相比来说更不需要解释。</span><span class="sxs-lookup"><span data-stu-id="98cd0-130">This makes a [DateTimeOffset](xref:System.DateTimeOffset) value more accurate and less in need of interpretation when used in comparisons and in most arithmetic operations that determine the interval between two dates and times.</span></span> <span data-ttu-id="98cd0-131">以下示例阐释了行为中的此差异，其中的 [DateTimeOffset](xref:System.DateTimeOffset) 等效于前述示例中比较本地和 UTC DateTime 值。</span><span class="sxs-lookup"><span data-stu-id="98cd0-131">The following example, which is the [DateTimeOffset](xref:System.DateTimeOffset) equivalent to the previous example that compared local and UTC DateTime values, illustrates this difference in behavior.</span></span>

```csharp
using System;

public enum TimeComparison
{
   EarlierThan = -1,
   TheSameAs = 0,
   LaterThan = 1
}

public class DateTimeOffsetManipulation
{
   public static void Main()
   {
      DateTimeOffset localTime = DateTimeOffset.Now;
      DateTimeOffset utcTime = DateTimeOffset.UtcNow;

      Console.WriteLine("Difference between local time and UTC: {0}:{1:D2} hours", 
                        (localTime - utcTime).Hours, 
                        (localTime - utcTime).Minutes);
      Console.WriteLine("The local time is {0} UTC.", 
                        Enum.GetName(typeof(TimeComparison), localTime.CompareTo(utcTime)));  
   }
}
// Regardless of the local time zone, the example displays 
// the following output to the console:
//    Difference between local time and UTC: 0:00 hours.
//    The local time is TheSameAs UTC.
```

```vb
Public Enum TimeComparison As Integer
   EarlierThan = -1
   TheSameAs = 0
   LaterThan = 1
End Enum

Module DateTimeOffsetManipulation
   Public Sub Main()
      Dim localTime As DateTimeOffset = DateTimeOffset.Now
      Dim utcTime As DateTimeOffset = DateTimeOffset.UtcNow

      Console.WriteLine("Difference between local time and UTC: {0}:{1:D2} hours.", _
                        (localTime - utcTime).Hours, _
                        (localTime - utcTime).Minutes)
      Console.WriteLine("The local time is {0} UTC.", _
                        [Enum].GetName(GetType(TimeComparison), localTime.CompareTo(utcTime)))  
   End Sub
End Module
' Regardless of the local time zone, the example displays 
' the following output to the console:
'    Difference between local time and UTC: 0:00 hours.
'    The local time is TheSameAs UTC.
'          Console.WriteLine(e.GetType().Name)
```

<span data-ttu-id="98cd0-132">在本示例中，[DateTimeOffset.CompareTo](xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)) 方法指示当前本地时间和当前 UTC 时间相等，[DateTimeOffset](xref:System.DateTimeOffset) 值相减得出的结果指示两个时间之差为 [TimeSpan.Zero](xref:System.TimeSpan.Zero)。</span><span class="sxs-lookup"><span data-stu-id="98cd0-132">In this example, the [DateTimeOffset.CompareTo](xref:System.DateTimeOffset.CompareTo(System.DateTimeOffset)) method indicates that the current local time and the current UTC time are equal, and subtraction of [DateTimeOffset](xref:System.DateTimeOffset) values indicates that the difference between the two times is [TimeSpan.Zero](xref:System.TimeSpan.Zero).</span></span> 

<span data-ttu-id="98cd0-133">在日期和时间算术中使用 [DateTimeOffset](xref:System.DateTimeOffset) 值的主要限制在于，虽然 [DateTimeOffset](xref:System.DateTimeOffset) 值具有一定的时区感知，但并不能完全感知时区。</span><span class="sxs-lookup"><span data-stu-id="98cd0-133">The chief limitation of using [DateTimeOffset](xref:System.DateTimeOffset) values in date and time arithmetic is that although [DateTimeOffset](xref:System.DateTimeOffset) values have some time zone awareness, they are not fully time zone aware.</span></span> <span data-ttu-id="98cd0-134">尽管首次向 [DateTimeOffset](xref:System.DateTimeOffset) 变量分配值时，[DateTimeOffset](xref:System.DateTimeOffset) 值的偏移量能反映时区与 UTC 之间的时差，但自那以后就将不再与时区相关联。</span><span class="sxs-lookup"><span data-stu-id="98cd0-134">Although the [DateTimeOffset](xref:System.DateTimeOffset) value's offset reflects a time zone's offset from UTC when a [DateTimeOffset](xref:System.DateTimeOffset) variable is first assigned a value, it becomes disassociated from the time zone thereafter.</span></span> <span data-ttu-id="98cd0-135">由于不再直接与可识别时间关联，日期和时间间隔的相加和相减将不会考虑时区调整规则。</span><span class="sxs-lookup"><span data-stu-id="98cd0-135">Because it is no longer directly associated with an identifiable time, the addition and subtraction of date and time intervals does not consider a time zone's adjustment rules.</span></span> 

<span data-ttu-id="98cd0-136">举例说明，美国中部标准时区的夏令时转换发生于 </span><span class="sxs-lookup"><span data-stu-id="98cd0-136">To illustrate, the transition to daylight saving time in the U.S. Central Standard Time zone occurs at 2:00 A.M.</span></span> <span data-ttu-id="98cd0-137">2008 年 3 月 9 日凌晨 2:00。</span><span class="sxs-lookup"><span data-stu-id="98cd0-137">on March 9, 2008.</span></span> <span data-ttu-id="98cd0-138">这意味着，向中部标准时间 2008 年 3 月 9 日凌晨 1:30 增加两个半小时的间隔，</span><span class="sxs-lookup"><span data-stu-id="98cd0-138">This means that adding a two and a half hour interval to a Central Standard time of 1:30 A.M.</span></span> <span data-ttu-id="98cd0-139">得出的日期和时间应为 </span><span class="sxs-lookup"><span data-stu-id="98cd0-139">on March 9, 2008, should produce a date and time of 5:00 A.M.</span></span> <span data-ttu-id="98cd0-140">2008 年 3 月 9 日凌晨 5:00。</span><span class="sxs-lookup"><span data-stu-id="98cd0-140">on March 9, 2008.</span></span> <span data-ttu-id="98cd0-141">但是，如下面的示例所示，加法运算得出的结果却是 </span><span class="sxs-lookup"><span data-stu-id="98cd0-141">However, as the following example shows, the result of the addition is 4:00 A.M.</span></span> <span data-ttu-id="98cd0-142">2008 年 3 月 9 日凌晨 4:00。</span><span class="sxs-lookup"><span data-stu-id="98cd0-142">on March 9, 2008.</span></span> <span data-ttu-id="98cd0-143">请注意，此运算结果并不表示正确的时间点，它也不是我们所关注的时区的时间（也就是说，运算未得出预期的时区时差）。</span><span class="sxs-lookup"><span data-stu-id="98cd0-143">Note that this result of this operation does represent the correct point in time, although it is not the time in the time zone in which we are interested (that is, it does not have the expected time zone offset).</span></span>

```csharp
using System;

public class IntervalArithmetic
{
   public static void Main()
   {
      DateTime generalTime = new DateTime(2008, 3, 9, 1, 30, 0);
      const string tzName = "Central Standard Time";
      TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

      // Instantiate DateTimeOffset value to have correct CST offset
      try
      {
         DateTimeOffset centralTime1 = new DateTimeOffset(generalTime, 
                    TimeZoneInfo.FindSystemTimeZoneById(tzName).GetUtcOffset(generalTime));

         // Add two and a half hours      
         DateTimeOffset centralTime2 = centralTime1.Add(twoAndAHalfHours);
         // Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, 
                                                    twoAndAHalfHours.ToString(), 
                                                    centralTime2);  
      }
      catch (TimeZoneNotFoundException)
      {
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.");
      }
   }
}
// The example displays the following output to the console:
//    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 4:00:00 AM -06:00
```

```vb
Module IntervalArithmetic
   Public Sub Main()
      Dim generalTime As Date = #03/09/2008 1:30AM#
      Const tzName As String = "Central Standard Time"
      Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

      ' Instantiate DateTimeOffset value to have correct CST offset
      Try
         Dim centralTime1 As New DateTimeOffset(generalTime, _
                    TimeZoneInfo.FindSystemTimeZoneById(tzName).GetUtcOffset(generalTime))

         ' Add two and a half hours      
         Dim centralTime2 As DateTimeOffset = centralTime1.Add(twoAndAHalfHours)
         ' Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, _
                                                    twoAndAHalfHours.ToString(), _
                                                    centralTime2)   
      Catch e As TimeZoneNotFoundException
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.")
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 4:00:00 AM -06:00
```

## <a name="arithmetic-operations-with-times-in-time-zones"></a><span data-ttu-id="98cd0-144">时区内时间的算术运算</span><span class="sxs-lookup"><span data-stu-id="98cd0-144">Arithmetic Operations with Times in Time Zones</span></span>

<span data-ttu-id="98cd0-145">执行日期和时间算术时，[System.TimeZoneInfo](xref:System.TimeZoneInfo) 类不提供任何可自动应用调整规则的方法。</span><span class="sxs-lookup"><span data-stu-id="98cd0-145">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class does not provide any methods that automatically apply adjustment rules when you perform date and time arithmetic.</span></span> <span data-ttu-id="98cd0-146">但是可以通过将某一时区内的时间转换为 UTC，执行算术运算，然后再将 UTC 转换回该时区内的时间，来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="98cd0-146">However, you can do this by converting the time in a time zone to UTC, performing the arithmetic operation, and then converting from UTC back to the time in the time zone.</span></span> <span data-ttu-id="98cd0-147">有关详细信息，请参阅[如何：在日期和时间算术中使用时区](use-time-zones-in-arithmetic.md)。</span><span class="sxs-lookup"><span data-stu-id="98cd0-147">For details, see [How to: Use Time Zones in Date and Time Arithmetic](use-time-zones-in-arithmetic.md).</span></span>

<span data-ttu-id="98cd0-148">例如，以下代码类似于之前向 2008 年 3 月 9 日凌晨 2:00 增加</span><span class="sxs-lookup"><span data-stu-id="98cd0-148">For example, the following code is similar to the previous code that added two-and-a-half hours to 2:00 A.M.</span></span> <span data-ttu-id="98cd0-149">两个半小时的代码。</span><span class="sxs-lookup"><span data-stu-id="98cd0-149">on March 9, 2008.</span></span> <span data-ttu-id="98cd0-150">但是，由于其在执行日期和时间算术前将中部标准时间转换为 UTC，然后将 UTC 结果转换回中部标准时间，所以得出的时间反映的是中部标准时区转换为夏令时。</span><span class="sxs-lookup"><span data-stu-id="98cd0-150">However, because it converts a Central Standard time to UTC before it performs date and time arithmetic, and then converts the result from UTC back to Central Standard time, the resulting time reflects the Central Standard Time Zone's transition to daylight saving time.</span></span>

```csharp
using System;

public class TimeZoneAwareArithmetic
{
   public static void Main()
   {
      const string tzName = "Central Standard Time";

      DateTime generalTime = new DateTime(2008, 3, 9, 1, 30, 0);
      TimeZoneInfo cst = TimeZoneInfo.FindSystemTimeZoneById(tzName);
      TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

      // Instantiate DateTimeOffset value to have correct CST offset
      try
      {
         DateTimeOffset centralTime1 = new DateTimeOffset(generalTime, 
                                       cst.GetUtcOffset(generalTime));

         // Add two and a half hours
         DateTimeOffset utcTime = centralTime1.ToUniversalTime();
         utcTime += twoAndAHalfHours;

         DateTimeOffset centralTime2 = TimeZoneInfo.ConvertTime(utcTime, cst);
         // Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, 
                                                    twoAndAHalfHours.ToString(), 
                                                    centralTime2);  
      }
      catch (TimeZoneNotFoundException)
      {
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.");
      }
   }
}
// The example displays the following output to the console:
//    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 5:00:00 AM -05:00
```

```vb
Module TimeZoneAwareArithmetic
   Public Sub Main()
      Const tzName As String = "Central Standard Time"

      Dim generalTime As Date = #03/09/2008 1:30AM#
      Dim cst As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(tzName) 
      Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

      ' Instantiate DateTimeOffset value to have correct CST offset
      Try
         Dim centralTime1 As New DateTimeOffset(generalTime, _
                    cst.GetUtcOffset(generalTime))

         ' Add two and a half hours 
         Dim utcTime As DateTimeOffset = centralTime1.ToUniversalTime()
         utcTime += twoAndAHalfHours

         Dim centralTime2 As DateTimeOffset = TimeZoneInfo.ConvertTime(utcTime, cst)
         ' Display result
         Console.WriteLine("{0} + {1} hours = {2}", centralTime1, _
                                                    twoAndAHalfHours.ToString(), _
                                                    centralTime2)   
      Catch e As TimeZoneNotFoundException
         Console.WriteLine("Unable to retrieve Central Standard Time zone information.")
      End Try
   End Sub
End Module
' The example displays the following output to the console:
'    3/9/2008 1:30:00 AM -06:00 + 02:30:00 hours = 3/9/2008 5:00:00 AM -05:00
```

## <a name="see-also"></a><span data-ttu-id="98cd0-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98cd0-151">See Also</span></span>

[<span data-ttu-id="98cd0-152">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="98cd0-152">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="98cd0-153">如何：在日期和时间算术中使用时区</span><span class="sxs-lookup"><span data-stu-id="98cd0-153">How to: use time zones in date and time arithmetic</span></span>](use-time-zones-in-arithmetic.md)




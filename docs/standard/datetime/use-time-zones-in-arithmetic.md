---
title: "如何：在日期和时间算术中使用时区"
description: "如何在日期和时间算法中使用时区"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 26870cdc-1709-4978-831b-ff2a2f24856f
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: a86471972d42adcbc412cc8eeb300410ca8a9c42
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a><span data-ttu-id="3b350-104">如何：在日期和时间算术中使用时区</span><span class="sxs-lookup"><span data-stu-id="3b350-104">How to: use time zones in date and time arithmetic</span></span>

<span data-ttu-id="3b350-105">通常，使用 [System.DateTimeOffset](xref:System.DateTimeOffset) 值执行日期和时间运算时，结果不会反映任何时区调整规则。</span><span class="sxs-lookup"><span data-stu-id="3b350-105">Ordinarily, when you perform date and time arithmetic using [System.DateTimeOffset](xref:System.DateTimeOffset) values, the result does not reflect any time zone adjustment rules.</span></span> <span data-ttu-id="3b350-106">即使日期和时间值的时区明确可辨也是如此。</span><span class="sxs-lookup"><span data-stu-id="3b350-106">This is true even when the time zone of the date and time value is clearly identifiable.</span></span> <span data-ttu-id="3b350-107">本文介绍如何对特定时区内的日期和时间值执行算术运算。</span><span class="sxs-lookup"><span data-stu-id="3b350-107">This article shows how to perform arithmetic operations on date and time values that belong to a particular time zone.</span></span> <span data-ttu-id="3b350-108">算术运算的结果将反映时区调整规则。</span><span class="sxs-lookup"><span data-stu-id="3b350-108">The results of the arithmetic operations will reflect the time zone's adjustment rules.</span></span>

## <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a><span data-ttu-id="3b350-109">将调整规则应用到日期和时间运算</span><span class="sxs-lookup"><span data-stu-id="3b350-109">To apply adjustment rules to date and time arithmetic</span></span>

1. <span data-ttu-id="3b350-110">采取措施将日期和时间值与其所属时区紧密耦合。</span><span class="sxs-lookup"><span data-stu-id="3b350-110">Implement some method of closely coupling a date and time value with the time zone to which it belongs.</span></span> <span data-ttu-id="3b350-111">例如声明同时包含日期和时间值及其时区的结构。</span><span class="sxs-lookup"><span data-stu-id="3b350-111">For example, declare a structure that includes both the date and time value and its time zone.</span></span> <span data-ttu-id="3b350-112">下方示例使用此方法链接 [DateTimeOffset](xref:System.DateTimeOffset) 值与其时区。</span><span class="sxs-lookup"><span data-stu-id="3b350-112">The following example uses this approach to link a [DateTimeOffset](xref:System.DateTimeOffset) value with its time zone.</span></span>

    ```csharp
    // Define a structure for DateTime values for internal use only
    internal struct TimeWithTimeZone
    {
    TimeZoneInfo TimeZone;
    DateTimeOffset Time;
    }
    ```

    ```vb
    ' Define a structure for DateTime values for internal use only
    Friend Structure TimeWithTimeZone
       Dim TimeZone As TimeZoneInfo
       Dim Time As Date
    End Structure
    ```
    
2. <span data-ttu-id="3b350-113">调用 [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) 方法，将时间转换为协调世界时 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="3b350-113">Convert a time to Coordinated Universal Time (UTC) by calling the [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method.</span></span>

3. <span data-ttu-id="3b350-114">对 UTC 时间执行算术运算。</span><span class="sxs-lookup"><span data-stu-id="3b350-114">Perform the arithmetic operation on the UTC time.</span></span>

4. <span data-ttu-id="3b350-115">调用 [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) 方法，将时间从 UTC 转换到与原始时间相关联的时区。</span><span class="sxs-lookup"><span data-stu-id="3b350-115">Convert the time from UTC to the original time's associated time zone by calling the [TimeZoneInfo.ConvertTime(DateTime, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method.</span></span> 

## <a name="example"></a><span data-ttu-id="3b350-116">示例</span><span class="sxs-lookup"><span data-stu-id="3b350-116">Example</span></span>

<span data-ttu-id="3b350-117">下方示例向中部标准时间 2008 年 3 月 9 日凌晨 1:30 添加了</span><span class="sxs-lookup"><span data-stu-id="3b350-117">The following example adds two hours and thirty minutes to March 9, 2008, at 1:30 A.M.</span></span> <span data-ttu-id="3b350-118">2 小时&30; 分钟。</span><span class="sxs-lookup"><span data-stu-id="3b350-118">Central Standard Time.</span></span> <span data-ttu-id="3b350-119">30 分钟后（即 2008 年 3 月 9 日凌晨 2:00）</span><span class="sxs-lookup"><span data-stu-id="3b350-119">The time zone's transition to daylight saving time occurs thirty minutes later, at 2:00 A.M.</span></span> <span data-ttu-id="3b350-120">会发生到夏时令的时区转换。</span><span class="sxs-lookup"><span data-stu-id="3b350-120">on March 9, 2008.</span></span> <span data-ttu-id="3b350-121">由于该示例遵从了上一部分中列出的四个步骤，因此它将最终时间正确地报告为 </span><span class="sxs-lookup"><span data-stu-id="3b350-121">Because the example follows the four steps listed in the previous section, it correctly reports the resulting time as 5:00 A.M.</span></span> <span data-ttu-id="3b350-122">2008 年 3 月 9 日凌晨 5:00。</span><span class="sxs-lookup"><span data-stu-id="3b350-122">on March 9, 2008.</span></span> 

```csharp
using System;

public struct TimeZoneTime
{
   public TimeZoneInfo TimeZone;
   public DateTimeOffset Time;

   public TimeZoneTime(TimeZoneInfo tz, DateTimeOffset time)
   {
      if (tz == null) 
         throw new ArgumentNullException("The time zone cannot be a null reference.");

      this.TimeZone = tz;
      this.Time = time;   
   }

   public TimeZoneTime AddTime(TimeSpan interval)
   {
      // Convert time to UTC
      DateTimeOffset utcTime = TimeZoneInfo.ConvertTime(this.Time, TimeZoneInfo.Utc);      
      // Add time interval to time
      utcTime = utcTime.Add(interval);
      // Convert time back to time in time zone
      return new TimeZoneTime(this.TimeZone, TimeZoneInfo.ConvertTime(utcTime, this.TimeZone));
   }
}

public class TimeArithmetic
{
   public const string tzName = "Central Standard Time";

   public static void Main()
   {
      try
      {
         TimeZoneTime cstTime1, cstTime2;

         TimeZoneInfo cst = TimeZoneInfo.FindSystemTimeZoneById(tzName);
         DateTime time1 = new DateTime(2008, 3, 9, 1, 30, 0);          
         TimeSpan twoAndAHalfHours = new TimeSpan(2, 30, 0);

         cstTime1 = new TimeZoneTime(cst, 
                        new DateTimeOffset(time1, cst.GetUtcOffset(time1)));
         cstTime2 = cstTime1.AddTime(twoAndAHalfHours);
         Console.WriteLine("{0} + {1} hours = {2}", cstTime1.Time, 
                                                    twoAndAHalfHours.ToString(),  
                                                    cstTime2.Time);
      }
      catch
      {
         Console.WriteLine("Unable to find {0}.", tzName);
      }
   }
}
```

```vb
Public Structure TimeZoneTime
   Public TimeZone As TimeZoneInfo
   Public Time As Date

   Public Sub New(tz As TimeZoneInfo, time As Date)
      If tz Is Nothing Then _
         Throw New ArgumentNullException("The time zone cannot be a null reference.")

      Me.TimeZone = tz
      Me.Time = time
   End Sub

   Public Function AddTime(interval As TimeSpan) As TimeZoneTime
      ' Convert time to UTC
      Dim utcTime As DateTime = TimeZoneInfo.ConvertTimeToUtc(Me.Time, _
                                                              Me.TimeZone)      
      ' Add time interval to time
      utcTime = utcTime.Add(interval)
      ' Convert time back to time in time zone
      Return New TimeZoneTime(Me.TimeZone, TimeZoneInfo.ConvertTime(utcTime, _
                              TimeZoneInfo.Utc, Me.TimeZone))
   End Function
End Structure

Module TimeArithmetic
   Public Const tzName As String = "Central Standard Time"

   Public Sub Main()
      Try
         Dim cstTime1, cstTime2 As TimeZoneTime

         Dim cst As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(tzName)
         Dim time1 As Date = #03/09/2008 1:30AM#
         Dim twoAndAHalfHours As New TimeSpan(2, 30, 0)

         cstTime1 = New TimeZoneTime(cst, time1)
         cstTime2 = cstTime1.AddTime(twoAndAHalfHours)

         Console.WriteLine("{0} + {1} hours = {2}", cstTime1.Time, _
                                                    twoAndAHalfHours.ToString(), _ 
                                                    cstTime2.Time)  
      Catch
         Console.WriteLine("Unable to find {0}.", tzName)
      End Try   
   End Sub   
End Module
```

<span data-ttu-id="3b350-123">请注意，如果未先将 [DateTimeOffset](xref:System.DateTimeOffset) 值转换为 UTC 就进行相加，那么结果将反映正确的时间点，但其时差无法反映指定时区在当时的时差。</span><span class="sxs-lookup"><span data-stu-id="3b350-123">Note that if this addition is simply performed on the [DateTimeOffset](xref:System.DateTimeOffset) value without first converting it to UTC, the result reflects the correct point in time but its offset does not reflect that of the designated time zone for that time.</span></span> 

<span data-ttu-id="3b350-124">[DateTimeOffset](xref:System.DateTimeOffset) 值将与其所属的任何时区解除关联。</span><span class="sxs-lookup"><span data-stu-id="3b350-124">[DateTimeOffset](xref:System.DateTimeOffset) values are disassociated from any time zone to which they might belong.</span></span> <span data-ttu-id="3b350-125">只有能够立即识别任意日期和时间所属的时区，才能在执行日期和时间运算时自动应用时区调整规则。</span><span class="sxs-lookup"><span data-stu-id="3b350-125">To perform date and time arithmetic in a way that automatically applies a time zone's adjustment rules, the time zone to which any date and time value belongs must be immediately identifiable.</span></span> <span data-ttu-id="3b350-126">这意味着，日期和时间及其关联时区必须紧密耦合。</span><span class="sxs-lookup"><span data-stu-id="3b350-126">This means that a date and time and its associated time zone must be tightly coupled.</span></span> <span data-ttu-id="3b350-127">可通过方法进行此操作，其中包括：</span><span class="sxs-lookup"><span data-stu-id="3b350-127">There are several ways to do this, which include the following:</span></span>

* <span data-ttu-id="3b350-128">假设应用程序中使用的所有时间均属于某个特定时区。</span><span class="sxs-lookup"><span data-stu-id="3b350-128">Assume that all times used in an application belong to a particular time zone.</span></span> <span data-ttu-id="3b350-129">尽管在某些情况下适用，但此方法的灵活性和可移植性有限。</span><span class="sxs-lookup"><span data-stu-id="3b350-129">Although appropriate in some cases, this approach offers limited flexibility and possibly limited portability.</span></span>

* <span data-ttu-id="3b350-130">在类型字段中包括日期和时间及其关联时区，定义将二者紧密耦合的类型。</span><span class="sxs-lookup"><span data-stu-id="3b350-130">Define a type that tightly couples a date and time with its associated time zone by including both as fields of the type.</span></span> <span data-ttu-id="3b350-131">代码示例中使用了此方法，定义了将日期和时间以及时区存储在两个成员字段中的结构。</span><span class="sxs-lookup"><span data-stu-id="3b350-131">This approach is used in the code example, which defines a structure to store the date and time and the time zone in two member fields.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b350-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b350-132">See Also</span></span>

[<span data-ttu-id="3b350-133">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="3b350-133">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="3b350-134">使用日期和时间执行算术运算</span><span class="sxs-lookup"><span data-stu-id="3b350-134">Performing arithmetic operations with dates and times</span></span>](performing-arithmetic-operations.md)


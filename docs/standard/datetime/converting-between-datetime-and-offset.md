---
title: "在 DateTime 与 DateTimeOffset 之间进行转换"
description: "在 DateTime 与 DateTimeOffset 之间进行转换"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: fab3af5b-5d0f-4384-a40a-1b5d99b30dd1
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 2ba70e9ea39148d040bdb46d5e00ea50dcbb8980
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="converting-between-datetime-and-datetimeoffset"></a><span data-ttu-id="8b4f0-104">在 DateTime 与 DateTimeOffset 之间进行转换</span><span class="sxs-lookup"><span data-stu-id="8b4f0-104">Converting between DateTime and DateTimeOffset</span></span>

<span data-ttu-id="8b4f0-105">虽然与 [System.DateTime](xref:System.DateTime) 结构相比，[System.DateTimeOffset](xref:System.DateTimeOffset) 结构提供的时区感知度更高，但在方法调用中更常使用 [DateTime](xref:System.DateTime) 参数。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-105">Although the [System.DateTimeOffset](xref:System.DateTimeOffset) structure provides a greater degree of time zone awareness than the [System.DateTime](xref:System.DateTime) structure, [DateTime](xref:System.DateTime) parameters are used more commonly in method calls.</span></span> <span data-ttu-id="8b4f0-106">因此，[DateTimeOffset](xref:System.DateTimeOffset) 值和[DateTime](xref:System.DateTime) 值之间的相互转换能力非常重要。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-106">Because of this, the ability to convert [DateTimeOffset](xref:System.DateTimeOffset) values to [DateTime](xref:System.DateTime) values and vice versa is particularly important.</span></span> <span data-ttu-id="8b4f0-107">本文演示如何以保留尽可能多的时区信息的方式执行这些转换。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-107">This article shows how to perform these conversions in a way that preserves as much time zone information as possible.</span></span>

> [!NOTE]
> <span data-ttu-id="8b4f0-108">[DateTime](xref:System.DateTime) 和 [DateTimeOffset](xref:System.DateTimeOffset) 类型在表示时区中的时间时都具有某些限制。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-108">Both the [DateTime](xref:System.DateTime) and the [DateTimeOffset](xref:System.DateTimeOffset) types have some limitations when representing times in time zones.</span></span> <span data-ttu-id="8b4f0-109">通过其 [Kind](xref:System.DateTime.Kind) 属性，[DateTime](xref:System.DateTime) 可以仅反映协调世界时 (UTC) 和系统的本地时区。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-109">With its [Kind](xref:System.DateTime.Kind) property, [DateTime](xref:System.DateTime) is able to reflect only Coordinated Universal Time (UTC) and the system's local time zone.</span></span> <span data-ttu-id="8b4f0-110">[DateTimeOffset](xref:System.DateTimeOffset) 反映相对于 UTC 的时间偏移量，但不能反映该偏移量所属的实际时区。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-110">[DateTimeOffset](xref:System.DateTimeOffset) reflects a time's offset from UTC, but it does not reflect the actual time zone to which that offset belongs.</span></span> <span data-ttu-id="8b4f0-111">有关时间值和时区支持的详细信息，请参阅[在 DateTime、DateTimeOffset、TimeSpan 和 TimeZoneInfo 之间进行选择](choosing-between-datetime.md)。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-111">For details about time values and support for time zones, see [Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](choosing-between-datetime.md).</span></span>

## <a name="conversions-from-datetime-to-datetimeoffset"></a><span data-ttu-id="8b4f0-112">从 DateTime 转换为 DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="8b4f0-112">Conversions from DateTime to DateTimeOffset</span></span>

<span data-ttu-id="8b4f0-113">[DateTimeOffset](xref:System.DateTimeOffset) 结构提供两种适用于大多数转换的等效方法来执行从[DateTime](xref:System.DateTime) 到 [DateTimeOffset](xref:System.DateTimeOffset) 的转换：</span><span class="sxs-lookup"><span data-stu-id="8b4f0-113">The [DateTimeOffset](xref:System.DateTimeOffset) structure provides two equivalent ways to perform [DateTime](xref:System.DateTime) to [DateTimeOffset](xref:System.DateTimeOffset) conversion that are suitable for most conversions:</span></span>

* <span data-ttu-id="8b4f0-114">[DateTimeOffset(DateTime)](xref:System.DateTimeOffset) 构造函数，它基于 [DateTime](xref:System.DateTime) 值创建新 [DateTimeOffset](xref:System.DateTimeOffset) 对象。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-114">The [DateTimeOffset(DateTime)](xref:System.DateTimeOffset) constructor, which creates a new [DateTimeOffset](xref:System.DateTimeOffset) object based on a [DateTime](xref:System.DateTime) value.</span></span>

* <span data-ttu-id="8b4f0-115">隐式转换运算符，允许将 [DateTime](xref:System.DateTime) 值分配给 [DateTimeOffset](xref:System.DateTimeOffset) 对象。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-115">The implicit conversion operator, which allows you to assign a [DateTime](xref:System.DateTime) value to a [DateTimeOffset](xref:System.DateTimeOffset) object.</span></span>

<span data-ttu-id="8b4f0-116">对于 UTC 和本地 [DateTime](xref:System.DateTime) 值，所生成 [DateTimeOffset](xref:System.DateTimeOffset) 值的 [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) 属性可准确反映 UTC 或本地时区偏移量。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-116">For UTC and local [DateTime](xref:System.DateTime) values, the [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) property of the resulting [DateTimeOffset](xref:System.DateTimeOffset) value accurately reflects the UTC or local time zone offset.</span></span> <span data-ttu-id="8b4f0-117">例如，以下代码将 UTC 时间转换为其等效的 [DateTimeOffset](xref:System.DateTimeOffset) 值。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-117">For example, the following code converts a UTC time to its equivalent [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> 

```csharp
DateTime utcTime1 = new DateTime(2008, 6, 19, 7, 0, 0);
utcTime1 = DateTime.SpecifyKind(utcTime1, DateTimeKind.Utc);
DateTimeOffset utcTime2 = utcTime1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  utcTime1, 
                  utcTime1.Kind.ToString(), 
                  utcTime2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Utc to a DateTimeOffset value of 6/19/2008 7:00:00 AM +00:00
```

```vb
Dim utcTime1 As Date = Date.SpecifyKind(#06/19/2008 7:00AM#, _
                                        DateTimeKind.Utc)
Dim utcTime2 As DateTimeOffset = utcTime1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  utcTime1, _
                  utcTime1.Kind.ToString(), _
                  utcTime2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Utc to a DateTimeOffset value of 6/19/2008 7:00:00 AM  +00:00
```

<span data-ttu-id="8b4f0-118">在本例中，`utcTime2` 变量的偏移量为 00:00。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-118">In this case, the offset of the `utcTime2` variable is 00:00.</span></span> <span data-ttu-id="8b4f0-119">同样，以下代码将本地时间转换为其等效的 [DateTimeOffset](xref:System.DateTimeOffset) 值。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-119">Similarly, the following code converts a local time to its equivalent [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

```csharp
DateTime localTime1 = new DateTime(2008, 6, 19, 7, 0, 0);
localTime1 = DateTime.SpecifyKind(localTime1, DateTimeKind.Local);
DateTimeOffset localTime2 = localTime1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  localTime1, 
                  localTime1.Kind.ToString(), 
                  localTime2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Local to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

```vb
Dim localTime1 As Date = Date.SpecifyKind(#06/19/2008 7:00AM#, DateTimeKind.Local)
Dim localTime2 As DateTimeOffset = localTime1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  localTime1, _
                  localTime1.Kind.ToString(), _
                  localTime2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Local to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

<span data-ttu-id="8b4f0-120">但是，对于 [Kind](xref:System.DateTime.Kind) 属性为 [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) 的 [DateTime](xref:System.DateTime) 值，这两种转换方法会生成 [DateTimeOffset](xref:System.DateTimeOffset) 值，其偏移量为本地时区的偏移量。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-120">However, for [DateTime](xref:System.DateTime) values whose [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), these two conversion methods produce a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset is that of the local time zone.</span></span> <span data-ttu-id="8b4f0-121">以下示例对此进行了演示，该示例在美国太平洋标准时区运行。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-121">This is shown in the following example, which is run in the U.S. Pacific Standard Time zone.</span></span>

```csharp
DateTime time1 = new DateTime(2008, 6, 19, 7, 0, 0);  // Kind is DateTimeKind.Unspecified
DateTimeOffset time2 = time1;
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", 
                  time1, 
                  time1.Kind.ToString(), 
                  time2);
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

```vb
Dim time1 As Date = #06/19/2008 7:00AM#      ' Kind is DateTimeKind.Unspecified
Dim time2 As DateTimeOffset = time1
Console.WriteLine("Converted {0} {1} to a DateTimeOffset value of {2}", _
                  time1, _
                  time1.Kind.ToString(), _
                  time2)
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTimeOffset value of 6/19/2008 7:00:00 AM -07:00
```

<span data-ttu-id="8b4f0-122">如果 [DateTime](xref:System.DateTime) 值所反映的不是本地时间或 UTC，可以调用已重载的 [DateTimeOffset(DateTime, TimeSpan)](xref:System.DateTimeOffset) 构造函数将其转换为 [DateTimeOffset](xref:System.DateTimeOffset) 值，并保留其时区信息。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-122">If the [DateTime](xref:System.DateTime) value reflects the date and time in something other than the local time zone or UTC, you can convert it to a [DateTimeOffset](xref:System.DateTimeOffset) value and preserve its time zone information by calling the overloaded [DateTimeOffset(DateTime, TimeSpan)](xref:System.DateTimeOffset) constructor.</span></span> <span data-ttu-id="8b4f0-123">例如，以下示例实例化反映中部标准时间的 [DateTimeOffset](xref:System.DateTimeOffset) 对象。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-123">For example, the following example instantiates a [DateTimeOffset](xref:System.DateTimeOffset) object that reflects Central Standard Time.</span></span>

```csharp
DateTime time1 = new DateTime(2008, 6, 19, 7, 0, 0);     // Kind is DateTimeKind.Unspecified
try
{
   DateTimeOffset time2 = new DateTimeOffset(time1, 
                  TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(time1)); 
   Console.WriteLine("Converted {0} {1} to a DateTime value of {2}", 
                     time1, 
                     time1.Kind.ToString(), 
                     time2);
}
// Handle exception if time zone is not defined in registry
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to identify target time zone for conversion.");
}
// This example displays the following output to the console:
//    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTime value of 6/19/2008 7:00:00 AM -05:00
```

```vb
Dim time1 As Date = #06/19/2008 7:00AM#      ' Kind is DateTimeKind.Unspecified
Try
   Dim time2 As New DateTimeOffset(time1, _
                    TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(time1)) 
   Console.WriteLine("Converted {0} {1} to a DateTime value of {2}", _
                     time1, _
                     time1.Kind.ToString(), _
                     time2)
' Handle exception if time zone is not defined in registry
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to identify target time zone for conversion.")
End Try
' This example displays the following output to the console:
'    Converted 6/19/2008 7:00:00 AM Unspecified to a DateTime value of 6/19/2008 7:00:00 AM -05:00
```

<span data-ttu-id="8b4f0-124">应调用该时间所对应时区的 [TimeZoneInfo.GetUtcOffset(DateTime)](xref:System.TimeZoneInfo) 方法检索此构造函数重载的第二个参数，即表示相对于 UCT 的时间偏移量的 [System.TimeSpan](xref:System.TimeSpan) 对象。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-124">The second parameter to this constructor overload, a [System.TimeSpan](xref:System.TimeSpan) object that represents the time's offset from UTC, should be retrieved by calling the [TimeZoneInfo.GetUtcOffset(DateTime)](xref:System.TimeZoneInfo) method of the time's corresponding time zone.</span></span> <span data-ttu-id="8b4f0-125">该方法的单个参数是 [DateTime](xref:System.DateTime) 值，表示要转换的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-125">The method's single parameter is the [DateTime](xref:System.DateTime) value that represents the date and time to be converted.</span></span> <span data-ttu-id="8b4f0-126">如果时区支持夏令时，此参数允许方法为该特定日期和时间确定适当偏移量。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-126">If the time zone supports daylight saving time, this parameter allows the method to determine the appropriate offset for that particular date and time.</span></span>

## <a name="conversions-from-datetimeoffset-to-datetime"></a><span data-ttu-id="8b4f0-127">从 DateTimeOffset 转换为 DateTime</span><span class="sxs-lookup"><span data-stu-id="8b4f0-127">Conversions from DateTimeOffset to DateTime</span></span>

<span data-ttu-id="8b4f0-128">[DateTime](xref:System.DateTime) 属性常用于执行从 [DateTimeOffset](xref:System.DateTimeOffset) 到 [DateTime](xref:System.DateTime) 的转换。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-128">The [DateTime](xref:System.DateTime) property is most commonly used to perform [DateTimeOffset](xref:System.DateTimeOffset) to [DateTime](xref:System.DateTime) conversion.</span></span> <span data-ttu-id="8b4f0-129">但是，它将返回 [Kind](xref:System.DateTime.Kind) 属性为 [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) 的 [DateTime](xref:System.DateTime) 值，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-129">However, it returns a [DateTime](xref:System.DateTime) value whose [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), as the following example illustrates.</span></span> 

```csharp
DateTime baseTime = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset sourceTime;
DateTime targetTime;

// Convert UTC to DateTime value
sourceTime = new DateTimeOffset(baseTime, TimeSpan.Zero);
targetTime = sourceTime.DateTime;
Console.WriteLine("{0} converts to {1} {2}", 
                  sourceTime, 
                  targetTime, 
                  targetTime.Kind.ToString());

// Convert local time to DateTime value
sourceTime = new DateTimeOffset(baseTime, 
                                TimeZoneInfo.Local.GetUtcOffset(baseTime));
targetTime = sourceTime.DateTime;
Console.WriteLine("{0} converts to {1} {2}", 
                  sourceTime, 
                  targetTime, 
                  targetTime.Kind.ToString());

// Convert Central Standard Time to a DateTime value
try
{
   TimeSpan offset = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(baseTime);
   sourceTime = new DateTimeOffset(baseTime, offset);
   targetTime = sourceTime.DateTime;
   Console.WriteLine("{0} converts to {1} {2}", 
                     sourceTime, 
                     targetTime, 
                     targetTime.Kind.ToString());
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to create DateTimeOffset based on U.S. Central Standard Time.");
} 
// This example displays the following output to the console:
//    6/19/2008 7:00:00 AM +00:00 converts to 6/19/2008 7:00:00 AM Unspecified
//    6/19/2008 7:00:00 AM -07:00 converts to 6/19/2008 7:00:00 AM Unspecified
//    6/19/2008 7:00:00 AM -05:00 converts to 6/19/2008 7:00:00 AM Unspecified 
```

```vb
Const baseTime As Date = #06/19/2008 7:00AM#
Dim sourceTime As DateTimeOffset
Dim targetTime As Date

' Convert UTC to DateTime value
sourceTime = New DateTimeOffset(baseTime, TimeSpan.Zero)
targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())

' Convert local time to DateTime value
sourceTime = New DateTimeOffset(baseTime, _
                                TimeZoneInfo.Local.GetUtcOffset(baseTime))
targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())

' Convert Central Standard Time to a DateTime value
Try
   Dim offset As TimeSpan = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(baseTime)
   sourceTime = New DateTimeOffset(baseTime, offset)
   targetTime = sourceTime.DateTime
Console.WriteLine("{0} converts to {1} {2}", _
                  sourceTime, _
                  targetTime, _
                  targetTime.Kind.ToString())
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to create DateTimeOffset based on U.S. Central Standard Time.")
End Try 
' This example displays the following output to the console:
'    6/19/2008 7:00:00 AM +00:00 converts to 6/19/2008 7:00:00 AM Unspecified
'    6/19/2008 7:00:00 AM -07:00 converts to 6/19/2008 7:00:00 AM Unspecified
'    6/19/2008 7:00:00 AM -05:00 converts to 6/19/2008 7:00:00 AM Unspecified 
```

<span data-ttu-id="8b4f0-130">这意味着，使用 [DateTime](xref:System.DateTime) 属性时，转换后会丢失任何有关 [DateTimeOffset](xref:System.DateTimeOffset) 值与 UTC 的关系信息。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-130">This means that any information about the [DateTimeOffset](xref:System.DateTimeOffset) value's relationship to UTC is lost by the conversion when the [DateTime](xref:System.DateTime) property is used.</span></span> <span data-ttu-id="8b4f0-131">这会影响对应于 UTC 时间或系统本地时间的 [DateTimeOffset](xref:System.DateTimeOffset) 值，因为 [DateTime](xref:System.DateTime) 结构仅会在其 [Kind](xref:System.DateTime.Kind) 属性中反映这两个时区。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-131">This affects [DateTimeOffset](xref:System.DateTimeOffset) values that correspond to UTC time or to the system's local time because the [DateTime](xref:System.DateTime) structure reflects only those two time zones in its [Kind](xref:System.DateTime.Kind) property.</span></span>

<span data-ttu-id="8b4f0-132">若要在将 [DateTimeOffset](xref:System.DateTimeOffset) 转换为 [DateTime](xref:System.DateTime) 值时保留尽可能多的时区信息，可以使用 [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) 和 [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) 属性。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-132">To preserve as much time zone information as possible when converting a [DateTimeOffset](xref:System.DateTimeOffset) to a [DateTime](xref:System.DateTime) value, you can use the [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) and [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) properties.</span></span> 

## <a name="converting-a-utc-time"></a><span data-ttu-id="8b4f0-133">转换 UTC 时间</span><span class="sxs-lookup"><span data-stu-id="8b4f0-133">Converting a UTC Time</span></span>

<span data-ttu-id="8b4f0-134">若要指示转换的 [DateTime](xref:System.DateTime) 值是 UTC 时间，可以检索 [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-134">To indicate that a converted [DateTime](xref:System.DateTime) value is the UTC time, you can retrieve the value of the [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) property.</span></span> <span data-ttu-id="8b4f0-135">它与 [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) 属性有所不同，表现在以下两个方面：</span><span class="sxs-lookup"><span data-stu-id="8b4f0-135">It differs from the [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) property in two ways:</span></span>

* <span data-ttu-id="8b4f0-136">它将返回 [DateTime](xref:System.DateTime) 值，其 [Kind](xref:System.DateTime.Kind) 属性为 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-136">It returns a [DateTime](xref:System.DateTime) value whose [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

* <span data-ttu-id="8b4f0-137">如果 [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) 属性值不等于 [TimeSpan.Zero](xref:System.TimeSpan.Zero)，则会将时间转换为 UTC。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-137">If the [DateTimeOffset.Offset](xref:System.DateTimeOffset.Offset) property value does not equal [TimeSpan.Zero](xref:System.TimeSpan.Zero), it converts the time to UTC.</span></span>

> [!NOTE]
> <span data-ttu-id="8b4f0-138">如果应用程序需要已转换的 [DateTime](xref:System.DateTime) 值明确标识单个时间点，应考虑使用 [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) 属性来处理所有从 [DateTimeOffset](xref:System.DateTimeOffset) 到 [DateTime](xref:System.DateTime) 的转换。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-138">If your application requires that converted [DateTime](xref:System.DateTime) values unambiguously identify a single point in time, you should consider using the [DateTimeOffset.UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) property to handle all [DateTimeOffset](xref:System.DateTimeOffset) to [DateTime](xref:System.DateTime) conversions.</span></span>

<span data-ttu-id="8b4f0-139">以下代码使用 [UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) 属性来转换 [DateTimeOffset](xref:System.DateTimeOffset) 值，其偏移量等于 [DateTime](xref:System.DateTime) 值的[TimeSpan.Zero](xref:System.TimeSpan.Zero)。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-139">The following code uses the [UtcDateTime](xref:System.DateTimeOffset.UtcDateTime) property to convert a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset equals [TimeSpan.Zero](xref:System.TimeSpan.Zero) to a [DateTime](xref:System.DateTime) value.</span></span>

```csharp
DateTimeOffset utcTime1 = new DateTimeOffset(2008, 6, 19, 7, 0, 0, TimeSpan.Zero);
DateTime utcTime2 = utcTime1.UtcDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime1, 
                  utcTime2, 
                  utcTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
```

```vb
Dim utcTime1 As New DateTimeOffset(#06/19/2008 7:00AM#, TimeSpan.Zero)
Dim utcTime2 As Date = utcTime1.UtcDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime1, _
                  utcTime2, _
                  utcTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
```

<span data-ttu-id="8b4f0-140">以下代码使用 UtcDateTime 属性同时执行时区转换和 [DateTimeOffset](xref:System.DateTimeOffset) 值的类型转换。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-140">The following code uses the UtcDateTime property to perform both a time zone conversion and a type conversion on a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span>

```csharp
DateTimeOffset originalTime = new DateTimeOffset(2008, 6, 19, 7, 0, 0, new TimeSpan(5, 0, 0));
DateTime utcTime = originalTime.UtcDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalTime, 
                  utcTime, 
                  utcTime.Kind.ToString());
// The example displays the following output to the console:
//       6/19/2008 7:00:00 AM +05:00 converted to 6/19/2008 2:00:00 AM Utc
```

```vb
Dim originalTime As New DateTimeOffset(#6/19/2008 7:00AM#, _
                                       New TimeSpan(5, 0, 0))
Dim utcTime As Date = originalTime.UtcDateTime
Console.WriteLine("{0} converted to {1} {2}", _ 
                  originalTime, _
                  utcTime, _
                  utcTime.Kind.ToString())
' The example displays the following output to the console:
'       6/19/2008 7:00:00 AM +05:00 converted to 6/19/2008 2:00:00 AM Utc
```

## <a name="converting-a-local-time"></a><span data-ttu-id="8b4f0-141">转换本地时间</span><span class="sxs-lookup"><span data-stu-id="8b4f0-141">Converting a Local Time</span></span>

<span data-ttu-id="8b4f0-142">若要指示 [DateTimeOffset](xref:System.DateTimeOffset) 值表示本地时间，可以将 [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) 属性返回的 [DateTime](xref:System.DateTime) 值传递给静态 [DateTime.SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) 方法。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-142">To indicate that a [DateTimeOffset](xref:System.DateTimeOffset) value represents the local time, you can pass the [DateTime](xref:System.DateTime) value returned by the [DateTimeOffset.DateTime](xref:System.DateTimeOffset.DateTime) property to the static [DateTime.SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method.</span></span> <span data-ttu-id="8b4f0-143">该方法将传递给它的日期和时间作为其首个参数返回，但会将 [Kind](xref:System.DateTime.Kind) 属性设置为其第二个参数指定的值。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-143">The method returns the date and time passed to it as its first parameter, but sets the [Kind](xref:System.DateTime.Kind) property to the value specified by its second parameter.</span></span> <span data-ttu-id="8b4f0-144">以下代码在转换 [DateTimeOffset](xref:System.DateTimeOffset) 值（其偏移量对应于本地时区的偏移量）时使用 [SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) 方法。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-144">The following code uses the [SpecifyKind(DateTime, DateTimeKind)](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method when converting a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset corresponds to that of the local time zone.</span></span>

```csharp
DateTime sourceDate = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset utcTime1 = new DateTimeOffset(sourceDate, 
                          TimeZoneInfo.Local.GetUtcOffset(sourceDate));
DateTime utcTime2 = utcTime1.DateTime;
if (utcTime1.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(utcTime1.DateTime))) 
   utcTime2 = DateTime.SpecifyKind(utcTime2, DateTimeKind.Local);

Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime1, 
                  utcTime2, 
                  utcTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

```vb
Dim sourceDate As Date = #06/19/2008 7:00AM#
Dim utcTime1 As New DateTimeOffset(sourceDate, _
                                   TimeZoneInfo.Local.GetUtcOffset(sourceDate))
Dim utcTime2 As Date = utcTime1.DateTime
If utcTime1.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(utcTime1.DateTime)) Then
   utcTime2 = DateTime.SpecifyKind(utcTime2, DateTimeKind.Local)
End If   
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime1, _
                  utcTime2, _
                  utcTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

<span data-ttu-id="8b4f0-145">此外，还可以使用 [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) 属性将 [DateTimeOffset](xref:System.DateTimeOffset) 值转换为本地 [DateTime](xref:System.DateTime) 值。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-145">You can also use the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property to convert a [DateTimeOffset](xref:System.DateTimeOffset) value to a local [DateTime](xref:System.DateTime) value.</span></span> <span data-ttu-id="8b4f0-146">返回的 [DateTime](xref:System.DateTime) 值的 [Kind](xref:System.DateTime.Kind) 属性为 [DateTimeKind.Local](xref:System.DateTimeKind.Local)。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-146">The [Kind](xref:System.DateTime.Kind) property of the returned [DateTime](xref:System.DateTime) value is [DateTimeKind.Local](xref:System.DateTimeKind.Local).</span></span> <span data-ttu-id="8b4f0-147">以下代码在转换 [DateTimeOffset](xref:System.DateTimeOffset) 值（其偏移量对应于本地时区的偏移量）时使用 [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) 属性。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-147">The following code uses the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property when converting a [DateTimeOffset](xref:System.DateTimeOffset) value whose offset corresponds to that of the local time zone.</span></span>

```csharp
DateTime sourceDate = new DateTime(2008, 6, 19, 7, 0, 0);
DateTimeOffset localTime1 = new DateTimeOffset(sourceDate, 
                          TimeZoneInfo.Local.GetUtcOffset(sourceDate));
DateTime localTime2 = localTime1.LocalDateTime;

Console.WriteLine("{0} converted to {1} {2}", 
                  localTime1, 
                  localTime2, 
                  localTime2.Kind.ToString());
// The example displays the following output to the console:
//   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
```

```vb
Dim sourceDate As Date = #06/19/2008 7:00AM#
Dim localTime1 As New DateTimeOffset(sourceDate, _
                                   TimeZoneInfo.Local.GetUtcOffset(sourceDate))
Dim localTime2 As Date = localTime1.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  localTime1, _
                  localTime2, _
                  localTime2.Kind.ToString())
' The example displays the following output to the console:
'   6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local 
```

<span data-ttu-id="8b4f0-148">使用 [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) 属性检索 [DateTime](xref:System.DateTime) 值时，该属性的 `get` 访问器会先将 [DateTimeOffset](xref:System.DateTimeOffset) 值转换为 UTC，然后通过调用 [DateTimeOffset.ToLocalTime](xref:System.DateTimeOffset) 方法将其转换为本地时间。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-148">When you retrieve a [DateTime](xref:System.DateTime) value using the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property, the property's `get` accessor first converts the [DateTimeOffset](xref:System.DateTimeOffset) value to UTC, then converts it to local time by calling the [DateTimeOffset.ToLocalTime](xref:System.DateTimeOffset) method.</span></span> <span data-ttu-id="8b4f0-149">这意味着，可以从 [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) 属性检索值，同时执行时区转换和类型转换。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-149">This means that you can retrieve a value from the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property to perform a time zone conversion at the same time that you perform a type conversion.</span></span> <span data-ttu-id="8b4f0-150">还意味着在执行转换期间应用本地时区的调整规则。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-150">It also means that the local time zone's adjustment rules are applied in performing the conversion.</span></span> <span data-ttu-id="8b4f0-151">以下代码说明了如何使用 [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) 属性同时执行类型和时区转换。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-151">The following code illustrates the use of the [DateTimeOffset.LocalDateTime](xref:System.DateTimeOffset.LocalDateTime) property to perform both a type and a time zone conversion.</span></span>

```csharp
DateTimeOffset originalDate;
DateTime localDate;

// Convert time originating in a different time zone
originalDate = new DateTimeOffset(2008, 6, 18, 7, 0, 0, 
                                  new TimeSpan(-5, 0, 0));
localDate = originalDate.LocalDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalDate, 
                  localDate, 
                  localDate.Kind.ToString());
// Convert time originating in a different time zone 
// so local time zone's adjustment rules are applied
originalDate = new DateTimeOffset(2007, 11, 4, 4, 0, 0, 
                                  new TimeSpan(-5, 0, 0));
localDate = originalDate.LocalDateTime;
Console.WriteLine("{0} converted to {1} {2}", 
                  originalDate, 
                  localDate, 
                  localDate.Kind.ToString());
// The example displays the following output to the console:
//       6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 5:00:00 AM Local
//       11/4/2007 4:00:00 AM -05:00 converted to 11/4/2007 1:00:00 AM Local
```

```vb
Dim originalDate As DateTimeOffset
Dim localDate As Date

' Convert time originating in a different time zone
originalDate = New DateTimeOffset(#06/19/2008 7:00AM#, _
                                  New TimeSpan(-5, 0, 0))
localDate = originalDate.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  originalDate, _
                  localDate, _
                  localDate.Kind.ToString())
' Convert time originating in a different time zone 
' so local time zone's adjustment rules are applied
originalDate = New DateTimeOffset(#11/04/2007 4:00AM#, _
                                  New TimeSpan(-5, 0, 0))
localDate = originalDate.LocalDateTime
Console.WriteLine("{0} converted to {1} {2}", _
                  originalDate, _
                  localDate, _
                  localDate.Kind.ToString())
' The example displays the following output to the console:
'       6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 5:00:00 AM Local
'       11/4/2007 4:00:00 AM -05:00 converted to 11/4/2007 1:00:00 AM Local
```

## <a name="a-general-purpose-conversion-method"></a><span data-ttu-id="8b4f0-152">通用转换方法</span><span class="sxs-lookup"><span data-stu-id="8b4f0-152">A General-Purpose Conversion Method</span></span>

<span data-ttu-id="8b4f0-153">以下示例定义名为 `ConvertFromDateTimeOffset` 的方法，该方法可将 [DateTimeOffset](xref:System.DateTimeOffset) 值转换为 [DateTime](xref:System.DateTime) 值。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-153">The following example defines a method named `ConvertFromDateTimeOffset` that converts [DateTimeOffset](xref:System.DateTimeOffset) values to [DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="8b4f0-154">它可根据其偏移量确定 [DateTimeOffset](xref:System.DateTimeOffset) 值是 UTC 时间，还是本地时间或其他时间，并定义返回的日期和时间值相应的 [Kind](xref:System.DateTime.Kind) 属性。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-154">Based on its offset, it determines whether the [DateTimeOffset](xref:System.DateTimeOffset) value is a UTC time, a local time, or some other time, and defines the returned date and time value's [Kind](xref:System.DateTime.Kind) property accordingly.</span></span> 

```csharp
static DateTime ConvertFromDateTimeOffset(DateTimeOffset dateTime)
{
   if (dateTime.Offset.Equals(TimeSpan.Zero))
      return dateTime.UtcDateTime;
   else if (dateTime.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(dateTime.DateTime)))
      return DateTime.SpecifyKind(dateTime.DateTime, DateTimeKind.Local);
   else
      return dateTime.DateTime;   
}
```

```vb
Function ConvertFromDateTimeOffset(dateTime As DateTimeOffset) As Date
   If dateTime.Offset.Equals(TimeSpan.Zero) Then
      Return dateTime.UtcDateTime
   ElseIf dateTime.Offset.Equals(TimeZoneInfo.Local.GetUtcOffset(dateTime.DateTime))
      Return Date.SpecifyKind(dateTime.DateTime, DateTimeKind.Local)
   Else
      Return dateTime.DateTime   
   End If
```

<span data-ttu-id="8b4f0-155">下面的示例调用 `ConvertFromDateTimeOffset` 方法来转换 [DateTimeOffset](xref:System.DateTimeOffset) 值，这些值表示 UTC 时间、本地时间和美国中部标准时区的时间。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-155">The follow example calls the `ConvertFromDateTimeOffset` method to convert [DateTimeOffset](xref:System.DateTimeOffset) values that represent a UTC time, a local time, and a time in the U.S. Central Standard Time zone.</span></span>

```csharp
DateTime timeComponent = new DateTime(2008, 6, 19, 7, 0, 0);
DateTime returnedDate; 

// Convert UTC time
DateTimeOffset utcTime = new DateTimeOffset(timeComponent, TimeSpan.Zero);
returnedDate = ConvertFromDateTimeOffset(utcTime); 
Console.WriteLine("{0} converted to {1} {2}", 
                  utcTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());

// Convert local time
DateTimeOffset localTime = new DateTimeOffset(timeComponent, 
                           TimeZoneInfo.Local.GetUtcOffset(timeComponent)); 
returnedDate = ConvertFromDateTimeOffset(localTime);                                          
Console.WriteLine("{0} converted to {1} {2}", 
                  localTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());

// Convert Central Standard Time
DateTimeOffset cstTime = new DateTimeOffset(timeComponent, 
               TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(timeComponent));
returnedDate = ConvertFromDateTimeOffset(cstTime);
Console.WriteLine("{0} converted to {1} {2}", 
                  cstTime, 
                  returnedDate, 
                  returnedDate.Kind.ToString());
// The example displays the following output to the console:
//    6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
//    6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
//    6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 7:00:00 AM Unspecified
```

```vb
Dim timeComponent As Date = #06/19/2008 7:00AM#
Dim returnedDate As Date 

' Convert UTC time
Dim utcTime As New DateTimeOffset(timeComponent, TimeSpan.Zero)
returnedDate = ConvertFromDateTimeOffset(utcTime) 
Console.WriteLine("{0} converted to {1} {2}", _
                  utcTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())

' Convert local time
Dim localTime As New DateTimeOffset(timeComponent, _
                                    TimeZoneInfo.Local.GetUtcOffset(timeComponent)) 
returnedDate = ConvertFromDateTimeOffset(localTime)                                                                  
Console.WriteLine("{0} converted to {1} {2}", _
                  localTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())

' Convert Central Standard Time
Dim cstTime As New DateTimeOffset(timeComponent, _
               TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time").GetUtcOffset(timeComponent))
returnedDate = ConvertFromDateTimeOffset(cstTime)                                                                  
Console.WriteLine("{0} converted to {1} {2}", _
                  cstTime, _
                  returnedDate, _
                  returnedDate.Kind.ToString())
' The example displays the following output to the console:
'    6/19/2008 7:00:00 AM +00:00 converted to 6/19/2008 7:00:00 AM Utc
'    6/19/2008 7:00:00 AM -07:00 converted to 6/19/2008 7:00:00 AM Local
'    6/19/2008 7:00:00 AM -05:00 converted to 6/19/2008 7:00:00 AM Unspecified
```

<span data-ttu-id="8b4f0-156">请注意，此代码根据应用程序及其日期和时间值的来源所作的两种假设不一定始终有效：</span><span class="sxs-lookup"><span data-stu-id="8b4f0-156">Note that this code makes two assumptions that, depending on the application and the source of its date and time values, may not always be valid:</span></span>

* <span data-ttu-id="8b4f0-157">假定偏移量为 [TimeSpan.Zero](xref:System.TimeSpan.Zero) 的日期和时间值表示 UTC。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-157">It assumes that a date and time value whose offset is [TimeSpan.Zero](xref:System.TimeSpan.Zero) represents UTC.</span></span> <span data-ttu-id="8b4f0-158">事实上，UTC 并不是特定时区中的时间，而是世界时区中的时间相对于它进行标准化的时间。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-158">In fact, UTC is not a time in a particular time zone, but the time in relation to which the times in the world's time zones are standardized.</span></span> <span data-ttu-id="8b4f0-159">时区偏移量还可能为[零](xref:System.TimeSpan.Zero)。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-159">Time zones can also have an offset of [Zero](xref:System.TimeSpan.Zero).</span></span>

* <span data-ttu-id="8b4f0-160">假定偏移量等于本地时区偏移量的日期和时间表示本地时区。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-160">It assumes that a date and time whose offset equals that of the local time zone represents the local time zone.</span></span> <span data-ttu-id="8b4f0-161">由于日期和时间值已从其原始时区解除关联，因此这可能不成立；日期和时间可能源自具有相同偏移量的其他时区。</span><span class="sxs-lookup"><span data-stu-id="8b4f0-161">Because date and time values are disassociated from their original time zone, this may not be the case; the date and time can have originated in another time zone with the same offset.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b4f0-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b4f0-162">See Also</span></span>

[<span data-ttu-id="8b4f0-163">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="8b4f0-163">Dates, times, and time zones</span></span>](index.md)






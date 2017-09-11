---
title: "在各时区之间转换时间"
description: "在各时区之间转换时间"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bf8f74e6-e7f2-4c2a-a04c-57db0e28dd36
ms.translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: c2baa48c3b79dfbc5d39652cc57fe015a2313d6e
ms.contentlocale: zh-cn
ms.lasthandoff: 11/16/2016

---

# <a name="converting-times-between-time-zones"></a><span data-ttu-id="31316-104">在各时区之间转换时间</span><span class="sxs-lookup"><span data-stu-id="31316-104">Converting times between time zones</span></span>

<span data-ttu-id="31316-105">对任何使用日期和时间的应用程序而言，处理各时区之间的差异变得愈发重要。</span><span class="sxs-lookup"><span data-stu-id="31316-105">It is becoming increasingly important for any application that works with dates and times to handle differences between time zones.</span></span> <span data-ttu-id="31316-106">应用程序不再能保证将所有时间表示为 [System.DateTime](xref:System.DateTime) 结构提供的本地时间。</span><span class="sxs-lookup"><span data-stu-id="31316-106">An application can no longer assume that all times can be expressed in the local time, which is the time available from the [System.DateTime](xref:System.DateTime) structure.</span></span> <span data-ttu-id="31316-107">例如，显示美国东部当前时间的网页对东亚客户而言缺乏可信度。</span><span class="sxs-lookup"><span data-stu-id="31316-107">For example, a Web page that displays the current time in the eastern part of the United States will lack credibility to a customer in eastern Asia.</span></span> <span data-ttu-id="31316-108">本主题介绍如何将时间从一个时区转换到另一个时区，以及如何转换时区感知有限的 [System.DateTimeOffset](xref:System.DateTimeOffset) 值。</span><span class="sxs-lookup"><span data-stu-id="31316-108">This topic explains how to convert times from one time zone to another, as well as how to convert [System.DateTimeOffset](xref:System.DateTimeOffset) values that have limited time zone awareness.</span></span>

## <a name="converting-to-coordinated-universal-time"></a><span data-ttu-id="31316-109">转换为协调世界时</span><span class="sxs-lookup"><span data-stu-id="31316-109">Converting to Coordinated Universal Time</span></span>

<span data-ttu-id="31316-110">协调世界时 (UTC) 是一项高精度的原子时标准。</span><span class="sxs-lookup"><span data-stu-id="31316-110">Coordinated Universal Time (UTC) is a high-precision, atomic time standard.</span></span> <span data-ttu-id="31316-111">世界的时区表示为相对于 UTC 的正/负偏移量。</span><span class="sxs-lookup"><span data-stu-id="31316-111">The world’s time zones are expressed as positive or negative offsets from UTC.</span></span> <span data-ttu-id="31316-112">因此，UTC 提供一种无时区或中间时区的时间。</span><span class="sxs-lookup"><span data-stu-id="31316-112">Thus, UTC provides a kind of time-zone free or time-zone neutral time.</span></span> <span data-ttu-id="31316-113">如果日期和时间在计算机之间的可移植性非常重要，则建议使用 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="31316-113">The use of UTC time is recommended when a date and time's portability across computers is important.</span></span> <span data-ttu-id="31316-114">通过将各个时区转换为 UTC，可以简化时间的比较。</span><span class="sxs-lookup"><span data-stu-id="31316-114">Converting individual time zones to UTC makes time comparisons easy.</span></span>

> [!NOTE]
> <span data-ttu-id="31316-115">还可以序列化 [DateTimeOffset](xref:System.DateTimeOffset) 结构，明确表示单个时间点。</span><span class="sxs-lookup"><span data-stu-id="31316-115">You can also serialize a [DateTimeOffset](xref:System.DateTimeOffset) structure to unambiguously represent a single point in time.</span></span> <span data-ttu-id="31316-116">由于 [DateTimeOffset](xref:System.DateTimeOffset) 对象会存储日期和时间值以及其相对于 UTC 的偏移量，它们始终表示与 UTC 相关的某一特定时间点。</span><span class="sxs-lookup"><span data-stu-id="31316-116">Because [DateTimeOffset](xref:System.DateTimeOffset) objects store a date and time value along with its offset from UTC, they always represent a particular point in time in relationship to UTC.</span></span>

<span data-ttu-id="31316-117">将时间转换为 UTC 的最简单方式是调用 `static`（在 Visual Basic 中调用 `Shared`）[TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="31316-117">The easiest way to convert a time to UTC is to call the `static` (`Shared` in Visual Basic) [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="31316-118">`TimeZoneInfo.ConvertTimeToUtc(DateTime)` 方法在 .NET Core 中当前不可用。</span><span class="sxs-lookup"><span data-stu-id="31316-118">The `TimeZoneInfo.ConvertTimeToUtc(DateTime)` method isn't currently available in .NET Core.</span></span> 

<span data-ttu-id="31316-119">该方法执行的具体转换取决于 `DateTime` 参数的 [Kind](xref:System.DateTime.Kind) 属性值，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="31316-119">The exact conversion performed by the method depends on the value of the `DateTime` parameter's [Kind](xref:System.DateTime.Kind) property, as the following table shows.</span></span>

<span data-ttu-id="31316-120">[DateTime.Kind](xref:System.DateTimeKind) 属性</span><span class="sxs-lookup"><span data-stu-id="31316-120">[DateTime.Kind](xref:System.DateTimeKind) property</span></span> | <span data-ttu-id="31316-121">转换</span><span class="sxs-lookup"><span data-stu-id="31316-121">Conversion</span></span>
---------------------------------------------------------------------------------------------- | ----------
[<span data-ttu-id="31316-122">DateTimeKind.Local</span><span class="sxs-lookup"><span data-stu-id="31316-122">DateTimeKind.Local</span></span>](xref:System.DateTimeKind.Local) | <span data-ttu-id="31316-123">将本地时间转换为 UTC。</span><span class="sxs-lookup"><span data-stu-id="31316-123">Converts local time to UTC.</span></span>
[<span data-ttu-id="31316-124">DateTimeKind.Unspecified</span><span class="sxs-lookup"><span data-stu-id="31316-124">DateTimeKind.Unspecified</span></span>](xref:System.DateTimeKind.Unspecified) | <span data-ttu-id="31316-125">假定 `DateTime` 参数为本地时间并将本地时间转换为 UTC。</span><span class="sxs-lookup"><span data-stu-id="31316-125">Assumes the `DateTime` parameter is local time and converts local time to UTC.</span></span>
[<span data-ttu-id="31316-126">DateTimeKind.Utc</span><span class="sxs-lookup"><span data-stu-id="31316-126">DateTimeKind.Utc</span></span>](xref:System.DateTimeKind.Utc) | <span data-ttu-id="31316-127">返回未更改的 `DateTime` 参数。</span><span class="sxs-lookup"><span data-stu-id="31316-127">Returns the `DateTime` parameter unchanged.</span></span>

<span data-ttu-id="31316-128">以下代码可将当前本地时间转换为 UTC，并将结果显示在控制台上。</span><span class="sxs-lookup"><span data-stu-id="31316-128">The following code converts the current local time to UTC and displays the result to the console.</span></span>

```csharp
DateTime dateNow = DateTime.Now;
Console.WriteLine("The date and time are {0} UTC.", 
                   TimeZoneInfo.ConvertTimeToUtc(dateNow));
```

```vb
Dim dateNow As Date = Date.Now      
Console.WriteLine("The date and time are {0} UTC.", _
                  TimeZoneInfo.ConvertTimeToUtc(dateNow))
```

> [!NOTE]
><span data-ttu-id="31316-129">[TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) 方法不一定会生成与 [TimeZone.ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) 和 [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime) 方法相同的结果。</span><span class="sxs-lookup"><span data-stu-id="31316-129">The [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method does not necessarily produce results that are identical to the [TimeZone.ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) and [DateTime.ToUniversalTime](xref:System.DateTime.ToUniversalTime) methods.</span></span> <span data-ttu-id="31316-130">如果主机系统的本地时区包含多个调整规则，[TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/System.TimeZone.ConvertTimeToUtc(v=vs.110).aspx) 会将适当的规则应用于特定日期和时间。</span><span class="sxs-lookup"><span data-stu-id="31316-130">If the host system's local time zone includes multiple adjustment rules, [TimeZoneInfo.ConvertTimeToUtc(DateTime)](https://msdn.microsoft.com/en-us/library/System.TimeZone.ConvertTimeToUtc(v=vs.110).aspx) applies the appropriate rule to a particular date and time.</span></span> <span data-ttu-id="31316-131">其他两种方法始终应用最新调整规则。</span><span class="sxs-lookup"><span data-stu-id="31316-131">The other two methods always apply the latest adjustment rule.</span></span>

<span data-ttu-id="31316-132">如果日期和时间值不表示本地时间或 UTC，[ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) 方法可能返回错误的结果。</span><span class="sxs-lookup"><span data-stu-id="31316-132">If the date and time value does not represent either the local time or UTC, the [ToUniversalTime](https://msdn.microsoft.com/en-us/library/System.TimeZone.ToUniversalTime(v=vs.110).aspx) method will likely return an erroneous result.</span></span> <span data-ttu-id="31316-133">但是，可以使用 [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) 方法转换指定时区的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="31316-133">However, you can use the [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method to convert the date and time from a specified time zone.</span></span> <span data-ttu-id="31316-134">（有关检索表示目标时区的 TimeZoneInfo 对象的详细信息，请参阅[查找本地系统上定义的时区](finding-the-time-zones-on-local-system.md)。</span><span class="sxs-lookup"><span data-stu-id="31316-134">(For details on retrieving a TimeZoneInfo object that represents the destination time zone, see [Finding the time zones defined on a local system](finding-the-time-zones-on-local-system.md).</span></span> <span data-ttu-id="31316-135">以下代码使用 [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) 方法将东部标准时间转换为 UTC。</span><span class="sxs-lookup"><span data-stu-id="31316-135">The following code uses the [TimeZoneInfo.ConvertTimeToUtc](https://msdn.microsoft.com/en-us/library/bb381744(v=vs.110).aspx) method to convert Eastern Standard Time to UTC.</span></span>

```csharp
DateTime easternTime = new DateTime(2007, 01, 02, 12, 16, 00);
string easternZoneId = "Eastern Standard Time";
try
{
   TimeZoneInfo easternZone = TimeZoneInfo.FindSystemTimeZoneById(easternZoneId);
   Console.WriteLine("The date and time are {0} UTC.", 
                     TimeZoneInfo.ConvertTimeToUtc(easternTime, easternZone));
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("Unable to find the {0} zone in the registry.", 
                     easternZoneId);
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the {0} zone has been corrupted.", 
                     easternZoneId);
}
```

```vb
Dim easternTime As New Date(2007, 01, 02, 12, 16, 00)
Dim easternZoneId As String = "Eastern Standard Time"
Try
   Dim easternZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(easternZoneId)
   Console.WriteLine("The date and time are {0} UTC.", _ 
                     TimeZoneInfo.ConvertTimeToUtc(easternTime, easternZone))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("Unable to find the {0} zone in the registry.", _
                     easternZoneId)
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the {0} zone has been corrupted.", _ 
                     easternZoneId)
End Try    
```

<span data-ttu-id="31316-136">请注意，如果 [DateTime](xref:System.DateTime) 对象的 [Kind](xref:System.DateTimeKind) 属性与时区不匹配，此方法将引发 [ArgumentException](xref:System.ArgumentException)。</span><span class="sxs-lookup"><span data-stu-id="31316-136">Note that this method throws an [ArgumentException](xref:System.ArgumentException) if the [DateTime](xref:System.DateTime) object's [Kind](xref:System.DateTimeKind) property and the time zone are mismatched.</span></span> <span data-ttu-id="31316-137">如果 Kind 属性为 [DateTimeKind.Local](xref:System.DateTimeKind.Local)，但[TimeZoneInfo](xref:System.TimeZoneInfo) 对象不表示本地时区，或如果 Kind 属性为 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)，但 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象不等于 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)，则会出现不匹配。</span><span class="sxs-lookup"><span data-stu-id="31316-137">A mismatch occurs if the Kind property is [DateTimeKind.Local](xref:System.DateTimeKind.Local) but the [TimeZoneInfo](xref:System.TimeZoneInfo) object does not represent the local time zone, or if the Kind property is [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) but the [TimeZoneInfo](xref:System.TimeZoneInfo) object does not equal [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

<span data-ttu-id="31316-138">所有这些方法均采用 [DateTime](xref:System.DateTime) 值作为参数，并返回 [DateTime](xref:System.DateTime) 值。</span><span class="sxs-lookup"><span data-stu-id="31316-138">All of these methods take [DateTime](xref:System.DateTime) values as parameters and return a [DateTime](xref:System.DateTime) value.</span></span> <span data-ttu-id="31316-139">对于 [DateTimeOffset](xref:System.DateTimeOffset) 值，[DateTimeOffset](xref:System.DateTimeOffset) 结构具有 [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) 实例方法，该方法可将当前实例的日期和时间转换为 UTC。</span><span class="sxs-lookup"><span data-stu-id="31316-139">For [DateTimeOffset](xref:System.DateTimeOffset) values, the [DateTimeOffset](xref:System.DateTimeOffset) structure has a [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) instance method that converts the date and time of the current instance to UTC.</span></span> <span data-ttu-id="31316-140">以下示例调用 [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) 方法，将本地时间和几个其他时间转换为协调世界时 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="31316-140">The following example calls the [ToUniversalTime](xref:System.DateTimeOffset.ToUniversalTime) method to convert a local time and several other times to Coordinated Universal Time (UTC).</span></span>

```csharp
DateTimeOffset localTime, otherTime, universalTime;

// Define local time in local time zone
localTime = new DateTimeOffset(new DateTime(2007, 6, 15, 12, 0, 0));
Console.WriteLine("Local time: {0}", localTime);
Console.WriteLine();

// Convert local time to offset 0 and assign to otherTime
otherTime = localTime.ToOffset(TimeSpan.Zero);
Console.WriteLine("Other time: {0}", otherTime);
Console.WriteLine("{0} = {1}: {2}", 
                  localTime, otherTime, 
                  localTime.Equals(otherTime));
Console.WriteLine("{0} exactly equals {1}: {2}", 
                  localTime, otherTime, 
                  localTime.EqualsExact(otherTime));
Console.WriteLine();

// Convert other time to UTC
universalTime = localTime.ToUniversalTime(); 
Console.WriteLine("Universal time: {0}", universalTime);
Console.WriteLine("{0} = {1}: {2}", 
                  otherTime, universalTime, 
                  universalTime.Equals(otherTime));
Console.WriteLine("{0} exactly equals {1}: {2}", 
                  otherTime, universalTime, 
                  universalTime.EqualsExact(otherTime));
Console.WriteLine();
// The example produces the following output to the console:
//    Local time: 6/15/2007 12:00:00 PM -07:00
//    
//    Other time: 6/15/2007 7:00:00 PM +00:00
//    6/15/2007 12:00:00 PM -07:00 = 6/15/2007 7:00:00 PM +00:00: True
//    6/15/2007 12:00:00 PM -07:00 exactly equals 6/15/2007 7:00:00 PM +00:00: False
//    
//    Universal time: 6/15/2007 7:00:00 PM +00:00
//    6/15/2007 7:00:00 PM +00:00 = 6/15/2007 7:00:00 PM +00:00: True
//    6/15/2007 7:00:00 PM +00:00 exactly equals 6/15/2007 7:00:00 PM +00:00: True 
```

```vb
Dim localTime, otherTime, universalTime As DateTimeOffset

' Define local time in local time zone
localTime = New DateTimeOffset(#6/15/2007 12:00:00PM#)
Console.WriteLine("Local time: {0}", localTime)
Console.WriteLine()

' Convert local time to offset 0 and assign to otherTime
otherTime = localTime.ToOffset(TimeSpan.Zero)
Console.WriteLine("Other time: {0}", otherTime)
Console.WriteLine("{0} = {1}: {2}", _
                  localTime, otherTime, _
                  localTime.Equals(otherTime))
Console.WriteLine("{0} exactly equals {1}: {2}", _ 
                  localTime, otherTime, _
                  localTime.EqualsExact(otherTime))
Console.WriteLine()

' Convert other time to UTC
universalTime = localTime.ToUniversalTime() 
Console.WriteLine("Universal time: {0}", universalTime)
Console.WriteLine("{0} = {1}: {2}", _
                  otherTime, universalTime, _ 
                  universalTime.Equals(otherTime))
Console.WriteLine("{0} exactly equals {1}: {2}", _ 
                  otherTime, universalTime, _
                  universalTime.EqualsExact(otherTime))
Console.WriteLine()
' The example produces the following output to the console:
'    Local time: 6/15/2007 12:00:00 PM -07:00
'    
'    Other time: 6/15/2007 7:00:00 PM +00:00
'    6/15/2007 12:00:00 PM -07:00 = 6/15/2007 7:00:00 PM +00:00: True
'    6/15/2007 12:00:00 PM -07:00 exactly equals 6/15/2007 7:00:00 PM +00:00: False
'    
'    Universal time: 6/15/2007 7:00:00 PM +00:00
'    6/15/2007 7:00:00 PM +00:00 = 6/15/2007 7:00:00 PM +00:00: True
'    6/15/2007 7:00:00 PM +00:00 exactly equals 6/15/2007 7:00:00 PM +00:00: True 
```

## <a name="converting-utc-to-a-designated-time-zone"></a><span data-ttu-id="31316-141">将 UTC 转换为指定的时区</span><span class="sxs-lookup"><span data-stu-id="31316-141">Converting UTC to a designated time zone</span></span>

<span data-ttu-id="31316-142">若要将 UTC 转换为本地时间，请参阅下方[将 UTC 转换为本地时间](#converting-utc-to-local-time)一节。</span><span class="sxs-lookup"><span data-stu-id="31316-142">To convert UTC to local time, see the [Converting UTC to local time](#converting-utc-to-local-time) section that follows.</span></span> 

<span data-ttu-id="31316-143">若要将 UTC 转换为任何指定时区中的时间，请调用 [ConvertTimeFromUtc](https://msdn.microsoft.com/en-us/library/System.TimeZoneInfo.converttimefromutc(v=vs.110).aspx) 方法。</span><span class="sxs-lookup"><span data-stu-id="31316-143">To convert UTC to the time in any time zone that you designate, call the [ConvertTimeFromUtc](https://msdn.microsoft.com/en-us/library/System.TimeZoneInfo.converttimefromutc(v=vs.110).aspx) method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="31316-144">“TimeZoneInfo.ConvertTimeFromUtc”方法当前在 .NET Core 中不可用。</span><span class="sxs-lookup"><span data-stu-id="31316-144">The \`TimeZoneInfo.ConvertTimeFromUtc' method isn't currently available in .NET Core.</span></span> 

<span data-ttu-id="31316-145">该方法采用两个参数：</span><span class="sxs-lookup"><span data-stu-id="31316-145">The method takes two parameters:</span></span>

* <span data-ttu-id="31316-146">要转换的 UTC。</span><span class="sxs-lookup"><span data-stu-id="31316-146">The UTC to convert.</span></span> <span data-ttu-id="31316-147">这必须是一个 [DateTime](xref:System.DateTime) 值，其 [Kind](xref:System.DateTime.Kind) 属性设置为 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) 或 [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)。</span><span class="sxs-lookup"><span data-stu-id="31316-147">This must be a [DateTime](xref:System.DateTime) value whose [Kind](xref:System.DateTime.Kind) property is set to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc) or [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span> 

* <span data-ttu-id="31316-148">UTC 要转换的目标时区。</span><span class="sxs-lookup"><span data-stu-id="31316-148">The time zone to convert the UTC to.</span></span> 

<span data-ttu-id="31316-149">以下代码可将 UTC 转换为中部标准时间。</span><span class="sxs-lookup"><span data-stu-id="31316-149">The following code converts UTC to Central Standard Time.</span></span>

```csharp
DateTime timeUtc = DateTime.UtcNow;
try
{
   TimeZoneInfo cstZone = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time");
   DateTime cstTime = TimeZoneInfo.ConvertTimeFromUtc(timeUtc, cstZone);
   Console.WriteLine("The date and time are {0} {1}.", 
                     cstTime, 
                     cstZone.IsDaylightSavingTime(cstTime) ?
                             cstZone.DaylightName : cstZone.StandardName);
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The registry does not define the Central Standard Time zone.");
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the Central Standard Time zone has been corrupted.");
}
```

```vb
Dim timeUtc As Date = Date.UtcNow
Try
   Dim cstZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Central Standard Time")
   Dim cstTime As Date = TimeZoneInfo.ConvertTimeFromUtc(timeUtc, cstZone)
   Console.WriteLine("The date and time are {0} {1}.", _
                     cstTime, _
                     IIf(cstZone.IsDaylightSavingTime(cstTime), _
                         cstZone.DaylightName, cstZone.StandardName))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The registry does not define the Central Standard Time zone.")
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the Central Standard Time zone has been corrupted.")
End Try
``` 

## <a name="converting-utc-to-local-time"></a><span data-ttu-id="31316-150">将 UTC 转换为本地时间</span><span class="sxs-lookup"><span data-stu-id="31316-150">Converting UTC to local time</span></span>

<span data-ttu-id="31316-151">若要将 UTC 转换为本地时间，请调用要转换其时间的 [DateTime](xref:System.DateTime) 对象的 [DateTime.ToLocalTime](xref:System.DateTime) 方法。</span><span class="sxs-lookup"><span data-stu-id="31316-151">To convert UTC to local time, call the [DateTime.ToLocalTime](xref:System.DateTime) method of the [DateTime](xref:System.DateTime) object whose time you want to convert.</span></span> <span data-ttu-id="31316-152">该方法的具体行为取决于该对象的 [Kind](xref:System.DateTime.Kind) 属性值，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="31316-152">The exact behavior of the method depends on the value of the object’s [Kind](xref:System.DateTime.Kind) property, as the following table shows.</span></span>

<span data-ttu-id="31316-153">[DateTime.Kind](xref:System.DateTimeKind) 属性</span><span class="sxs-lookup"><span data-stu-id="31316-153">[DateTime.Kind](xref:System.DateTimeKind) property</span></span> | <span data-ttu-id="31316-154">转换</span><span class="sxs-lookup"><span data-stu-id="31316-154">Conversion</span></span>
---------------------------------------------------------------------------------------------- | ----------
[<span data-ttu-id="31316-155">DateTimeKind.Local</span><span class="sxs-lookup"><span data-stu-id="31316-155">DateTimeKind.Local</span></span>](xref:System.DateTimeKind.Local) | <span data-ttu-id="31316-156">返回未更改的 [DateTime](xref:System.DateTime) 值。</span><span class="sxs-lookup"><span data-stu-id="31316-156">Returns the [DateTime](xref:System.DateTime) value unchanged.</span></span>
[<span data-ttu-id="31316-157">DateTimeKind.Unspecified</span><span class="sxs-lookup"><span data-stu-id="31316-157">DateTimeKind.Unspecified</span></span>](xref:System.DateTimeKind.Unspecified) | <span data-ttu-id="31316-158">假定 [DateTime](xref:System.DateTime) 值为 UTC 并将 UTC 转换为本地时间。</span><span class="sxs-lookup"><span data-stu-id="31316-158">Assumes that the [DateTime](xref:System.DateTime) value is UTC and converts the UTC to local time.</span></span>
[<span data-ttu-id="31316-159">DateTimeKind.Utc</span><span class="sxs-lookup"><span data-stu-id="31316-159">DateTimeKind.Utc</span></span>](xref:System.DateTimeKind.Utc) | <span data-ttu-id="31316-160">将 [DateTime](xref:System.DateTime) 值转换为本地时间。</span><span class="sxs-lookup"><span data-stu-id="31316-160">Converts the [DateTime](xref:System.DateTime) value to local time.</span></span>

## <a name="converting-between-any-two-time-zones"></a><span data-ttu-id="31316-161">在任意两个时区之间转换</span><span class="sxs-lookup"><span data-stu-id="31316-161">Converting between any two time zones</span></span>

<span data-ttu-id="31316-162">可以使用静态 [TimeZoneInfo.ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) 方法实现两个任意时区之间的转换。</span><span class="sxs-lookup"><span data-stu-id="31316-162">You can convert between any two time zones by using the static [TimeZoneInfo.ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method.</span></span> <span data-ttu-id="31316-163">此方法的参数是要转换的 [DateTime](xref:System.DateTime) 值，一个 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象（表示日期和时间值的时区）和一个 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象（表示日期和时间值要转换的目标时区）。</span><span class="sxs-lookup"><span data-stu-id="31316-163">This method's parameters are the [DateTime](xref:System.DateTime) value to convert, a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the time zone of the date and time value, and a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the time zone to convert the date and time value to.</span></span>

<span data-ttu-id="31316-164">该方法要求要转换的日期和时间值的 [Kind](xref:System.DateTime.Kind) 属性、[TimeZoneInfo](xref:System.TimeZoneInfo) 对象或表示其时区的时区标识符彼此对应。</span><span class="sxs-lookup"><span data-stu-id="31316-164">The method requires that the [Kind](xref:System.DateTime.Kind) property of the date and time value to convert and the [TimeZoneInfo](xref:System.TimeZoneInfo) object or time zone identifier that represents its time zone correspond to one another.</span></span> <span data-ttu-id="31316-165">否则，会引发 [ArgumentException](xref:System.ArgumentException)。</span><span class="sxs-lookup"><span data-stu-id="31316-165">Otherwise, an [ArgumentException](xref:System.ArgumentException) is thrown.</span></span> <span data-ttu-id="31316-166">例如，如果日期和时间值的 [Kind](xref:System.DateTime.Kind) 属性为[DateTimeKind.Local](xref:System.DateTimeKind.Local)，而作为参数传递给该方法的 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象不等于 [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local)，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="31316-166">For example, if the [Kind](xref:System.DateTime.Kind) property of the date and time value is [DateTimeKind.Local](xref:System.DateTimeKind.Local), an exception is thrown if the [TimeZoneInfo](xref:System.TimeZoneInfo) object passed as a parameter to the method is not equal to [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local).</span></span> <span data-ttu-id="31316-167">如果作为参数传递给该方法的标识符不等于 [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id)，也会引发异常。</span><span class="sxs-lookup"><span data-stu-id="31316-167">An exception is also thrown if the identifier passed as a parameter to the method is not equal to [TimeZoneInfo.Id](xref:System.TimeZoneInfo.Id).</span></span>

<span data-ttu-id="31316-168">下面的示例使用 [ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) 方法将夏威夷标准时间转换为本地时间。</span><span class="sxs-lookup"><span data-stu-id="31316-168">The following example uses the [ConvertTime](xref:System.TimeZoneInfo.ConvertTime(System.DateTime,System.TimeZoneInfo)) method to convert from Hawaiian Standard Time to local time.</span></span>

```csharp
DateTime hwTime = new DateTime(2007, 02, 01, 08, 00, 00);
try
{
   TimeZoneInfo hwZone = TimeZoneInfo.FindSystemTimeZoneById("Hawaiian Standard Time");
   Console.WriteLine("{0} {1} is {2} local time.", 
           hwTime, 
           hwZone.IsDaylightSavingTime(hwTime) ? hwZone.DaylightName : hwZone.StandardName, 
           TimeZoneInfo.ConvertTime(hwTime, hwZone, TimeZoneInfo.Local));
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The registry does not define the Hawaiian Standard Time zone.");
}                           
catch (InvalidTimeZoneException)
{
   Console.WriteLine("Registry data on the Hawaiian STandard Time zone has been corrupted.");
}
```

```vb
Dim hwTime As Date = #2/01/2007 8:00:00 AM#
Try
   Dim hwZone As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById("Hawaiian Standard Time")
   Console.WriteLine("{0} {1} is {2} local time.", _
                     hwTime, _
                     IIf(hwZone.IsDaylightSavingTime(hwTime), hwZone.DaylightName, hwZone.StandardName), _
                     TimeZoneInfo.ConvertTime(hwTime, hwZone, TimeZoneInfo.Local))
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The registry does not define the Hawaiian Standard Time zone.")
Catch e As InvalidTimeZoneException
   Console.WriteLine("Registry data on the Hawaiian Standard Time zone has been corrupted.")
End Try
```

## <a name="converting-datetimeoffset-values"></a><span data-ttu-id="31316-169">转换 DateTimeOffset 值</span><span class="sxs-lookup"><span data-stu-id="31316-169">Converting DateTimeOffset values</span></span>

<span data-ttu-id="31316-170">由 [System.DateTimeOffset](xref:System.DateTimeOffset) 对象表示的日期和时间值不具备完全时区感知能力，因为实例化该对象时已解除其与其时区的关联。</span><span class="sxs-lookup"><span data-stu-id="31316-170">Date and time values represented by [System.DateTimeOffset](xref:System.DateTimeOffset) objects are not fully time-zone aware because the object is disassociated from its time zone at the time it is instantiated.</span></span> <span data-ttu-id="31316-171">但是，大多数情况下，应用程序仅需根据两种相对于 UTC 的偏移量，而不是特定时区的时间来转换日期和时间。</span><span class="sxs-lookup"><span data-stu-id="31316-171">However, in many cases an application simply needs to convert a date and time based on two different offsets from UTC rather than on the time in particular time zones.</span></span> <span data-ttu-id="31316-172">若要执行此转换，可以调用当前实例的 [ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan)) 方法。</span><span class="sxs-lookup"><span data-stu-id="31316-172">To perform this conversion, you can call the current instance's [ToOffset](xref:System.DateTimeOffset.ToOffset(System.TimeSpan)) method.</span></span> <span data-ttu-id="31316-173">该方法的单个参数是 [TimeSpan](xref:System.TimeSpan)，表示方法将返回的新日期和时间值的偏移量。</span><span class="sxs-lookup"><span data-stu-id="31316-173">The method's single parameter is [TimeSpan](xref:System.TimeSpan) representing the offset of the new date and time value that the method is to return.</span></span>  

<span data-ttu-id="31316-174">例如，如果用户所请求网页的日期和时间已知，并且已被序列化为 MM/dd/yyyy hh:mm:ss zzzz 格式的字符串，以下 `ReturnTimeOnServer` 方法会将此日期和时间值转换为 Web 服务器上的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="31316-174">For example, if the date and time of a user request for a Web page is known and is serialized as a string in the format MM/dd/yyyy hh:mm:ss zzzz, the following `ReturnTimeOnServer` method converts this date and time value to the date and time on the Web server.</span></span>

```csharp
public DateTimeOffset ReturnTimeOnServer(string clientString)
{
   string format = @"M/d/yyyy H:m:s zzz";
   TimeSpan serverOffset = TimeZoneInfo.Local.GetUtcOffset(DateTimeOffset.Now);

   try
   {      
      DateTimeOffset clientTime = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture);
      DateTimeOffset serverTime = clientTime.ToOffset(serverOffset);
      return serverTime;
   }
   catch (FormatException)
   {
      return DateTimeOffset.MinValue;
   }
}
```

```vb
Public Function ReturnTimeOnServer(clientString As String) As DateTimeOffset
   Dim format As String = "M/d/yyyy H:m:s zzz"
   Dim serverOffset As TimeSpan = TimeZoneInfo.Local.GetUtcOffset(DateTimeOffset.Now)

   Try      
      Dim clientTime As DateTimeOffset = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture)
      Dim serverTime As DateTimeOffset = clientTime.ToOffset(serverOffset)
      Return serverTime
   Catch e As FormatException
      Return DateTimeOffset.MinValue
   End Try    
End Function
```

<span data-ttu-id="31316-175">如果向该方法传递字符串“9/1/2007 5:32:07 -05:00”（表示比 UTC 早五个小时的时区中的日期和时间），则对处于美国太平洋标准时区中的服务器，它将返回 9/1/2007 3:32:07 AM -07:00。</span><span class="sxs-lookup"><span data-stu-id="31316-175">If the method is passed the string "9/1/2007 5:32:07 -05:00", which represents the date and time in a time zone five hours earlier than UTC, it returns 9/1/2007 3:32:07 AM -07:00 for a server located in the U.S. Pacific Standard Time zone.</span></span>

<span data-ttu-id="31316-176">[TimeZoneInfo](xref:System.TimeZoneInfo) 类还包括通过 [System.DateTimeOffset](xref:System.DateTimeOffset) 值执行时区转换的已重载 [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) 方法。</span><span class="sxs-lookup"><span data-stu-id="31316-176">The [TimeZoneInfo](xref:System.TimeZoneInfo) class also includes an overloaded [TimeZoneInfo.ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) method that performs time zone conversions with [System.DateTimeOffset](xref:System.DateTimeOffset) values.</span></span> <span data-ttu-id="31316-177">该方法有两个参数：一个是 [System.DateTimeOffset](xref:System.DateTimeOffset) 值，另一个是对时间要转换的目标时区的引用。</span><span class="sxs-lookup"><span data-stu-id="31316-177">The method's parameters are a [System.DateTimeOffset](xref:System.DateTimeOffset) value and a reference to the time zone to which the time is to be converted.</span></span> <span data-ttu-id="31316-178">该方法调用返回 [System.DateTimeOffset](xref:System.DateTimeOffset) 值。</span><span class="sxs-lookup"><span data-stu-id="31316-178">The method call returns a [System.DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="31316-179">例如，可如下所示重写上一示例中的 `ReturnTimeOnServer` 方法，以调用 [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) 方法。</span><span class="sxs-lookup"><span data-stu-id="31316-179">For example, the `ReturnTimeOnServer` method in the previous example could be rewritten as follows to call the [ConvertTime(DateTimeOffset, TimeZoneInfo)](xref:System.TimeZoneInfo.ConvertTime(System.DateTimeOffset,System.TimeZoneInfo)) method.</span></span>

```csharp
public DateTimeOffset ReturnTimeOnServer(string clientString)
{
   string format = @"M/d/yyyy H:m:s zzz";

   try
   {      
      DateTimeOffset clientTime = DateTimeOffset.ParseExact(clientString, format, 
                                  CultureInfo.InvariantCulture);
      DateTimeOffset serverTime = TimeZoneInfo.ConvertTime(clientTime, 
                                  TimeZoneInfo.Local);
      return serverTime;
   }
   catch (FormatException)
   {
      return DateTimeOffset.MinValue;
   }
}
```

```vb
Public Function ReturnTimeOnServer(clientString As String) As DateTimeOffset
   Dim format As String = "M/d/yyyy H:m:s zzz"

   Try      
      Dim clientTime As DateTimeOffset = DateTimeOffset.ParseExact(clientString, format, CultureInfo.InvariantCulture)
      Dim serverTime As DateTimeOffset = TimeZoneInfo.ConvertTime(clientTime, TimeZoneInfo.Local)
      Return serverTime
   Catch e As FormatException
      Return DateTimeOffset.MinValue
   End Try    
End Function
```

## <a name="see-also"></a><span data-ttu-id="31316-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31316-180">See also</span></span>

[<span data-ttu-id="31316-181">TimeZoneInfo</span><span class="sxs-lookup"><span data-stu-id="31316-181">TimeZoneInfo</span></span>](xref:System.TimeZoneInfo)

[<span data-ttu-id="31316-182">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="31316-182">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="31316-183">查找本地系统上定义的时区</span><span class="sxs-lookup"><span data-stu-id="31316-183">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)




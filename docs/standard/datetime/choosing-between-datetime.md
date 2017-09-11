---
title: "在 DateTime、DateTimeOffset、TimeSpan 和 TimeZoneInfo 之间进行选择"
description: "在 DateTime、DateTimeOffset、TimeSpan 和 TimeZoneInfo 之间进行选择"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 08/11/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 2dd84ee8-9f0f-4054-9537-155857a460cd
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: aeb1928be32584ee4b6acf7c9a4f4330daedc590
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="choosing-between-datetime-datetimeoffset-timespan-and-timezoneinfo"></a><span data-ttu-id="3e868-104">在 DateTime、DateTimeOffset、TimeSpan 和 TimeZoneInfo 之间进行选择</span><span class="sxs-lookup"><span data-stu-id="3e868-104">Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo</span></span>

<span data-ttu-id="3e868-105">使用日期和时间信息的 .NET 应用程序多种多样，并可以多种方式使用此类信息。</span><span class="sxs-lookup"><span data-stu-id="3e868-105">.NET applications that use date and time information are very diverse and can use that information in several ways.</span></span> <span data-ttu-id="3e868-106">日期和时间信息的较常见使用方法包括以下一种或多种：</span><span class="sxs-lookup"><span data-stu-id="3e868-106">The more common uses of date and time information include one or more of the following:</span></span>

* <span data-ttu-id="3e868-107">仅反映日期，而时间信息不重要。</span><span class="sxs-lookup"><span data-stu-id="3e868-107">To reflect a date only, so that time information is not important.</span></span>

* <span data-ttu-id="3e868-108">仅反映时间，而日期信息不重要。</span><span class="sxs-lookup"><span data-stu-id="3e868-108">To reflect a time only, so that date information is not important.</span></span>

* <span data-ttu-id="3e868-109">反映未绑定到特定时间和位置的抽象的日期和时间（例如，国际上大多数连锁店在工作日上午 9:00 开张）。</span><span class="sxs-lookup"><span data-stu-id="3e868-109">To reflect an abstract date and time that is not tied to a specific time and place (for example, most stores in an international chain open on weekdays at 9:00 A.M.).</span></span>

* <span data-ttu-id="3e868-110">从 .NET 应用程序外部的源中（其中日期和时间信息通常以简单数据类型存储）检索日期和时间信息。</span><span class="sxs-lookup"><span data-stu-id="3e868-110">To retrieve date and time information from sources outside of the .NET application, typically where date and time information is stored in a simple data type.</span></span>

* <span data-ttu-id="3e868-111">唯一、明确地标识单个时间点。</span><span class="sxs-lookup"><span data-stu-id="3e868-111">To uniquely and unambiguously identify a single point in time.</span></span> <span data-ttu-id="3e868-112">某些应用程序仅要求主机系统具有明确的日期和时间；其他程序要求整个系统中均具有明确的日期和时间（即，在意义上，某个系统上序列化的日期可以在世界各地的其他系统上进行反序列化和使用）。</span><span class="sxs-lookup"><span data-stu-id="3e868-112">Some applications require that a date and time be unambiguous only on the host system; others require that it be unambiguous across systems (that is, a date serialized on one system can be meaningfully deserialized and used on another system anywhere in the world).</span></span> 

* <span data-ttu-id="3e868-113">保留多个相关时间（例如请求程序的本地时间和服务器接收 Web 请求的时间）。</span><span class="sxs-lookup"><span data-stu-id="3e868-113">To preserve multiple related times (such as the requestor's local time and the server's time of receipt for a Web request).</span></span>

* <span data-ttu-id="3e868-114">执行日期和时间算法，可能致使唯一、明确标识单个时间点。</span><span class="sxs-lookup"><span data-stu-id="3e868-114">To perform date and time arithmetic, possibly with a result that uniquely and unambiguously identifies a single point in time.</span></span> 

<span data-ttu-id="3e868-115">.NET 包括 [System.DateTime](xref:System.DateTime)、[System.DateTimeOffset](xref:System.DateTimeOffset)、[System.TimeSpan](xref:System.TimeSpan) 和 [System.TimeZoneInfo](xref:System.TimeZoneInfo) 类型，以上所有类型都可用于生成处理日期和时间的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3e868-115">.NET includes the [System.DateTime](xref:System.DateTime), [System.DateTimeOffset](xref:System.DateTimeOffset), [System.TimeSpan](xref:System.TimeSpan), and [System.TimeZoneInfo](xref:System.TimeZoneInfo) types, all of which can be used to build applications that work with dates and times.</span></span> 

> [!NOTE]
> <span data-ttu-id="3e868-116">本主题不讨论较早的 `TimeZone` 类型，因为 [System.TimeZoneInfo](xref:System.TimeZoneInfo) 类中几乎包含其全部功能。</span><span class="sxs-lookup"><span data-stu-id="3e868-116">This topic does not discuss the older `TimeZone` type, because its functionality is almost entirely incorporated in the [System.TimeZoneInfo](xref:System.TimeZoneInfo) class.</span></span> <span data-ttu-id="3e868-117">开发人员应尽可能地使用 [System.TimeZoneInfo](xref:System.TimeZoneInfo) 类，而不是使用 `TimeZone` 类。</span><span class="sxs-lookup"><span data-stu-id="3e868-117">Whenever possible, developers should use the [System.TimeZoneInfo](xref:System.TimeZoneInfo) class instead of the `TimeZone` class.</span></span>


## <a name="the-datetime-structure"></a><span data-ttu-id="3e868-118">DateTime 结构</span><span class="sxs-lookup"><span data-stu-id="3e868-118">The DateTime structure</span></span>

<span data-ttu-id="3e868-119">[System.DateTime](xref:System.DateTime) 值定义特定日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3e868-119">A [System.DateTime](xref:System.DateTime) value defines a particular date and time.</span></span> <span data-ttu-id="3e868-120">它包括 [Kind](xref:System.DateTime.Kind) 属性，此属性提供有关日期和时间所属时区的有限信息。</span><span class="sxs-lookup"><span data-stu-id="3e868-120">It includes a [Kind](xref:System.DateTime.Kind) property that provides limited information about the time zone to which that date and time belongs.</span></span> <span data-ttu-id="3e868-121">[Kind](xref:System.DateTime.Kind) 属性返回的 [DateTimeKind](xref:System.DateTimeKind) 值指示 [DateTime](xref:System.DateTime) 值是否表示本地时间 [DateTimeKind.Local](xref:System.DateTimeKind.Local)、协调世界时 (UTC) [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)，或未指定的时间 [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)。</span><span class="sxs-lookup"><span data-stu-id="3e868-121">The [DateTimeKind](xref:System.DateTimeKind) value returned by the [Kind](xref:System.DateTime.Kind) property indicates whether the [DateTime](xref:System.DateTime) value represents the local time [DateTimeKind.Local](xref:System.DateTimeKind.Local)), Coordinated Universal Time (UTC) [DateTimeKind.Utc](xref:System.DateTimeKind.Utc), or an unspecified time [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span>

<span data-ttu-id="3e868-122">[DateTime](xref:System.DateTime) 结构适用于执行以下操作的应用程序：</span><span class="sxs-lookup"><span data-stu-id="3e868-122">The [DateTime](xref:System.DateTime) structure is suitable for applications that do the following:</span></span> 

* <span data-ttu-id="3e868-123">仅使用日期。</span><span class="sxs-lookup"><span data-stu-id="3e868-123">Work with dates only.</span></span>

* <span data-ttu-id="3e868-124">只使用时间。</span><span class="sxs-lookup"><span data-stu-id="3e868-124">Work with times only.</span></span>

* <span data-ttu-id="3e868-125">使用抽象的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3e868-125">Work with abstract dates and times.</span></span>

* <span data-ttu-id="3e868-126">使用缺少时区信息的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3e868-126">Work with dates and times for which time zone information is missing.</span></span> 

* <span data-ttu-id="3e868-127">只使用 UTC 日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3e868-127">Work with UTC dates and times only.</span></span> 

* <span data-ttu-id="3e868-128">从 .NET Framework 外部的源（如 SQL 数据库）中检索日期和时间信息。</span><span class="sxs-lookup"><span data-stu-id="3e868-128">Retrieve date and time information from sources outside the .NET Framework, such as SQL databases.</span></span> <span data-ttu-id="3e868-129">通常，这些源按与 [DateTime](xref:System.DateTime) 结构兼容的简单格式存储日期和时间信息。</span><span class="sxs-lookup"><span data-stu-id="3e868-129">Typically, these sources store date and time information in a simple format that is compatible with the [DateTime](xref:System.DateTime) structure.</span></span>

* <span data-ttu-id="3e868-130">执行日期和时间算法，但不关注常规结果。</span><span class="sxs-lookup"><span data-stu-id="3e868-130">Perform date and time arithmetic, but are concerned with general results.</span></span> <span data-ttu-id="3e868-131">例如，在向特定日期和时间添加六个月的加法运算中，是否将结果调整为夏令时通常并不重要。</span><span class="sxs-lookup"><span data-stu-id="3e868-131">For example, in an addition operation that adds six months to a particular date and time, it is often not important whether the result is adjusted for daylight saving time.</span></span>

<span data-ttu-id="3e868-132">除非特定的 [DateTime](xref:System.DateTime) 值表示 UTC，否则日期和时间值通常不明确或其可移植性受限。</span><span class="sxs-lookup"><span data-stu-id="3e868-132">Unless a particular [DateTime](xref:System.DateTime) value represents UTC, that date and time value is often ambiguous or limited in its portability.</span></span> <span data-ttu-id="3e868-133">例如，如果 [DateTime](xref:System.DateTime) 值表示本地时间，则在该本地时区内可移植（即，如果在其他系统的相同时区上反序列化此值，它仍然明确标识单个时间点）。</span><span class="sxs-lookup"><span data-stu-id="3e868-133">For example, if a [DateTime](xref:System.DateTime) value represents the local time, it is portable within that local time zone (that is, if the value is deserialized on another system in the same time zone, that value still unambiguously identifies a single point in time).</span></span> <span data-ttu-id="3e868-134">在本地时区之外，[DateTime](xref:System.DateTime) 值可以有多个解释。</span><span class="sxs-lookup"><span data-stu-id="3e868-134">Outside the local time zone, that [DateTime](xref:System.DateTime) value can have multiple interpretations.</span></span> <span data-ttu-id="3e868-135">如果值的 [Kind](xref:System.DateTime.Kind) 属性是 [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified)，其可移植性更低：此时它在相同时区内（甚至可能在首次序列化的同一系统上）是不明确的。</span><span class="sxs-lookup"><span data-stu-id="3e868-135">If the value's [Kind](xref:System.DateTime.Kind) property is [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified), it is even less portable: it is now ambiguous within the same time zone and possibly even on the same system on which it was first serialized.</span></span> <span data-ttu-id="3e868-136">仅当 [DateTime](xref:System.DateTime) 值表示 UTC 时，无论使用此值的系统和时区为何，它都会明确标识单个时间点。</span><span class="sxs-lookup"><span data-stu-id="3e868-136">Only if a [DateTime](xref:System.DateTime) value represents UTC does that value unambiguously identify a single point in time regardless of the system or time zone in which the value is used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e868-137">保存或共享 [DateTime](xref:System.DateTime) 数据时，应使用 UTC 并将 [DateTime](xref:System.DateTime) 值的 [Kind](xref:System.DateTime.Kind) 属性设置为 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)。</span><span class="sxs-lookup"><span data-stu-id="3e868-137">When saving or sharing [DateTime](xref:System.DateTime) data, UTC should be used and the [DateTime](xref:System.DateTime) value's [Kind](xref:System.DateTime.Kind) property should be set to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="the-datetimeoffset-structure"></a><span data-ttu-id="3e868-138">DateTimeOffset 结构</span><span class="sxs-lookup"><span data-stu-id="3e868-138">The DateTimeOffset structure</span></span>

<span data-ttu-id="3e868-139">[System.DateTimeOffset](xref:System.DateTimeOffset) 结构表示日期和时间值，以及指示此值与 UTC 的差异程度的偏移量。</span><span class="sxs-lookup"><span data-stu-id="3e868-139">The [System.DateTimeOffset](xref:System.DateTimeOffset) structure represents a date and time value, together with an offset that indicates how much that value differs from UTC.</span></span> <span data-ttu-id="3e868-140">因此，此值始终明确地标识单个时间点。</span><span class="sxs-lookup"><span data-stu-id="3e868-140">Thus, the value always unambiguously identifies a single point in time.</span></span> 

<span data-ttu-id="3e868-141">[DateTimeOffset](xref:System.DateTimeOffset) 类型包括 [DateTime](xref:System.DateTime) 类型的所有功能以及时区感知功能。</span><span class="sxs-lookup"><span data-stu-id="3e868-141">The [DateTimeOffset](xref:System.DateTimeOffset) type includes all of the functionality of the [DateTime](xref:System.DateTime) type along with time zone awareness.</span></span> <span data-ttu-id="3e868-142">这使它适用于执行以下操作的应用程序：</span><span class="sxs-lookup"><span data-stu-id="3e868-142">This makes it is suitable for applications that do the following:</span></span> 

* <span data-ttu-id="3e868-143">唯一、明确地标识单个时间点。</span><span class="sxs-lookup"><span data-stu-id="3e868-143">Uniquely and unambiguously identify a single point in time.</span></span> <span data-ttu-id="3e868-144">[DateTimeOffset](xref:System.DateTimeOffset) 类型可用于明确定义“现在”的含义、记录事务时间、记录系统或应用程序事件时间以及记录创建和修改时间。</span><span class="sxs-lookup"><span data-stu-id="3e868-144">The [DateTimeOffset](xref:System.DateTimeOffset) type can be used to unambiguously define the meaning of "now", to log transaction times, to log the times of system or application events, and to record file creation and modification times.</span></span> 

* <span data-ttu-id="3e868-145">执行常规日期和时间算法。</span><span class="sxs-lookup"><span data-stu-id="3e868-145">Perform general date and time arithmetic.</span></span>

* <span data-ttu-id="3e868-146">保留多个相关时间，只要这些时间存储为两个单独的值或结构中的两个成员。</span><span class="sxs-lookup"><span data-stu-id="3e868-146">Preserve multiple related times, as long as those times are stored as two separate values or as two members of a structure.</span></span>

> [!NOTE]
> <span data-ttu-id="3e868-147">[DateTimeOffset](xref:System.DateTimeOffset) 值的使用频率比 [DateTime](xref:System.DateTime) 值的更高。</span><span class="sxs-lookup"><span data-stu-id="3e868-147">These uses for [DateTimeOffset](xref:System.DateTimeOffset) values are much more common than those for [DateTime](xref:System.DateTime) values.</span></span> <span data-ttu-id="3e868-148">因此，在应用程序开发中应考虑使用 [DateTimeOffset](xref:System.DateTimeOffset) 作为默认日期和时间类型。</span><span class="sxs-lookup"><span data-stu-id="3e868-148">As a result, [DateTimeOffset](xref:System.DateTimeOffset) should be considered the default date and time type for application development.</span></span>

<span data-ttu-id="3e868-149">[DateTimeOffset](xref:System.DateTimeOffset) 值不限于特定时区，而可以来自各个时区。</span><span class="sxs-lookup"><span data-stu-id="3e868-149">A [DateTimeOffset](xref:System.DateTimeOffset) value is not tied to a particular time zone, but can originate from any of a variety of time zones.</span></span> <span data-ttu-id="3e868-150">为了说明这一点，以下示例列出了许多 [DateTimeOffset](xref:System.DateTimeOffset) 值（包括本地太平洋标准时间）可归属的时区。</span><span class="sxs-lookup"><span data-stu-id="3e868-150">To illustrate this, the following example lists the time zones to which a number of [DateTimeOffset](xref:System.DateTimeOffset) values (including a local Pacific Standard Time) can belong.</span></span>

```csharp
using System;
using System.Collections.ObjectModel;

public class TimeOffsets
{
   public static void Main()
   {
      DateTime thisDate = new DateTime(2007, 3, 10, 0, 0, 0);
      DateTime dstDate = new DateTime(2007, 6, 10, 0, 0, 0);
      DateTimeOffset thisTime;

      thisTime = new DateTimeOffset(dstDate, new TimeSpan(-7, 0, 0));
      ShowPossibleTimeZones(thisTime);

      thisTime = new DateTimeOffset(thisDate, new TimeSpan(-6, 0, 0));  
      ShowPossibleTimeZones(thisTime);

      thisTime = new DateTimeOffset(thisDate, new TimeSpan(+1, 0, 0));
      ShowPossibleTimeZones(thisTime);
   }

   private static void ShowPossibleTimeZones(DateTimeOffset offsetTime)
   {
      TimeSpan offset = offsetTime.Offset;
      ReadOnlyCollection<TimeZoneInfo> timeZones;

      Console.WriteLine("{0} could belong to the following time zones:", 
                        offsetTime.ToString());
      // Get all time zones defined on local system
      timeZones = TimeZoneInfo.GetSystemTimeZones();     
      // Iterate time zones 
      foreach (TimeZoneInfo timeZone in timeZones)
      {
         // Compare offset with offset for that date in that time zone
         if (timeZone.GetUtcOffset(offsetTime.DateTime).Equals(offset))
            Console.WriteLine("   {0}", timeZone.DisplayName);
      }
      Console.WriteLine();
   } 
}
// This example displays the following output to the console:
//       6/10/2007 12:00:00 AM -07:00 could belong to the following time zones:
//          (GMT-07:00) Arizona
//          (GMT-08:00) Pacific Time (US & Canada)
//          (GMT-08:00) Tijuana, Baja California
//       
//       3/10/2007 12:00:00 AM -06:00 could belong to the following time zones:
//          (GMT-06:00) Central America
//          (GMT-06:00) Central Time (US & Canada)
//          (GMT-06:00) Guadalajara, Mexico City, Monterrey - New
//          (GMT-06:00) Guadalajara, Mexico City, Monterrey - Old
//          (GMT-06:00) Saskatchewan
//       
//       3/10/2007 12:00:00 AM +01:00 could belong to the following time zones:
//          (GMT+01:00) Amsterdam, Berlin, Bern, Rome, Stockholm, Vienna
//          (GMT+01:00) Belgrade, Bratislava, Budapest, Ljubljana, Prague
//          (GMT+01:00) Brussels, Copenhagen, Madrid, Paris
//          (GMT+01:00) Sarajevo, Skopje, Warsaw, Zagreb
//          (GMT+01:00) West Central Africa
```

```vb
Imports System.Collections.ObjectModel

Module TimeOffsets
   Public Sub Main()
      Dim thisTime As DateTimeOffset 

      thisTime = New DateTimeOffset(#06/10/2007#, New TimeSpan(-7, 0, 0))
      ShowPossibleTimeZones(thisTime) 

      thisTime = New DateTimeOffset(#03/10/2007#, New TimeSpan(-6, 0, 0))  
      ShowPossibleTimeZones(thisTime)

      thisTime = New DateTimeOffset(#03/10/2007#, New TimeSpan(+1, 0, 0))
      ShowPossibleTimeZones(thisTime)
   End Sub

   Private Sub ShowPossibleTimeZones(offsetTime As DateTimeOffset)
      Dim offset As TimeSpan = offsetTime.Offset
      Dim timeZones As ReadOnlyCollection(Of TimeZoneInfo)

      Console.WriteLine("{0} could belong to the following time zones:", _
                        offsetTime.ToString())
      ' Get all time zones defined on local system
      timeZones = TimeZoneInfo.GetSystemTimeZones()     
      ' Iterate time zones
      For Each timeZone As TimeZoneInfo In timeZones
         ' Compare offset with offset for that date in that time zone
         If timeZone.GetUtcOffset(offsetTime.DateTime).Equals(offset) Then
            Console.WriteLine("   {0}", timeZone.DisplayName)
         End If   
      Next
      Console.WriteLine()
   End Sub
End Module
' This example displays the following output to the console:
'       6/10/2007 12:00:00 AM -07:00 could belong to the following time zones:
'          (GMT-07:00) Arizona
'          (GMT-08:00) Pacific Time (US & Canada)
'          (GMT-08:00) Tijuana, Baja California
'       
'       3/10/2007 12:00:00 AM -06:00 could belong to the following time zones:
'          (GMT-06:00) Central America
'          (GMT-06:00) Central Time (US & Canada)
'          (GMT-06:00) Guadalajara, Mexico City, Monterrey - New
'          (GMT-06:00) Guadalajara, Mexico City, Monterrey - Old
'          (GMT-06:00) Saskatchewan
'       
'       3/10/2007 12:00:00 AM +01:00 could belong to the following time zones:
'          (GMT+01:00) Amsterdam, Berlin, Bern, Rome, Stockholm, Vienna
'          (GMT+01:00) Belgrade, Bratislava, Budapest, Ljubljana, Prague
'          (GMT+01:00) Brussels, Copenhagen, Madrid, Paris
'          (GMT+01:00) Sarajevo, Skopje, Warsaw, Zagreb
'          (GMT+01:00) West Central Africa
```

<span data-ttu-id="3e868-151">输出显示，此示例中的每个日期和时间值至少可以属于三个不同时区。</span><span class="sxs-lookup"><span data-stu-id="3e868-151">The output shows that each date and time value in this example can belong to at least three different time zones.</span></span> <span data-ttu-id="3e868-152">2007 年 6 月 10 日的 [DateTimeOffset](xref:System.DateTimeOffset) 值显示，如果日期和时间值表示夏令时，则其相对于 UTC 的偏移量甚至不一定对应于原始时区的基本 UTC 偏移量或其显示名称中找到的相对于 UTC 的偏移量。</span><span class="sxs-lookup"><span data-stu-id="3e868-152">The [DateTimeOffset](xref:System.DateTimeOffset) value of 6/10/2007 shows that if a date and time value represents a daylight saving time, its offset from UTC does not even necessarily correspond to the originating time zone's base UTC offset or to the offset from UTC found in its display name.</span></span> <span data-ttu-id="3e868-153">这意味着，由于单个 [DateTimeOffset](xref:System.DateTimeOffset) 值并非与其时区紧密耦合，因此无法反映到/从夏令时的时区转换。</span><span class="sxs-lookup"><span data-stu-id="3e868-153">This means that, because a single [DateTimeOffset](xref:System.DateTimeOffset)  value is not tightly coupled with its time zone, it cannot reflect a time zone's transition to and from daylight saving time.</span></span> <span data-ttu-id="3e868-154">这在使用日期和时间算术操纵 [DateTimeOffset](xref:System.DateTimeOffset) 值时特别容易出现问题。</span><span class="sxs-lookup"><span data-stu-id="3e868-154">This can be particularly problematic when date and time arithmetic is used to manipulate a [DateTimeOffset](xref:System.DateTimeOffset) value.</span></span> <span data-ttu-id="3e868-155">有关如何以考虑时区调整规则的方式执行日期和时间算术运算的讨论，请参阅[执行日期和时间算术运算](performing-arithmetic-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="3e868-155">For a discussion of how to perform date and time arithmetic in a way that takes account of a time zone's adjustment rules, see [Performing arithmetic operations with dates and times](performing-arithmetic-operations.md).</span></span>

## <a name="the-timespan-structure"></a><span data-ttu-id="3e868-156">TimeSpan 结构</span><span class="sxs-lookup"><span data-stu-id="3e868-156">The TimeSpan structure</span></span>

<span data-ttu-id="3e868-157">[System.TimeSpan](xref:System.TimeSpan) 结构表示时间间隔。</span><span class="sxs-lookup"><span data-stu-id="3e868-157">The [System.TimeSpan](xref:System.TimeSpan) structure represents a time interval.</span></span> <span data-ttu-id="3e868-158">它的两个典型用途是：</span><span class="sxs-lookup"><span data-stu-id="3e868-158">Its two typical uses are:</span></span> 

* <span data-ttu-id="3e868-159">反映两个日期和时间值之间的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="3e868-159">Reflecting the time interval between two date and time values.</span></span> <span data-ttu-id="3e868-160">例如，两个 [DateTime](xref:System.DateTime) 值相减将返回 [TimeSpan](xref:System.TimeSpan) 值。</span><span class="sxs-lookup"><span data-stu-id="3e868-160">For example, subtracting one [DateTime](xref:System.DateTime) value from another returns a [TimeSpan](xref:System.TimeSpan) value.</span></span> 

* <span data-ttu-id="3e868-161">测量运行时间。</span><span class="sxs-lookup"><span data-stu-id="3e868-161">Measuring elapsed time.</span></span> <span data-ttu-id="3e868-162">例如，[Stopwatch.Elapsed](xref:System.Diagnostics.Stopwatch.Elapsed) 属性返回 [TimeSpan](xref:System.TimeSpan) 值，此值反映自调用开始测量运行时间的其中一种 [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch) 方法起所经过的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="3e868-162">For example, the [Stopwatch.Elapsed](xref:System.Diagnostics.Stopwatch.Elapsed) property returns a [TimeSpan](xref:System.TimeSpan) value that reflects the time interval that has elapsed since the call to one of the [System.Diagnostics.Stopwatch](xref:System.Diagnostics.Stopwatch) methods that begins to measure elapsed time.</span></span>

<span data-ttu-id="3e868-163">[TimeSpan](xref:System.TimeSpan) 值还可用于在 [DateTime](xref:System.DateTime) 值反映某一时间而不引用某天的特定时间时替代它。</span><span class="sxs-lookup"><span data-stu-id="3e868-163">A [TimeSpan](xref:System.TimeSpan) value can also be used as a replacement for a [DateTime](xref:System.DateTime) value when that value reflects a time without reference to a particular time of day.</span></span> <span data-ttu-id="3e868-164">这种用法类似于 [DateTime.TimeOfDay](xref:System.DateTime.TimeOfDay) 和 [DateTimeOffset.TimeOfDay](xref:System.DateTimeOffset.TimeOfDay) 属性，它们返回表示未引用日期的时间的 [TimeSpan](xref:System.TimeSpan) 值。</span><span class="sxs-lookup"><span data-stu-id="3e868-164">This usage is similar to the [DateTime.TimeOfDay](xref:System.DateTime.TimeOfDay) and [DateTimeOffset.TimeOfDay](xref:System.DateTimeOffset.TimeOfDay) properties, which return a [TimeSpan](xref:System.TimeSpan) value that represents the time without reference to a date.</span></span> <span data-ttu-id="3e868-165">例如，[TimeSpan](xref:System.TimeSpan) 结构可用于反映商店每天的开张或打烊时间，还可用来表示任何常规事件发生的时间。</span><span class="sxs-lookup"><span data-stu-id="3e868-165">For example, the [TimeSpan](xref:System.TimeSpan) structure can be used to reflect a store's daily opening or closing time, or it can be used to represent the time at which any regular event occurs.</span></span>

<span data-ttu-id="3e868-166">以下示例定义了 `StoreInfo` 结构，其中包含表示商店开张或打烊时间的 [TimeSpan](xref:System.TimeSpan) 对象，以及表示商店所在时区的 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象。</span><span class="sxs-lookup"><span data-stu-id="3e868-166">The following example defines a `StoreInfo` structure that includes [TimeSpan](xref:System.TimeSpan) objects for store opening and closing times, as well as a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents the store's time zone.</span></span> <span data-ttu-id="3e868-167">此结构还包含两个方法（`IsOpenNow` 和 `IsOpenAt`），用于指示假定用户处于本地时区时其所指定的时间商店是否开张。</span><span class="sxs-lookup"><span data-stu-id="3e868-167">The structure also includes two methods, `IsOpenNow` and `IsOpenAt`, that indicates whether the store is open at a time specified by the user, who is assumed to be in the local time zone.</span></span>  

```csharp
using System;

public struct StoreInfo
{
   public String store;
   public TimeZoneInfo tz;
   public TimeSpan open;
   public TimeSpan close;

   public bool IsOpenNow()
   {
      return IsOpenAt(DateTime.TimeOfDay);
   }

   public bool IsOpenAt(TimeSpan time)
   {
      TimeZoneInfo local = TimeZoneInfo.Local;
      TimeSpan offset = TimeZoneInfo.BaseUtcOffset;

      // Is the store in the same time zone?
      if (tz.Equals(local)) {
         return time >= open & time <= close;
      }
   }
}
```

```vb
Public Structure StoreInfo
   Dim store As String
   Dim tz As TimeZoneInfo
   Dim open As TimeSpan
   Dim close As TimeSpan

   Public Function IsOpenNow() As Boolean
      Return IsOpenAt(Date.Now.TimeOfDay)
   End Function

   Public Function IsOpenAt(time As TimeSpan) As Boolean
      Dim local As TimeZoneInfo = TimeZoneInfo.Local
      Dim offset As TimeSpan = TimeZoneInfo.Local.BaseUtcOffset

      ' Is the store in the same time zone?
      If tz.Equals(local) Then
         Return time >= open And time <= close
      Else
         Dim delta As TimeSpan = TimeSpan.Zero
         Dim storeDelta As TimeSpan = TimeSpan.Zero

         ' Is it daylight saving time in either time zone?
         If local.IsDaylightSavingTime(Date.Now.Date + time) Then
            delta = local.GetAdjustmentRules(local.GetAdjustmentRules().Length - 1).DaylightDelta
         End If
         If tz.IsDaylightSavingTime(TimeZoneInfo.ConvertTime(Date.Now.Date + time, local, tz))
            storeDelta = tz.GetAdjustmentRules(local.GetAdjustmentRules().Length - 1).DaylightDelta
         End If
         Dim comparisonTime As TimeSpan = time + (offset - tz.BaseUtcOffset).Negate() + (delta - storeDelta).Negate
         Return (comparisonTime >= open And comparisonTime <= close)
      End If
   End Function
End Structure
```

<span data-ttu-id="3e868-168">随后，`StoreInfo` 结构可由客户端代码按如下方式使用。</span><span class="sxs-lookup"><span data-stu-id="3e868-168">The `StoreInfo` structure can then be used by client code like the following.</span></span> 

```csharp
public class Example
{
   public static void Main()
   {
      // Instantiate a StoreInfo object.
      var store103 = new StoreInfo();
      store103.store = "Store #103";
      store103.tz = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time");
      // Store opens at 8:00.
      store103.open = new TimeSpan(8, 0, 0);
      // Store closes at 9:30.
      store103.close = new TimeSpan(21, 30, 0);

      Console.WriteLine("Store is open now at {0}: {1}",
                        DateTime.TimeOfDay, store103.IsOpenNow());
      TimeSpan[] times = { new TimeSpan(8, 0, 0), new TimeSpan(21, 0, 0),
                           new TimeSpan(4, 59, 0), new TimeSpan(18, 31, 0) };
      foreach (var time in times)
         Console.WriteLine("Store is open at {0}: {1}",
                           time, store103.IsOpenAt(time));
   }
}
// The example displays the following output:
//       Store is open now at 15:29:01.6129911: True
//       Store is open at 08:00:00: True
//       Store is open at 21:00:00: False
//       Store is open at 04:59:00: False
//       Store is open at 18:31:00: False
```

```vb
Module Example
   Public Sub Main()
      ' Instantiate a StoreInfo object.
      Dim store103 As New StoreInfo()
      store103.store = "Store #103"
      store103.tz = TimeZoneInfo.FindSystemTimeZoneById("Eastern Standard Time")
      ' Store opens at 8:00.
      store103.open = new TimeSpan(8, 0, 0)
      ' Store closes at 9:30.
      store103.close = new TimeSpan(21, 30, 0)

      Console.WriteLine("Store is open now at {0}: {1}",
                        Date.Now.TimeOfDay, store103.IsOpenNow())
      Dim times() As TimeSpan = { New TimeSpan(8, 0, 0),
                                  New TimeSpan(21, 0, 0),
                                  New TimeSpan(4, 59, 0),
                                  New TimeSpan(18, 31, 0) }
      For Each time In times
         Console.WriteLine("Store is open at {0}: {1}",
                           time, store103.IsOpenAt(time))
      Next
   End Sub
End Module
' The example displays the following output:
'       Store is open now at 15:29:01.6129911: True
'       Store is open at 08:00:00: True
'       Store is open at 21:00:00: False
'       Store is open at 04:59:00: False
'       Store is open at 18:31:00: False
```

## <a name="the-timezoneinfo-class"></a><span data-ttu-id="3e868-169">TimeZoneInfo 类</span><span class="sxs-lookup"><span data-stu-id="3e868-169">The TimeZoneInfo class</span></span>

<span data-ttu-id="3e868-170">[System.TimeZoneInfo](xref:System.TimeZoneInfo) 类表示地球上的任何时区，并可将一个时区的任何日期和时间转换为其他时区的对等日期和时间。</span><span class="sxs-lookup"><span data-stu-id="3e868-170">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class represents any of the earth's time zones, and enables the conversion of any date and time in one time zone to its equivalent in another time zone.</span></span> <span data-ttu-id="3e868-171">借助 [TimeZoneInfo](xref:System.TimeZoneInfo) 类，即可处理日期和时间，以使任何日期和时间值均明确标识单个时间点。</span><span class="sxs-lookup"><span data-stu-id="3e868-171">The [TimeZoneInfo](xref:System.TimeZoneInfo) class makes it possible to work with dates and times so that any date and time value unambiguously identifies a single point in time.</span></span>

<span data-ttu-id="3e868-172">在某些情况下，可能需要进一步的开发工作才可以充分利用 [TimeZoneInfo](xref:System.TimeZoneInfo) 类。</span><span class="sxs-lookup"><span data-stu-id="3e868-172">In some cases, taking full advantage of the [TimeZoneInfo](xref:System.TimeZoneInfo) class may require further development work.</span></span> <span data-ttu-id="3e868-173">日期和时间值不与其所属的时区紧密耦合。</span><span class="sxs-lookup"><span data-stu-id="3e868-173">Date and time values are not tightly coupled with the time zones to which they belong.</span></span> <span data-ttu-id="3e868-174">因此，除非你的应用程序可提供某种机制将日期和时间与其关联的时区链接，否则特定日期和时间值很容易与其所属时区失去关联。</span><span class="sxs-lookup"><span data-stu-id="3e868-174">As a result, unless your application provides some mechanism for linking a date and time with its associated time zone, it is easy for a particular date and time value to become disassociated from its time zone.</span></span> <span data-ttu-id="3e868-175">链接此信息的一种方法是，定义一个同时包含日期和时间值及其关联时区对象的类或结构。</span><span class="sxs-lookup"><span data-stu-id="3e868-175">One method of linking this information is to define a class or structure that contains both the date and time value and its associated time zone object.</span></span>

<span data-ttu-id="3e868-176">仅当日期和时间对象实例化时其值所属的时区已知，才可使用 .NET 中的时区支持。</span><span class="sxs-lookup"><span data-stu-id="3e868-176">Taking advantage of time zone support in .NET is possible only if the time zone to which a date and time value belongs is known when that date and time object is instantiated.</span></span> <span data-ttu-id="3e868-177">这通情况并非如此，尤其是在 Web 或网络应用程序中。</span><span class="sxs-lookup"><span data-stu-id="3e868-177">This is often not the case, particularly in Web or network applications.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e868-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e868-178">See Also</span></span>

[<span data-ttu-id="3e868-179">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="3e868-179">Dates, times, and time zones</span></span>](index.md)

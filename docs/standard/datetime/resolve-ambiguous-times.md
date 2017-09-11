---
title: "如何：解决不明确时间"
description: "如何解决不明确时间"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e86050c6-d16d-405e-8bba-7205945c9a81
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f4ab3b4bf3487e70be7e885e9b8a2281927eb30e
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="74f3f-104">如何：解决不明确时间</span><span class="sxs-lookup"><span data-stu-id="74f3f-104">How to: resolve ambiguous times</span></span>

<span data-ttu-id="74f3f-105">不明确时间是指映射到多个协调世界时 (UTC) 的时间。</span><span class="sxs-lookup"><span data-stu-id="74f3f-105">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="74f3f-106">在向后调整时钟时间时，例如从时区的夏令时调整到标准时间这段转换期间，便会出现不明确时间。</span><span class="sxs-lookup"><span data-stu-id="74f3f-106">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="74f3f-107">在处理不明确时间时，可执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="74f3f-107">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="74f3f-108">假设一下时间如何映射到 UTC。</span><span class="sxs-lookup"><span data-stu-id="74f3f-108">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="74f3f-109">例如，可以假定不明确时间始终以时区的标准时间表示。</span><span class="sxs-lookup"><span data-stu-id="74f3f-109">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="74f3f-110">如果不明确时间是用户输入的数据项，则可以让用户自行解决。</span><span class="sxs-lookup"><span data-stu-id="74f3f-110">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="74f3f-111">本文介绍如何通过假定不明确时间表示时区的标准时间，来解决不明确时间。</span><span class="sxs-lookup"><span data-stu-id="74f3f-111">This article shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

## <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="74f3f-112">将不明确时间映射到时区的标准时间</span><span class="sxs-lookup"><span data-stu-id="74f3f-112">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="74f3f-113">调用 [System.TimeZoneInfo.IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) 或 [System.TimeZoneInfo.IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) 方法，确定时间是否不明确。</span><span class="sxs-lookup"><span data-stu-id="74f3f-113">Call the [System.TimeZoneInfo.IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) or [System.TimeZoneInfo.IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="74f3f-114">如果时间不明确，请从时区的 [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) 属性返回的 [TimeSpan](xref:System.TimeSpan) 对象减去该时间。</span><span class="sxs-lookup"><span data-stu-id="74f3f-114">If the time is ambiguous, subtract the time from the [TimeSpan](xref:System.TimeSpan) object returned by the time zone's [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property.</span></span>

3. <span data-ttu-id="74f3f-115">调用 `static`（Visual Basic 中的 `Shared`）[SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) 方法，将 UTC 日期和时间值的 [Kind](xref:System.DateTime.Kind) 属性设置为 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)。</span><span class="sxs-lookup"><span data-stu-id="74f3f-115">Call the `static` (`Shared` in Visual Basic) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method to set the UTC date and time value's [Kind](xref:System.DateTime.Kind) property to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="example"></a><span data-ttu-id="74f3f-116">示例</span><span class="sxs-lookup"><span data-stu-id="74f3f-116">Example</span></span>

<span data-ttu-id="74f3f-117">以下示例阐述如何通过假定不明确时间表示本地时区的标准时间，将不明确的 [DateTime](xref:System.DateTime) 转换为 UTC。</span><span class="sxs-lookup"><span data-stu-id="74f3f-117">The following example illustrates how to convert an ambiguous [DateTime](xref:System.DateTime) to UTC by assuming that it represents the local time zone's standard time.</span></span> 

```csharp
private DateTime ResolveAmbiguousTime(DateTime ambiguousTime)
{
   // Time is not ambiguous
   if (! TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime))
   { 
      return ambiguousTime; 
   }
   // Time is ambiguous
   else
   {
      DateTime utcTime = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, 
                                              DateTimeKind.Utc);      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", 
                        ambiguousTime, utcTime, utcTime.Kind.ToString());
      return utcTime;            
   }   
}
```

```vb
Private Function ResolveAmbiguousTime(ambiguousTime As Date) As Date
   ' Time is not ambiguous
   If Not TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime) Then 
      Return TimeZoneInfo.ConvertTimeToUtc(ambiguousTime) 
   ' Time is ambiguous
   Else
      Dim utcTime As Date = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, DateTimeKind.Utc)      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", ambiguousTime, utcTime, utcTime.Kind.ToString())
      Return utcTime            
   End If   
End Function
```

<span data-ttu-id="74f3f-118">此示例包含一个名为 `ResolveAmbiguousTime` 的方法，该方法可确定传递到它的 [DateTime](xref:System.DateTime) 值是否不明确。</span><span class="sxs-lookup"><span data-stu-id="74f3f-118">The example consists of a method named `ResolveAmbiguousTime` that determines whether the [DateTime](xref:System.DateTime) value passed to it is ambiguous.</span></span> <span data-ttu-id="74f3f-119">如果值不明确，则该方法会返回一个表示相应 UTC 时间的 [DateTime](xref:System.DateTime) 值。</span><span class="sxs-lookup"><span data-stu-id="74f3f-119">If the value is ambiguous, the method returns a [DateTime](xref:System.DateTime) value that represents the corresponding UTC time.</span></span> <span data-ttu-id="74f3f-120">该方法通过从本地时间减去本地时区的 [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) 属性的值，来处理此转换。</span><span class="sxs-lookup"><span data-stu-id="74f3f-120">The method handles this conversion by subtracting the value of the local time zone's [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property from the local time.</span></span> 

<span data-ttu-id="74f3f-121">通常，通过调用 [GetAmbiguousTimeOffsets](xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets(System.DateTime)) 方法检索一组 [TimeSpan](xref:System.TimeSpan) 对象（其中包含不明确时间与 UTC 可能的时差），来处理不明确时间。</span><span class="sxs-lookup"><span data-stu-id="74f3f-121">Ordinarily, an ambiguous time is handled by calling the [GetAmbiguousTimeOffsets](xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets(System.DateTime)) method to retrieve an array of [TimeSpan](xref:System.TimeSpan) objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="74f3f-122">但是，本示例建立在一个大胆假设之上，即不明确时间始终映射到时区的标准时间。</span><span class="sxs-lookup"><span data-stu-id="74f3f-122">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="74f3f-123">[BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) 属性返回 UTC 与时区的标准时间之间的时差。</span><span class="sxs-lookup"><span data-stu-id="74f3f-123">The [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property returns the offset between UTC and a time zone's standard time.</span></span>

## <a name="see-also"></a><span data-ttu-id="74f3f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74f3f-124">See Also</span></span>

[<span data-ttu-id="74f3f-125">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="74f3f-125">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="74f3f-126">如何：让用户解决不明确时间</span><span class="sxs-lookup"><span data-stu-id="74f3f-126">How to: let users resolve ambiguous times</span></span>](let-users-resolve-ambiguous-times.md)



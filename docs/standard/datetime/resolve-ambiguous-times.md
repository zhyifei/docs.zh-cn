---
title: 如何： 解决不明确的时间
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a92081a164d15e5150c582b37c6c688cd15e619e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571194"
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="5ed93-102">如何： 解决不明确的时间</span><span class="sxs-lookup"><span data-stu-id="5ed93-102">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="5ed93-103">不明确时间是指映射到多个协调世界时 (UTC) 的时间。</span><span class="sxs-lookup"><span data-stu-id="5ed93-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="5ed93-104">在向后调整时钟时间时，例如从时区的夏令时调整到标准时间这段转换期间，便会出现不明确时间。</span><span class="sxs-lookup"><span data-stu-id="5ed93-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="5ed93-105">在处理不明确时间时，可执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="5ed93-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="5ed93-106">假设一下时间如何映射到 UTC。</span><span class="sxs-lookup"><span data-stu-id="5ed93-106">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="5ed93-107">例如，可以假定不明确时间始终以时区的标准时间表示。</span><span class="sxs-lookup"><span data-stu-id="5ed93-107">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

* <span data-ttu-id="5ed93-108">如果不明确时间是用户输入的数据项，则可以让用户自行解决。</span><span class="sxs-lookup"><span data-stu-id="5ed93-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="5ed93-109">本主题说明如何解决由不明确的时间，前提是它表示时区的标准时间。</span><span class="sxs-lookup"><span data-stu-id="5ed93-109">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="5ed93-110">将不明确时间映射到时区的标准时间</span><span class="sxs-lookup"><span data-stu-id="5ed93-110">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="5ed93-111">调用<xref:System.TimeZoneInfo.IsAmbiguousTime%2A>方法来确定时间是否不明确。</span><span class="sxs-lookup"><span data-stu-id="5ed93-111">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="5ed93-112">如果所不明确的时间，减去的时间<xref:System.TimeSpan>对象返回的时区的<xref:System.TimeZoneInfo.BaseUtcOffset%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="5ed93-112">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="5ed93-113">调用`static`(`Shared`在 Visual Basic.NET)<xref:System.DateTime.SpecifyKind%2A>方法以设置的 UTC 日期和时间值的<xref:System.DateTime.Kind%2A>属性<xref:System.DateTimeKind.Utc?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="5ed93-113">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="5ed93-114">示例</span><span class="sxs-lookup"><span data-stu-id="5ed93-114">Example</span></span>

<span data-ttu-id="5ed93-115">下面的示例演示如何将明确的时间转换为 UTC，前提是它表示本地时区的标准时间。</span><span class="sxs-lookup"><span data-stu-id="5ed93-115">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="5ed93-116">此示例由一个名为方法组成`ResolveAmbiguousTime`，它确定是否<xref:System.DateTime>传递给它的值是不明确。</span><span class="sxs-lookup"><span data-stu-id="5ed93-116">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="5ed93-117">如果值是不明确的该方法返回<xref:System.DateTime>值，该值表示相应的 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="5ed93-117">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="5ed93-118">该方法减去的本地时区的值来处理此转换<xref:System.TimeZoneInfo.BaseUtcOffset%2A>属性从本地时间。</span><span class="sxs-lookup"><span data-stu-id="5ed93-118">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="5ed93-119">通常，由不明确的时间调用<xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A>方法来检索其中的数组<xref:System.TimeSpan>对象，其中包含不明确的时间可能的 UTC 偏移量。</span><span class="sxs-lookup"><span data-stu-id="5ed93-119">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="5ed93-120">但是，本示例建立在一个大胆假设之上，即不明确时间始终映射到时区的标准时间。</span><span class="sxs-lookup"><span data-stu-id="5ed93-120">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="5ed93-121"><xref:System.TimeZoneInfo.BaseUtcOffset%2A>属性返回 UTC 和时区的标准时间之间的偏移量。</span><span class="sxs-lookup"><span data-stu-id="5ed93-121">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="5ed93-122">在此示例中，对本地时区的所有引用都都通过<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>属性; 区域永远不会分配给对象变量的本地时间。</span><span class="sxs-lookup"><span data-stu-id="5ed93-122">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="5ed93-123">这是建议的做法，因为调用<xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>方法失效的本地时区分配给任何对象。</span><span class="sxs-lookup"><span data-stu-id="5ed93-123">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="5ed93-124">编译代码</span><span class="sxs-lookup"><span data-stu-id="5ed93-124">Compiling the code</span></span>

<span data-ttu-id="5ed93-125">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="5ed93-125">This example requires:</span></span>

* <span data-ttu-id="5ed93-126">对 System.Core.dll 的引用无法添加到项目。</span><span class="sxs-lookup"><span data-stu-id="5ed93-126">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="5ed93-127"><xref:System>命名空间导入`using`语句 （C# 代码中需要）。</span><span class="sxs-lookup"><span data-stu-id="5ed93-127">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="5ed93-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ed93-128">See also</span></span>

<span data-ttu-id="5ed93-129">[日期、 时间和时区](../../../docs/standard/datetime/index.md)
[How to： 让用户解决不明确的时间](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)</span><span class="sxs-lookup"><span data-stu-id="5ed93-129">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Let users resolve ambiguous times](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)</span></span>

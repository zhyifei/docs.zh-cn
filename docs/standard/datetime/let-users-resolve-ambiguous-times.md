---
title: 如何： 让用户解决不明确时间
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91e80f44934092007f6f842f0694789d49321446
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863546"
---
# <a name="how-to-let-users-resolve-ambiguous-times"></a><span data-ttu-id="25ee3-102">如何： 让用户解决不明确时间</span><span class="sxs-lookup"><span data-stu-id="25ee3-102">How to: Let users resolve ambiguous times</span></span>

<span data-ttu-id="25ee3-103">不明确时间是指映射到多个协调世界时 (UTC) 的时间。</span><span class="sxs-lookup"><span data-stu-id="25ee3-103">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="25ee3-104">在向后调整时钟时间时，例如从时区的夏令时调整到标准时间这段转换期间，便会出现不明确时间。</span><span class="sxs-lookup"><span data-stu-id="25ee3-104">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="25ee3-105">在处理不明确时间时，可执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="25ee3-105">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="25ee3-106">如果不明确时间是用户输入的数据项，则可以让用户自行解决。</span><span class="sxs-lookup"><span data-stu-id="25ee3-106">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

* <span data-ttu-id="25ee3-107">假设一下时间如何映射到 UTC。</span><span class="sxs-lookup"><span data-stu-id="25ee3-107">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="25ee3-108">例如，可以假定不明确时间始终以时区的标准时间表示。</span><span class="sxs-lookup"><span data-stu-id="25ee3-108">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

<span data-ttu-id="25ee3-109">本主题演示如何让用户解决不明确时间。</span><span class="sxs-lookup"><span data-stu-id="25ee3-109">This topic shows how to let a user resolve an ambiguous time.</span></span>

### <a name="to-let-a-user-resolve-an-ambiguous-time"></a><span data-ttu-id="25ee3-110">让用户解决不明确时间</span><span class="sxs-lookup"><span data-stu-id="25ee3-110">To let a user resolve an ambiguous time</span></span>

1. <span data-ttu-id="25ee3-111">获取用户输入的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="25ee3-111">Get the date and time input by the user.</span></span>

2. <span data-ttu-id="25ee3-112">调用<xref:System.TimeZoneInfo.IsAmbiguousTime%2A>方法，以确定时间是否不明确。</span><span class="sxs-lookup"><span data-stu-id="25ee3-112">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

3. <span data-ttu-id="25ee3-113">如果时间不明确，则调用<xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A>方法来检索其中的数组<xref:System.TimeSpan>对象。</span><span class="sxs-lookup"><span data-stu-id="25ee3-113">If the time is ambiguous, call the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects.</span></span> <span data-ttu-id="25ee3-114">数组中的每个元素包含不明确时间可以映射到的 UTC 偏移量。</span><span class="sxs-lookup"><span data-stu-id="25ee3-114">Each element in the array contains a UTC offset that the ambiguous time can map to.</span></span>

4. <span data-ttu-id="25ee3-115">让用户选择所需时差。</span><span class="sxs-lookup"><span data-stu-id="25ee3-115">Let the user select the desired offset.</span></span>

5. <span data-ttu-id="25ee3-116">用本地时间减去用户所选时差，得出 UTC 日期和时间。</span><span class="sxs-lookup"><span data-stu-id="25ee3-116">Get the UTC date and time by subtracting the offset selected by the user from the local time.</span></span>

6. <span data-ttu-id="25ee3-117">调用`static`(`Shared`在 Visual Basic.NET)<xref:System.DateTime.SpecifyKind%2A>方法设置的 UTC 日期和时间值的<xref:System.DateTime.Kind%2A>属性设置为<xref:System.DateTimeKind.Utc?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="25ee3-117">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="25ee3-118">示例</span><span class="sxs-lookup"><span data-stu-id="25ee3-118">Example</span></span>

<span data-ttu-id="25ee3-119">以下示例将提示用户输入日期和时间，如果时间不明确，会让用户选择不明确时间映射到的 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="25ee3-119">The following example prompts the user to enter a date and time and, if it is ambiguous, lets the user select the UTC time that the ambiguous time maps to.</span></span>

[!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
[!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]

<span data-ttu-id="25ee3-120">示例代码的核心使用一组<xref:System.TimeSpan>对象，来指示可能不明确时间与 UTC 的时差。</span><span class="sxs-lookup"><span data-stu-id="25ee3-120">The core of the example code uses an array of <xref:System.TimeSpan> objects to indicate possible offsets of the ambiguous time from UTC.</span></span> <span data-ttu-id="25ee3-121">但是，这些时差值对用户可能没有什么意义。</span><span class="sxs-lookup"><span data-stu-id="25ee3-121">However, these offsets are unlikely to be meaningful to the user.</span></span> <span data-ttu-id="25ee3-122">为了阐明时差的含义，该代码还会指示时差是表示本地时区的标准时间还是其夏令时。</span><span class="sxs-lookup"><span data-stu-id="25ee3-122">To clarify the meaning of the offsets, the code also notes whether an offset represents the local time zone's standard time or its daylight saving time.</span></span> <span data-ttu-id="25ee3-123">该代码将确定哪个是标准时间，哪个是夏令时进行比较的值的偏移量<xref:System.TimeZoneInfo.BaseUtcOffset%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="25ee3-123">The code determines which time is standard and which time is daylight by comparing the offset with the value of the <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span> <span data-ttu-id="25ee3-124">此属性指示 UTC 与时区的标准时间之差。</span><span class="sxs-lookup"><span data-stu-id="25ee3-124">This property indicates the difference between the UTC and the time zone's standard time.</span></span>

<span data-ttu-id="25ee3-125">在此示例中，对本地时区的所有引用都都通过<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>属性; 区域永远不会分配给对象变量的本地时间。</span><span class="sxs-lookup"><span data-stu-id="25ee3-125">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="25ee3-126">这是建议的做法，因为调用<xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>方法使本地时区分配给任何对象无效。</span><span class="sxs-lookup"><span data-stu-id="25ee3-126">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="25ee3-127">编译代码</span><span class="sxs-lookup"><span data-stu-id="25ee3-127">Compiling the code</span></span>

<span data-ttu-id="25ee3-128">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="25ee3-128">This example requires:</span></span>

* <span data-ttu-id="25ee3-129">包含对 System.Core.dll 的引用添加到项目。</span><span class="sxs-lookup"><span data-stu-id="25ee3-129">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="25ee3-130">是否<xref:System>命名空间导入与`using`语句 （C# 代码中需要）。</span><span class="sxs-lookup"><span data-stu-id="25ee3-130">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="25ee3-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="25ee3-131">See also</span></span>

* [<span data-ttu-id="25ee3-132">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="25ee3-132">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
* [<span data-ttu-id="25ee3-133">如何：解析不明确时间</span><span class="sxs-lookup"><span data-stu-id="25ee3-133">How to: Resolve ambiguous times</span></span>](../../../docs/standard/datetime/resolve-ambiguous-times.md)

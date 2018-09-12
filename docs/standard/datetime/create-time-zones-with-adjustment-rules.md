---
title: 如何： 创建含调整规则的时区
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], creating
- time zones [.NET Framework], and adjustment rules
- adjustment rule [.NET Framework]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80a5c04f7807638a4a8b114828083835f348ac08
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2018
ms.locfileid: "44494130"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a><span data-ttu-id="3e1eb-102">如何： 创建含调整规则的时区</span><span class="sxs-lookup"><span data-stu-id="3e1eb-102">How to: Create time zones with adjustment rules</span></span>

<span data-ttu-id="3e1eb-103">应用程序所需的精确的时区信息可能不存在的特定系统上有几个原因：</span><span class="sxs-lookup"><span data-stu-id="3e1eb-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

* <span data-ttu-id="3e1eb-104">永远不会在本地系统注册表中定义的时区。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-104">The time zone has never been defined in the local system's registry.</span></span>

* <span data-ttu-id="3e1eb-105">有关时区的数据已修改或从注册表中删除。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-105">Data about the time zone has been modified or removed from the registry.</span></span>

* <span data-ttu-id="3e1eb-106">时区没有特定的历史时期时区调整的准确信息。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-106">The time zone does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="3e1eb-107">在这些情况下，您可以调用<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>方法以定义你的应用程序所需的时区。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="3e1eb-108">可以使用此方法的重载来创建带有或不带调整规则的时区。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="3e1eb-109">如果时区支持夏令时，则可以定义与任一固定或浮动调整规则的调整。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="3e1eb-110">(有关这些术语的定义，请参阅中的"时区术语"一节[时区概述](../../../docs/standard/datetime/time-zone-overview.md)。)</span><span class="sxs-lookup"><span data-stu-id="3e1eb-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e1eb-111">通过调用创建的自定义时区<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>方法不会添加到注册表。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="3e1eb-112">相反，它们可以访问只能通过返回的对象引用<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>方法调用。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="3e1eb-113">本主题演示如何创建含调整规则的时区。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-113">This topic shows how to create a time zone with adjustment rules.</span></span> <span data-ttu-id="3e1eb-114">若要创建不支持夏令时调整规则的时区，请参阅[如何： 创建调整规则无需时区](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-114">To create a time zone that does not support daylight saving time adjustment rules, see [How to: Create Time Zones Without Adjustment Rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a><span data-ttu-id="3e1eb-115">若要创建带浮动调整规则的时区</span><span class="sxs-lookup"><span data-stu-id="3e1eb-115">To create a time zone with floating adjustment rules</span></span>

1. <span data-ttu-id="3e1eb-116">对于每次调整 （即，对于每个转换离开并段特定时间间隔内回标准时间），执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3e1eb-116">For each adjustment (that is, for each transition away from and back to standard time over a particular time interval), do the following:</span></span>

    1. <span data-ttu-id="3e1eb-117">定义时区调整的起始过渡时间。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-117">Define the starting transition time for the time zone adjustment.</span></span>

       <span data-ttu-id="3e1eb-118">必须调用<xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType>方法并将其传递<xref:System.DateTime>值，该值定义的转换、 一个整数值，定义的转换的月、 一个整数值，定义转换发生的一周的时间和<xref:System.DayOfWeek>定义在转换发生星期几的值。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-118">You must call the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> method and pass it a <xref:System.DateTime> value that defines the time of the transition, an integer value that defines the month of the transition, an integer value that defines the week on which the transition occurs, and a <xref:System.DayOfWeek> value that defines the day of the week on which the transition occurs.</span></span> <span data-ttu-id="3e1eb-119">此方法调用实例化<xref:System.TimeZoneInfo.TransitionTime>对象。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-119">This method call instantiates a <xref:System.TimeZoneInfo.TransitionTime> object.</span></span>

    2. <span data-ttu-id="3e1eb-120">定义时区调整的结束转换时间。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-120">Define the ending transition time for the time zone adjustment.</span></span> <span data-ttu-id="3e1eb-121">这要求对另一个调用<xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-121">This requires another call to the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3e1eb-122">此方法调用实例化第二个<xref:System.TimeZoneInfo.TransitionTime>对象。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-122">This method call instantiates a second <xref:System.TimeZoneInfo.TransitionTime> object.</span></span>

    3. <span data-ttu-id="3e1eb-123">调用<xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A>方法并将其传递的有效起始和结束日期的调整，<xref:System.TimeSpan>对象，它在转换和两个定义的时间量<xref:System.TimeZoneInfo.TransitionTime>对象，用于定义何时与夏令时的转换时间日期/时间。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-123">Call the <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> method and pass it the effective start and end dates of the adjustment, a <xref:System.TimeSpan> object that defines the amount of time in the transition, and the two <xref:System.TimeZoneInfo.TransitionTime> objects that define when the transitions to and from daylight saving time occur.</span></span> <span data-ttu-id="3e1eb-124">此方法调用实例化<xref:System.TimeZoneInfo.AdjustmentRule>对象。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-124">This method call instantiates a <xref:System.TimeZoneInfo.AdjustmentRule> object.</span></span>

    4. <span data-ttu-id="3e1eb-125">将分配<xref:System.TimeZoneInfo.AdjustmentRule>对象的数组<xref:System.TimeZoneInfo.AdjustmentRule>对象。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-125">Assign the <xref:System.TimeZoneInfo.AdjustmentRule> object to an array of <xref:System.TimeZoneInfo.AdjustmentRule> objects.</span></span>

2. <span data-ttu-id="3e1eb-126">定义时区的显示名称。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-126">Define the time zone's display name.</span></span> <span data-ttu-id="3e1eb-127">显示名称应遵循相当标准的格式时区的偏移量从协调世界时 (UTC) 括在括号中后, 跟一个字符串，标识一个或多个城市中时区，或其中一个或多个 cou 时区ntries 或时区中的区域。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-127">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

3. <span data-ttu-id="3e1eb-128">定义时区的标准时间的名称。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-128">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="3e1eb-129">通常情况下，此字符串还用作时区的标识符。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-129">Typically, this string is also used as the time zone's identifier.</span></span>

4. <span data-ttu-id="3e1eb-130">定义时区的夏时制时间的名称。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-130">Define the name of the time zone's daylight time.</span></span>

5. <span data-ttu-id="3e1eb-131">如果你想要使用其他标识符，于时区的标准名称，定义的时区标识符。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-131">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

6. <span data-ttu-id="3e1eb-132">实例化<xref:System.TimeSpan>对象，用于定义相对于 UTC 的时区的偏移量。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-132">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="3e1eb-133">时间晚于 UTC 的时区具有负偏移量。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-133">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="3e1eb-134">时间早于 UTC 的时区具有负偏移量。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-134">Time zones with times that are earlier than UTC have a negative offset.</span></span>

7. <span data-ttu-id="3e1eb-135">调用<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType>方法可实例化新的时区。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-135">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="3e1eb-136">示例</span><span class="sxs-lookup"><span data-stu-id="3e1eb-136">Example</span></span>

<span data-ttu-id="3e1eb-137">下面的示例定义为包括从 1918年到最新的时间间隔的多个调整规则的美国中部标准时区。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-137">The following example defines a Central Standard Time zone for the United States that includes adjustment rules for a variety of time intervals from 1918 to the present.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

<span data-ttu-id="3e1eb-138">在此示例中创建的时间区域具有多个调整规则。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-138">The time zone created in this example has multiple adjustment rules.</span></span> <span data-ttu-id="3e1eb-139">必须格外小心以确保有效开始日期和结束日期的任何调整规则执行不重叠的另一个调整规则的日期。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-139">Care must be taken to ensure that the effective start and end dates of any adjustment rule do not overlap with the dates of another adjustment rule.</span></span> <span data-ttu-id="3e1eb-140">如果存在重叠，<xref:System.InvalidTimeZoneException>引发。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-140">If there is an overlap, an <xref:System.InvalidTimeZoneException> is thrown.</span></span>

<span data-ttu-id="3e1eb-141">对于浮动调整规则，值 5 传递到`week`参数的<xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A>方法，以指示转换发生在特定月份的最后一周。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-141">For floating adjustment rules, the value 5 is passed to the `week` parameter of the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> method to indicate that the transition occurs on the last week of a particular month.</span></span>

<span data-ttu-id="3e1eb-142">在中创建的数组<xref:System.TimeZoneInfo.AdjustmentRule>对象中使用<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType>方法调用中，该代码可以初始化到多种调整时区为创建所需的大小的数组。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-142">In creating the array of <xref:System.TimeZoneInfo.AdjustmentRule> objects to use in the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> method call, the code could initialize the array to the size required by the number of adjustments to be created for the time zone.</span></span> <span data-ttu-id="3e1eb-143">相反，此代码示例调用<xref:System.Collections.Generic.List%601.Add%2A>方法将每个调整规则添加到泛型<xref:System.Collections.Generic.List%601>的集合<xref:System.TimeZoneInfo.AdjustmentRule>对象。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-143">Instead, this code example calls the <xref:System.Collections.Generic.List%601.Add%2A> method to add each adjustment rule to a generic <xref:System.Collections.Generic.List%601> collection of <xref:System.TimeZoneInfo.AdjustmentRule> objects.</span></span> <span data-ttu-id="3e1eb-144">然后，代码调用<xref:System.Collections.Generic.List%601.CopyTo%2A>方法将此集合的成员复制到数组。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-144">The code then calls the <xref:System.Collections.Generic.List%601.CopyTo%2A> method to copy the members of this collection to the array.</span></span>

<span data-ttu-id="3e1eb-145">此示例还使用<xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A>方法以定义固定日期进行调整。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-145">The example also uses the <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> method to define fixed-date adjustments.</span></span> <span data-ttu-id="3e1eb-146">这是类似于调用<xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A>方法，它需要时间、 月和日转换参数不同。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-146">This is similar to calling the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> method, except that it requires only the time, month, and day of the transition parameters.</span></span>

<span data-ttu-id="3e1eb-147">该示例可以使用类似以下的代码进行测试：</span><span class="sxs-lookup"><span data-stu-id="3e1eb-147">The example can be tested using code such as the following:</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a><span data-ttu-id="3e1eb-148">编译代码</span><span class="sxs-lookup"><span data-stu-id="3e1eb-148">Compiling the code</span></span>

<span data-ttu-id="3e1eb-149">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="3e1eb-149">This example requires:</span></span>

* <span data-ttu-id="3e1eb-150">包含对 System.Core.dll 的引用添加到项目。</span><span class="sxs-lookup"><span data-stu-id="3e1eb-150">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="3e1eb-151">将导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="3e1eb-151">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="3e1eb-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e1eb-152">See also</span></span>

* [<span data-ttu-id="3e1eb-153">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="3e1eb-153">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
* [<span data-ttu-id="3e1eb-154">时区概述</span><span class="sxs-lookup"><span data-stu-id="3e1eb-154">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
* [<span data-ttu-id="3e1eb-155">如何：创建不含调整规则的时区</span><span class="sxs-lookup"><span data-stu-id="3e1eb-155">How to: Create time zones without adjustment rules</span></span>](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)

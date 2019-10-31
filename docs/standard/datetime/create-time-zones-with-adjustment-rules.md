---
title: 如何：创建带有调整规则的时区
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
ms.openlocfilehash: 4ef3d93746c5688dc15fc7e45d9be054dcfba4c8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132555"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a><span data-ttu-id="54a2c-102">如何：创建带有调整规则的时区</span><span class="sxs-lookup"><span data-stu-id="54a2c-102">How to: Create time zones with adjustment rules</span></span>

<span data-ttu-id="54a2c-103">由于以下几个原因，应用程序所需的确切时区信息在特定系统上可能不存在：</span><span class="sxs-lookup"><span data-stu-id="54a2c-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

- <span data-ttu-id="54a2c-104">本地系统的注册表中从未定义过该时区。</span><span class="sxs-lookup"><span data-stu-id="54a2c-104">The time zone has never been defined in the local system's registry.</span></span>

- <span data-ttu-id="54a2c-105">已修改或删除注册表中有关时区的数据。</span><span class="sxs-lookup"><span data-stu-id="54a2c-105">Data about the time zone has been modified or removed from the registry.</span></span>

- <span data-ttu-id="54a2c-106">对于特定的历史时间段，时区没有有关时区调整的准确信息。</span><span class="sxs-lookup"><span data-stu-id="54a2c-106">The time zone does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="54a2c-107">在这些情况下，可以调用 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 方法来定义应用程序所需的时区。</span><span class="sxs-lookup"><span data-stu-id="54a2c-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="54a2c-108">您可以使用此方法的重载来创建具有或不带调整规则的时区。</span><span class="sxs-lookup"><span data-stu-id="54a2c-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="54a2c-109">如果时区支持夏令时，则可以用固定或浮动调整规则定义调整。</span><span class="sxs-lookup"><span data-stu-id="54a2c-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="54a2c-110">（有关这些术语的定义，请参阅时区[概述](../../../docs/standard/datetime/time-zone-overview.md)中的 "时区术语" 部分。）</span><span class="sxs-lookup"><span data-stu-id="54a2c-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54a2c-111">通过调用 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 方法创建的自定义时区不会添加到注册表中。</span><span class="sxs-lookup"><span data-stu-id="54a2c-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="54a2c-112">相反，它们只能通过 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 方法调用返回的对象引用进行访问。</span><span class="sxs-lookup"><span data-stu-id="54a2c-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="54a2c-113">本主题说明如何创建具有调整规则的时区。</span><span class="sxs-lookup"><span data-stu-id="54a2c-113">This topic shows how to create a time zone with adjustment rules.</span></span> <span data-ttu-id="54a2c-114">若要创建不支持夏令时调整规则的时区，请参阅[如何：创建不带调整规则的时区](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="54a2c-114">To create a time zone that does not support daylight saving time adjustment rules, see [How to: Create Time Zones Without Adjustment Rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a><span data-ttu-id="54a2c-115">创建具有浮动调整规则的时区</span><span class="sxs-lookup"><span data-stu-id="54a2c-115">To create a time zone with floating adjustment rules</span></span>

1. <span data-ttu-id="54a2c-116">对于每个调整（即，每次从一个特定时间间隔转换到标准时间时），请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54a2c-116">For each adjustment (that is, for each transition away from and back to standard time over a particular time interval), do the following:</span></span>

    1. <span data-ttu-id="54a2c-117">定义时区调整的开始转换时间。</span><span class="sxs-lookup"><span data-stu-id="54a2c-117">Define the starting transition time for the time zone adjustment.</span></span>

       <span data-ttu-id="54a2c-118">您必须调用 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> 方法，并向其传递一个定义转换时间的 <xref:System.DateTime> 值、一个定义转换月份的整数值、一个整数值（用于定义转换发生的周）以及一个用于定义的 <xref:System.DayOfWeek> 值发生转换的一周中的哪一天。</span><span class="sxs-lookup"><span data-stu-id="54a2c-118">You must call the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> method and pass it a <xref:System.DateTime> value that defines the time of the transition, an integer value that defines the month of the transition, an integer value that defines the week on which the transition occurs, and a <xref:System.DayOfWeek> value that defines the day of the week on which the transition occurs.</span></span> <span data-ttu-id="54a2c-119">此方法调用将实例化一个 <xref:System.TimeZoneInfo.TransitionTime> 对象。</span><span class="sxs-lookup"><span data-stu-id="54a2c-119">This method call instantiates a <xref:System.TimeZoneInfo.TransitionTime> object.</span></span>

    2. <span data-ttu-id="54a2c-120">为时区调整定义结束转换时间。</span><span class="sxs-lookup"><span data-stu-id="54a2c-120">Define the ending transition time for the time zone adjustment.</span></span> <span data-ttu-id="54a2c-121">这需要对 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> 方法的另一次调用。</span><span class="sxs-lookup"><span data-stu-id="54a2c-121">This requires another call to the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="54a2c-122">此方法调用将实例化第二个 <xref:System.TimeZoneInfo.TransitionTime> 对象。</span><span class="sxs-lookup"><span data-stu-id="54a2c-122">This method call instantiates a second <xref:System.TimeZoneInfo.TransitionTime> object.</span></span>

    3. <span data-ttu-id="54a2c-123">调用 <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> 方法，并向其传递调整的有效开始日期和结束日期、定义转换中时间量的 <xref:System.TimeSpan> 对象和两个 <xref:System.TimeZoneInfo.TransitionTime> 对象，这些对象定义在夏令时发生转换的时间。</span><span class="sxs-lookup"><span data-stu-id="54a2c-123">Call the <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> method and pass it the effective start and end dates of the adjustment, a <xref:System.TimeSpan> object that defines the amount of time in the transition, and the two <xref:System.TimeZoneInfo.TransitionTime> objects that define when the transitions to and from daylight saving time occur.</span></span> <span data-ttu-id="54a2c-124">此方法调用将实例化一个 <xref:System.TimeZoneInfo.AdjustmentRule> 对象。</span><span class="sxs-lookup"><span data-stu-id="54a2c-124">This method call instantiates a <xref:System.TimeZoneInfo.AdjustmentRule> object.</span></span>

    4. <span data-ttu-id="54a2c-125">将 <xref:System.TimeZoneInfo.AdjustmentRule> 对象分配给 <xref:System.TimeZoneInfo.AdjustmentRule> 对象的数组。</span><span class="sxs-lookup"><span data-stu-id="54a2c-125">Assign the <xref:System.TimeZoneInfo.AdjustmentRule> object to an array of <xref:System.TimeZoneInfo.AdjustmentRule> objects.</span></span>

2. <span data-ttu-id="54a2c-126">定义时区的显示名称。</span><span class="sxs-lookup"><span data-stu-id="54a2c-126">Define the time zone's display name.</span></span> <span data-ttu-id="54a2c-127">显示名称采用相当标准的格式，在此格式中，时区与协调世界时（UTC）的偏移量括在括号中，后面跟有标识时区的字符串、时区中的一个或多个城市，或者一个或多个 cou时区中的 ntries 或区域。</span><span class="sxs-lookup"><span data-stu-id="54a2c-127">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

3. <span data-ttu-id="54a2c-128">定义时区标准时间的名称。</span><span class="sxs-lookup"><span data-stu-id="54a2c-128">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="54a2c-129">通常，此字符串还用作时区的标识符。</span><span class="sxs-lookup"><span data-stu-id="54a2c-129">Typically, this string is also used as the time zone's identifier.</span></span>

4. <span data-ttu-id="54a2c-130">定义时区的夏令时的名称。</span><span class="sxs-lookup"><span data-stu-id="54a2c-130">Define the name of the time zone's daylight time.</span></span>

5. <span data-ttu-id="54a2c-131">如果要使用不同于时区的标准名称的标识符，请定义时区标识符。</span><span class="sxs-lookup"><span data-stu-id="54a2c-131">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

6. <span data-ttu-id="54a2c-132">实例化定义时区与 UTC 的偏移量的 <xref:System.TimeSpan> 对象。</span><span class="sxs-lookup"><span data-stu-id="54a2c-132">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="54a2c-133">时间时区晚于 UTC 的时区具有正偏移量。</span><span class="sxs-lookup"><span data-stu-id="54a2c-133">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="54a2c-134">其时间早于 UTC 的时区具有负偏移量。</span><span class="sxs-lookup"><span data-stu-id="54a2c-134">Time zones with times that are earlier than UTC have a negative offset.</span></span>

7. <span data-ttu-id="54a2c-135">调用 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> 方法来实例化新时区。</span><span class="sxs-lookup"><span data-stu-id="54a2c-135">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="54a2c-136">示例</span><span class="sxs-lookup"><span data-stu-id="54a2c-136">Example</span></span>

<span data-ttu-id="54a2c-137">下面的示例为美国定义了一个中部标准时区，其中包括从1918到当前时间间隔内的各种时间间隔的调整规则。</span><span class="sxs-lookup"><span data-stu-id="54a2c-137">The following example defines a Central Standard Time zone for the United States that includes adjustment rules for a variety of time intervals from 1918 to the present.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

<span data-ttu-id="54a2c-138">在此示例中创建的时区具有多个调整规则。</span><span class="sxs-lookup"><span data-stu-id="54a2c-138">The time zone created in this example has multiple adjustment rules.</span></span> <span data-ttu-id="54a2c-139">必须小心，以确保任何调整规则的有效开始日期和结束日期不会与另一个调整规则的日期重叠。</span><span class="sxs-lookup"><span data-stu-id="54a2c-139">Care must be taken to ensure that the effective start and end dates of any adjustment rule do not overlap with the dates of another adjustment rule.</span></span> <span data-ttu-id="54a2c-140">如果有重叠，则会引发 <xref:System.InvalidTimeZoneException>。</span><span class="sxs-lookup"><span data-stu-id="54a2c-140">If there is an overlap, an <xref:System.InvalidTimeZoneException> is thrown.</span></span>

<span data-ttu-id="54a2c-141">对于浮点调整规则，将值5传递到 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 方法的 `week` 参数，以指示在特定月份的最后一周发生转换。</span><span class="sxs-lookup"><span data-stu-id="54a2c-141">For floating adjustment rules, the value 5 is passed to the `week` parameter of the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> method to indicate that the transition occurs on the last week of a particular month.</span></span>

<span data-ttu-id="54a2c-142">在创建要在 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> 方法调用中使用的 <xref:System.TimeZoneInfo.AdjustmentRule> 对象数组时，代码可以将数组初始化为要为时区创建的调整数所需的大小。</span><span class="sxs-lookup"><span data-stu-id="54a2c-142">In creating the array of <xref:System.TimeZoneInfo.AdjustmentRule> objects to use in the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> method call, the code could initialize the array to the size required by the number of adjustments to be created for the time zone.</span></span> <span data-ttu-id="54a2c-143">相反，此代码示例调用 <xref:System.Collections.Generic.List%601.Add%2A> 方法，将每个调整规则添加到 <xref:System.TimeZoneInfo.AdjustmentRule> 对象的泛型 <xref:System.Collections.Generic.List%601> 集合。</span><span class="sxs-lookup"><span data-stu-id="54a2c-143">Instead, this code example calls the <xref:System.Collections.Generic.List%601.Add%2A> method to add each adjustment rule to a generic <xref:System.Collections.Generic.List%601> collection of <xref:System.TimeZoneInfo.AdjustmentRule> objects.</span></span> <span data-ttu-id="54a2c-144">然后，该代码调用 <xref:System.Collections.Generic.List%601.CopyTo%2A> 方法将此集合的成员复制到数组中。</span><span class="sxs-lookup"><span data-stu-id="54a2c-144">The code then calls the <xref:System.Collections.Generic.List%601.CopyTo%2A> method to copy the members of this collection to the array.</span></span>

<span data-ttu-id="54a2c-145">该示例还使用 <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> 方法定义固定日期调整。</span><span class="sxs-lookup"><span data-stu-id="54a2c-145">The example also uses the <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> method to define fixed-date adjustments.</span></span> <span data-ttu-id="54a2c-146">这类似于调用 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 方法，但它只要求转换参数的时间、月份和日期。</span><span class="sxs-lookup"><span data-stu-id="54a2c-146">This is similar to calling the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> method, except that it requires only the time, month, and day of the transition parameters.</span></span>

<span data-ttu-id="54a2c-147">可以使用如下所示的代码测试该示例：</span><span class="sxs-lookup"><span data-stu-id="54a2c-147">The example can be tested using code such as the following:</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a><span data-ttu-id="54a2c-148">编译代码</span><span class="sxs-lookup"><span data-stu-id="54a2c-148">Compiling the code</span></span>

<span data-ttu-id="54a2c-149">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="54a2c-149">This example requires:</span></span>

- <span data-ttu-id="54a2c-150">导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="54a2c-150">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="54a2c-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="54a2c-151">See also</span></span>

- [<span data-ttu-id="54a2c-152">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="54a2c-152">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="54a2c-153">时区概述</span><span class="sxs-lookup"><span data-stu-id="54a2c-153">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="54a2c-154">如何：创建不含调整规则的时区</span><span class="sxs-lookup"><span data-stu-id="54a2c-154">How to: Create time zones without adjustment rules</span></span>](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)

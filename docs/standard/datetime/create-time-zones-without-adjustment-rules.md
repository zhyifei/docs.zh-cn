---
title: 如何：创建不含调整规则的时区
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff4cfe2b492b676c061043f018390844f1807440
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586394"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a><span data-ttu-id="1209f-102">如何：创建不含调整规则的时区</span><span class="sxs-lookup"><span data-stu-id="1209f-102">How to: Create time zones without adjustment rules</span></span>

<span data-ttu-id="1209f-103">应用程序所需的精确的时区信息可能不存在的特定系统上有几个原因：</span><span class="sxs-lookup"><span data-stu-id="1209f-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

* <span data-ttu-id="1209f-104">永远不会在本地系统注册表中定义的时区。</span><span class="sxs-lookup"><span data-stu-id="1209f-104">The time zone has never been defined in the local system's registry.</span></span>

* <span data-ttu-id="1209f-105">有关时区的数据已修改或从注册表中删除。</span><span class="sxs-lookup"><span data-stu-id="1209f-105">Data about the time zone has been modified or removed from the registry.</span></span>

* <span data-ttu-id="1209f-106">时区存在，但不具有特定的历史时期时区调整的准确信息。</span><span class="sxs-lookup"><span data-stu-id="1209f-106">The time zone exists but does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="1209f-107">在这些情况下，您可以调用<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>方法以定义你的应用程序所需的时区。</span><span class="sxs-lookup"><span data-stu-id="1209f-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="1209f-108">可以使用此方法的重载来创建带有或不带调整规则的时区。</span><span class="sxs-lookup"><span data-stu-id="1209f-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="1209f-109">如果时区支持夏令时，则可以定义与任一固定或浮动调整规则的调整。</span><span class="sxs-lookup"><span data-stu-id="1209f-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="1209f-110">(有关这些术语的定义，请参阅中的"时区术语"一节[时区概述](../../../docs/standard/datetime/time-zone-overview.md)。)</span><span class="sxs-lookup"><span data-stu-id="1209f-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1209f-111">通过调用创建的自定义时区<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>方法不会添加到注册表。</span><span class="sxs-lookup"><span data-stu-id="1209f-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="1209f-112">相反，它们可以访问只能通过返回的对象引用<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>方法调用。</span><span class="sxs-lookup"><span data-stu-id="1209f-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="1209f-113">本主题演示如何创建不含调整规则的时区。</span><span class="sxs-lookup"><span data-stu-id="1209f-113">This topic shows how to create a time zone without adjustment rules.</span></span> <span data-ttu-id="1209f-114">若要创建支持夏令时调整规则的时区，请参阅[如何：创建含调整规则的时区](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="1209f-114">To create a time zone that supports daylight saving time adjustment rules, see [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-without-adjustment-rules"></a><span data-ttu-id="1209f-115">若要创建不含调整规则的时区</span><span class="sxs-lookup"><span data-stu-id="1209f-115">To create a time zone without adjustment rules</span></span>

1. <span data-ttu-id="1209f-116">定义时区的显示名称。</span><span class="sxs-lookup"><span data-stu-id="1209f-116">Define the time zone's display name.</span></span>

   <span data-ttu-id="1209f-117">显示名称应遵循相当标准的格式时区的偏移量从协调世界时 (UTC) 括在括号中后, 跟一个字符串，标识一个或多个城市中时区，或其中一个或多个 cou 时区ntries 或时区中的区域。</span><span class="sxs-lookup"><span data-stu-id="1209f-117">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

2. <span data-ttu-id="1209f-118">定义时区的标准时间的名称。</span><span class="sxs-lookup"><span data-stu-id="1209f-118">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="1209f-119">通常情况下，此字符串还用作时区的标识符。</span><span class="sxs-lookup"><span data-stu-id="1209f-119">Typically, this string is also used as the time zone's identifier.</span></span>

3. <span data-ttu-id="1209f-120">如果你想要使用其他标识符，于时区的标准名称，定义的时区标识符。</span><span class="sxs-lookup"><span data-stu-id="1209f-120">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

4. <span data-ttu-id="1209f-121">实例化<xref:System.TimeSpan>对象，用于定义相对于 UTC 的时区的偏移量。</span><span class="sxs-lookup"><span data-stu-id="1209f-121">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="1209f-122">时间晚于 UTC 的时区具有负偏移量。</span><span class="sxs-lookup"><span data-stu-id="1209f-122">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="1209f-123">时间早于 UTC 的时区具有负偏移量。</span><span class="sxs-lookup"><span data-stu-id="1209f-123">Time zones with times that are earlier than UTC have a negative offset.</span></span>

5. <span data-ttu-id="1209f-124">调用<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType>方法可实例化新的时区。</span><span class="sxs-lookup"><span data-stu-id="1209f-124">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="1209f-125">示例</span><span class="sxs-lookup"><span data-stu-id="1209f-125">Example</span></span>

<span data-ttu-id="1209f-126">下面的示例定义莫森，南极洲，带调整规则的自定义时区。</span><span class="sxs-lookup"><span data-stu-id="1209f-126">The following example defines a custom time zone for Mawson, Antarctica, which has no adjustment rules.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

<span data-ttu-id="1209f-127">将字符串分配给<xref:System.TimeZoneInfo.DisplayName%2A>属性应遵循标准格式，相对于 UTC 的时区的偏移量跟时区的易懂说明。</span><span class="sxs-lookup"><span data-stu-id="1209f-127">The string assigned to the <xref:System.TimeZoneInfo.DisplayName%2A> property follows a standard format in which the time zone's offset from UTC is followed by a friendly description of the time zone.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="1209f-128">编译代码</span><span class="sxs-lookup"><span data-stu-id="1209f-128">Compiling the code</span></span>

<span data-ttu-id="1209f-129">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="1209f-129">This example requires:</span></span>

* <span data-ttu-id="1209f-130">将导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="1209f-130">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="1209f-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="1209f-131">See also</span></span>

- [<span data-ttu-id="1209f-132">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="1209f-132">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="1209f-133">时区概述</span><span class="sxs-lookup"><span data-stu-id="1209f-133">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="1209f-134">如何：创建含调整规则的时区</span><span class="sxs-lookup"><span data-stu-id="1209f-134">How to: Create time zones with adjustment rules</span></span>](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)

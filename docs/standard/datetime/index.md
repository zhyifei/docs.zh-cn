---
title: "日期、时间和时区"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time zone objects [.NET Framework]
- date and time data [.NET Framework]
- time zones [.NET Framework]
- times [.NET Framework], time zones
- time [.NET Framework], time zones
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1e85fc8eac25cc6fdfb8cb3aaa77318019695c51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="dates-times-and-time-zones"></a><span data-ttu-id="08a4c-102">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="08a4c-102">Dates, times, and time zones</span></span>

<span data-ttu-id="08a4c-103">除基本 <xref:System.DateTime> 结构外，.NET 还提供以下支持处理时区的类型：</span><span class="sxs-lookup"><span data-stu-id="08a4c-103">In addition to the basic <xref:System.DateTime> structure, .NET provides the following classes that support working with time zones:</span></span>

* <xref:System.TimeZone>

  <span data-ttu-id="08a4c-104">使用此类处理系统的本地时区和协调世界时 (UTC) 区域。<xref:System.TimeZone> 类的功能在很大程度上已被 <xref:System.TimeZoneInfo> 类取代。</span><span class="sxs-lookup"><span data-stu-id="08a4c-104">Use this class to work with the system's local time zone and the Coordinated Universal Time (UTC) zone.The functionality of the <xref:System.TimeZone> class is largely superseded by the <xref:System.TimeZoneInfo> class.</span></span>

* <xref:System.TimeZoneInfo>

  <span data-ttu-id="08a4c-105">此类可用于处理系统上预定义的任何时区、创建新时区，以及将日期和时间从一个时区轻松转换成另一个时区。</span><span class="sxs-lookup"><span data-stu-id="08a4c-105">Use this class to work with any time zone that is predefined on a system, to create new time zones, and to easily convert dates and times from one time zone to another.</span></span> <span data-ttu-id="08a4c-106">对于新的开发，使用 <xref:System.TimeZoneInfo> 类而不使用 <xref:System.TimeZone> 类。</span><span class="sxs-lookup"><span data-stu-id="08a4c-106">For new development, use the <xref:System.TimeZoneInfo> class instead of the <xref:System.TimeZone> class.</span></span>

* <xref:System.DateTimeOffset>

  <span data-ttu-id="08a4c-107">使用此结构处理已知 UTC 偏移量（或差值）的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="08a4c-107">Use this structure to work with dates and times whose offset (or difference) from UTC is known.</span></span> <span data-ttu-id="08a4c-108"><xref:System.DateTimeOffset> 结构结合了日期和时间值与该时间的 UTC 偏移量。</span><span class="sxs-lookup"><span data-stu-id="08a4c-108">The <xref:System.DateTimeOffset> structure combines a date and time value with that time's offset from UTC.</span></span> <span data-ttu-id="08a4c-109">由于其与 UTC 间的关系，单独的日期和时间值可以明确地识别单个时间点。</span><span class="sxs-lookup"><span data-stu-id="08a4c-109">Because of its relationship to UTC, an individual date and time value unambiguously identifies a single point in time.</span></span> <span data-ttu-id="08a4c-110">这使 <xref:System.DateTimeOffset> 值比 <xref:System.DateTime> 值更容易从一台计算机移植到另一台计算机。</span><span class="sxs-lookup"><span data-stu-id="08a4c-110">This makes a <xref:System.DateTimeOffset> value more portable from one computer to another than a <xref:System.DateTime> value.</span></span>

<span data-ttu-id="08a4c-111">文档的此部分提供处理时区和创建时区识别应用程序所需的信息，时区识别程序可将日期和时间从一个时区转换到另一时区。</span><span class="sxs-lookup"><span data-stu-id="08a4c-111">This section of the documentation provides the information that you need to work with time zones and to create time zone-aware applications that can convert dates and times from one time zone to another.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="08a4c-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="08a4c-112">In this section</span></span>

<span data-ttu-id="08a4c-113">[时区概述](../../../docs/standard/datetime/time-zone-overview.md)讨论了创建时区识别应用程序时涉及的术语、概念以及问题。</span><span class="sxs-lookup"><span data-stu-id="08a4c-113">[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md) Discusses the terminology, concepts, and issues involved in creating time zone-aware applications.</span></span>

<span data-ttu-id="08a4c-114">[在 DateTime、DateTimeOffset、TimeSpan 和 TimeZoneInfo 间进行选择](../../../docs/standard/datetime/choosing-between-datetime.md)讨论处理日期和时间数据时，应何时使用 <xref:System.DateTime>、<xref:System.DateTimeOffset> 和 <xref:System.TimeZoneInfo> 类型。</span><span class="sxs-lookup"><span data-stu-id="08a4c-114">[Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md) Discusses when to use the <xref:System.DateTime>, <xref:System.DateTimeOffset>, and <xref:System.TimeZoneInfo> types when working with date and time data.</span></span>

<span data-ttu-id="08a4c-115">[查找本地系统上定义的时区](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)介绍如何枚举在本地系统上找到的时区。</span><span class="sxs-lookup"><span data-stu-id="08a4c-115">[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) Describes how to enumerate the time zones found on a local system.</span></span>

<span data-ttu-id="08a4c-116">[如何：枚举计算机上存在的时区](../../../docs/standard/datetime/enumerate-time-zones.md)举例说明枚举在计算机注册表中定义的时区，以及允许用户从列表选择一个预定义时区。</span><span class="sxs-lookup"><span data-stu-id="08a4c-116">[How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md) Provides examples that enumerate the time zones defined in a computer's registry and that let users select a predefined time zone from a list.</span></span>

<span data-ttu-id="08a4c-117">[如何：访问预定义的 UTC 和本地时区对象](../../../docs/standard/datetime/access-utc-and-local.md)介绍如何访问协调世界时和本地时区。</span><span class="sxs-lookup"><span data-stu-id="08a4c-117">[How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) Describes how to access Coordinated Universal Time and the local time zone.</span></span>

<span data-ttu-id="08a4c-118">[如何：实例化 TimeZoneInfo 对象](../../../docs/standard/datetime/instantiate-time-zone-info.md)介绍如何实例化本地系统注册表中的 <xref:System.TimeZoneInfo> 对象。</span><span class="sxs-lookup"><span data-stu-id="08a4c-118">[How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md) Describes how to instantiate a <xref:System.TimeZoneInfo> object from the local system registry.</span></span>

<span data-ttu-id="08a4c-119">[实例化 DateTimeOffset 对象](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md)讨论实例化 <xref:System.DateTimeOffset> 对象的方式，以及可以将 <xref:System.DateTime> 值转化为 <xref:System.DateTimeOffset> 值的方法。</span><span class="sxs-lookup"><span data-stu-id="08a4c-119">[Instantiating a DateTimeOffset object](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md) Discusses the ways in which a <xref:System.DateTimeOffset> object can be instantiated, and the ways in which a <xref:System.DateTime> value can be converted to a <xref:System.DateTimeOffset> value.</span></span>

<span data-ttu-id="08a4c-120">[如何：创建不含调整规则的时区](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)介绍如何创建不支持夏令时转换规则的自定义时区。</span><span class="sxs-lookup"><span data-stu-id="08a4c-120">[How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) Describes how to create a custom time zone that does not support the transition to and from daylight saving time.</span></span>

<span data-ttu-id="08a4c-121">[如何：创建含调整规则的时区](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)介绍如何创建支持一个或多个夏令时转换规则的自定义时区。</span><span class="sxs-lookup"><span data-stu-id="08a4c-121">[How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md) Describes how to create a custom time zone that supports one or more transitions to and from daylight saving time.</span></span>

<span data-ttu-id="08a4c-122">[保存和还原时区](../../../docs/standard/datetime/saving-and-restoring-time-zones.md)介绍 <xref:System.TimeZoneInfo> 提供的时区数据序列化和反序列化支持，并通过一些应用场景介绍了如何使用这些功能。</span><span class="sxs-lookup"><span data-stu-id="08a4c-122">[Saving and restoring time zones](../../../docs/standard/datetime/saving-and-restoring-time-zones.md) Describes <xref:System.TimeZoneInfo> support for serialization and deserialization of time zone data and illustrates some of the scenarios in which these features can be used.</span></span>

<span data-ttu-id="08a4c-123">[如何：将时区保存到嵌入的资源中](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)介绍如何创建自定义时区，并将其信息保存到资源文件中。</span><span class="sxs-lookup"><span data-stu-id="08a4c-123">[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) Describes how to create a custom time zone and save its information in a resource file.</span></span>

<span data-ttu-id="08a4c-124">[如何：从嵌入的资源还原时区](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)介绍如何实例化已保存到嵌入的资源文件中的自定义时区。</span><span class="sxs-lookup"><span data-stu-id="08a4c-124">[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) Describes how to instantiate custom time zones that have been saved to an embedded resource file.</span></span>

<span data-ttu-id="08a4c-125">[使用日期和时间执行算术运算](../../../docs/standard/datetime/performing-arithmetic-operations.md)讨论加上，减去和比较 <xref:System.DateTime> 与 <xref:System.DateTimeOffset> 值时会出现的问题。</span><span class="sxs-lookup"><span data-stu-id="08a4c-125">[Performing arithmetic operations with dates and times](../../../docs/standard/datetime/performing-arithmetic-operations.md) Discusses the issues involved in adding, subtracting, and comparing <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="08a4c-126">[如何：在日期和时间算法中使用时区](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)讨论如何执行反映时区调整规则的日期和时间算术。</span><span class="sxs-lookup"><span data-stu-id="08a4c-126">[How to: Use time zones in date and time arithmetic](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md) Discusses how to perform date and time arithmetic that reflects a time zone's adjustment rules.</span></span>

<span data-ttu-id="08a4c-127">[在 DateTime 与 DateTimeOffset 之间进行转换](../../../docs/standard/datetime/converting-between-datetime-and-offset.md)介绍如何在 <xref:System.DateTime> 和 <xref:System.DateTimeOffset> 值间进行转换。</span><span class="sxs-lookup"><span data-stu-id="08a4c-127">[Converting between DateTime and DateTimeOffset](../../../docs/standard/datetime/converting-between-datetime-and-offset.md) Describes how to convert between <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="08a4c-128">[在各时区之间转换时间](../../../docs/standard/datetime/converting-between-time-zones.md)介绍如何将时间从一个时区转换到另一个时区。</span><span class="sxs-lookup"><span data-stu-id="08a4c-128">[Converting times between time zones](../../../docs/standard/datetime/converting-between-time-zones.md) Describes how to convert times from one time zone to another.</span></span>

<span data-ttu-id="08a4c-129">[如何：解决不明确时间](../../../docs/standard/datetime/resolve-ambiguous-times.md)介绍如何通过将不明确时间映射到时区标准时间解决该时间。</span><span class="sxs-lookup"><span data-stu-id="08a4c-129">[How to: Resolve ambiguous times](../../../docs/standard/datetime/resolve-ambiguous-times.md) Describes how to resolve an ambiguous time by mapping it to the time zone's standard time.</span></span>

<span data-ttu-id="08a4c-130">[如何：让用户解决不明确时间](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)介绍如何让用户确定不明确本地时间与协调世界时之间的映射。</span><span class="sxs-lookup"><span data-stu-id="08a4c-130">[How to: Let users resolve ambiguous times](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md) Describes how to let a user determine the mapping between an ambiguous local time and Coordinated Universal Time.</span></span>

## <a name="reference"></a><span data-ttu-id="08a4c-131">参考</span><span class="sxs-lookup"><span data-stu-id="08a4c-131">Reference</span></span>

<xref:System.TimeZoneInfo?displayProperty=nameWithType>

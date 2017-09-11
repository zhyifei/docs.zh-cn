---
title: "查找本地系统上定义的时区"
description: "查找本地系统上定义的时区"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3a6ee323-f3cf-486d-aa0c-103931f1eba9
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: e61017e2a0e26295c3be7e8265674b1a5d2ae5a3
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="finding-the-time-zones-defined-on-a-local-system"></a><span data-ttu-id="ccdb6-104">查找本地系统上定义的时区</span><span class="sxs-lookup"><span data-stu-id="ccdb6-104">Finding the time zones defined on a local system</span></span>

<span data-ttu-id="ccdb6-105">[System.TimeZoneInfo](xref:System.TimeZoneInfo) 类不公开公共构造函数。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-105">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class does not expose a public constructor.</span></span> <span data-ttu-id="ccdb6-106">因此，`new` 关键字不能用于创建新的 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-106">As a result, the `new` keyword cannot be used to create a new [TimeZoneInfo](xref:System.TimeZoneInfo) object.</span></span> <span data-ttu-id="ccdb6-107">相反，[TimeZoneInfo](xref:System.TimeZoneInfo) 对象通过检索操作系统上有关预定义时区的信息进行实例化。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-107">Instead, [TimeZoneInfo](xref:System.TimeZoneInfo) objects are instantiated by retrieving information on predefined time zones from the operating system.</span></span> <span data-ttu-id="ccdb6-108">本主题讨论从操作系统存储的数据实例化时区。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-108">This topic discusses instantiating a time zone from data stored by the operating system.</span></span> <span data-ttu-id="ccdb6-109">此外，[TimeZoneInfo](xref:System.TimeZoneInfo) 类的 `static`（在 Visual Basic 中为 `Shared`）属性提供对协调世界时 (UTC) 和本地时区的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-109">In addition, `static` (`Shared` in Visual Basic) properties of the [TimeZoneInfo](xref:System.TimeZoneInfo) class provide access to Coordinated Universal Time (UTC) and the local time zone.</span></span>

## <a name="accessing-individual-time-zones"></a><span data-ttu-id="ccdb6-110">访问独立时区</span><span class="sxs-lookup"><span data-stu-id="ccdb6-110">Accessing Individual Time Zones</span></span>

<span data-ttu-id="ccdb6-111">[TimeZoneInfo](xref:System.TimeZoneInfo) 类提供两个预定义时区对象，分别表示 UTC 时间和本地时区。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-111">The [TimeZoneInfo](xref:System.TimeZoneInfo) class provides two predefined time zone objects that represent the UTC time and the local time zone.</span></span> <span data-ttu-id="ccdb6-112">可分别从 [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) 和 [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) 属性找到这两个对象。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-112">They are available from the [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) and [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) properties, respectively.</span></span> <span data-ttu-id="ccdb6-113">有关访问 UTC 或本地时区的说明，请参阅[如何：访问预定义 UTC 和本地时区对象](access-utc-and-local.md)。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-113">For instructions on accessing the UTC or local time zones, see [How to: access the predefined UTC and local time zone objects](access-utc-and-local.md).</span></span> 

<span data-ttu-id="ccdb6-114">还可以实例化表示任何由操作系统定义的时区的 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-114">You can also instantiate a [TimeZoneInfo](xref:System.TimeZoneInfo) object that represents any time zone defined by the operating system.</span></span> <span data-ttu-id="ccdb6-115">有关实例化特定时区对象的说明，请参阅[如何：实例化 TimeZoneInfo 对象](instantiate-time-zone-info.md)。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-115">For instructions on instantiating a specific time zone object, see [How to: instantiate a TimeZoneInfo object](instantiate-time-zone-info.md).</span></span>

## <a name="time-zone-identifiers"></a><span data-ttu-id="ccdb6-116">时区标识符</span><span class="sxs-lookup"><span data-stu-id="ccdb6-116">Time Zone Identifiers</span></span>

<span data-ttu-id="ccdb6-117">时区标识符是唯一标识时区的键字段。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-117">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="ccdb6-118">虽然大多数键都相对较短，但时区标识符相对较长。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-118">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="ccdb6-119">在大多数情况下，其值对应于 [TimeZoneInfo.StandardName](xref:System.TimeZoneInfo.StandardName) 属性，该属性用于提供时区标准时间的名称。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-119">In most cases, its value corresponds to the [TimeZoneInfo.StandardName](xref:System.TimeZoneInfo.StandardName) property, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="ccdb6-120">但是，有例外情况。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-120">However, there are exceptions.</span></span> <span data-ttu-id="ccdb6-121">确保提供有效标识符最好的办法是枚举系统上可用的时区，并记下其关联的标识符。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-121">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note their associated identifiers.</span></span> <span data-ttu-id="ccdb6-122">有关枚举时区的说明，请参阅[如何：枚举计算机上存在的时区](enumerate-time-zones.md)。</span><span class="sxs-lookup"><span data-stu-id="ccdb6-122">For instructions on enumerating time zones, see [How to: enumerate time zones present on a computer](enumerate-time-zones.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ccdb6-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ccdb6-123">See Also</span></span>

[<span data-ttu-id="ccdb6-124">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="ccdb6-124">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="ccdb6-125">如何访问预定义 UTC 和本地时区对象</span><span class="sxs-lookup"><span data-stu-id="ccdb6-125">How to: access the predefined UTC and local time zone objects</span></span>](access-utc-and-local.md)

[<span data-ttu-id="ccdb6-126">如何：实例化 TimeZoneInfo 对象</span><span class="sxs-lookup"><span data-stu-id="ccdb6-126">How to: instantiate a TimeZoneInfo object</span></span>](instantiate-time-zone-info.md)

[<span data-ttu-id="ccdb6-127">如何：枚举计算机上存在的时区</span><span class="sxs-lookup"><span data-stu-id="ccdb6-127">How to: enumerate time zones present on a computer</span></span>](enumerate-time-zones.md)

[<span data-ttu-id="ccdb6-128">在各时区之间转换时间</span><span class="sxs-lookup"><span data-stu-id="ccdb6-128">Converting times between time zones</span></span>](converting-between-time-zones.md)

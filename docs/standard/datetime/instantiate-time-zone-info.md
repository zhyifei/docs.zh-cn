---
title: "如何： 实例化 TimeZoneInfo 对象"
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- instantiating time zone objects
- time zone objects [.NET Framework], instantiation
ms.assetid: 8cb620e5-c6a6-4267-a52e-beeb73cd1a34
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 59c23b4517e1150a8b17dd41667f3e793809fd21
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="11b6f-102">如何： 实例化 TimeZoneInfo 对象</span><span class="sxs-lookup"><span data-stu-id="11b6f-102">How to: Instantiate a TimeZoneInfo object</span></span>

<span data-ttu-id="11b6f-103">实例化 <xref:System.TimeZoneInfo> 对象的常用方法是从注册表中检索与其有关的信息。</span><span class="sxs-lookup"><span data-stu-id="11b6f-103">The most common way to instantiate a <xref:System.TimeZoneInfo> object is to retrieve information about it from the registry.</span></span> <span data-ttu-id="11b6f-104">本主题讨论如何从本地系统注册表中实例化 <xref:System.TimeZoneInfo> 对象。</span><span class="sxs-lookup"><span data-stu-id="11b6f-104">This topic discusses how to instantiate a <xref:System.TimeZoneInfo> object from the local system registry.</span></span>

### <a name="to-instantiate-a-timezoneinfo-object"></a><span data-ttu-id="11b6f-105">实例化 TimeZoneInfo 对象</span><span class="sxs-lookup"><span data-stu-id="11b6f-105">To instantiate a TimeZoneInfo object</span></span>

1. <span data-ttu-id="11b6f-106">声明 <xref:System.TimeZoneInfo> 对象。</span><span class="sxs-lookup"><span data-stu-id="11b6f-106">Declare a <xref:System.TimeZoneInfo> object.</span></span>

2. <span data-ttu-id="11b6f-107">调用`static`(`Shared`在 Visual Basic 中)<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="11b6f-107">Call the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> method.</span></span>

3. <span data-ttu-id="11b6f-108">处理方法引发的所有异常，尤其是注册表中未定义时区时引发的 <xref:System.TimeZoneNotFoundException> 。</span><span class="sxs-lookup"><span data-stu-id="11b6f-108">Handle any exceptions thrown by the method, particularly the <xref:System.TimeZoneNotFoundException> that is thrown if the time zone is not defined in the registry.</span></span>

## <a name="example"></a><span data-ttu-id="11b6f-109">示例</span><span class="sxs-lookup"><span data-stu-id="11b6f-109">Example</span></span>

<span data-ttu-id="11b6f-110">下面的代码会检索表示东部标准时区并显示本地时间所对应的东部标准时间的 <xref:System.TimeZoneInfo> 对象。</span><span class="sxs-lookup"><span data-stu-id="11b6f-110">The following code retrieves a <xref:System.TimeZoneInfo> object that represents the Eastern Standard Time zone and displays the Eastern Standard time that corresponds to the local time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#5)]
[!code-vb[System.TimeZone2.Concepts#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#5)]

<span data-ttu-id="11b6f-111"><xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType>方法的单个参数是时区的标识符，你想要检索，对应于对象的<xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="11b6f-111">The <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A?displayProperty=nameWithType> method's single parameter is the identifier of the time zone that you want to retrieve, which corresponds to the object's <xref:System.TimeZoneInfo.Id%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="11b6f-112">时区标识符是唯一标识时区的键字段。</span><span class="sxs-lookup"><span data-stu-id="11b6f-112">The time zone identifier is a key field that uniquely identifies the time zone.</span></span> <span data-ttu-id="11b6f-113">虽然大多数键都相对较短，但时区标识符相对较长。</span><span class="sxs-lookup"><span data-stu-id="11b6f-113">While most keys are relatively short, the time zone identifier is comparatively long.</span></span> <span data-ttu-id="11b6f-114">在大多数情况下，其值对应于 <xref:System.TimeZoneInfo.StandardName%2A> 对象的 <xref:System.TimeZoneInfo> 属性，该属性用于提供时区标准时间的名称。</span><span class="sxs-lookup"><span data-stu-id="11b6f-114">In most cases, its value corresponds to the <xref:System.TimeZoneInfo.StandardName%2A> property of a <xref:System.TimeZoneInfo> object, which is used to provide the name of the time zone's standard time.</span></span> <span data-ttu-id="11b6f-115">但是，有例外情况。</span><span class="sxs-lookup"><span data-stu-id="11b6f-115">However, there are exceptions.</span></span> <span data-ttu-id="11b6f-116">确保提供有效标识符的最好方法是枚举系统上可用的时区，然后记下上面显示的时区标识符。</span><span class="sxs-lookup"><span data-stu-id="11b6f-116">The best way to make sure that you supply a valid identifier is to enumerate the time zones available on your system and note the identifiers of the time zones present on them.</span></span> <span data-ttu-id="11b6f-117">有关说明，请参阅 [How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md)。</span><span class="sxs-lookup"><span data-stu-id="11b6f-117">For an illustration, see [How to: Enumerate time zones present on a computer](../../../docs/standard/datetime/enumerate-time-zones.md).</span></span> <span data-ttu-id="11b6f-118">[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) 主题还包含所选时区标识符的列表。</span><span class="sxs-lookup"><span data-stu-id="11b6f-118">The [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md) topic also contains a list of selected time zone identifiers.</span></span>

<span data-ttu-id="11b6f-119">如果找到时区，该方法将返回其 <xref:System.TimeZoneInfo> 对象。</span><span class="sxs-lookup"><span data-stu-id="11b6f-119">If the time zone is found, the method returns its <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="11b6f-120">如果未找到时区，该方法将引发 <xref:System.TimeZoneNotFoundException>。</span><span class="sxs-lookup"><span data-stu-id="11b6f-120">If the time zone is not found, the method throws a <xref:System.TimeZoneNotFoundException>.</span></span> <span data-ttu-id="11b6f-121">如果找到该时区但其数据已损坏或不完整，该方法将引发 <xref:System.InvalidTimeZoneException>。</span><span class="sxs-lookup"><span data-stu-id="11b6f-121">If the time zone is found but its data is corrupted or incomplete, the method throws an <xref:System.InvalidTimeZoneException>.</span></span>

<span data-ttu-id="11b6f-122">如果你的应用程序依赖于一个必须存在的时区，则应首先调用 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 方法从注册表中检索时区信息。</span><span class="sxs-lookup"><span data-stu-id="11b6f-122">If your application relies on a time zone that must be present, you should first call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method to retrieve the time zone information from the registry.</span></span> <span data-ttu-id="11b6f-123">如果方法调用失败，则异常处理程序应创建时区的新实例，或通过对序列化的 <xref:System.TimeZoneInfo> 对象进行反序列化来重新创建它。</span><span class="sxs-lookup"><span data-stu-id="11b6f-123">If the method call fails, your exception handler should then either create a new instance of the time zone or re-create it by deserializing a serialized <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="11b6f-124">请参阅[如何： 从嵌入的资源还原时区](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)有关示例。</span><span class="sxs-lookup"><span data-stu-id="11b6f-124">See [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md) for an example.</span></span>

## <a name="see-also"></a><span data-ttu-id="11b6f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="11b6f-125">See also</span></span>

<span data-ttu-id="11b6f-126">[日期、 时间和时区](../../../docs/standard/datetime/index.md)
[查找本地系统上定义的时区](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[如何： 访问预定义的 UTC 和当地时间区域对象](../../../docs/standard/datetime/access-utc-and-local.md)</span><span class="sxs-lookup"><span data-stu-id="11b6f-126">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md)</span></span>

---
title: "如何： 访问预定义的 UTC 和当地时间区域对象"
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
- time zones [.NET Framework], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET Framework], retrieving
- time zones [.NET Framework], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 600dbb98264c4750db1ffb98b757ad191eaf4fe5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="2c0f5-102">如何： 访问预定义的 UTC 和当地时间区域对象</span><span class="sxs-lookup"><span data-stu-id="2c0f5-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="2c0f5-103"><xref:System.TimeZoneInfo>类提供了两个属性<xref:System.TimeZoneInfo.Utc%2A>和<xref:System.TimeZoneInfo.Local%2A>，您的代码访问权限向预定义的时区对象。</span><span class="sxs-lookup"><span data-stu-id="2c0f5-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="2c0f5-104">本主题介绍如何访问这些属性返回的 <xref:System.TimeZoneInfo> 对象。</span><span class="sxs-lookup"><span data-stu-id="2c0f5-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="2c0f5-105">访问协调世界时 (UTC) TimeZoneInfo 对象</span><span class="sxs-lookup"><span data-stu-id="2c0f5-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="2c0f5-106">使用`static`(`Shared`在 Visual Basic 中)<xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>属性来访问协调世界时。</span><span class="sxs-lookup"><span data-stu-id="2c0f5-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="2c0f5-107">而不是分配<xref:System.TimeZoneInfo>对象属性返回给对象变量，继续访问通过协调世界时<xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="2c0f5-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="2c0f5-108">访问本地时区</span><span class="sxs-lookup"><span data-stu-id="2c0f5-108">To access the local time zone</span></span>

1. <span data-ttu-id="2c0f5-109">使用`static`(`Shared`在 Visual Basic 中)<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>属性来访问本地系统时区。</span><span class="sxs-lookup"><span data-stu-id="2c0f5-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="2c0f5-110">而不是分配<xref:System.TimeZoneInfo>对象属性返回给对象变量，继续访问本地时区通过<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="2c0f5-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="2c0f5-111">示例</span><span class="sxs-lookup"><span data-stu-id="2c0f5-111">Example</span></span>

<span data-ttu-id="2c0f5-112">下面的代码使用 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 和 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> 属性转换美国和加拿大东部标准时区的时间，并将时区名称显示到控制台。</span><span class="sxs-lookup"><span data-stu-id="2c0f5-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="2c0f5-113">你应始终访问本地时区通过<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>属性，而不是无需分配本地时间时区分配给<xref:System.TimeZoneInfo>对象变量。</span><span class="sxs-lookup"><span data-stu-id="2c0f5-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="2c0f5-114">同样，你应始终访问通过协调世界时<xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>属性，而不是无需分配 UTC 时区分配给<xref:System.TimeZoneInfo>对象变量。</span><span class="sxs-lookup"><span data-stu-id="2c0f5-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="2c0f5-115">这可以防止<xref:System.TimeZoneInfo>通过调用而失效的对象变量<xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="2c0f5-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="2c0f5-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="2c0f5-116">Compiling the code</span></span>

<span data-ttu-id="2c0f5-117">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="2c0f5-117">This example requires:</span></span>

* <span data-ttu-id="2c0f5-118">对 System.Core.dll 的引用无法添加到项目。</span><span class="sxs-lookup"><span data-stu-id="2c0f5-118">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="2c0f5-119"><xref:System>命名空间导入`using`语句 （C# 代码中需要）。</span><span class="sxs-lookup"><span data-stu-id="2c0f5-119">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="2c0f5-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c0f5-120">See also</span></span>

<span data-ttu-id="2c0f5-121">[日期、 时间和时区](../../../docs/standard/datetime/index.md)
[查找本地系统上定义的时区](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[如何： 实例化 TimeZoneInfo 对象](../../../docs/standard/datetime/instantiate-time-zone-info.md)</span><span class="sxs-lookup"><span data-stu-id="2c0f5-121">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
[How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md)</span></span>

---
title: 如何：访问预定义的 UTC 和本地时区对象
ms.date: 04/10/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: ef22753d9934a52d955412a4493b608f265519aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132603"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="aff35-102">如何：访问预定义的 UTC 和本地时区对象</span><span class="sxs-lookup"><span data-stu-id="aff35-102">How to: Access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="aff35-103"><xref:System.TimeZoneInfo> 类提供了两个属性，<xref:System.TimeZoneInfo.Utc%2A> 和 <xref:System.TimeZoneInfo.Local%2A>，使代码可以访问预定义的时区对象。</span><span class="sxs-lookup"><span data-stu-id="aff35-103">The <xref:System.TimeZoneInfo> class provides two properties, <xref:System.TimeZoneInfo.Utc%2A> and <xref:System.TimeZoneInfo.Local%2A>, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="aff35-104">本主题介绍如何访问这些属性返回的 <xref:System.TimeZoneInfo> 对象。</span><span class="sxs-lookup"><span data-stu-id="aff35-104">This topic discusses how to access the <xref:System.TimeZoneInfo> objects returned by those properties.</span></span>

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="aff35-105">访问协调世界时 (UTC) TimeZoneInfo 对象</span><span class="sxs-lookup"><span data-stu-id="aff35-105">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="aff35-106">使用 `static` （Visual Basic 中`Shared`） <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> 属性访问协调世界时。</span><span class="sxs-lookup"><span data-stu-id="aff35-106">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="aff35-107">不是将属性返回的 <xref:System.TimeZoneInfo> 对象分配给对象变量，而是继续通过 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> 属性访问协调世界时。</span><span class="sxs-lookup"><span data-stu-id="aff35-107">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property.</span></span>

### <a name="to-access-the-local-time-zone"></a><span data-ttu-id="aff35-108">访问本地时区</span><span class="sxs-lookup"><span data-stu-id="aff35-108">To access the local time zone</span></span>

1. <span data-ttu-id="aff35-109">使用 `static` （Visual Basic 中`Shared`） <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 属性访问本地系统时区。</span><span class="sxs-lookup"><span data-stu-id="aff35-109">Use the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property to access the local system time zone.</span></span>

2. <span data-ttu-id="aff35-110">不是将属性返回的 <xref:System.TimeZoneInfo> 对象分配给对象变量，而是继续通过 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 属性访问本地时区。</span><span class="sxs-lookup"><span data-stu-id="aff35-110">Rather than assigning the <xref:System.TimeZoneInfo> object returned by the property to an object variable, continue to access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property.</span></span>

## <a name="example"></a><span data-ttu-id="aff35-111">示例</span><span class="sxs-lookup"><span data-stu-id="aff35-111">Example</span></span>

<span data-ttu-id="aff35-112">下面的代码使用 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 和 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> 属性转换美国和加拿大东部标准时区的时间，并将时区名称显示到控制台。</span><span class="sxs-lookup"><span data-stu-id="aff35-112">The following code uses the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> and <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

<span data-ttu-id="aff35-113">应始终通过 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 属性访问本地时区，而不是将本地时区分配给 <xref:System.TimeZoneInfo> 对象变量。</span><span class="sxs-lookup"><span data-stu-id="aff35-113">You should always access the local time zone through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property rather than assigning the local time zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="aff35-114">同样，应始终通过 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> 属性访问协调世界时，而不是将 UTC 时区分配给 <xref:System.TimeZoneInfo> 对象变量。</span><span class="sxs-lookup"><span data-stu-id="aff35-114">Similarly, you should always access Coordinated Universal Time through the <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> property rather than assigning the UTC zone to a <xref:System.TimeZoneInfo> object variable.</span></span> <span data-ttu-id="aff35-115">这会阻止 <xref:System.TimeZoneInfo> 对象变量通过调用 <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> 方法来使其失效。</span><span class="sxs-lookup"><span data-stu-id="aff35-115">This prevents the <xref:System.TimeZoneInfo> object variable from being invalidated by a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="aff35-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="aff35-116">Compiling the code</span></span>

<span data-ttu-id="aff35-117">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="aff35-117">This example requires:</span></span>

- <span data-ttu-id="aff35-118">将 <xref:System> 命名空间与 `using` 语句一起导入（在代码C#中是必需的）。</span><span class="sxs-lookup"><span data-stu-id="aff35-118">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="aff35-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="aff35-119">See also</span></span>

- [<span data-ttu-id="aff35-120">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="aff35-120">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="aff35-121">查找本地系统上定义的时区</span><span class="sxs-lookup"><span data-stu-id="aff35-121">Finding the time zones defined on a local system</span></span>](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [<span data-ttu-id="aff35-122">如何：实例化 TimeZoneInfo 对象</span><span class="sxs-lookup"><span data-stu-id="aff35-122">How to: Instantiate a TimeZoneInfo object</span></span>](../../../docs/standard/datetime/instantiate-time-zone-info.md)

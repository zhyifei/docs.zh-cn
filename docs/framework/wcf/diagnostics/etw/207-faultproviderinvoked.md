---
title: 207 - FaultProviderInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9035739f8625a07e8bf2b9bce2fe109880676405
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="d0144-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="d0144-102">207 - FaultProviderInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="d0144-103">属性</span><span class="sxs-lookup"><span data-stu-id="d0144-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0144-104">ID</span><span class="sxs-lookup"><span data-stu-id="d0144-104">ID</span></span>|<span data-ttu-id="d0144-105">207</span><span class="sxs-lookup"><span data-stu-id="d0144-105">207</span></span>|  
|<span data-ttu-id="d0144-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d0144-106">Keywords</span></span>|<span data-ttu-id="d0144-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d0144-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="d0144-108">级别</span><span class="sxs-lookup"><span data-stu-id="d0144-108">Level</span></span>|<span data-ttu-id="d0144-109">信息</span><span class="sxs-lookup"><span data-stu-id="d0144-109">Information</span></span>|  
|<span data-ttu-id="d0144-110">通道</span><span class="sxs-lookup"><span data-stu-id="d0144-110">Channel</span></span>|<span data-ttu-id="d0144-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="d0144-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d0144-112">描述</span><span class="sxs-lookup"><span data-stu-id="d0144-112">Description</span></span>  
 <span data-ttu-id="d0144-113">此事件在调用 `FaultProvider` 之后发出。</span><span class="sxs-lookup"><span data-stu-id="d0144-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d0144-114">消息</span><span class="sxs-lookup"><span data-stu-id="d0144-114">Message</span></span>  
 <span data-ttu-id="d0144-115">调度程序调用了“%1”类型的 FaultProvider 来处理“%2”类型的异常。</span><span class="sxs-lookup"><span data-stu-id="d0144-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d0144-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="d0144-116">Details</span></span>  
  
|<span data-ttu-id="d0144-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d0144-117">Data Item Name</span></span>|<span data-ttu-id="d0144-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d0144-118">Data Item Type</span></span>|<span data-ttu-id="d0144-119">描述</span><span class="sxs-lookup"><span data-stu-id="d0144-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d0144-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="d0144-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="d0144-121">所调用 `FaultProvider` 的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="d0144-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="d0144-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="d0144-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="d0144-123">`FaultProvider` 处理的异常的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="d0144-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="d0144-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="d0144-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="d0144-125">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="d0144-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d0144-126">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="d0144-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d0144-127">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="d0144-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d0144-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d0144-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d0144-129">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d0144-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

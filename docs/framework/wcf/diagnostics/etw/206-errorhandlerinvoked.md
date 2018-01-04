---
title: 206 - ErrorHandlerInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 43acd7ae7bbfc84e1d1ffb1bf4fa49a3dd3f191a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="8d7fe-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="8d7fe-102">206 - ErrorHandlerInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="8d7fe-103">属性</span><span class="sxs-lookup"><span data-stu-id="8d7fe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d7fe-104">Id</span><span class="sxs-lookup"><span data-stu-id="8d7fe-104">ID</span></span>|<span data-ttu-id="8d7fe-105">206</span><span class="sxs-lookup"><span data-stu-id="8d7fe-105">206</span></span>|  
|<span data-ttu-id="8d7fe-106">关键字</span><span class="sxs-lookup"><span data-stu-id="8d7fe-106">Keywords</span></span>|<span data-ttu-id="8d7fe-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8d7fe-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="8d7fe-108">级别</span><span class="sxs-lookup"><span data-stu-id="8d7fe-108">Level</span></span>|<span data-ttu-id="8d7fe-109">信息</span><span class="sxs-lookup"><span data-stu-id="8d7fe-109">Information</span></span>|  
|<span data-ttu-id="8d7fe-110">通道</span><span class="sxs-lookup"><span data-stu-id="8d7fe-110">Channel</span></span>|<span data-ttu-id="8d7fe-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="8d7fe-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8d7fe-112">描述</span><span class="sxs-lookup"><span data-stu-id="8d7fe-112">Description</span></span>  
 <span data-ttu-id="8d7fe-113">当 `ErrorHandler` 有机会处理在服务操作中发生的异常后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="8d7fe-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8d7fe-114">消息</span><span class="sxs-lookup"><span data-stu-id="8d7fe-114">Message</span></span>  
 <span data-ttu-id="8d7fe-115">调度程序调用类型 '%1' 的类型"%3"的异常 errorhandler 来的处理。</span><span class="sxs-lookup"><span data-stu-id="8d7fe-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="8d7fe-116">ErrorHandled 为“%2”。</span><span class="sxs-lookup"><span data-stu-id="8d7fe-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8d7fe-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="8d7fe-117">Details</span></span>  
  
|<span data-ttu-id="8d7fe-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="8d7fe-118">Data Item Name</span></span>|<span data-ttu-id="8d7fe-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="8d7fe-119">Data Item Type</span></span>|<span data-ttu-id="8d7fe-120">描述</span><span class="sxs-lookup"><span data-stu-id="8d7fe-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8d7fe-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="8d7fe-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="8d7fe-122">所调用 `ErrorHandler` 的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="8d7fe-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="8d7fe-123">Handled</span><span class="sxs-lookup"><span data-stu-id="8d7fe-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="8d7fe-124">如果错误处理程序已处理错误，则为 `true`；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="8d7fe-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="8d7fe-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="8d7fe-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="8d7fe-126">待处理异常的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="8d7fe-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="8d7fe-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="8d7fe-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="8d7fe-128">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="8d7fe-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="8d7fe-129">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="8d7fe-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="8d7fe-130">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="8d7fe-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="8d7fe-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8d7fe-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8d7fe-132">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="8d7fe-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

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
ms.openlocfilehash: 4ff48217b1430002e1590ec3fdb1707d65075ffe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="be50e-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="be50e-102">206 - ErrorHandlerInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="be50e-103">属性</span><span class="sxs-lookup"><span data-stu-id="be50e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be50e-104">ID</span><span class="sxs-lookup"><span data-stu-id="be50e-104">ID</span></span>|<span data-ttu-id="be50e-105">206</span><span class="sxs-lookup"><span data-stu-id="be50e-105">206</span></span>|  
|<span data-ttu-id="be50e-106">关键字</span><span class="sxs-lookup"><span data-stu-id="be50e-106">Keywords</span></span>|<span data-ttu-id="be50e-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="be50e-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="be50e-108">级别</span><span class="sxs-lookup"><span data-stu-id="be50e-108">Level</span></span>|<span data-ttu-id="be50e-109">信息</span><span class="sxs-lookup"><span data-stu-id="be50e-109">Information</span></span>|  
|<span data-ttu-id="be50e-110">通道</span><span class="sxs-lookup"><span data-stu-id="be50e-110">Channel</span></span>|<span data-ttu-id="be50e-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="be50e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="be50e-112">描述</span><span class="sxs-lookup"><span data-stu-id="be50e-112">Description</span></span>  
 <span data-ttu-id="be50e-113">当 `ErrorHandler` 有机会处理在服务操作中发生的异常后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="be50e-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="be50e-114">消息</span><span class="sxs-lookup"><span data-stu-id="be50e-114">Message</span></span>  
 <span data-ttu-id="be50e-115">调度程序调用类型 '%1' 的类型"%3"的异常 errorhandler 来的处理。</span><span class="sxs-lookup"><span data-stu-id="be50e-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="be50e-116">ErrorHandled 为“%2”。</span><span class="sxs-lookup"><span data-stu-id="be50e-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="be50e-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="be50e-117">Details</span></span>  
  
|<span data-ttu-id="be50e-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="be50e-118">Data Item Name</span></span>|<span data-ttu-id="be50e-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="be50e-119">Data Item Type</span></span>|<span data-ttu-id="be50e-120">描述</span><span class="sxs-lookup"><span data-stu-id="be50e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="be50e-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="be50e-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="be50e-122">所调用 `ErrorHandler` 的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="be50e-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="be50e-123">Handled</span><span class="sxs-lookup"><span data-stu-id="be50e-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="be50e-124">如果错误处理程序已处理错误，则为 `true`；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="be50e-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="be50e-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="be50e-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="be50e-126">待处理异常的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="be50e-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="be50e-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="be50e-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="be50e-128">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="be50e-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="be50e-129">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="be50e-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="be50e-130">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="be50e-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="be50e-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="be50e-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="be50e-132">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="be50e-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

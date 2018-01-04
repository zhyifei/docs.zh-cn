---
title: 219 - ServiceException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81e2efac-39aa-4ed2-85a9-97eb8793b844
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fceff5c748076c75c942f515e2621edff5106f4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="219---serviceexception"></a><span data-ttu-id="ece79-102">219 - ServiceException</span><span class="sxs-lookup"><span data-stu-id="ece79-102">219 - ServiceException</span></span>
## <a name="properties"></a><span data-ttu-id="ece79-103">属性</span><span class="sxs-lookup"><span data-stu-id="ece79-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ece79-104">Id</span><span class="sxs-lookup"><span data-stu-id="ece79-104">ID</span></span>|<span data-ttu-id="ece79-105">219</span><span class="sxs-lookup"><span data-stu-id="ece79-105">219</span></span>|  
|<span data-ttu-id="ece79-106">关键字</span><span class="sxs-lookup"><span data-stu-id="ece79-106">Keywords</span></span>|<span data-ttu-id="ece79-107">EndToEndMonitoring、HealthMonitoring、疑难解答、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ece79-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="ece79-108">级别</span><span class="sxs-lookup"><span data-stu-id="ece79-108">Level</span></span>|<span data-ttu-id="ece79-109">错误</span><span class="sxs-lookup"><span data-stu-id="ece79-109">Error</span></span>|  
|<span data-ttu-id="ece79-110">通道</span><span class="sxs-lookup"><span data-stu-id="ece79-110">Channel</span></span>|<span data-ttu-id="ece79-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="ece79-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ece79-112">描述</span><span class="sxs-lookup"><span data-stu-id="ece79-112">Description</span></span>  
 <span data-ttu-id="ece79-113">当 WCF 服务遇到未经处理的异常时会发出此事件。</span><span class="sxs-lookup"><span data-stu-id="ece79-113">This event is emitted when a WCF service encounters an unhandled exception.</span></span> <span data-ttu-id="ece79-114">这包括在激活和消息处理期间以及在用户代码中出现的未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="ece79-114">This includes unhandled exceptions during activation, during message processing, and in user code.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ece79-115">消息</span><span class="sxs-lookup"><span data-stu-id="ece79-115">Message</span></span>  
 <span data-ttu-id="ece79-116">消息处理过程中出现了“%2”类型的未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="ece79-116">There was an unhandled exception of type '%2' during message processing.</span></span> <span data-ttu-id="ece79-117">完整异常 ToString: %1。</span><span class="sxs-lookup"><span data-stu-id="ece79-117">Full Exception ToString: %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ece79-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="ece79-118">Details</span></span>  
  
|<span data-ttu-id="ece79-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="ece79-119">Data Item Name</span></span>|<span data-ttu-id="ece79-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="ece79-120">Data Item Type</span></span>|<span data-ttu-id="ece79-121">描述</span><span class="sxs-lookup"><span data-stu-id="ece79-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ece79-122">ExceptionToString</span><span class="sxs-lookup"><span data-stu-id="ece79-122">ExceptionToString</span></span>|`xs:string`|<span data-ttu-id="ece79-123">对 CLR 异常调用 `ToString`() 的结果。</span><span class="sxs-lookup"><span data-stu-id="ece79-123">The result of calling `ToString`() on the CLR exception.</span></span>|  
|<span data-ttu-id="ece79-124">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="ece79-124">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="ece79-125">异常的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="ece79-125">The CLR FullName of the exception's type.</span></span>|  
|<span data-ttu-id="ece79-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="ece79-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="ece79-127">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="ece79-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ece79-128">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="ece79-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ece79-129">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="ece79-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ece79-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ece79-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ece79-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="ece79-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

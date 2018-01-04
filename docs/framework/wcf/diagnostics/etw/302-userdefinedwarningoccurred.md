---
title: "302 - 出现用户定义的警告"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d1f0bf1-0151-45e6-be92-573d397b54de
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae455c9eec2335fcf6eb5473932bd8d9e5d2db95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="302---userdefinedwarningoccurred"></a><span data-ttu-id="ec5bf-102">302 - 出现用户定义的警告</span><span class="sxs-lookup"><span data-stu-id="ec5bf-102">302 - UserDefinedWarningOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="ec5bf-103">属性</span><span class="sxs-lookup"><span data-stu-id="ec5bf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec5bf-104">Id</span><span class="sxs-lookup"><span data-stu-id="ec5bf-104">ID</span></span>|<span data-ttu-id="ec5bf-105">302</span><span class="sxs-lookup"><span data-stu-id="ec5bf-105">302</span></span>|  
|<span data-ttu-id="ec5bf-106">关键字</span><span class="sxs-lookup"><span data-stu-id="ec5bf-106">Keywords</span></span>|<span data-ttu-id="ec5bf-107">疑难解答，HealthMonitoring，UserEvents，ServiceModel，EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="ec5bf-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="ec5bf-108">级别</span><span class="sxs-lookup"><span data-stu-id="ec5bf-108">Level</span></span>|<span data-ttu-id="ec5bf-109">警告</span><span class="sxs-lookup"><span data-stu-id="ec5bf-109">Warning</span></span>|  
|<span data-ttu-id="ec5bf-110">通道</span><span class="sxs-lookup"><span data-stu-id="ec5bf-110">Channel</span></span>|<span data-ttu-id="ec5bf-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="ec5bf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ec5bf-112">描述</span><span class="sxs-lookup"><span data-stu-id="ec5bf-112">Description</span></span>  
 <span data-ttu-id="ec5bf-113">此事件从用户代码发出。</span><span class="sxs-lookup"><span data-stu-id="ec5bf-113">This event is emitted from user code.</span></span> <span data-ttu-id="ec5bf-114">当开发人员的服务中出现自定义的警告事件时，开发人员可以发出此事件。</span><span class="sxs-lookup"><span data-stu-id="ec5bf-114">Developers can emit this event when a custom-defined warning event occurs in their service.</span></span> <span data-ttu-id="ec5bf-115">可以使用 <xref:System.Diagnostics.Eventing> API 完成此操作。</span><span class="sxs-lookup"><span data-stu-id="ec5bf-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="ec5bf-116">此外，还提供了一个 WCF 示例，该示例包装 API 并演示如何正确发出此事件。</span><span class="sxs-lookup"><span data-stu-id="ec5bf-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ec5bf-117">消息</span><span class="sxs-lookup"><span data-stu-id="ec5bf-117">Message</span></span>  
 <span data-ttu-id="ec5bf-118">Name“%1”、Reference“%2”、Payload: %3</span><span class="sxs-lookup"><span data-stu-id="ec5bf-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="ec5bf-119">详细信息</span><span class="sxs-lookup"><span data-stu-id="ec5bf-119">Details</span></span>  
  
|<span data-ttu-id="ec5bf-120">数据项名称</span><span class="sxs-lookup"><span data-stu-id="ec5bf-120">Data Item Name</span></span>|<span data-ttu-id="ec5bf-121">数据项类型</span><span class="sxs-lookup"><span data-stu-id="ec5bf-121">Data Item Type</span></span>|<span data-ttu-id="ec5bf-122">描述</span><span class="sxs-lookup"><span data-stu-id="ec5bf-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ec5bf-123">name</span><span class="sxs-lookup"><span data-stu-id="ec5bf-123">Name</span></span>|`xs:string`|<span data-ttu-id="ec5bf-124">事件的用户定义名称。</span><span class="sxs-lookup"><span data-stu-id="ec5bf-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="ec5bf-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="ec5bf-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="ec5bf-126">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="ec5bf-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="ec5bf-127">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="ec5bf-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="ec5bf-128">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="ec5bf-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="ec5bf-129">Payload</span><span class="sxs-lookup"><span data-stu-id="ec5bf-129">Payload</span></span>|`xs:string`|<span data-ttu-id="ec5bf-130">事件的用户定义负载。</span><span class="sxs-lookup"><span data-stu-id="ec5bf-130">The user-defined payload of the event.</span></span>|

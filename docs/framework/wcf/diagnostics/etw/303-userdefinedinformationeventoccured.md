---
title: 303 - UserDefinedInformationEventOccured
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3bc04837834277dccc9d21d27e89c84f09f36167
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="303---userdefinedinformationeventoccured"></a><span data-ttu-id="25fc3-102">303 - UserDefinedInformationEventOccured</span><span class="sxs-lookup"><span data-stu-id="25fc3-102">303 - UserDefinedInformationEventOccured</span></span>
## <a name="properties"></a><span data-ttu-id="25fc3-103">属性</span><span class="sxs-lookup"><span data-stu-id="25fc3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25fc3-104">ID</span><span class="sxs-lookup"><span data-stu-id="25fc3-104">ID</span></span>|<span data-ttu-id="25fc3-105">303</span><span class="sxs-lookup"><span data-stu-id="25fc3-105">303</span></span>|  
|<span data-ttu-id="25fc3-106">关键字</span><span class="sxs-lookup"><span data-stu-id="25fc3-106">Keywords</span></span>|<span data-ttu-id="25fc3-107">疑难解答，HealthMonitoring，UserEvents，ServiceModel，EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="25fc3-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="25fc3-108">级别</span><span class="sxs-lookup"><span data-stu-id="25fc3-108">Level</span></span>|<span data-ttu-id="25fc3-109">信息</span><span class="sxs-lookup"><span data-stu-id="25fc3-109">Information</span></span>|  
|<span data-ttu-id="25fc3-110">通道</span><span class="sxs-lookup"><span data-stu-id="25fc3-110">Channel</span></span>|<span data-ttu-id="25fc3-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="25fc3-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="25fc3-112">描述</span><span class="sxs-lookup"><span data-stu-id="25fc3-112">Description</span></span>  
 <span data-ttu-id="25fc3-113">此事件从用户代码发出。</span><span class="sxs-lookup"><span data-stu-id="25fc3-113">This event is emitted from user code.</span></span> <span data-ttu-id="25fc3-114">当开发人员的服务中出现自定义的信息性事件时，开发人员可以发出此事件。</span><span class="sxs-lookup"><span data-stu-id="25fc3-114">Developers can emit this event when a custom-defined informational event occurs in their service.</span></span> <span data-ttu-id="25fc3-115">可以使用 <xref:System.Diagnostics.Eventing> API 完成此操作。</span><span class="sxs-lookup"><span data-stu-id="25fc3-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="25fc3-116">此外，还提供了一个 WCF 示例，该示例包装 API 并演示如何正确发出此事件。</span><span class="sxs-lookup"><span data-stu-id="25fc3-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="25fc3-117">消息</span><span class="sxs-lookup"><span data-stu-id="25fc3-117">Message</span></span>  
 <span data-ttu-id="25fc3-118">Name“%1”、Reference“%2”、Payload: %3</span><span class="sxs-lookup"><span data-stu-id="25fc3-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="25fc3-119">详细信息</span><span class="sxs-lookup"><span data-stu-id="25fc3-119">Details</span></span>  
  
|<span data-ttu-id="25fc3-120">数据项名称</span><span class="sxs-lookup"><span data-stu-id="25fc3-120">Data Item Name</span></span>|<span data-ttu-id="25fc3-121">数据项类型</span><span class="sxs-lookup"><span data-stu-id="25fc3-121">Data Item Type</span></span>|<span data-ttu-id="25fc3-122">描述</span><span class="sxs-lookup"><span data-stu-id="25fc3-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="25fc3-123">名称</span><span class="sxs-lookup"><span data-stu-id="25fc3-123">Name</span></span>|`xs:string`|<span data-ttu-id="25fc3-124">事件的用户定义名称</span><span class="sxs-lookup"><span data-stu-id="25fc3-124">The user-defined name of the event</span></span>|  
|<span data-ttu-id="25fc3-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="25fc3-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="25fc3-126">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="25fc3-126">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="25fc3-127">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="25fc3-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="25fc3-128">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="25fc3-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="25fc3-129">Payload</span><span class="sxs-lookup"><span data-stu-id="25fc3-129">Payload</span></span>|`xs:string`|<span data-ttu-id="25fc3-130">事件的用户定义负载。</span><span class="sxs-lookup"><span data-stu-id="25fc3-130">The user-defined payload of the event.</span></span>|

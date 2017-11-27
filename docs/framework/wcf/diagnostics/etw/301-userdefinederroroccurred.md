---
title: 301 - UserDefinedErrorOccurred
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: df75fdfa68e11a4a017dffa54e1bb4d628940968
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="301---userdefinederroroccurred"></a><span data-ttu-id="2c242-102">301 - UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="2c242-102">301 - UserDefinedErrorOccurred</span></span>
## <a name="properties"></a><span data-ttu-id="2c242-103">属性</span><span class="sxs-lookup"><span data-stu-id="2c242-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2c242-104">ID</span><span class="sxs-lookup"><span data-stu-id="2c242-104">ID</span></span>|<span data-ttu-id="2c242-105">301</span><span class="sxs-lookup"><span data-stu-id="2c242-105">301</span></span>|  
|<span data-ttu-id="2c242-106">关键字</span><span class="sxs-lookup"><span data-stu-id="2c242-106">Keywords</span></span>|<span data-ttu-id="2c242-107">疑难解答，HealthMonitoring，UserEvents，ServiceModel，EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="2c242-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="2c242-108">级别</span><span class="sxs-lookup"><span data-stu-id="2c242-108">Level</span></span>|<span data-ttu-id="2c242-109">错误</span><span class="sxs-lookup"><span data-stu-id="2c242-109">Error</span></span>|  
|<span data-ttu-id="2c242-110">通道</span><span class="sxs-lookup"><span data-stu-id="2c242-110">Channel</span></span>|<span data-ttu-id="2c242-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="2c242-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2c242-112">描述</span><span class="sxs-lookup"><span data-stu-id="2c242-112">Description</span></span>  
 <span data-ttu-id="2c242-113">此事件从用户代码发出。</span><span class="sxs-lookup"><span data-stu-id="2c242-113">This event is emitted from user code.</span></span> <span data-ttu-id="2c242-114">当开发人员的服务中出现自定义错误时，开发人员可以发出此事件。</span><span class="sxs-lookup"><span data-stu-id="2c242-114">Developers can emit this event when a custom-defined error occurs in their service.</span></span> <span data-ttu-id="2c242-115">可以使用 <xref:System.Diagnostics.Eventing> API 完成此操作。</span><span class="sxs-lookup"><span data-stu-id="2c242-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="2c242-116">此外，还提供了一个 WCF 示例，该示例包装 API 并演示如何正确发出此事件。</span><span class="sxs-lookup"><span data-stu-id="2c242-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2c242-117">消息</span><span class="sxs-lookup"><span data-stu-id="2c242-117">Message</span></span>  
 <span data-ttu-id="2c242-118">Name“%1”、Reference“%2”、Payload: %3</span><span class="sxs-lookup"><span data-stu-id="2c242-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="2c242-119">详细信息</span><span class="sxs-lookup"><span data-stu-id="2c242-119">Details</span></span>  
  
|<span data-ttu-id="2c242-120">数据项名称</span><span class="sxs-lookup"><span data-stu-id="2c242-120">Data Item Name</span></span>|<span data-ttu-id="2c242-121">数据项类型</span><span class="sxs-lookup"><span data-stu-id="2c242-121">Data Item Type</span></span>|<span data-ttu-id="2c242-122">描述</span><span class="sxs-lookup"><span data-stu-id="2c242-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2c242-123">名称</span><span class="sxs-lookup"><span data-stu-id="2c242-123">Name</span></span>|`xs:string`|<span data-ttu-id="2c242-124">事件的用户定义名称。</span><span class="sxs-lookup"><span data-stu-id="2c242-124">The user-defined name of the event.</span></span>|  
|<span data-ttu-id="2c242-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="2c242-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="2c242-126">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="2c242-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2c242-127">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="2c242-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2c242-128">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="2c242-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2c242-129">Payload</span><span class="sxs-lookup"><span data-stu-id="2c242-129">Payload</span></span>|`xs:string`|<span data-ttu-id="2c242-130">事件的用户定义负载。</span><span class="sxs-lookup"><span data-stu-id="2c242-130">The user-defined payload of the event.</span></span>|

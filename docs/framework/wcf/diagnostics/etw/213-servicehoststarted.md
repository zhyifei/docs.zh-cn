---
title: 213 - ServiceHostStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 61d79adce71be9ef93e9232e01a8cba5f5319f79
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="213---servicehoststarted"></a><span data-ttu-id="2cb6e-102">213 - ServiceHostStarted</span><span class="sxs-lookup"><span data-stu-id="2cb6e-102">213 - ServiceHostStarted</span></span>
## <a name="properties"></a><span data-ttu-id="2cb6e-103">属性</span><span class="sxs-lookup"><span data-stu-id="2cb6e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2cb6e-104">ID</span><span class="sxs-lookup"><span data-stu-id="2cb6e-104">ID</span></span>|<span data-ttu-id="2cb6e-105">213</span><span class="sxs-lookup"><span data-stu-id="2cb6e-105">213</span></span>|  
|<span data-ttu-id="2cb6e-106">关键字</span><span class="sxs-lookup"><span data-stu-id="2cb6e-106">Keywords</span></span>|<span data-ttu-id="2cb6e-107">EndToEndMonitoring，HealthMonitoring，疑难解答，ServiceHost</span><span class="sxs-lookup"><span data-stu-id="2cb6e-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost</span></span>|  
|<span data-ttu-id="2cb6e-108">级别</span><span class="sxs-lookup"><span data-stu-id="2cb6e-108">Level</span></span>|<span data-ttu-id="2cb6e-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="2cb6e-109">LogAlways</span></span>|  
|<span data-ttu-id="2cb6e-110">通道</span><span class="sxs-lookup"><span data-stu-id="2cb6e-110">Channel</span></span>|<span data-ttu-id="2cb6e-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="2cb6e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2cb6e-112">描述</span><span class="sxs-lookup"><span data-stu-id="2cb6e-112">Description</span></span>  
 <span data-ttu-id="2cb6e-113">在启动 Web 承载的服务主机时发出此事件。</span><span class="sxs-lookup"><span data-stu-id="2cb6e-113">This event is emitted when a Web-hosted service host is started.</span></span> <span data-ttu-id="2cb6e-114">这通常在消息激活服务时发生。</span><span class="sxs-lookup"><span data-stu-id="2cb6e-114">This typically happens when the service is activated by a message.</span></span> <span data-ttu-id="2cb6e-115">如果将服务配置为自动启动，也可能发生此事件。</span><span class="sxs-lookup"><span data-stu-id="2cb6e-115">It may also happen if the service is configured to be automatically started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2cb6e-116">消息</span><span class="sxs-lookup"><span data-stu-id="2cb6e-116">Message</span></span>  
 <span data-ttu-id="2cb6e-117">ServiceHost 已启动:“%1”。</span><span class="sxs-lookup"><span data-stu-id="2cb6e-117">ServiceHost started: '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2cb6e-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="2cb6e-118">Details</span></span>  
  
|<span data-ttu-id="2cb6e-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="2cb6e-119">Data Item Name</span></span>|<span data-ttu-id="2cb6e-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="2cb6e-120">Data Item Type</span></span>|<span data-ttu-id="2cb6e-121">描述</span><span class="sxs-lookup"><span data-stu-id="2cb6e-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2cb6e-122">服务类型名称</span><span class="sxs-lookup"><span data-stu-id="2cb6e-122">Service Type Name</span></span>|`xs:string`|<span data-ttu-id="2cb6e-123">服务实现的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="2cb6e-123">The CLR FullName of the type of the service implementation.</span></span>|  
|<span data-ttu-id="2cb6e-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="2cb6e-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="2cb6e-125">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="2cb6e-125">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2cb6e-126">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="2cb6e-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2cb6e-127">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="2cb6e-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2cb6e-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2cb6e-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2cb6e-129">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="2cb6e-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

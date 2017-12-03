---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 461c9e423abb7b34edec4135f05f8fcf66244cfc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="87205-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="87205-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="87205-103">属性</span><span class="sxs-lookup"><span data-stu-id="87205-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87205-104">ID</span><span class="sxs-lookup"><span data-stu-id="87205-104">ID</span></span>|<span data-ttu-id="87205-105">202</span><span class="sxs-lookup"><span data-stu-id="87205-105">202</span></span>|  
|<span data-ttu-id="87205-106">关键字</span><span class="sxs-lookup"><span data-stu-id="87205-106">Keywords</span></span>|<span data-ttu-id="87205-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="87205-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="87205-108">级别</span><span class="sxs-lookup"><span data-stu-id="87205-108">Level</span></span>|<span data-ttu-id="87205-109">信息</span><span class="sxs-lookup"><span data-stu-id="87205-109">Information</span></span>|  
|<span data-ttu-id="87205-110">通道</span><span class="sxs-lookup"><span data-stu-id="87205-110">Channel</span></span>|<span data-ttu-id="87205-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="87205-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="87205-112">描述</span><span class="sxs-lookup"><span data-stu-id="87205-112">Description</span></span>  
 <span data-ttu-id="87205-113">服务模型在客户端消息检查器上调用 `BeforeSendRequest` 方法之后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="87205-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="87205-114">消息</span><span class="sxs-lookup"><span data-stu-id="87205-114">Message</span></span>  
 <span data-ttu-id="87205-115">调度程序对“%1”类型的 ClientMessageInspector 调用了“BeforeSendRequest”。</span><span class="sxs-lookup"><span data-stu-id="87205-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="87205-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="87205-116">Details</span></span>  
  
|<span data-ttu-id="87205-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="87205-117">Data Item Name</span></span>|<span data-ttu-id="87205-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="87205-118">Data Item Type</span></span>|<span data-ttu-id="87205-119">描述</span><span class="sxs-lookup"><span data-stu-id="87205-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="87205-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="87205-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="87205-121">所调用检查器的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="87205-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="87205-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="87205-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="87205-123">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="87205-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="87205-124">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="87205-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="87205-125">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="87205-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="87205-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="87205-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="87205-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="87205-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

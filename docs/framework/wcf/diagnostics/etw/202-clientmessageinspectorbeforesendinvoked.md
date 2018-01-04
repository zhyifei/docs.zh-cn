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
ms.workload: dotnet
ms.openlocfilehash: f6d737a7334098961cccb73a114be9be5bb71727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="0dc83-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="0dc83-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="0dc83-103">属性</span><span class="sxs-lookup"><span data-stu-id="0dc83-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0dc83-104">Id</span><span class="sxs-lookup"><span data-stu-id="0dc83-104">ID</span></span>|<span data-ttu-id="0dc83-105">202</span><span class="sxs-lookup"><span data-stu-id="0dc83-105">202</span></span>|  
|<span data-ttu-id="0dc83-106">关键字</span><span class="sxs-lookup"><span data-stu-id="0dc83-106">Keywords</span></span>|<span data-ttu-id="0dc83-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0dc83-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0dc83-108">级别</span><span class="sxs-lookup"><span data-stu-id="0dc83-108">Level</span></span>|<span data-ttu-id="0dc83-109">信息</span><span class="sxs-lookup"><span data-stu-id="0dc83-109">Information</span></span>|  
|<span data-ttu-id="0dc83-110">通道</span><span class="sxs-lookup"><span data-stu-id="0dc83-110">Channel</span></span>|<span data-ttu-id="0dc83-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="0dc83-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0dc83-112">描述</span><span class="sxs-lookup"><span data-stu-id="0dc83-112">Description</span></span>  
 <span data-ttu-id="0dc83-113">服务模型在客户端消息检查器上调用 `BeforeSendRequest` 方法之后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="0dc83-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0dc83-114">消息</span><span class="sxs-lookup"><span data-stu-id="0dc83-114">Message</span></span>  
 <span data-ttu-id="0dc83-115">调度程序对“%1”类型的 ClientMessageInspector 调用了“BeforeSendRequest”。</span><span class="sxs-lookup"><span data-stu-id="0dc83-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0dc83-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="0dc83-116">Details</span></span>  
  
|<span data-ttu-id="0dc83-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="0dc83-117">Data Item Name</span></span>|<span data-ttu-id="0dc83-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="0dc83-118">Data Item Type</span></span>|<span data-ttu-id="0dc83-119">描述</span><span class="sxs-lookup"><span data-stu-id="0dc83-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0dc83-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="0dc83-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="0dc83-121">所调用检查器的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="0dc83-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="0dc83-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="0dc83-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="0dc83-123">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="0dc83-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0dc83-124">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="0dc83-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0dc83-125">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="0dc83-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0dc83-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0dc83-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0dc83-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="0dc83-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

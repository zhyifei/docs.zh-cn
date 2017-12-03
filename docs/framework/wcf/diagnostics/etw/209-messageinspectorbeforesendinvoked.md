---
title: 209 - MessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3341f9ae5600536a7d824034582bf232f5be90ad
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="b52d3-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="b52d3-102">209 - MessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="b52d3-103">属性</span><span class="sxs-lookup"><span data-stu-id="b52d3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b52d3-104">ID</span><span class="sxs-lookup"><span data-stu-id="b52d3-104">ID</span></span>|<span data-ttu-id="b52d3-105">209</span><span class="sxs-lookup"><span data-stu-id="b52d3-105">209</span></span>|  
|<span data-ttu-id="b52d3-106">关键字</span><span class="sxs-lookup"><span data-stu-id="b52d3-106">Keywords</span></span>|<span data-ttu-id="b52d3-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b52d3-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b52d3-108">级别</span><span class="sxs-lookup"><span data-stu-id="b52d3-108">Level</span></span>|<span data-ttu-id="b52d3-109">信息</span><span class="sxs-lookup"><span data-stu-id="b52d3-109">Information</span></span>|  
|<span data-ttu-id="b52d3-110">通道</span><span class="sxs-lookup"><span data-stu-id="b52d3-110">Channel</span></span>|<span data-ttu-id="b52d3-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="b52d3-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b52d3-112">描述</span><span class="sxs-lookup"><span data-stu-id="b52d3-112">Description</span></span>  
 <span data-ttu-id="b52d3-113">服务模型对消息检查器调用 `BeforeSend` 方法之后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="b52d3-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b52d3-114">消息</span><span class="sxs-lookup"><span data-stu-id="b52d3-114">Message</span></span>  
 <span data-ttu-id="b52d3-115">调度程序对“%1”类型的 MessageInspector 调用了“BeforeSendRequest”。</span><span class="sxs-lookup"><span data-stu-id="b52d3-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b52d3-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="b52d3-116">Details</span></span>  
  
|<span data-ttu-id="b52d3-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="b52d3-117">Data Item Name</span></span>|<span data-ttu-id="b52d3-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="b52d3-118">Data Item Type</span></span>|<span data-ttu-id="b52d3-119">描述</span><span class="sxs-lookup"><span data-stu-id="b52d3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b52d3-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="b52d3-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="b52d3-121">所调用 `MessageInspector` 的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="b52d3-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="b52d3-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="b52d3-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="b52d3-123">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="b52d3-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b52d3-124">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="b52d3-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b52d3-125">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="b52d3-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b52d3-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b52d3-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b52d3-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="b52d3-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

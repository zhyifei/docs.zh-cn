---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 253daea49ed36e27a23c55f3baf252344c0a34f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="e7f16-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="e7f16-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="e7f16-103">属性</span><span class="sxs-lookup"><span data-stu-id="e7f16-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e7f16-104">ID</span><span class="sxs-lookup"><span data-stu-id="e7f16-104">ID</span></span>|<span data-ttu-id="e7f16-105">208</span><span class="sxs-lookup"><span data-stu-id="e7f16-105">208</span></span>|  
|<span data-ttu-id="e7f16-106">关键字</span><span class="sxs-lookup"><span data-stu-id="e7f16-106">Keywords</span></span>|<span data-ttu-id="e7f16-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e7f16-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e7f16-108">级别</span><span class="sxs-lookup"><span data-stu-id="e7f16-108">Level</span></span>|<span data-ttu-id="e7f16-109">信息</span><span class="sxs-lookup"><span data-stu-id="e7f16-109">Information</span></span>|  
|<span data-ttu-id="e7f16-110">通道</span><span class="sxs-lookup"><span data-stu-id="e7f16-110">Channel</span></span>|<span data-ttu-id="e7f16-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="e7f16-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e7f16-112">描述</span><span class="sxs-lookup"><span data-stu-id="e7f16-112">Description</span></span>  
 <span data-ttu-id="e7f16-113">服务模型对消息检查器调用 `AfterReceive` 方法之后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="e7f16-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e7f16-114">消息</span><span class="sxs-lookup"><span data-stu-id="e7f16-114">Message</span></span>  
 <span data-ttu-id="e7f16-115">调度程序对“%1”类型的 MessageInspector 调用了“AfterReceiveReply”。</span><span class="sxs-lookup"><span data-stu-id="e7f16-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e7f16-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="e7f16-116">Details</span></span>  
  
|<span data-ttu-id="e7f16-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="e7f16-117">Data Item Name</span></span>|<span data-ttu-id="e7f16-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="e7f16-118">Data Item Type</span></span>|<span data-ttu-id="e7f16-119">描述</span><span class="sxs-lookup"><span data-stu-id="e7f16-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e7f16-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="e7f16-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="e7f16-121">所调用 `MessageInspector` 的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="e7f16-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="e7f16-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="e7f16-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="e7f16-123">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="e7f16-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e7f16-124">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="e7f16-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e7f16-125">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="e7f16-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e7f16-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e7f16-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e7f16-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="e7f16-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

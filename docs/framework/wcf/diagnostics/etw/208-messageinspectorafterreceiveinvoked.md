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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cdb89eb9f2a50db20f6da53a2b3f527aef8c0ed1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="0ec9d-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="0ec9d-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="0ec9d-103">属性</span><span class="sxs-lookup"><span data-stu-id="0ec9d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ec9d-104">ID</span><span class="sxs-lookup"><span data-stu-id="0ec9d-104">ID</span></span>|<span data-ttu-id="0ec9d-105">208</span><span class="sxs-lookup"><span data-stu-id="0ec9d-105">208</span></span>|  
|<span data-ttu-id="0ec9d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="0ec9d-106">Keywords</span></span>|<span data-ttu-id="0ec9d-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0ec9d-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0ec9d-108">级别</span><span class="sxs-lookup"><span data-stu-id="0ec9d-108">Level</span></span>|<span data-ttu-id="0ec9d-109">信息</span><span class="sxs-lookup"><span data-stu-id="0ec9d-109">Information</span></span>|  
|<span data-ttu-id="0ec9d-110">通道</span><span class="sxs-lookup"><span data-stu-id="0ec9d-110">Channel</span></span>|<span data-ttu-id="0ec9d-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="0ec9d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0ec9d-112">描述</span><span class="sxs-lookup"><span data-stu-id="0ec9d-112">Description</span></span>  
 <span data-ttu-id="0ec9d-113">服务模型对消息检查器调用 `AfterReceive` 方法之后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0ec9d-114">消息</span><span class="sxs-lookup"><span data-stu-id="0ec9d-114">Message</span></span>  
 <span data-ttu-id="0ec9d-115">调度程序对“%1”类型的 MessageInspector 调用了“AfterReceiveReply”。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0ec9d-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="0ec9d-116">Details</span></span>  
  
|<span data-ttu-id="0ec9d-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="0ec9d-117">Data Item Name</span></span>|<span data-ttu-id="0ec9d-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="0ec9d-118">Data Item Type</span></span>|<span data-ttu-id="0ec9d-119">描述</span><span class="sxs-lookup"><span data-stu-id="0ec9d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0ec9d-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="0ec9d-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="0ec9d-121">所调用 `MessageInspector` 的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="0ec9d-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="0ec9d-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="0ec9d-123">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0ec9d-124">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0ec9d-125">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0ec9d-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0ec9d-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0ec9d-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="0ec9d-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

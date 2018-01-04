---
title: 499 - TransferEmitted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1034ae6bd6072a3849d72fafcad55c61e500439
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="499---transferemitted"></a><span data-ttu-id="7643c-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="7643c-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="7643c-103">属性</span><span class="sxs-lookup"><span data-stu-id="7643c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7643c-104">Id</span><span class="sxs-lookup"><span data-stu-id="7643c-104">ID</span></span>|<span data-ttu-id="7643c-105">499</span><span class="sxs-lookup"><span data-stu-id="7643c-105">499</span></span>|  
|<span data-ttu-id="7643c-106">关键字</span><span class="sxs-lookup"><span data-stu-id="7643c-106">Keywords</span></span>|<span data-ttu-id="7643c-107">疑难解答，UserEvents，EndToEndMonitoring，ServiceModel，WFTracking，ServiceHost，WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="7643c-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="7643c-108">级别</span><span class="sxs-lookup"><span data-stu-id="7643c-108">Level</span></span>|<span data-ttu-id="7643c-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="7643c-109">LogAlways</span></span>|  
|<span data-ttu-id="7643c-110">通道</span><span class="sxs-lookup"><span data-stu-id="7643c-110">Channel</span></span>|<span data-ttu-id="7643c-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="7643c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7643c-112">描述</span><span class="sxs-lookup"><span data-stu-id="7643c-112">Description</span></span>  
 <span data-ttu-id="7643c-113">此事件在发生传输事件时发出。</span><span class="sxs-lookup"><span data-stu-id="7643c-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7643c-114">消息</span><span class="sxs-lookup"><span data-stu-id="7643c-114">Message</span></span>  
 <span data-ttu-id="7643c-115">发出了传输事件。</span><span class="sxs-lookup"><span data-stu-id="7643c-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7643c-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="7643c-116">Details</span></span>  
  
|<span data-ttu-id="7643c-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="7643c-117">Data Item Name</span></span>|<span data-ttu-id="7643c-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="7643c-118">Data Item Type</span></span>|<span data-ttu-id="7643c-119">描述</span><span class="sxs-lookup"><span data-stu-id="7643c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7643c-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="7643c-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="7643c-121">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="7643c-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="7643c-122">其格式定义为网站名称应用程序虚拟路径 &#124;服务虚拟路径 &#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="7643c-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="7643c-123">示例: 默认网站/CalculatorApplication &#124;/CalculatorService.svc &#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="7643c-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="7643c-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7643c-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7643c-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="7643c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

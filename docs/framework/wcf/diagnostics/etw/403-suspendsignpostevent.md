---
title: 403 - SuspendSignpostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb2e6f29-e556-47b4-b4c1-acd6b8879702
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee1daab843ad0a2161d13b86bcd657b7236ddaa6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="a617a-102">403 - SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="a617a-102">403 - SuspendSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="a617a-103">属性</span><span class="sxs-lookup"><span data-stu-id="a617a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a617a-104">ID</span><span class="sxs-lookup"><span data-stu-id="a617a-104">ID</span></span>|<span data-ttu-id="a617a-105">403</span><span class="sxs-lookup"><span data-stu-id="a617a-105">403</span></span>|  
|<span data-ttu-id="a617a-106">关键字</span><span class="sxs-lookup"><span data-stu-id="a617a-106">Keywords</span></span>|<span data-ttu-id="a617a-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="a617a-107">Troubleshooting</span></span>|  
|<span data-ttu-id="a617a-108">级别</span><span class="sxs-lookup"><span data-stu-id="a617a-108">Level</span></span>|<span data-ttu-id="a617a-109">信息</span><span class="sxs-lookup"><span data-stu-id="a617a-109">Information</span></span>|  
|<span data-ttu-id="a617a-110">通道</span><span class="sxs-lookup"><span data-stu-id="a617a-110">Channel</span></span>|<span data-ttu-id="a617a-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="a617a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a617a-112">描述</span><span class="sxs-lookup"><span data-stu-id="a617a-112">Description</span></span>  
 <span data-ttu-id="a617a-113">此事件标记端对端活动的挂起，</span><span class="sxs-lookup"><span data-stu-id="a617a-113">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="a617a-114">它包含活动的名称。</span><span class="sxs-lookup"><span data-stu-id="a617a-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a617a-115">消息</span><span class="sxs-lookup"><span data-stu-id="a617a-115">Message</span></span>  
 <span data-ttu-id="a617a-116">活动边界。</span><span class="sxs-lookup"><span data-stu-id="a617a-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a617a-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="a617a-117">Details</span></span>  
  
|<span data-ttu-id="a617a-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="a617a-118">Data Item Name</span></span>|<span data-ttu-id="a617a-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="a617a-119">Data Item Type</span></span>|<span data-ttu-id="a617a-120">描述</span><span class="sxs-lookup"><span data-stu-id="a617a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a617a-121">扩展数据</span><span class="sxs-lookup"><span data-stu-id="a617a-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="a617a-122">活动的名称。</span><span class="sxs-lookup"><span data-stu-id="a617a-122">The name of the activity.</span></span>|  
|<span data-ttu-id="a617a-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a617a-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a617a-124">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="a617a-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

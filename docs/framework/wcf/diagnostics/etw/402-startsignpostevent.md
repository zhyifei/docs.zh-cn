---
title: 402 - StartSignpostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e5be126-765d-4ac9-88e7-008e9ef4f0e5
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 62587e6aa15ef57d5fee349795dfd60bb52812d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="402---startsignpostevent"></a><span data-ttu-id="526ae-102">402 - StartSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="526ae-102">402 - StartSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="526ae-103">属性</span><span class="sxs-lookup"><span data-stu-id="526ae-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="526ae-104">Id</span><span class="sxs-lookup"><span data-stu-id="526ae-104">ID</span></span>|<span data-ttu-id="526ae-105">402</span><span class="sxs-lookup"><span data-stu-id="526ae-105">402</span></span>|  
|<span data-ttu-id="526ae-106">关键字</span><span class="sxs-lookup"><span data-stu-id="526ae-106">Keywords</span></span>|<span data-ttu-id="526ae-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="526ae-107">Troubleshooting</span></span>|  
|<span data-ttu-id="526ae-108">级别</span><span class="sxs-lookup"><span data-stu-id="526ae-108">Level</span></span>|<span data-ttu-id="526ae-109">信息</span><span class="sxs-lookup"><span data-stu-id="526ae-109">Information</span></span>|  
|<span data-ttu-id="526ae-110">通道</span><span class="sxs-lookup"><span data-stu-id="526ae-110">Channel</span></span>|<span data-ttu-id="526ae-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="526ae-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="526ae-112">描述</span><span class="sxs-lookup"><span data-stu-id="526ae-112">Description</span></span>  
 <span data-ttu-id="526ae-113">此事件标记端对端活动的开始。</span><span class="sxs-lookup"><span data-stu-id="526ae-113">This event marks the beginning of an end-to-end activity.</span></span> <span data-ttu-id="526ae-114">它包含活动的名称。</span><span class="sxs-lookup"><span data-stu-id="526ae-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="526ae-115">消息</span><span class="sxs-lookup"><span data-stu-id="526ae-115">Message</span></span>  
 <span data-ttu-id="526ae-116">活动边界。</span><span class="sxs-lookup"><span data-stu-id="526ae-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="526ae-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="526ae-117">Details</span></span>  
  
|<span data-ttu-id="526ae-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="526ae-118">Data Item Name</span></span>|<span data-ttu-id="526ae-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="526ae-119">Data Item Type</span></span>|<span data-ttu-id="526ae-120">描述</span><span class="sxs-lookup"><span data-stu-id="526ae-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="526ae-121">扩展数据</span><span class="sxs-lookup"><span data-stu-id="526ae-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="526ae-122">活动的名称。</span><span class="sxs-lookup"><span data-stu-id="526ae-122">The name of the activity.</span></span>|  
|<span data-ttu-id="526ae-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="526ae-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="526ae-124">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="526ae-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

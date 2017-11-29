---
title: 404 - ResumeSignpostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 395cc7ca-f35f-4295-be97-39a077f99c97
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 45267f8eae7e9b7bc56540bf6c7d1842ad68889d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="404---resumesignpostevent"></a><span data-ttu-id="49ded-102">404 - ResumeSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="49ded-102">404 - ResumeSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="49ded-103">属性</span><span class="sxs-lookup"><span data-stu-id="49ded-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49ded-104">ID</span><span class="sxs-lookup"><span data-stu-id="49ded-104">ID</span></span>|<span data-ttu-id="49ded-105">404</span><span class="sxs-lookup"><span data-stu-id="49ded-105">404</span></span>|  
|<span data-ttu-id="49ded-106">关键字</span><span class="sxs-lookup"><span data-stu-id="49ded-106">Keywords</span></span>|<span data-ttu-id="49ded-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="49ded-107">Troubleshooting</span></span>|  
|<span data-ttu-id="49ded-108">级别</span><span class="sxs-lookup"><span data-stu-id="49ded-108">Level</span></span>|<span data-ttu-id="49ded-109">信息</span><span class="sxs-lookup"><span data-stu-id="49ded-109">Information</span></span>|  
|<span data-ttu-id="49ded-110">通道</span><span class="sxs-lookup"><span data-stu-id="49ded-110">Channel</span></span>|<span data-ttu-id="49ded-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="49ded-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="49ded-112">描述</span><span class="sxs-lookup"><span data-stu-id="49ded-112">Description</span></span>  
 <span data-ttu-id="49ded-113">此事件标记端对端活动的恢复，</span><span class="sxs-lookup"><span data-stu-id="49ded-113">This event marks the resumption of an end-to-end activity.</span></span> <span data-ttu-id="49ded-114">它包含活动的名称。</span><span class="sxs-lookup"><span data-stu-id="49ded-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="49ded-115">消息</span><span class="sxs-lookup"><span data-stu-id="49ded-115">Message</span></span>  
 <span data-ttu-id="49ded-116">活动边界。</span><span class="sxs-lookup"><span data-stu-id="49ded-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="49ded-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="49ded-117">Details</span></span>  
  
|<span data-ttu-id="49ded-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="49ded-118">Data Item Name</span></span>|<span data-ttu-id="49ded-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="49ded-119">Data Item Type</span></span>|<span data-ttu-id="49ded-120">描述</span><span class="sxs-lookup"><span data-stu-id="49ded-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="49ded-121">扩展数据</span><span class="sxs-lookup"><span data-stu-id="49ded-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="49ded-122">活动的名称。</span><span class="sxs-lookup"><span data-stu-id="49ded-122">The name of the activity.</span></span>|  
|<span data-ttu-id="49ded-123">应用程序域</span><span class="sxs-lookup"><span data-stu-id="49ded-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="49ded-124">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="49ded-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

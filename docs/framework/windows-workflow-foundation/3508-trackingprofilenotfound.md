---
title: 3508 - TrackingProfileNotFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fb5636057193fcfb59e5062f6f3833a62b4f3027
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="8b2cb-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="8b2cb-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="8b2cb-103">属性</span><span class="sxs-lookup"><span data-stu-id="8b2cb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8b2cb-104">ID</span><span class="sxs-lookup"><span data-stu-id="8b2cb-104">ID</span></span>|<span data-ttu-id="8b2cb-105">3508</span><span class="sxs-lookup"><span data-stu-id="8b2cb-105">3508</span></span>|  
|<span data-ttu-id="8b2cb-106">关键字</span><span class="sxs-lookup"><span data-stu-id="8b2cb-106">Keywords</span></span>|<span data-ttu-id="8b2cb-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="8b2cb-107">WFServices</span></span>|  
|<span data-ttu-id="8b2cb-108">级别</span><span class="sxs-lookup"><span data-stu-id="8b2cb-108">Level</span></span>|<span data-ttu-id="8b2cb-109">详细</span><span class="sxs-lookup"><span data-stu-id="8b2cb-109">Verbose</span></span>|  
|<span data-ttu-id="8b2cb-110">通道</span><span class="sxs-lookup"><span data-stu-id="8b2cb-110">Channel</span></span>|<span data-ttu-id="8b2cb-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="8b2cb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8b2cb-112">描述</span><span class="sxs-lookup"><span data-stu-id="8b2cb-112">Description</span></span>  
 <span data-ttu-id="8b2cb-113">指示在配置文件中找不到 TrackingProfile，或 ActivityDefinitionId 与配置文件不匹配。</span><span class="sxs-lookup"><span data-stu-id="8b2cb-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8b2cb-114">消息</span><span class="sxs-lookup"><span data-stu-id="8b2cb-114">Message</span></span>  
 <span data-ttu-id="8b2cb-115">未找到 ActivityDefinitionId“%2”的 TrackingProfile“%1”。</span><span class="sxs-lookup"><span data-stu-id="8b2cb-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="8b2cb-116">在配置文件中找不到 TrackingProfile，或 ActivityDefinitionId 不匹配。</span><span class="sxs-lookup"><span data-stu-id="8b2cb-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8b2cb-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="8b2cb-117">Details</span></span>  
  
|<span data-ttu-id="8b2cb-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="8b2cb-118">Data Item Name</span></span>|<span data-ttu-id="8b2cb-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="8b2cb-119">Data Item Type</span></span>|<span data-ttu-id="8b2cb-120">描述</span><span class="sxs-lookup"><span data-stu-id="8b2cb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8b2cb-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="8b2cb-121">TrackingProfile</span></span>|<span data-ttu-id="8b2cb-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b2cb-122">xs:string</span></span>|<span data-ttu-id="8b2cb-123">跟踪配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8b2cb-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="8b2cb-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="8b2cb-124">ActivityDefinitionId</span></span>|<span data-ttu-id="8b2cb-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b2cb-125">xs:string</span></span>|<span data-ttu-id="8b2cb-126">活动定义 ID。</span><span class="sxs-lookup"><span data-stu-id="8b2cb-126">The activity definition id.</span></span>|  
|<span data-ttu-id="8b2cb-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8b2cb-127">AppDomain</span></span>|<span data-ttu-id="8b2cb-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="8b2cb-128">xs:string</span></span>|<span data-ttu-id="8b2cb-129">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="8b2cb-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

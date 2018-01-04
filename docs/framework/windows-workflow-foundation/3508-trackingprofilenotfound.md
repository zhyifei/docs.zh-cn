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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34812b6ddefb69c053cfefa91d7227a7bf15f42e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="ae31c-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="ae31c-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="ae31c-103">属性</span><span class="sxs-lookup"><span data-stu-id="ae31c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ae31c-104">ID</span><span class="sxs-lookup"><span data-stu-id="ae31c-104">ID</span></span>|<span data-ttu-id="ae31c-105">3508</span><span class="sxs-lookup"><span data-stu-id="ae31c-105">3508</span></span>|  
|<span data-ttu-id="ae31c-106">关键字</span><span class="sxs-lookup"><span data-stu-id="ae31c-106">Keywords</span></span>|<span data-ttu-id="ae31c-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="ae31c-107">WFServices</span></span>|  
|<span data-ttu-id="ae31c-108">级别</span><span class="sxs-lookup"><span data-stu-id="ae31c-108">Level</span></span>|<span data-ttu-id="ae31c-109">详细</span><span class="sxs-lookup"><span data-stu-id="ae31c-109">Verbose</span></span>|  
|<span data-ttu-id="ae31c-110">通道</span><span class="sxs-lookup"><span data-stu-id="ae31c-110">Channel</span></span>|<span data-ttu-id="ae31c-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="ae31c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ae31c-112">描述</span><span class="sxs-lookup"><span data-stu-id="ae31c-112">Description</span></span>  
 <span data-ttu-id="ae31c-113">指示在配置文件中找不到 TrackingProfile，或 ActivityDefinitionId 与配置文件不匹配。</span><span class="sxs-lookup"><span data-stu-id="ae31c-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ae31c-114">消息</span><span class="sxs-lookup"><span data-stu-id="ae31c-114">Message</span></span>  
 <span data-ttu-id="ae31c-115">未找到 ActivityDefinitionId“%2”的 TrackingProfile“%1”。</span><span class="sxs-lookup"><span data-stu-id="ae31c-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="ae31c-116">在配置文件中找不到 TrackingProfile，或 ActivityDefinitionId 不匹配。</span><span class="sxs-lookup"><span data-stu-id="ae31c-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ae31c-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="ae31c-117">Details</span></span>  
  
|<span data-ttu-id="ae31c-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="ae31c-118">Data Item Name</span></span>|<span data-ttu-id="ae31c-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="ae31c-119">Data Item Type</span></span>|<span data-ttu-id="ae31c-120">描述</span><span class="sxs-lookup"><span data-stu-id="ae31c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ae31c-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="ae31c-121">TrackingProfile</span></span>|<span data-ttu-id="ae31c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="ae31c-122">xs:string</span></span>|<span data-ttu-id="ae31c-123">跟踪配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ae31c-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="ae31c-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="ae31c-124">ActivityDefinitionId</span></span>|<span data-ttu-id="ae31c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="ae31c-125">xs:string</span></span>|<span data-ttu-id="ae31c-126">活动定义 ID。</span><span class="sxs-lookup"><span data-stu-id="ae31c-126">The activity definition id.</span></span>|  
|<span data-ttu-id="ae31c-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ae31c-127">AppDomain</span></span>|<span data-ttu-id="ae31c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="ae31c-128">xs:string</span></span>|<span data-ttu-id="ae31c-129">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="ae31c-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

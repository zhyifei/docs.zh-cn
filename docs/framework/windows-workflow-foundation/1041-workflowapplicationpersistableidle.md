---
title: 1041 - WorkflowApplicationPersistableIdle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b321f8c20fbd79b5e748601ee06f975dc75a7d56
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="deb62-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="deb62-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="deb62-103">属性</span><span class="sxs-lookup"><span data-stu-id="deb62-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="deb62-104">ID</span><span class="sxs-lookup"><span data-stu-id="deb62-104">ID</span></span>|<span data-ttu-id="deb62-105">1041</span><span class="sxs-lookup"><span data-stu-id="deb62-105">1041</span></span>|  
|<span data-ttu-id="deb62-106">关键字</span><span class="sxs-lookup"><span data-stu-id="deb62-106">Keywords</span></span>|<span data-ttu-id="deb62-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="deb62-107">WFRuntime</span></span>|  
|<span data-ttu-id="deb62-108">级别</span><span class="sxs-lookup"><span data-stu-id="deb62-108">Level</span></span>|<span data-ttu-id="deb62-109">信息</span><span class="sxs-lookup"><span data-stu-id="deb62-109">Information</span></span>|  
|<span data-ttu-id="deb62-110">通道</span><span class="sxs-lookup"><span data-stu-id="deb62-110">Channel</span></span>|<span data-ttu-id="deb62-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="deb62-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="deb62-112">描述</span><span class="sxs-lookup"><span data-stu-id="deb62-112">Description</span></span>  
 <span data-ttu-id="deb62-113">指示工作流应用程序空闲且可持久化。</span><span class="sxs-lookup"><span data-stu-id="deb62-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="deb62-114">工作流应用程序将是空闲且可持久化的。</span><span class="sxs-lookup"><span data-stu-id="deb62-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="deb62-115">消息</span><span class="sxs-lookup"><span data-stu-id="deb62-115">Message</span></span>  
 <span data-ttu-id="deb62-116">WorkflowApplication Id ' %1' 是空闲且可持久化。</span><span class="sxs-lookup"><span data-stu-id="deb62-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="deb62-117">不会执行以下操作: %2。</span><span class="sxs-lookup"><span data-stu-id="deb62-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="deb62-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="deb62-118">Details</span></span>  
  
|<span data-ttu-id="deb62-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="deb62-119">Data Item Name</span></span>|<span data-ttu-id="deb62-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="deb62-120">Data Item Type</span></span>|<span data-ttu-id="deb62-121">描述</span><span class="sxs-lookup"><span data-stu-id="deb62-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="deb62-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="deb62-122">WorkflowApplicationId</span></span>|<span data-ttu-id="deb62-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="deb62-123">xs:string</span></span>|<span data-ttu-id="deb62-124">工作流应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="deb62-124">The workflow application id</span></span>|  
|<span data-ttu-id="deb62-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="deb62-125">ActionTaken</span></span>|<span data-ttu-id="deb62-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="deb62-126">xs:string</span></span>|<span data-ttu-id="deb62-127">将对工作流应用程序执行的操作。</span><span class="sxs-lookup"><span data-stu-id="deb62-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="deb62-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="deb62-128">AppDomain</span></span>|<span data-ttu-id="deb62-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="deb62-129">xs:string</span></span>|<span data-ttu-id="deb62-130">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="deb62-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

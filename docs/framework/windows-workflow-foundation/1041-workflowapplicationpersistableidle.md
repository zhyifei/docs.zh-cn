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
ms.workload: dotnet
ms.openlocfilehash: 1efc32ed0304d5b0d222054e5c65abe279ef93ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="8cff7-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="8cff7-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="8cff7-103">属性</span><span class="sxs-lookup"><span data-stu-id="8cff7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8cff7-104">ID</span><span class="sxs-lookup"><span data-stu-id="8cff7-104">ID</span></span>|<span data-ttu-id="8cff7-105">1041</span><span class="sxs-lookup"><span data-stu-id="8cff7-105">1041</span></span>|  
|<span data-ttu-id="8cff7-106">关键字</span><span class="sxs-lookup"><span data-stu-id="8cff7-106">Keywords</span></span>|<span data-ttu-id="8cff7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8cff7-107">WFRuntime</span></span>|  
|<span data-ttu-id="8cff7-108">级别</span><span class="sxs-lookup"><span data-stu-id="8cff7-108">Level</span></span>|<span data-ttu-id="8cff7-109">信息</span><span class="sxs-lookup"><span data-stu-id="8cff7-109">Information</span></span>|  
|<span data-ttu-id="8cff7-110">通道</span><span class="sxs-lookup"><span data-stu-id="8cff7-110">Channel</span></span>|<span data-ttu-id="8cff7-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="8cff7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8cff7-112">描述</span><span class="sxs-lookup"><span data-stu-id="8cff7-112">Description</span></span>  
 <span data-ttu-id="8cff7-113">指示工作流应用程序空闲且可持久化。</span><span class="sxs-lookup"><span data-stu-id="8cff7-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="8cff7-114">工作流应用程序将是空闲且可持久化的。</span><span class="sxs-lookup"><span data-stu-id="8cff7-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8cff7-115">消息</span><span class="sxs-lookup"><span data-stu-id="8cff7-115">Message</span></span>  
 <span data-ttu-id="8cff7-116">WorkflowApplication Id ' %1' 是空闲且可持久化。</span><span class="sxs-lookup"><span data-stu-id="8cff7-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="8cff7-117">不会执行以下操作: %2。</span><span class="sxs-lookup"><span data-stu-id="8cff7-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8cff7-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="8cff7-118">Details</span></span>  
  
|<span data-ttu-id="8cff7-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="8cff7-119">Data Item Name</span></span>|<span data-ttu-id="8cff7-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="8cff7-120">Data Item Type</span></span>|<span data-ttu-id="8cff7-121">描述</span><span class="sxs-lookup"><span data-stu-id="8cff7-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8cff7-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="8cff7-122">WorkflowApplicationId</span></span>|<span data-ttu-id="8cff7-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cff7-123">xs:string</span></span>|<span data-ttu-id="8cff7-124">工作流应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="8cff7-124">The workflow application id</span></span>|  
|<span data-ttu-id="8cff7-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="8cff7-125">ActionTaken</span></span>|<span data-ttu-id="8cff7-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cff7-126">xs:string</span></span>|<span data-ttu-id="8cff7-127">将对工作流应用程序执行的操作。</span><span class="sxs-lookup"><span data-stu-id="8cff7-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="8cff7-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8cff7-128">AppDomain</span></span>|<span data-ttu-id="8cff7-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cff7-129">xs:string</span></span>|<span data-ttu-id="8cff7-130">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="8cff7-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

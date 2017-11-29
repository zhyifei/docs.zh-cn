---
title: 1103 - WorkflowActivitySuspend
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b64e15c2-cb2c-4314-9074-ce2c6717232e
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a55cd953b294ca5e8a90f6ade666c55b51dc1e58
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1103---workflowactivitysuspend"></a><span data-ttu-id="6fb37-102">1103 - WorkflowActivitySuspend</span><span class="sxs-lookup"><span data-stu-id="6fb37-102">1103 - WorkflowActivitySuspend</span></span>
## <a name="properties"></a><span data-ttu-id="6fb37-103">属性</span><span class="sxs-lookup"><span data-stu-id="6fb37-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6fb37-104">ID</span><span class="sxs-lookup"><span data-stu-id="6fb37-104">ID</span></span>|<span data-ttu-id="6fb37-105">1103</span><span class="sxs-lookup"><span data-stu-id="6fb37-105">1103</span></span>|  
|<span data-ttu-id="6fb37-106">关键字</span><span class="sxs-lookup"><span data-stu-id="6fb37-106">Keywords</span></span>|<span data-ttu-id="6fb37-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6fb37-107">WFRuntime</span></span>|  
|<span data-ttu-id="6fb37-108">级别</span><span class="sxs-lookup"><span data-stu-id="6fb37-108">Level</span></span>|<span data-ttu-id="6fb37-109">信息</span><span class="sxs-lookup"><span data-stu-id="6fb37-109">Information</span></span>|  
|<span data-ttu-id="6fb37-110">通道</span><span class="sxs-lookup"><span data-stu-id="6fb37-110">Channel</span></span>|<span data-ttu-id="6fb37-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="6fb37-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6fb37-112">描述</span><span class="sxs-lookup"><span data-stu-id="6fb37-112">Description</span></span>  
 <span data-ttu-id="6fb37-113">指示工作流活动已挂起。</span><span class="sxs-lookup"><span data-stu-id="6fb37-113">Indicates a workflow activity has been suspended.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6fb37-114">消息</span><span class="sxs-lookup"><span data-stu-id="6fb37-114">Message</span></span>  
 <span data-ttu-id="6fb37-115">WorkflowInstance Id“%1”E2E 活动</span><span class="sxs-lookup"><span data-stu-id="6fb37-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="6fb37-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="6fb37-116">Details</span></span>  
  
|<span data-ttu-id="6fb37-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="6fb37-117">Data Item Name</span></span>|<span data-ttu-id="6fb37-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="6fb37-118">Data Item Type</span></span>|<span data-ttu-id="6fb37-119">描述</span><span class="sxs-lookup"><span data-stu-id="6fb37-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6fb37-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="6fb37-120">WorkflowInstanceId</span></span>|<span data-ttu-id="6fb37-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6fb37-121">xs:string</span></span>|<span data-ttu-id="6fb37-122">工作流实例 ID。</span><span class="sxs-lookup"><span data-stu-id="6fb37-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="6fb37-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6fb37-123">AppDomain</span></span>|<span data-ttu-id="6fb37-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6fb37-124">xs:string</span></span>|<span data-ttu-id="6fb37-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="6fb37-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

---
title: 1101 - WorkflowActivityStart
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 831cd386-b9b5-47a9-9690-aff6292ff348
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8d89b6f41838ee89b503746be4020b93db0ac96e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1101---workflowactivitystart"></a><span data-ttu-id="6b07c-102">1101 - WorkflowActivityStart</span><span class="sxs-lookup"><span data-stu-id="6b07c-102">1101 - WorkflowActivityStart</span></span>
## <a name="properties"></a><span data-ttu-id="6b07c-103">属性</span><span class="sxs-lookup"><span data-stu-id="6b07c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6b07c-104">ID</span><span class="sxs-lookup"><span data-stu-id="6b07c-104">ID</span></span>|<span data-ttu-id="6b07c-105">1101</span><span class="sxs-lookup"><span data-stu-id="6b07c-105">1101</span></span>|  
|<span data-ttu-id="6b07c-106">关键字</span><span class="sxs-lookup"><span data-stu-id="6b07c-106">Keywords</span></span>|<span data-ttu-id="6b07c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="6b07c-107">WFRuntime</span></span>|  
|<span data-ttu-id="6b07c-108">级别</span><span class="sxs-lookup"><span data-stu-id="6b07c-108">Level</span></span>|<span data-ttu-id="6b07c-109">信息</span><span class="sxs-lookup"><span data-stu-id="6b07c-109">Information</span></span>|  
|<span data-ttu-id="6b07c-110">通道</span><span class="sxs-lookup"><span data-stu-id="6b07c-110">Channel</span></span>|<span data-ttu-id="6b07c-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="6b07c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6b07c-112">描述</span><span class="sxs-lookup"><span data-stu-id="6b07c-112">Description</span></span>  
 <span data-ttu-id="6b07c-113">指示工作流活动已开始。</span><span class="sxs-lookup"><span data-stu-id="6b07c-113">Indicates a workflow activity has started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6b07c-114">消息</span><span class="sxs-lookup"><span data-stu-id="6b07c-114">Message</span></span>  
 <span data-ttu-id="6b07c-115">WorkflowInstance Id“%1”E2E 活动</span><span class="sxs-lookup"><span data-stu-id="6b07c-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="6b07c-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="6b07c-116">Details</span></span>  
  
|<span data-ttu-id="6b07c-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="6b07c-117">Data Item Name</span></span>|<span data-ttu-id="6b07c-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="6b07c-118">Data Item Type</span></span>|<span data-ttu-id="6b07c-119">描述</span><span class="sxs-lookup"><span data-stu-id="6b07c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6b07c-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="6b07c-120">WorkflowInstanceId</span></span>|<span data-ttu-id="6b07c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="6b07c-121">xs:string</span></span>|<span data-ttu-id="6b07c-122">工作流实例 ID。</span><span class="sxs-lookup"><span data-stu-id="6b07c-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="6b07c-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6b07c-123">AppDomain</span></span>|<span data-ttu-id="6b07c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="6b07c-124">xs:string</span></span>|<span data-ttu-id="6b07c-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="6b07c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

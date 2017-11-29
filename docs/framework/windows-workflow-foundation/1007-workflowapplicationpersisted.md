---
title: 1007 - WorkflowApplicationPersisted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f4ea4452-28e3-4e66-93c6-eb12ee29bcb1
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f8aa98aec96843fb6ef169c2b168d1984ccdda5d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1007---workflowapplicationpersisted"></a><span data-ttu-id="da1f9-102">1007 - WorkflowApplicationPersisted</span><span class="sxs-lookup"><span data-stu-id="da1f9-102">1007 - WorkflowApplicationPersisted</span></span>
## <a name="properties"></a><span data-ttu-id="da1f9-103">属性</span><span class="sxs-lookup"><span data-stu-id="da1f9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da1f9-104">ID</span><span class="sxs-lookup"><span data-stu-id="da1f9-104">ID</span></span>|<span data-ttu-id="da1f9-105">1007</span><span class="sxs-lookup"><span data-stu-id="da1f9-105">1007</span></span>|  
|<span data-ttu-id="da1f9-106">关键字</span><span class="sxs-lookup"><span data-stu-id="da1f9-106">Keywords</span></span>|<span data-ttu-id="da1f9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="da1f9-107">WFRuntime</span></span>|  
|<span data-ttu-id="da1f9-108">级别</span><span class="sxs-lookup"><span data-stu-id="da1f9-108">Level</span></span>|<span data-ttu-id="da1f9-109">信息</span><span class="sxs-lookup"><span data-stu-id="da1f9-109">Information</span></span>|  
|<span data-ttu-id="da1f9-110">通道</span><span class="sxs-lookup"><span data-stu-id="da1f9-110">Channel</span></span>|<span data-ttu-id="da1f9-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="da1f9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="da1f9-112">描述</span><span class="sxs-lookup"><span data-stu-id="da1f9-112">Description</span></span>  
 <span data-ttu-id="da1f9-113">指示工作流应用程序已持久化。</span><span class="sxs-lookup"><span data-stu-id="da1f9-113">Indicates a workflow application has persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="da1f9-114">消息</span><span class="sxs-lookup"><span data-stu-id="da1f9-114">Message</span></span>  
 <span data-ttu-id="da1f9-115">WorkflowApplication ID“%1”已持久化。</span><span class="sxs-lookup"><span data-stu-id="da1f9-115">WorkflowApplication Id: '%1' was Persisted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="da1f9-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="da1f9-116">Details</span></span>  
  
|<span data-ttu-id="da1f9-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="da1f9-117">Data Item Name</span></span>|<span data-ttu-id="da1f9-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="da1f9-118">Data Item Type</span></span>|<span data-ttu-id="da1f9-119">描述</span><span class="sxs-lookup"><span data-stu-id="da1f9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="da1f9-120">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="da1f9-120">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="da1f9-121">工作流应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="da1f9-121">The workflow application id</span></span>|  
|<span data-ttu-id="da1f9-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="da1f9-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="da1f9-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="da1f9-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

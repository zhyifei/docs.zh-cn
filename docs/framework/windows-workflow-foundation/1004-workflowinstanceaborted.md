---
title: 1004 - WorkflowInstanceAborted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7394ebbcb14850af89d906b0b573c4f677346825
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="948a9-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="948a9-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="948a9-103">属性</span><span class="sxs-lookup"><span data-stu-id="948a9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="948a9-104">ID</span><span class="sxs-lookup"><span data-stu-id="948a9-104">ID</span></span>|<span data-ttu-id="948a9-105">1004</span><span class="sxs-lookup"><span data-stu-id="948a9-105">1004</span></span>|  
|<span data-ttu-id="948a9-106">关键字</span><span class="sxs-lookup"><span data-stu-id="948a9-106">Keywords</span></span>|<span data-ttu-id="948a9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="948a9-107">WFRuntime</span></span>|  
|<span data-ttu-id="948a9-108">级别</span><span class="sxs-lookup"><span data-stu-id="948a9-108">Level</span></span>|<span data-ttu-id="948a9-109">信息</span><span class="sxs-lookup"><span data-stu-id="948a9-109">Information</span></span>|  
|<span data-ttu-id="948a9-110">通道</span><span class="sxs-lookup"><span data-stu-id="948a9-110">Channel</span></span>|<span data-ttu-id="948a9-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="948a9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="948a9-112">描述</span><span class="sxs-lookup"><span data-stu-id="948a9-112">Description</span></span>  
 <span data-ttu-id="948a9-113">指示工作流实例已中止并且具有异常。</span><span class="sxs-lookup"><span data-stu-id="948a9-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="948a9-114">消息</span><span class="sxs-lookup"><span data-stu-id="948a9-114">Message</span></span>  
 <span data-ttu-id="948a9-115">WorkflowInstance Id“%1”因出现异常而中止。</span><span class="sxs-lookup"><span data-stu-id="948a9-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="948a9-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="948a9-116">Details</span></span>  
  
|<span data-ttu-id="948a9-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="948a9-117">Data Item Name</span></span>|<span data-ttu-id="948a9-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="948a9-118">Data Item Type</span></span>|<span data-ttu-id="948a9-119">描述</span><span class="sxs-lookup"><span data-stu-id="948a9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="948a9-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="948a9-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="948a9-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="948a9-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="948a9-122">例外</span><span class="sxs-lookup"><span data-stu-id="948a9-122">Exception</span></span>|`xs:string`|<span data-ttu-id="948a9-123">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="948a9-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="948a9-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="948a9-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="948a9-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="948a9-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

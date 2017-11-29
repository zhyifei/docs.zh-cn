---
title: 1006 - WorkflowApplicationUnhandledException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a03809be5e5d61c505e295e2f769a0298f770f7f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="2b701-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="2b701-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="2b701-103">属性</span><span class="sxs-lookup"><span data-stu-id="2b701-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b701-104">ID</span><span class="sxs-lookup"><span data-stu-id="2b701-104">ID</span></span>|<span data-ttu-id="2b701-105">1006</span><span class="sxs-lookup"><span data-stu-id="2b701-105">1006</span></span>|  
|<span data-ttu-id="2b701-106">关键字</span><span class="sxs-lookup"><span data-stu-id="2b701-106">Keywords</span></span>|<span data-ttu-id="2b701-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2b701-107">WFRuntime</span></span>|  
|<span data-ttu-id="2b701-108">级别</span><span class="sxs-lookup"><span data-stu-id="2b701-108">Level</span></span>|<span data-ttu-id="2b701-109">错误</span><span class="sxs-lookup"><span data-stu-id="2b701-109">Error</span></span>|  
|<span data-ttu-id="2b701-110">通道</span><span class="sxs-lookup"><span data-stu-id="2b701-110">Channel</span></span>|<span data-ttu-id="2b701-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="2b701-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2b701-112">描述</span><span class="sxs-lookup"><span data-stu-id="2b701-112">Description</span></span>  
 <span data-ttu-id="2b701-113">指示工作流应用程序遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="2b701-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2b701-114">消息</span><span class="sxs-lookup"><span data-stu-id="2b701-114">Message</span></span>  
 <span data-ttu-id="2b701-115">WorkflowInstance Id"%1"遇到未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="2b701-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="2b701-116">则将产生异常从 Activity"%2"、 DisplayName:"%3"。</span><span class="sxs-lookup"><span data-stu-id="2b701-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="2b701-117">不会执行以下操作: %4。</span><span class="sxs-lookup"><span data-stu-id="2b701-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2b701-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="2b701-118">Details</span></span>  
  
|<span data-ttu-id="2b701-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="2b701-119">Data Item Name</span></span>|<span data-ttu-id="2b701-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="2b701-120">Data Item Type</span></span>|<span data-ttu-id="2b701-121">描述</span><span class="sxs-lookup"><span data-stu-id="2b701-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2b701-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="2b701-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="2b701-123">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="2b701-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="2b701-124">例外</span><span class="sxs-lookup"><span data-stu-id="2b701-124">Exception</span></span>|`xs:string`|<span data-ttu-id="2b701-125">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="2b701-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="2b701-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2b701-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2b701-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="2b701-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

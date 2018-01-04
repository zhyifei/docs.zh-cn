---
title: 1005 - WorkflowApplicationIdled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dc9f8f72000fe283baa5bb2814e41051c1424983
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="e85ae-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="e85ae-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="e85ae-103">属性</span><span class="sxs-lookup"><span data-stu-id="e85ae-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e85ae-104">ID</span><span class="sxs-lookup"><span data-stu-id="e85ae-104">ID</span></span>|<span data-ttu-id="e85ae-105">1005</span><span class="sxs-lookup"><span data-stu-id="e85ae-105">1005</span></span>|  
|<span data-ttu-id="e85ae-106">关键字</span><span class="sxs-lookup"><span data-stu-id="e85ae-106">Keywords</span></span>|<span data-ttu-id="e85ae-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e85ae-107">WFRuntime</span></span>|  
|<span data-ttu-id="e85ae-108">级别</span><span class="sxs-lookup"><span data-stu-id="e85ae-108">Level</span></span>|<span data-ttu-id="e85ae-109">信息</span><span class="sxs-lookup"><span data-stu-id="e85ae-109">Information</span></span>|  
|<span data-ttu-id="e85ae-110">通道</span><span class="sxs-lookup"><span data-stu-id="e85ae-110">Channel</span></span>|<span data-ttu-id="e85ae-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="e85ae-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e85ae-112">描述</span><span class="sxs-lookup"><span data-stu-id="e85ae-112">Description</span></span>  
 <span data-ttu-id="e85ae-113">指示工作流应用程序已处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="e85ae-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e85ae-114">消息</span><span class="sxs-lookup"><span data-stu-id="e85ae-114">Message</span></span>  
 <span data-ttu-id="e85ae-115">WorkflowApplication ID“%1”变为空闲状态。</span><span class="sxs-lookup"><span data-stu-id="e85ae-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e85ae-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="e85ae-116">Details</span></span>  
  
|<span data-ttu-id="e85ae-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="e85ae-117">Data Item Name</span></span>|<span data-ttu-id="e85ae-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="e85ae-118">Data Item Type</span></span>|<span data-ttu-id="e85ae-119">描述</span><span class="sxs-lookup"><span data-stu-id="e85ae-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e85ae-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="e85ae-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="e85ae-121">工作流应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="e85ae-121">The workflow application id</span></span>|  
|<span data-ttu-id="e85ae-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e85ae-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e85ae-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="e85ae-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

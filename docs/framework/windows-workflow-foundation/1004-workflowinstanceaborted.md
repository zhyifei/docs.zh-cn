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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc940e1781f821f12efb42c5198e77eb0451a164
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="1aec4-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="1aec4-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="1aec4-103">属性</span><span class="sxs-lookup"><span data-stu-id="1aec4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1aec4-104">ID</span><span class="sxs-lookup"><span data-stu-id="1aec4-104">ID</span></span>|<span data-ttu-id="1aec4-105">1004</span><span class="sxs-lookup"><span data-stu-id="1aec4-105">1004</span></span>|  
|<span data-ttu-id="1aec4-106">关键字</span><span class="sxs-lookup"><span data-stu-id="1aec4-106">Keywords</span></span>|<span data-ttu-id="1aec4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1aec4-107">WFRuntime</span></span>|  
|<span data-ttu-id="1aec4-108">级别</span><span class="sxs-lookup"><span data-stu-id="1aec4-108">Level</span></span>|<span data-ttu-id="1aec4-109">信息</span><span class="sxs-lookup"><span data-stu-id="1aec4-109">Information</span></span>|  
|<span data-ttu-id="1aec4-110">通道</span><span class="sxs-lookup"><span data-stu-id="1aec4-110">Channel</span></span>|<span data-ttu-id="1aec4-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="1aec4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1aec4-112">描述</span><span class="sxs-lookup"><span data-stu-id="1aec4-112">Description</span></span>  
 <span data-ttu-id="1aec4-113">指示工作流实例已中止并且具有异常。</span><span class="sxs-lookup"><span data-stu-id="1aec4-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1aec4-114">消息</span><span class="sxs-lookup"><span data-stu-id="1aec4-114">Message</span></span>  
 <span data-ttu-id="1aec4-115">WorkflowInstance Id“%1”因出现异常而中止。</span><span class="sxs-lookup"><span data-stu-id="1aec4-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1aec4-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="1aec4-116">Details</span></span>  
  
|<span data-ttu-id="1aec4-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="1aec4-117">Data Item Name</span></span>|<span data-ttu-id="1aec4-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="1aec4-118">Data Item Type</span></span>|<span data-ttu-id="1aec4-119">描述</span><span class="sxs-lookup"><span data-stu-id="1aec4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1aec4-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="1aec4-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="1aec4-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="1aec4-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="1aec4-122">例外</span><span class="sxs-lookup"><span data-stu-id="1aec4-122">Exception</span></span>|`xs:string`|<span data-ttu-id="1aec4-123">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="1aec4-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="1aec4-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1aec4-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1aec4-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="1aec4-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

---
title: 1001 - WorkflowApplicationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ded4558b937a23fbe90d2bca55e6d5e4be0f0290
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="0dcaf-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="0dcaf-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="0dcaf-103">属性</span><span class="sxs-lookup"><span data-stu-id="0dcaf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0dcaf-104">ID</span><span class="sxs-lookup"><span data-stu-id="0dcaf-104">ID</span></span>|<span data-ttu-id="0dcaf-105">1001</span><span class="sxs-lookup"><span data-stu-id="0dcaf-105">1001</span></span>|  
|<span data-ttu-id="0dcaf-106">关键字</span><span class="sxs-lookup"><span data-stu-id="0dcaf-106">Keywords</span></span>|<span data-ttu-id="0dcaf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0dcaf-107">WFRuntime</span></span>|  
|<span data-ttu-id="0dcaf-108">级别</span><span class="sxs-lookup"><span data-stu-id="0dcaf-108">Level</span></span>|<span data-ttu-id="0dcaf-109">信息</span><span class="sxs-lookup"><span data-stu-id="0dcaf-109">Information</span></span>|  
|<span data-ttu-id="0dcaf-110">通道</span><span class="sxs-lookup"><span data-stu-id="0dcaf-110">Channel</span></span>|<span data-ttu-id="0dcaf-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="0dcaf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0dcaf-112">描述</span><span class="sxs-lookup"><span data-stu-id="0dcaf-112">Description</span></span>  
 <span data-ttu-id="0dcaf-113">指示工作流应用程序在“已关闭”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="0dcaf-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0dcaf-114">消息</span><span class="sxs-lookup"><span data-stu-id="0dcaf-114">Message</span></span>  
 <span data-ttu-id="0dcaf-115">WorkflowInstance Id“%1”在“已关闭”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="0dcaf-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0dcaf-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="0dcaf-116">Details</span></span>  
  
|<span data-ttu-id="0dcaf-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="0dcaf-117">Data Item Name</span></span>|<span data-ttu-id="0dcaf-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="0dcaf-118">Data Item Type</span></span>|<span data-ttu-id="0dcaf-119">描述</span><span class="sxs-lookup"><span data-stu-id="0dcaf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0dcaf-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="0dcaf-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="0dcaf-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="0dcaf-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="0dcaf-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0dcaf-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0dcaf-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="0dcaf-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

---
title: 1003 - WorkflowInstanceCanceled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6930aeed8c3cd224d5d37dcecf357195e78390ed
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="8ffeb-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="8ffeb-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="8ffeb-103">属性</span><span class="sxs-lookup"><span data-stu-id="8ffeb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8ffeb-104">ID</span><span class="sxs-lookup"><span data-stu-id="8ffeb-104">ID</span></span>|<span data-ttu-id="8ffeb-105">1003</span><span class="sxs-lookup"><span data-stu-id="8ffeb-105">1003</span></span>|  
|<span data-ttu-id="8ffeb-106">关键字</span><span class="sxs-lookup"><span data-stu-id="8ffeb-106">Keywords</span></span>|<span data-ttu-id="8ffeb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8ffeb-107">WFRuntime</span></span>|  
|<span data-ttu-id="8ffeb-108">级别</span><span class="sxs-lookup"><span data-stu-id="8ffeb-108">Level</span></span>|<span data-ttu-id="8ffeb-109">信息</span><span class="sxs-lookup"><span data-stu-id="8ffeb-109">Information</span></span>|  
|<span data-ttu-id="8ffeb-110">通道</span><span class="sxs-lookup"><span data-stu-id="8ffeb-110">Channel</span></span>|<span data-ttu-id="8ffeb-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="8ffeb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8ffeb-112">描述</span><span class="sxs-lookup"><span data-stu-id="8ffeb-112">Description</span></span>  
 <span data-ttu-id="8ffeb-113">指示工作流实例在“已取消”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="8ffeb-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8ffeb-114">消息</span><span class="sxs-lookup"><span data-stu-id="8ffeb-114">Message</span></span>  
 <span data-ttu-id="8ffeb-115">WorkflowInstance Id“%1”在“已取消”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="8ffeb-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8ffeb-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="8ffeb-116">Details</span></span>  
  
|<span data-ttu-id="8ffeb-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="8ffeb-117">Data Item Name</span></span>|<span data-ttu-id="8ffeb-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="8ffeb-118">Data Item Type</span></span>|<span data-ttu-id="8ffeb-119">描述</span><span class="sxs-lookup"><span data-stu-id="8ffeb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8ffeb-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="8ffeb-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="8ffeb-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="8ffeb-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="8ffeb-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8ffeb-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8ffeb-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="8ffeb-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

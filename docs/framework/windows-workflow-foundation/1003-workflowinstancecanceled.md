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
ms.workload: dotnet
ms.openlocfilehash: b264450703090edfcf99f9584c16d33eb82a76e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="3aa93-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="3aa93-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="3aa93-103">属性</span><span class="sxs-lookup"><span data-stu-id="3aa93-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3aa93-104">ID</span><span class="sxs-lookup"><span data-stu-id="3aa93-104">ID</span></span>|<span data-ttu-id="3aa93-105">1003</span><span class="sxs-lookup"><span data-stu-id="3aa93-105">1003</span></span>|  
|<span data-ttu-id="3aa93-106">关键字</span><span class="sxs-lookup"><span data-stu-id="3aa93-106">Keywords</span></span>|<span data-ttu-id="3aa93-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3aa93-107">WFRuntime</span></span>|  
|<span data-ttu-id="3aa93-108">级别</span><span class="sxs-lookup"><span data-stu-id="3aa93-108">Level</span></span>|<span data-ttu-id="3aa93-109">信息</span><span class="sxs-lookup"><span data-stu-id="3aa93-109">Information</span></span>|  
|<span data-ttu-id="3aa93-110">通道</span><span class="sxs-lookup"><span data-stu-id="3aa93-110">Channel</span></span>|<span data-ttu-id="3aa93-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="3aa93-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3aa93-112">描述</span><span class="sxs-lookup"><span data-stu-id="3aa93-112">Description</span></span>  
 <span data-ttu-id="3aa93-113">指示工作流实例在“已取消”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="3aa93-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3aa93-114">消息</span><span class="sxs-lookup"><span data-stu-id="3aa93-114">Message</span></span>  
 <span data-ttu-id="3aa93-115">WorkflowInstance Id“%1”在“已取消”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="3aa93-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3aa93-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="3aa93-116">Details</span></span>  
  
|<span data-ttu-id="3aa93-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="3aa93-117">Data Item Name</span></span>|<span data-ttu-id="3aa93-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="3aa93-118">Data Item Type</span></span>|<span data-ttu-id="3aa93-119">描述</span><span class="sxs-lookup"><span data-stu-id="3aa93-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3aa93-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="3aa93-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="3aa93-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="3aa93-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="3aa93-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3aa93-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3aa93-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="3aa93-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

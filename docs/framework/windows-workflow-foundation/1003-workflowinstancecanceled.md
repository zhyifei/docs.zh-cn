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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b287c99453724f855a51e9a1b8068337dd5e373
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="19f62-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="19f62-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="19f62-103">属性</span><span class="sxs-lookup"><span data-stu-id="19f62-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="19f62-104">ID</span><span class="sxs-lookup"><span data-stu-id="19f62-104">ID</span></span>|<span data-ttu-id="19f62-105">1003</span><span class="sxs-lookup"><span data-stu-id="19f62-105">1003</span></span>|  
|<span data-ttu-id="19f62-106">关键字</span><span class="sxs-lookup"><span data-stu-id="19f62-106">Keywords</span></span>|<span data-ttu-id="19f62-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="19f62-107">WFRuntime</span></span>|  
|<span data-ttu-id="19f62-108">级别</span><span class="sxs-lookup"><span data-stu-id="19f62-108">Level</span></span>|<span data-ttu-id="19f62-109">信息</span><span class="sxs-lookup"><span data-stu-id="19f62-109">Information</span></span>|  
|<span data-ttu-id="19f62-110">通道</span><span class="sxs-lookup"><span data-stu-id="19f62-110">Channel</span></span>|<span data-ttu-id="19f62-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="19f62-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="19f62-112">描述</span><span class="sxs-lookup"><span data-stu-id="19f62-112">Description</span></span>  
 <span data-ttu-id="19f62-113">指示工作流实例在“已取消”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="19f62-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="19f62-114">消息</span><span class="sxs-lookup"><span data-stu-id="19f62-114">Message</span></span>  
 <span data-ttu-id="19f62-115">WorkflowInstance Id“%1”在“已取消”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="19f62-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="19f62-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="19f62-116">Details</span></span>  
  
|<span data-ttu-id="19f62-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="19f62-117">Data Item Name</span></span>|<span data-ttu-id="19f62-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="19f62-118">Data Item Type</span></span>|<span data-ttu-id="19f62-119">描述</span><span class="sxs-lookup"><span data-stu-id="19f62-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="19f62-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="19f62-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="19f62-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="19f62-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="19f62-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="19f62-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="19f62-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="19f62-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

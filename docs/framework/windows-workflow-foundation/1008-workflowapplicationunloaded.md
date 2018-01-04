---
title: 1008 - WorkflowApplicationUnloaded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26491c1e2b20f4285aaedbcd12947cad3562f041
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="562ab-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="562ab-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="562ab-103">属性</span><span class="sxs-lookup"><span data-stu-id="562ab-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="562ab-104">ID</span><span class="sxs-lookup"><span data-stu-id="562ab-104">ID</span></span>|<span data-ttu-id="562ab-105">1008</span><span class="sxs-lookup"><span data-stu-id="562ab-105">1008</span></span>|  
|<span data-ttu-id="562ab-106">关键字</span><span class="sxs-lookup"><span data-stu-id="562ab-106">Keywords</span></span>|<span data-ttu-id="562ab-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="562ab-107">WFRuntime</span></span>|  
|<span data-ttu-id="562ab-108">级别</span><span class="sxs-lookup"><span data-stu-id="562ab-108">Level</span></span>|<span data-ttu-id="562ab-109">信息</span><span class="sxs-lookup"><span data-stu-id="562ab-109">Information</span></span>|  
|<span data-ttu-id="562ab-110">通道</span><span class="sxs-lookup"><span data-stu-id="562ab-110">Channel</span></span>|<span data-ttu-id="562ab-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="562ab-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="562ab-112">描述</span><span class="sxs-lookup"><span data-stu-id="562ab-112">Description</span></span>  
 <span data-ttu-id="562ab-113">指示工作流应用程序已卸载。</span><span class="sxs-lookup"><span data-stu-id="562ab-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="562ab-114">消息</span><span class="sxs-lookup"><span data-stu-id="562ab-114">Message</span></span>  
 <span data-ttu-id="562ab-115">WorkflowInstance Id“%1”已卸载。</span><span class="sxs-lookup"><span data-stu-id="562ab-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="562ab-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="562ab-116">Details</span></span>  
  
|<span data-ttu-id="562ab-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="562ab-117">Data Item Name</span></span>|<span data-ttu-id="562ab-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="562ab-118">Data Item Type</span></span>|<span data-ttu-id="562ab-119">描述</span><span class="sxs-lookup"><span data-stu-id="562ab-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="562ab-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="562ab-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="562ab-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="562ab-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="562ab-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="562ab-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="562ab-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="562ab-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

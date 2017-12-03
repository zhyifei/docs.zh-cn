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
ms.openlocfilehash: dedb1dd389e2308ea8f70d71f057d17a45172517
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="4a590-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="4a590-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="4a590-103">属性</span><span class="sxs-lookup"><span data-stu-id="4a590-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4a590-104">ID</span><span class="sxs-lookup"><span data-stu-id="4a590-104">ID</span></span>|<span data-ttu-id="4a590-105">1008</span><span class="sxs-lookup"><span data-stu-id="4a590-105">1008</span></span>|  
|<span data-ttu-id="4a590-106">关键字</span><span class="sxs-lookup"><span data-stu-id="4a590-106">Keywords</span></span>|<span data-ttu-id="4a590-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4a590-107">WFRuntime</span></span>|  
|<span data-ttu-id="4a590-108">级别</span><span class="sxs-lookup"><span data-stu-id="4a590-108">Level</span></span>|<span data-ttu-id="4a590-109">信息</span><span class="sxs-lookup"><span data-stu-id="4a590-109">Information</span></span>|  
|<span data-ttu-id="4a590-110">通道</span><span class="sxs-lookup"><span data-stu-id="4a590-110">Channel</span></span>|<span data-ttu-id="4a590-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="4a590-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4a590-112">描述</span><span class="sxs-lookup"><span data-stu-id="4a590-112">Description</span></span>  
 <span data-ttu-id="4a590-113">指示工作流应用程序已卸载。</span><span class="sxs-lookup"><span data-stu-id="4a590-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4a590-114">消息</span><span class="sxs-lookup"><span data-stu-id="4a590-114">Message</span></span>  
 <span data-ttu-id="4a590-115">WorkflowInstance Id“%1”已卸载。</span><span class="sxs-lookup"><span data-stu-id="4a590-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4a590-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="4a590-116">Details</span></span>  
  
|<span data-ttu-id="4a590-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="4a590-117">Data Item Name</span></span>|<span data-ttu-id="4a590-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="4a590-118">Data Item Type</span></span>|<span data-ttu-id="4a590-119">描述</span><span class="sxs-lookup"><span data-stu-id="4a590-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4a590-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="4a590-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="4a590-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="4a590-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="4a590-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4a590-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4a590-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="4a590-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

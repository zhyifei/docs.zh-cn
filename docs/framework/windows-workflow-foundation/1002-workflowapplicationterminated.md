---
title: 1002 - WorkflowApplicationTerminated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 54ef06c3aded628e18325b78f55e80e4470ecd01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="b5f9e-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="b5f9e-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="b5f9e-103">属性</span><span class="sxs-lookup"><span data-stu-id="b5f9e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b5f9e-104">ID</span><span class="sxs-lookup"><span data-stu-id="b5f9e-104">ID</span></span>|<span data-ttu-id="b5f9e-105">1002</span><span class="sxs-lookup"><span data-stu-id="b5f9e-105">1002</span></span>|  
|<span data-ttu-id="b5f9e-106">关键字</span><span class="sxs-lookup"><span data-stu-id="b5f9e-106">Keywords</span></span>|<span data-ttu-id="b5f9e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b5f9e-107">WFRuntime</span></span>|  
|<span data-ttu-id="b5f9e-108">级别</span><span class="sxs-lookup"><span data-stu-id="b5f9e-108">Level</span></span>|<span data-ttu-id="b5f9e-109">信息</span><span class="sxs-lookup"><span data-stu-id="b5f9e-109">Information</span></span>|  
|<span data-ttu-id="b5f9e-110">通道</span><span class="sxs-lookup"><span data-stu-id="b5f9e-110">Channel</span></span>|<span data-ttu-id="b5f9e-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="b5f9e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b5f9e-112">描述</span><span class="sxs-lookup"><span data-stu-id="b5f9e-112">Description</span></span>  
 <span data-ttu-id="b5f9e-113">指示工作流应用程序因出现异常而在“出错”状态下终止。</span><span class="sxs-lookup"><span data-stu-id="b5f9e-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b5f9e-114">消息</span><span class="sxs-lookup"><span data-stu-id="b5f9e-114">Message</span></span>  
 <span data-ttu-id="b5f9e-115">WorkflowApplication Id“%1”已终止。</span><span class="sxs-lookup"><span data-stu-id="b5f9e-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="b5f9e-116">该应用程序因出现异常而在“出错”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="b5f9e-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b5f9e-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="b5f9e-117">Details</span></span>  
  
|<span data-ttu-id="b5f9e-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="b5f9e-118">Data Item Name</span></span>|<span data-ttu-id="b5f9e-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="b5f9e-119">Data Item Type</span></span>|<span data-ttu-id="b5f9e-120">描述</span><span class="sxs-lookup"><span data-stu-id="b5f9e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b5f9e-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="b5f9e-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="b5f9e-122">工作流应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="b5f9e-122">The workflow application id</span></span>|  
|<span data-ttu-id="b5f9e-123">例外</span><span class="sxs-lookup"><span data-stu-id="b5f9e-123">Exception</span></span>|`xs:string`|<span data-ttu-id="b5f9e-124">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="b5f9e-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="b5f9e-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b5f9e-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b5f9e-126">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="b5f9e-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

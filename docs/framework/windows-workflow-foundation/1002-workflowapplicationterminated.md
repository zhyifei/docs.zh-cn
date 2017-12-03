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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 93a6a400576df84faae3cd58940462255b0073c6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="672b3-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="672b3-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="672b3-103">属性</span><span class="sxs-lookup"><span data-stu-id="672b3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="672b3-104">ID</span><span class="sxs-lookup"><span data-stu-id="672b3-104">ID</span></span>|<span data-ttu-id="672b3-105">1002</span><span class="sxs-lookup"><span data-stu-id="672b3-105">1002</span></span>|  
|<span data-ttu-id="672b3-106">关键字</span><span class="sxs-lookup"><span data-stu-id="672b3-106">Keywords</span></span>|<span data-ttu-id="672b3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="672b3-107">WFRuntime</span></span>|  
|<span data-ttu-id="672b3-108">级别</span><span class="sxs-lookup"><span data-stu-id="672b3-108">Level</span></span>|<span data-ttu-id="672b3-109">信息</span><span class="sxs-lookup"><span data-stu-id="672b3-109">Information</span></span>|  
|<span data-ttu-id="672b3-110">通道</span><span class="sxs-lookup"><span data-stu-id="672b3-110">Channel</span></span>|<span data-ttu-id="672b3-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="672b3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="672b3-112">描述</span><span class="sxs-lookup"><span data-stu-id="672b3-112">Description</span></span>  
 <span data-ttu-id="672b3-113">指示工作流应用程序因出现异常而在“出错”状态下终止。</span><span class="sxs-lookup"><span data-stu-id="672b3-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="672b3-114">消息</span><span class="sxs-lookup"><span data-stu-id="672b3-114">Message</span></span>  
 <span data-ttu-id="672b3-115">WorkflowApplication Id“%1”已终止。</span><span class="sxs-lookup"><span data-stu-id="672b3-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="672b3-116">该应用程序因出现异常而在“出错”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="672b3-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="672b3-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="672b3-117">Details</span></span>  
  
|<span data-ttu-id="672b3-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="672b3-118">Data Item Name</span></span>|<span data-ttu-id="672b3-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="672b3-119">Data Item Type</span></span>|<span data-ttu-id="672b3-120">描述</span><span class="sxs-lookup"><span data-stu-id="672b3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="672b3-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="672b3-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="672b3-122">工作流应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="672b3-122">The workflow application id</span></span>|  
|<span data-ttu-id="672b3-123">例外</span><span class="sxs-lookup"><span data-stu-id="672b3-123">Exception</span></span>|`xs:string`|<span data-ttu-id="672b3-124">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="672b3-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="672b3-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="672b3-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="672b3-126">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="672b3-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

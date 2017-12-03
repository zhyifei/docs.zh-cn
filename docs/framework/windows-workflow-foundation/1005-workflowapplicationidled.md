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
ms.openlocfilehash: 2603621eb23747275e6db22a1743c5260967c6a3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="801b0-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="801b0-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="801b0-103">属性</span><span class="sxs-lookup"><span data-stu-id="801b0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="801b0-104">ID</span><span class="sxs-lookup"><span data-stu-id="801b0-104">ID</span></span>|<span data-ttu-id="801b0-105">1005</span><span class="sxs-lookup"><span data-stu-id="801b0-105">1005</span></span>|  
|<span data-ttu-id="801b0-106">关键字</span><span class="sxs-lookup"><span data-stu-id="801b0-106">Keywords</span></span>|<span data-ttu-id="801b0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="801b0-107">WFRuntime</span></span>|  
|<span data-ttu-id="801b0-108">级别</span><span class="sxs-lookup"><span data-stu-id="801b0-108">Level</span></span>|<span data-ttu-id="801b0-109">信息</span><span class="sxs-lookup"><span data-stu-id="801b0-109">Information</span></span>|  
|<span data-ttu-id="801b0-110">通道</span><span class="sxs-lookup"><span data-stu-id="801b0-110">Channel</span></span>|<span data-ttu-id="801b0-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="801b0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="801b0-112">描述</span><span class="sxs-lookup"><span data-stu-id="801b0-112">Description</span></span>  
 <span data-ttu-id="801b0-113">指示工作流应用程序已处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="801b0-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="801b0-114">消息</span><span class="sxs-lookup"><span data-stu-id="801b0-114">Message</span></span>  
 <span data-ttu-id="801b0-115">WorkflowApplication ID“%1”变为空闲状态。</span><span class="sxs-lookup"><span data-stu-id="801b0-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="801b0-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="801b0-116">Details</span></span>  
  
|<span data-ttu-id="801b0-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="801b0-117">Data Item Name</span></span>|<span data-ttu-id="801b0-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="801b0-118">Data Item Type</span></span>|<span data-ttu-id="801b0-119">描述</span><span class="sxs-lookup"><span data-stu-id="801b0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="801b0-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="801b0-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="801b0-121">工作流应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="801b0-121">The workflow application id</span></span>|  
|<span data-ttu-id="801b0-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="801b0-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="801b0-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="801b0-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

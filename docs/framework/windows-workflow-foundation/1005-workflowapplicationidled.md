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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 42d22a7187adc712c0f236111cecac89dd59e2f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="d0b90-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="d0b90-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="d0b90-103">属性</span><span class="sxs-lookup"><span data-stu-id="d0b90-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0b90-104">ID</span><span class="sxs-lookup"><span data-stu-id="d0b90-104">ID</span></span>|<span data-ttu-id="d0b90-105">1005</span><span class="sxs-lookup"><span data-stu-id="d0b90-105">1005</span></span>|  
|<span data-ttu-id="d0b90-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d0b90-106">Keywords</span></span>|<span data-ttu-id="d0b90-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d0b90-107">WFRuntime</span></span>|  
|<span data-ttu-id="d0b90-108">级别</span><span class="sxs-lookup"><span data-stu-id="d0b90-108">Level</span></span>|<span data-ttu-id="d0b90-109">信息</span><span class="sxs-lookup"><span data-stu-id="d0b90-109">Information</span></span>|  
|<span data-ttu-id="d0b90-110">通道</span><span class="sxs-lookup"><span data-stu-id="d0b90-110">Channel</span></span>|<span data-ttu-id="d0b90-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="d0b90-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d0b90-112">描述</span><span class="sxs-lookup"><span data-stu-id="d0b90-112">Description</span></span>  
 <span data-ttu-id="d0b90-113">指示工作流应用程序已处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="d0b90-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d0b90-114">消息</span><span class="sxs-lookup"><span data-stu-id="d0b90-114">Message</span></span>  
 <span data-ttu-id="d0b90-115">WorkflowApplication ID“%1”变为空闲状态。</span><span class="sxs-lookup"><span data-stu-id="d0b90-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d0b90-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="d0b90-116">Details</span></span>  
  
|<span data-ttu-id="d0b90-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d0b90-117">Data Item Name</span></span>|<span data-ttu-id="d0b90-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d0b90-118">Data Item Type</span></span>|<span data-ttu-id="d0b90-119">描述</span><span class="sxs-lookup"><span data-stu-id="d0b90-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d0b90-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="d0b90-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="d0b90-121">工作流应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="d0b90-121">The workflow application id</span></span>|  
|<span data-ttu-id="d0b90-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d0b90-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d0b90-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d0b90-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a62a8448319e7b07a3ea302f00f2fa269bf654ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="bf66c-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="bf66c-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="bf66c-103">属性</span><span class="sxs-lookup"><span data-stu-id="bf66c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bf66c-104">ID</span><span class="sxs-lookup"><span data-stu-id="bf66c-104">ID</span></span>|<span data-ttu-id="bf66c-105">1001</span><span class="sxs-lookup"><span data-stu-id="bf66c-105">1001</span></span>|  
|<span data-ttu-id="bf66c-106">关键字</span><span class="sxs-lookup"><span data-stu-id="bf66c-106">Keywords</span></span>|<span data-ttu-id="bf66c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="bf66c-107">WFRuntime</span></span>|  
|<span data-ttu-id="bf66c-108">级别</span><span class="sxs-lookup"><span data-stu-id="bf66c-108">Level</span></span>|<span data-ttu-id="bf66c-109">信息</span><span class="sxs-lookup"><span data-stu-id="bf66c-109">Information</span></span>|  
|<span data-ttu-id="bf66c-110">通道</span><span class="sxs-lookup"><span data-stu-id="bf66c-110">Channel</span></span>|<span data-ttu-id="bf66c-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="bf66c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bf66c-112">描述</span><span class="sxs-lookup"><span data-stu-id="bf66c-112">Description</span></span>  
 <span data-ttu-id="bf66c-113">指示工作流应用程序在“已关闭”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="bf66c-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bf66c-114">消息</span><span class="sxs-lookup"><span data-stu-id="bf66c-114">Message</span></span>  
 <span data-ttu-id="bf66c-115">WorkflowInstance Id“%1”在“已关闭”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="bf66c-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="bf66c-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="bf66c-116">Details</span></span>  
  
|<span data-ttu-id="bf66c-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="bf66c-117">Data Item Name</span></span>|<span data-ttu-id="bf66c-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="bf66c-118">Data Item Type</span></span>|<span data-ttu-id="bf66c-119">描述</span><span class="sxs-lookup"><span data-stu-id="bf66c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bf66c-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="bf66c-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="bf66c-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="bf66c-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="bf66c-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bf66c-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="bf66c-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="bf66c-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

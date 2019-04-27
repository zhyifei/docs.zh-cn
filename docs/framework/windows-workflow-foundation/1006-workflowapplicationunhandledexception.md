---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 471f3ecea66ebbd07a09686ab536a84b25d46e6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924704"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="19f82-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="19f82-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="19f82-103">属性</span><span class="sxs-lookup"><span data-stu-id="19f82-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="19f82-104">Id</span><span class="sxs-lookup"><span data-stu-id="19f82-104">ID</span></span>|<span data-ttu-id="19f82-105">1006</span><span class="sxs-lookup"><span data-stu-id="19f82-105">1006</span></span>|  
|<span data-ttu-id="19f82-106">关键字</span><span class="sxs-lookup"><span data-stu-id="19f82-106">Keywords</span></span>|<span data-ttu-id="19f82-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="19f82-107">WFRuntime</span></span>|  
|<span data-ttu-id="19f82-108">级别</span><span class="sxs-lookup"><span data-stu-id="19f82-108">Level</span></span>|<span data-ttu-id="19f82-109">Error</span><span class="sxs-lookup"><span data-stu-id="19f82-109">Error</span></span>|  
|<span data-ttu-id="19f82-110">通道</span><span class="sxs-lookup"><span data-stu-id="19f82-110">Channel</span></span>|<span data-ttu-id="19f82-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="19f82-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="19f82-112">描述</span><span class="sxs-lookup"><span data-stu-id="19f82-112">Description</span></span>  
 <span data-ttu-id="19f82-113">指示工作流应用程序遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="19f82-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="19f82-114">消息</span><span class="sxs-lookup"><span data-stu-id="19f82-114">Message</span></span>  
 <span data-ttu-id="19f82-115">工作流实例 Id:"%1"遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="19f82-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="19f82-116">异常来自 Activity"%2"、 DisplayName:"%3"。</span><span class="sxs-lookup"><span data-stu-id="19f82-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="19f82-117">不会执行以下操作: %4。</span><span class="sxs-lookup"><span data-stu-id="19f82-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="19f82-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="19f82-118">Details</span></span>  
  
|<span data-ttu-id="19f82-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="19f82-119">Data Item Name</span></span>|<span data-ttu-id="19f82-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="19f82-120">Data Item Type</span></span>|<span data-ttu-id="19f82-121">描述</span><span class="sxs-lookup"><span data-stu-id="19f82-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="19f82-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="19f82-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="19f82-123">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="19f82-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="19f82-124">例外</span><span class="sxs-lookup"><span data-stu-id="19f82-124">Exception</span></span>|`xs:string`|<span data-ttu-id="19f82-125">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="19f82-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="19f82-126">应用程序域</span><span class="sxs-lookup"><span data-stu-id="19f82-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="19f82-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="19f82-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

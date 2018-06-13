---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 471f3ecea66ebbd07a09686ab536a84b25d46e6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510752"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="0fecb-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="0fecb-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="0fecb-103">属性</span><span class="sxs-lookup"><span data-stu-id="0fecb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0fecb-104">ID</span><span class="sxs-lookup"><span data-stu-id="0fecb-104">ID</span></span>|<span data-ttu-id="0fecb-105">1006</span><span class="sxs-lookup"><span data-stu-id="0fecb-105">1006</span></span>|  
|<span data-ttu-id="0fecb-106">关键字</span><span class="sxs-lookup"><span data-stu-id="0fecb-106">Keywords</span></span>|<span data-ttu-id="0fecb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0fecb-107">WFRuntime</span></span>|  
|<span data-ttu-id="0fecb-108">级别</span><span class="sxs-lookup"><span data-stu-id="0fecb-108">Level</span></span>|<span data-ttu-id="0fecb-109">错误</span><span class="sxs-lookup"><span data-stu-id="0fecb-109">Error</span></span>|  
|<span data-ttu-id="0fecb-110">通道</span><span class="sxs-lookup"><span data-stu-id="0fecb-110">Channel</span></span>|<span data-ttu-id="0fecb-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="0fecb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0fecb-112">描述</span><span class="sxs-lookup"><span data-stu-id="0fecb-112">Description</span></span>  
 <span data-ttu-id="0fecb-113">指示工作流应用程序遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="0fecb-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0fecb-114">消息</span><span class="sxs-lookup"><span data-stu-id="0fecb-114">Message</span></span>  
 <span data-ttu-id="0fecb-115">WorkflowInstance Id"%1"遇到未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="0fecb-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="0fecb-116">则将产生异常从 Activity"%2"、 DisplayName:"%3"。</span><span class="sxs-lookup"><span data-stu-id="0fecb-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="0fecb-117">不会执行以下操作: %4。</span><span class="sxs-lookup"><span data-stu-id="0fecb-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0fecb-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="0fecb-118">Details</span></span>  
  
|<span data-ttu-id="0fecb-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="0fecb-119">Data Item Name</span></span>|<span data-ttu-id="0fecb-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="0fecb-120">Data Item Type</span></span>|<span data-ttu-id="0fecb-121">描述</span><span class="sxs-lookup"><span data-stu-id="0fecb-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0fecb-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="0fecb-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="0fecb-123">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="0fecb-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="0fecb-124">例外</span><span class="sxs-lookup"><span data-stu-id="0fecb-124">Exception</span></span>|`xs:string`|<span data-ttu-id="0fecb-125">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="0fecb-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="0fecb-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0fecb-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0fecb-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="0fecb-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

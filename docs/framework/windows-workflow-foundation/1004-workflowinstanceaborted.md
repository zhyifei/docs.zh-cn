---
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d1eaf3cf107a6b5e244cc2d9372ee68d387ef6c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510661"
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="be508-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="be508-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="be508-103">属性</span><span class="sxs-lookup"><span data-stu-id="be508-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="be508-104">ID</span><span class="sxs-lookup"><span data-stu-id="be508-104">ID</span></span>|<span data-ttu-id="be508-105">1004</span><span class="sxs-lookup"><span data-stu-id="be508-105">1004</span></span>|  
|<span data-ttu-id="be508-106">关键字</span><span class="sxs-lookup"><span data-stu-id="be508-106">Keywords</span></span>|<span data-ttu-id="be508-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="be508-107">WFRuntime</span></span>|  
|<span data-ttu-id="be508-108">级别</span><span class="sxs-lookup"><span data-stu-id="be508-108">Level</span></span>|<span data-ttu-id="be508-109">信息</span><span class="sxs-lookup"><span data-stu-id="be508-109">Information</span></span>|  
|<span data-ttu-id="be508-110">通道</span><span class="sxs-lookup"><span data-stu-id="be508-110">Channel</span></span>|<span data-ttu-id="be508-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="be508-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="be508-112">描述</span><span class="sxs-lookup"><span data-stu-id="be508-112">Description</span></span>  
 <span data-ttu-id="be508-113">指示工作流实例已中止并且具有异常。</span><span class="sxs-lookup"><span data-stu-id="be508-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="be508-114">消息</span><span class="sxs-lookup"><span data-stu-id="be508-114">Message</span></span>  
 <span data-ttu-id="be508-115">WorkflowInstance Id“%1”因出现异常而中止。</span><span class="sxs-lookup"><span data-stu-id="be508-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="be508-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="be508-116">Details</span></span>  
  
|<span data-ttu-id="be508-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="be508-117">Data Item Name</span></span>|<span data-ttu-id="be508-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="be508-118">Data Item Type</span></span>|<span data-ttu-id="be508-119">描述</span><span class="sxs-lookup"><span data-stu-id="be508-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="be508-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="be508-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="be508-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="be508-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="be508-122">例外</span><span class="sxs-lookup"><span data-stu-id="be508-122">Exception</span></span>|`xs:string`|<span data-ttu-id="be508-123">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="be508-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="be508-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="be508-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="be508-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="be508-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

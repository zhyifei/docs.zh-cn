---
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: c76a2dab6a95bda7f3969af07f814aba30071c7f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008624"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="8bf5d-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="8bf5d-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="8bf5d-103">属性</span><span class="sxs-lookup"><span data-stu-id="8bf5d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8bf5d-104">Id</span><span class="sxs-lookup"><span data-stu-id="8bf5d-104">ID</span></span>|<span data-ttu-id="8bf5d-105">1003</span><span class="sxs-lookup"><span data-stu-id="8bf5d-105">1003</span></span>|  
|<span data-ttu-id="8bf5d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="8bf5d-106">Keywords</span></span>|<span data-ttu-id="8bf5d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8bf5d-107">WFRuntime</span></span>|  
|<span data-ttu-id="8bf5d-108">级别</span><span class="sxs-lookup"><span data-stu-id="8bf5d-108">Level</span></span>|<span data-ttu-id="8bf5d-109">信息</span><span class="sxs-lookup"><span data-stu-id="8bf5d-109">Information</span></span>|  
|<span data-ttu-id="8bf5d-110">通道</span><span class="sxs-lookup"><span data-stu-id="8bf5d-110">Channel</span></span>|<span data-ttu-id="8bf5d-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="8bf5d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8bf5d-112">描述</span><span class="sxs-lookup"><span data-stu-id="8bf5d-112">Description</span></span>  
 <span data-ttu-id="8bf5d-113">指示工作流实例在“已取消”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="8bf5d-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8bf5d-114">消息</span><span class="sxs-lookup"><span data-stu-id="8bf5d-114">Message</span></span>  
 <span data-ttu-id="8bf5d-115">WorkflowInstance Id“%1”在“已取消”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="8bf5d-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8bf5d-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="8bf5d-116">Details</span></span>  
  
|<span data-ttu-id="8bf5d-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="8bf5d-117">Data Item Name</span></span>|<span data-ttu-id="8bf5d-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="8bf5d-118">Data Item Type</span></span>|<span data-ttu-id="8bf5d-119">描述</span><span class="sxs-lookup"><span data-stu-id="8bf5d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8bf5d-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="8bf5d-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="8bf5d-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="8bf5d-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="8bf5d-122">应用程序域</span><span class="sxs-lookup"><span data-stu-id="8bf5d-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8bf5d-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="8bf5d-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

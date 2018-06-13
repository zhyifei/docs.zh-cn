---
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: c76a2dab6a95bda7f3969af07f814aba30071c7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509764"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="fb800-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="fb800-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="fb800-103">属性</span><span class="sxs-lookup"><span data-stu-id="fb800-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fb800-104">ID</span><span class="sxs-lookup"><span data-stu-id="fb800-104">ID</span></span>|<span data-ttu-id="fb800-105">1003</span><span class="sxs-lookup"><span data-stu-id="fb800-105">1003</span></span>|  
|<span data-ttu-id="fb800-106">关键字</span><span class="sxs-lookup"><span data-stu-id="fb800-106">Keywords</span></span>|<span data-ttu-id="fb800-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fb800-107">WFRuntime</span></span>|  
|<span data-ttu-id="fb800-108">级别</span><span class="sxs-lookup"><span data-stu-id="fb800-108">Level</span></span>|<span data-ttu-id="fb800-109">信息</span><span class="sxs-lookup"><span data-stu-id="fb800-109">Information</span></span>|  
|<span data-ttu-id="fb800-110">通道</span><span class="sxs-lookup"><span data-stu-id="fb800-110">Channel</span></span>|<span data-ttu-id="fb800-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="fb800-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fb800-112">描述</span><span class="sxs-lookup"><span data-stu-id="fb800-112">Description</span></span>  
 <span data-ttu-id="fb800-113">指示工作流实例在“已取消”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="fb800-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fb800-114">消息</span><span class="sxs-lookup"><span data-stu-id="fb800-114">Message</span></span>  
 <span data-ttu-id="fb800-115">WorkflowInstance Id“%1”在“已取消”状态下完成。</span><span class="sxs-lookup"><span data-stu-id="fb800-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fb800-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="fb800-116">Details</span></span>  
  
|<span data-ttu-id="fb800-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="fb800-117">Data Item Name</span></span>|<span data-ttu-id="fb800-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="fb800-118">Data Item Type</span></span>|<span data-ttu-id="fb800-119">描述</span><span class="sxs-lookup"><span data-stu-id="fb800-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fb800-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="fb800-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="fb800-121">工作流的实例 ID</span><span class="sxs-lookup"><span data-stu-id="fb800-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="fb800-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fb800-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fb800-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="fb800-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

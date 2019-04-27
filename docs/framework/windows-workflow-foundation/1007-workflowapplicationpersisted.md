---
title: 1007 - WorkflowApplicationPersisted
ms.date: 03/30/2017
ms.assetid: f4ea4452-28e3-4e66-93c6-eb12ee29bcb1
ms.openlocfilehash: 0b3c290ad06eda6921626c0d7a1c8ec854c30e7a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925263"
---
# <a name="1007---workflowapplicationpersisted"></a><span data-ttu-id="07535-102">1007 - WorkflowApplicationPersisted</span><span class="sxs-lookup"><span data-stu-id="07535-102">1007 - WorkflowApplicationPersisted</span></span>
## <a name="properties"></a><span data-ttu-id="07535-103">属性</span><span class="sxs-lookup"><span data-stu-id="07535-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07535-104">Id</span><span class="sxs-lookup"><span data-stu-id="07535-104">ID</span></span>|<span data-ttu-id="07535-105">1007</span><span class="sxs-lookup"><span data-stu-id="07535-105">1007</span></span>|  
|<span data-ttu-id="07535-106">关键字</span><span class="sxs-lookup"><span data-stu-id="07535-106">Keywords</span></span>|<span data-ttu-id="07535-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="07535-107">WFRuntime</span></span>|  
|<span data-ttu-id="07535-108">级别</span><span class="sxs-lookup"><span data-stu-id="07535-108">Level</span></span>|<span data-ttu-id="07535-109">信息</span><span class="sxs-lookup"><span data-stu-id="07535-109">Information</span></span>|  
|<span data-ttu-id="07535-110">通道</span><span class="sxs-lookup"><span data-stu-id="07535-110">Channel</span></span>|<span data-ttu-id="07535-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="07535-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="07535-112">描述</span><span class="sxs-lookup"><span data-stu-id="07535-112">Description</span></span>  
 <span data-ttu-id="07535-113">指示工作流应用程序已持久化。</span><span class="sxs-lookup"><span data-stu-id="07535-113">Indicates a workflow application has persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="07535-114">消息</span><span class="sxs-lookup"><span data-stu-id="07535-114">Message</span></span>  
 <span data-ttu-id="07535-115">WorkflowApplication ID“%1”已持久化。</span><span class="sxs-lookup"><span data-stu-id="07535-115">WorkflowApplication Id: '%1' was Persisted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="07535-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="07535-116">Details</span></span>  
  
|<span data-ttu-id="07535-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="07535-117">Data Item Name</span></span>|<span data-ttu-id="07535-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="07535-118">Data Item Type</span></span>|<span data-ttu-id="07535-119">描述</span><span class="sxs-lookup"><span data-stu-id="07535-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="07535-120">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="07535-120">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="07535-121">工作流应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="07535-121">The workflow application id</span></span>|  
|<span data-ttu-id="07535-122">应用程序域</span><span class="sxs-lookup"><span data-stu-id="07535-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="07535-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="07535-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

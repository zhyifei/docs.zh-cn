---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 07be0ae603443a1ef06cb539bba7b227d7b3e325
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924184"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="5402a-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="5402a-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="5402a-103">属性</span><span class="sxs-lookup"><span data-stu-id="5402a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5402a-104">Id</span><span class="sxs-lookup"><span data-stu-id="5402a-104">ID</span></span>|<span data-ttu-id="5402a-105">1041</span><span class="sxs-lookup"><span data-stu-id="5402a-105">1041</span></span>|  
|<span data-ttu-id="5402a-106">关键字</span><span class="sxs-lookup"><span data-stu-id="5402a-106">Keywords</span></span>|<span data-ttu-id="5402a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5402a-107">WFRuntime</span></span>|  
|<span data-ttu-id="5402a-108">级别</span><span class="sxs-lookup"><span data-stu-id="5402a-108">Level</span></span>|<span data-ttu-id="5402a-109">信息</span><span class="sxs-lookup"><span data-stu-id="5402a-109">Information</span></span>|  
|<span data-ttu-id="5402a-110">通道</span><span class="sxs-lookup"><span data-stu-id="5402a-110">Channel</span></span>|<span data-ttu-id="5402a-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="5402a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5402a-112">描述</span><span class="sxs-lookup"><span data-stu-id="5402a-112">Description</span></span>  
 <span data-ttu-id="5402a-113">指示工作流应用程序空闲且可持久化。</span><span class="sxs-lookup"><span data-stu-id="5402a-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="5402a-114">工作流应用程序将是空闲且可持久化的。</span><span class="sxs-lookup"><span data-stu-id="5402a-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5402a-115">消息</span><span class="sxs-lookup"><span data-stu-id="5402a-115">Message</span></span>  
 <span data-ttu-id="5402a-116">WorkflowApplication Id"%1"是空闲且可持久化。</span><span class="sxs-lookup"><span data-stu-id="5402a-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="5402a-117">不会执行以下操作: %2。</span><span class="sxs-lookup"><span data-stu-id="5402a-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5402a-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="5402a-118">Details</span></span>  
  
|<span data-ttu-id="5402a-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="5402a-119">Data Item Name</span></span>|<span data-ttu-id="5402a-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="5402a-120">Data Item Type</span></span>|<span data-ttu-id="5402a-121">描述</span><span class="sxs-lookup"><span data-stu-id="5402a-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5402a-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="5402a-122">WorkflowApplicationId</span></span>|<span data-ttu-id="5402a-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="5402a-123">xs:string</span></span>|<span data-ttu-id="5402a-124">工作流应用程序 ID</span><span class="sxs-lookup"><span data-stu-id="5402a-124">The workflow application id</span></span>|  
|<span data-ttu-id="5402a-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="5402a-125">ActionTaken</span></span>|<span data-ttu-id="5402a-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="5402a-126">xs:string</span></span>|<span data-ttu-id="5402a-127">将对工作流应用程序执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5402a-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="5402a-128">应用程序域</span><span class="sxs-lookup"><span data-stu-id="5402a-128">AppDomain</span></span>|<span data-ttu-id="5402a-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="5402a-129">xs:string</span></span>|<span data-ttu-id="5402a-130">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="5402a-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

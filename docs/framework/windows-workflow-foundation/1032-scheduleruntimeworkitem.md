---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: 505b852d54e256b2c2bfff8d90944dd4e993e0c0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924860"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="9f30b-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="9f30b-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="9f30b-103">属性</span><span class="sxs-lookup"><span data-stu-id="9f30b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9f30b-104">Id</span><span class="sxs-lookup"><span data-stu-id="9f30b-104">ID</span></span>|<span data-ttu-id="9f30b-105">1032</span><span class="sxs-lookup"><span data-stu-id="9f30b-105">1032</span></span>|  
|<span data-ttu-id="9f30b-106">关键字</span><span class="sxs-lookup"><span data-stu-id="9f30b-106">Keywords</span></span>|<span data-ttu-id="9f30b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9f30b-107">WFRuntime</span></span>|  
|<span data-ttu-id="9f30b-108">级别</span><span class="sxs-lookup"><span data-stu-id="9f30b-108">Level</span></span>|<span data-ttu-id="9f30b-109">详细</span><span class="sxs-lookup"><span data-stu-id="9f30b-109">Verbose</span></span>|  
|<span data-ttu-id="9f30b-110">通道</span><span class="sxs-lookup"><span data-stu-id="9f30b-110">Channel</span></span>|<span data-ttu-id="9f30b-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="9f30b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9f30b-112">描述</span><span class="sxs-lookup"><span data-stu-id="9f30b-112">Description</span></span>  
 <span data-ttu-id="9f30b-113">指示已安排 RuntimeWorkItem。</span><span class="sxs-lookup"><span data-stu-id="9f30b-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9f30b-114">消息</span><span class="sxs-lookup"><span data-stu-id="9f30b-114">Message</span></span>  
 <span data-ttu-id="9f30b-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了运行时工作项。</span><span class="sxs-lookup"><span data-stu-id="9f30b-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9f30b-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="9f30b-116">Details</span></span>  
  
|<span data-ttu-id="9f30b-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="9f30b-117">Data Item Name</span></span>|<span data-ttu-id="9f30b-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="9f30b-118">Data Item Type</span></span>|<span data-ttu-id="9f30b-119">描述</span><span class="sxs-lookup"><span data-stu-id="9f30b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9f30b-120">活动</span><span class="sxs-lookup"><span data-stu-id="9f30b-120">Activity</span></span>|<span data-ttu-id="9f30b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9f30b-121">xs:string</span></span>|<span data-ttu-id="9f30b-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="9f30b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="9f30b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9f30b-123">DisplayName</span></span>|<span data-ttu-id="9f30b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9f30b-124">xs:string</span></span>|<span data-ttu-id="9f30b-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="9f30b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="9f30b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="9f30b-126">InstanceId</span></span>|<span data-ttu-id="9f30b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9f30b-127">xs:string</span></span>|<span data-ttu-id="9f30b-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="9f30b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="9f30b-129">应用程序域</span><span class="sxs-lookup"><span data-stu-id="9f30b-129">AppDomain</span></span>|<span data-ttu-id="9f30b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="9f30b-130">xs:string</span></span>|<span data-ttu-id="9f30b-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="9f30b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

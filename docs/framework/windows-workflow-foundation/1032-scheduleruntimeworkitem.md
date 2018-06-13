---
title: 1032 - ScheduleRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
ms.openlocfilehash: 505b852d54e256b2c2bfff8d90944dd4e993e0c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510242"
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="ab06a-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="ab06a-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ab06a-103">属性</span><span class="sxs-lookup"><span data-stu-id="ab06a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ab06a-104">ID</span><span class="sxs-lookup"><span data-stu-id="ab06a-104">ID</span></span>|<span data-ttu-id="ab06a-105">1032</span><span class="sxs-lookup"><span data-stu-id="ab06a-105">1032</span></span>|  
|<span data-ttu-id="ab06a-106">关键字</span><span class="sxs-lookup"><span data-stu-id="ab06a-106">Keywords</span></span>|<span data-ttu-id="ab06a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ab06a-107">WFRuntime</span></span>|  
|<span data-ttu-id="ab06a-108">级别</span><span class="sxs-lookup"><span data-stu-id="ab06a-108">Level</span></span>|<span data-ttu-id="ab06a-109">详细</span><span class="sxs-lookup"><span data-stu-id="ab06a-109">Verbose</span></span>|  
|<span data-ttu-id="ab06a-110">通道</span><span class="sxs-lookup"><span data-stu-id="ab06a-110">Channel</span></span>|<span data-ttu-id="ab06a-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="ab06a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ab06a-112">描述</span><span class="sxs-lookup"><span data-stu-id="ab06a-112">Description</span></span>  
 <span data-ttu-id="ab06a-113">指示已安排 RuntimeWorkItem。</span><span class="sxs-lookup"><span data-stu-id="ab06a-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ab06a-114">消息</span><span class="sxs-lookup"><span data-stu-id="ab06a-114">Message</span></span>  
 <span data-ttu-id="ab06a-115">已为 Activity“%1”、DisplayName“%2”、InstanceId“%3”安排了运行时工作项。</span><span class="sxs-lookup"><span data-stu-id="ab06a-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ab06a-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="ab06a-116">Details</span></span>  
  
|<span data-ttu-id="ab06a-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="ab06a-117">Data Item Name</span></span>|<span data-ttu-id="ab06a-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="ab06a-118">Data Item Type</span></span>|<span data-ttu-id="ab06a-119">描述</span><span class="sxs-lookup"><span data-stu-id="ab06a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ab06a-120">Activity</span><span class="sxs-lookup"><span data-stu-id="ab06a-120">Activity</span></span>|<span data-ttu-id="ab06a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab06a-121">xs:string</span></span>|<span data-ttu-id="ab06a-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="ab06a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ab06a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ab06a-123">DisplayName</span></span>|<span data-ttu-id="ab06a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab06a-124">xs:string</span></span>|<span data-ttu-id="ab06a-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ab06a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ab06a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ab06a-126">InstanceId</span></span>|<span data-ttu-id="ab06a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab06a-127">xs:string</span></span>|<span data-ttu-id="ab06a-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="ab06a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ab06a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ab06a-129">AppDomain</span></span>|<span data-ttu-id="ab06a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ab06a-130">xs:string</span></span>|<span data-ttu-id="ab06a-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="ab06a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

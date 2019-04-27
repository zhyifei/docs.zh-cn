---
title: 1034 - CompleteRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
ms.openlocfilehash: bd49c608a8f6a6caab6975850507a00a2c0edb03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924548"
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="30232-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="30232-102">1034 - CompleteRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="30232-103">属性</span><span class="sxs-lookup"><span data-stu-id="30232-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30232-104">Id</span><span class="sxs-lookup"><span data-stu-id="30232-104">ID</span></span>|<span data-ttu-id="30232-105">1034</span><span class="sxs-lookup"><span data-stu-id="30232-105">1034</span></span>|  
|<span data-ttu-id="30232-106">关键字</span><span class="sxs-lookup"><span data-stu-id="30232-106">Keywords</span></span>|<span data-ttu-id="30232-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="30232-107">WFRuntime</span></span>|  
|<span data-ttu-id="30232-108">级别</span><span class="sxs-lookup"><span data-stu-id="30232-108">Level</span></span>|<span data-ttu-id="30232-109">详细</span><span class="sxs-lookup"><span data-stu-id="30232-109">Verbose</span></span>|  
|<span data-ttu-id="30232-110">通道</span><span class="sxs-lookup"><span data-stu-id="30232-110">Channel</span></span>|<span data-ttu-id="30232-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="30232-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="30232-112">描述</span><span class="sxs-lookup"><span data-stu-id="30232-112">Description</span></span>  
 <span data-ttu-id="30232-113">指示 RuntimeWorkItem 已完成。</span><span class="sxs-lookup"><span data-stu-id="30232-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="30232-114">消息</span><span class="sxs-lookup"><span data-stu-id="30232-114">Message</span></span>  
 <span data-ttu-id="30232-115">Activity“%1”、DisplayName“%2”、InstanceId“%3”的运行时工作项已经完成。</span><span class="sxs-lookup"><span data-stu-id="30232-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="30232-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="30232-116">Details</span></span>  
  
|<span data-ttu-id="30232-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="30232-117">Data Item Name</span></span>|<span data-ttu-id="30232-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="30232-118">Data Item Type</span></span>|<span data-ttu-id="30232-119">描述</span><span class="sxs-lookup"><span data-stu-id="30232-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="30232-120">活动</span><span class="sxs-lookup"><span data-stu-id="30232-120">Activity</span></span>|<span data-ttu-id="30232-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="30232-121">xs:string</span></span>|<span data-ttu-id="30232-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="30232-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="30232-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="30232-123">DisplayName</span></span>|<span data-ttu-id="30232-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="30232-124">xs:string</span></span>|<span data-ttu-id="30232-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="30232-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="30232-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="30232-126">InstanceId</span></span>|<span data-ttu-id="30232-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="30232-127">xs:string</span></span>|<span data-ttu-id="30232-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="30232-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="30232-129">应用程序域</span><span class="sxs-lookup"><span data-stu-id="30232-129">AppDomain</span></span>|<span data-ttu-id="30232-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="30232-130">xs:string</span></span>|<span data-ttu-id="30232-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="30232-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

---
title: 1150 - CompensationState
ms.date: 03/30/2017
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
ms.openlocfilehash: 61613a27c4d4d8fb0b206246fef25ae87def47a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510675"
---
# <a name="1150---compensationstate"></a><span data-ttu-id="b999c-102">1150 - CompensationState</span><span class="sxs-lookup"><span data-stu-id="b999c-102">1150 - CompensationState</span></span>
## <a name="properties"></a><span data-ttu-id="b999c-103">属性</span><span class="sxs-lookup"><span data-stu-id="b999c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b999c-104">ID</span><span class="sxs-lookup"><span data-stu-id="b999c-104">ID</span></span>|<span data-ttu-id="b999c-105">1150</span><span class="sxs-lookup"><span data-stu-id="b999c-105">1150</span></span>|  
|<span data-ttu-id="b999c-106">关键字</span><span class="sxs-lookup"><span data-stu-id="b999c-106">Keywords</span></span>|<span data-ttu-id="b999c-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="b999c-107">WFActivities</span></span>|  
|<span data-ttu-id="b999c-108">级别</span><span class="sxs-lookup"><span data-stu-id="b999c-108">Level</span></span>|<span data-ttu-id="b999c-109">信息</span><span class="sxs-lookup"><span data-stu-id="b999c-109">Information</span></span>|  
|<span data-ttu-id="b999c-110">通道</span><span class="sxs-lookup"><span data-stu-id="b999c-110">Channel</span></span>|<span data-ttu-id="b999c-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="b999c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b999c-112">描述</span><span class="sxs-lookup"><span data-stu-id="b999c-112">Description</span></span>  
 <span data-ttu-id="b999c-113">指示状态在 CompensableActivity 中发生更改。</span><span class="sxs-lookup"><span data-stu-id="b999c-113">Indicates a change of state in a CompensableActivity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b999c-114">消息</span><span class="sxs-lookup"><span data-stu-id="b999c-114">Message</span></span>  
 <span data-ttu-id="b999c-115">CompensableActivity“%1”的状态为“%2”。</span><span class="sxs-lookup"><span data-stu-id="b999c-115">CompensableActivity '%1' is in the '%2' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b999c-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="b999c-116">Details</span></span>  
  
|<span data-ttu-id="b999c-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="b999c-117">Data Item Name</span></span>|<span data-ttu-id="b999c-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="b999c-118">Data Item Type</span></span>|<span data-ttu-id="b999c-119">描述</span><span class="sxs-lookup"><span data-stu-id="b999c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b999c-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b999c-120">DisplayName</span></span>|<span data-ttu-id="b999c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b999c-121">xs:string</span></span>|<span data-ttu-id="b999c-122">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="b999c-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="b999c-123">状态</span><span class="sxs-lookup"><span data-stu-id="b999c-123">State</span></span>|<span data-ttu-id="b999c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b999c-124">xs:string</span></span>|<span data-ttu-id="b999c-125">补偿状态。</span><span class="sxs-lookup"><span data-stu-id="b999c-125">The compensation state.</span></span>|  
|<span data-ttu-id="b999c-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b999c-126">AppDomain</span></span>|<span data-ttu-id="b999c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b999c-127">xs:string</span></span>|<span data-ttu-id="b999c-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="b999c-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

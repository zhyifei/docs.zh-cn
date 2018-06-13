---
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: 8d7045b0a7f31ecfd5dd90f319192bd202804353
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510648"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="22f27-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="22f27-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="22f27-103">属性</span><span class="sxs-lookup"><span data-stu-id="22f27-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="22f27-104">ID</span><span class="sxs-lookup"><span data-stu-id="22f27-104">ID</span></span>|<span data-ttu-id="22f27-105">1018</span><span class="sxs-lookup"><span data-stu-id="22f27-105">1018</span></span>|  
|<span data-ttu-id="22f27-106">关键字</span><span class="sxs-lookup"><span data-stu-id="22f27-106">Keywords</span></span>|<span data-ttu-id="22f27-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="22f27-107">WFRuntime</span></span>|  
|<span data-ttu-id="22f27-108">级别</span><span class="sxs-lookup"><span data-stu-id="22f27-108">Level</span></span>|<span data-ttu-id="22f27-109">详细</span><span class="sxs-lookup"><span data-stu-id="22f27-109">Verbose</span></span>|  
|<span data-ttu-id="22f27-110">通道</span><span class="sxs-lookup"><span data-stu-id="22f27-110">Channel</span></span>|<span data-ttu-id="22f27-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="22f27-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="22f27-112">描述</span><span class="sxs-lookup"><span data-stu-id="22f27-112">Description</span></span>  
 <span data-ttu-id="22f27-113">指示 CancelActivityWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="22f27-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="22f27-114">消息</span><span class="sxs-lookup"><span data-stu-id="22f27-114">Message</span></span>  
 <span data-ttu-id="22f27-115">开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 CancelActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="22f27-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="22f27-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="22f27-116">Details</span></span>  
  
|<span data-ttu-id="22f27-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="22f27-117">Data Item Name</span></span>|<span data-ttu-id="22f27-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="22f27-118">Data Item Type</span></span>|<span data-ttu-id="22f27-119">描述</span><span class="sxs-lookup"><span data-stu-id="22f27-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="22f27-120">Activity</span><span class="sxs-lookup"><span data-stu-id="22f27-120">Activity</span></span>|<span data-ttu-id="22f27-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="22f27-121">xs:string</span></span>|<span data-ttu-id="22f27-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="22f27-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="22f27-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="22f27-123">DisplayName</span></span>|<span data-ttu-id="22f27-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="22f27-124">xs:string</span></span>|<span data-ttu-id="22f27-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="22f27-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="22f27-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="22f27-126">InstanceId</span></span>|<span data-ttu-id="22f27-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="22f27-127">xs:string</span></span>|<span data-ttu-id="22f27-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="22f27-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="22f27-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="22f27-129">AppDomain</span></span>|<span data-ttu-id="22f27-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="22f27-130">xs:string</span></span>|<span data-ttu-id="22f27-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="22f27-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

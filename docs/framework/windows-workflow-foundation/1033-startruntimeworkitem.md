---
title: 1033 - StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: c7192ed7c5fb43fe6f65b47b8cebde3cf4aed32c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510061"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="986b6-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="986b6-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="986b6-103">属性</span><span class="sxs-lookup"><span data-stu-id="986b6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="986b6-104">ID</span><span class="sxs-lookup"><span data-stu-id="986b6-104">ID</span></span>|<span data-ttu-id="986b6-105">1033</span><span class="sxs-lookup"><span data-stu-id="986b6-105">1033</span></span>|  
|<span data-ttu-id="986b6-106">关键字</span><span class="sxs-lookup"><span data-stu-id="986b6-106">Keywords</span></span>|<span data-ttu-id="986b6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="986b6-107">WFRuntime</span></span>|  
|<span data-ttu-id="986b6-108">级别</span><span class="sxs-lookup"><span data-stu-id="986b6-108">Level</span></span>|<span data-ttu-id="986b6-109">详细</span><span class="sxs-lookup"><span data-stu-id="986b6-109">Verbose</span></span>|  
|<span data-ttu-id="986b6-110">通道</span><span class="sxs-lookup"><span data-stu-id="986b6-110">Channel</span></span>|<span data-ttu-id="986b6-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="986b6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="986b6-112">描述</span><span class="sxs-lookup"><span data-stu-id="986b6-112">Description</span></span>  
 <span data-ttu-id="986b6-113">指示 RuntimeWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="986b6-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="986b6-114">消息</span><span class="sxs-lookup"><span data-stu-id="986b6-114">Message</span></span>  
 <span data-ttu-id="986b6-115">开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行运行时工作项。</span><span class="sxs-lookup"><span data-stu-id="986b6-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="986b6-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="986b6-116">Details</span></span>  
  
|<span data-ttu-id="986b6-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="986b6-117">Data Item Name</span></span>|<span data-ttu-id="986b6-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="986b6-118">Data Item Type</span></span>|<span data-ttu-id="986b6-119">描述</span><span class="sxs-lookup"><span data-stu-id="986b6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="986b6-120">Activity</span><span class="sxs-lookup"><span data-stu-id="986b6-120">Activity</span></span>|<span data-ttu-id="986b6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="986b6-121">xs:string</span></span>|<span data-ttu-id="986b6-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="986b6-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="986b6-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="986b6-123">DisplayName</span></span>|<span data-ttu-id="986b6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="986b6-124">xs:string</span></span>|<span data-ttu-id="986b6-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="986b6-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="986b6-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="986b6-126">InstanceId</span></span>|<span data-ttu-id="986b6-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="986b6-127">xs:string</span></span>|<span data-ttu-id="986b6-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="986b6-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="986b6-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="986b6-129">AppDomain</span></span>|<span data-ttu-id="986b6-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="986b6-130">xs:string</span></span>|<span data-ttu-id="986b6-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="986b6-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

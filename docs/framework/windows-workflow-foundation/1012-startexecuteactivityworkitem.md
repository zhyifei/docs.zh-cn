---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: d6b330bc454c39584e5027f757fd9d9d3434d941
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924574"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="a6062-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="a6062-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="a6062-103">属性</span><span class="sxs-lookup"><span data-stu-id="a6062-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a6062-104">Id</span><span class="sxs-lookup"><span data-stu-id="a6062-104">ID</span></span>|<span data-ttu-id="a6062-105">1012</span><span class="sxs-lookup"><span data-stu-id="a6062-105">1012</span></span>|  
|<span data-ttu-id="a6062-106">关键字</span><span class="sxs-lookup"><span data-stu-id="a6062-106">Keywords</span></span>|<span data-ttu-id="a6062-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a6062-107">WFRuntime</span></span>|  
|<span data-ttu-id="a6062-108">级别</span><span class="sxs-lookup"><span data-stu-id="a6062-108">Level</span></span>|<span data-ttu-id="a6062-109">详细</span><span class="sxs-lookup"><span data-stu-id="a6062-109">Verbose</span></span>|  
|<span data-ttu-id="a6062-110">通道</span><span class="sxs-lookup"><span data-stu-id="a6062-110">Channel</span></span>|<span data-ttu-id="a6062-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="a6062-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a6062-112">描述</span><span class="sxs-lookup"><span data-stu-id="a6062-112">Description</span></span>  
 <span data-ttu-id="a6062-113">指示 ExecuteActivityWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="a6062-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a6062-114">消息</span><span class="sxs-lookup"><span data-stu-id="a6062-114">Message</span></span>  
 <span data-ttu-id="a6062-115">开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 ExecuteActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="a6062-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a6062-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="a6062-116">Details</span></span>  
  
|<span data-ttu-id="a6062-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="a6062-117">Data Item Name</span></span>|<span data-ttu-id="a6062-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="a6062-118">Data Item Type</span></span>|<span data-ttu-id="a6062-119">描述</span><span class="sxs-lookup"><span data-stu-id="a6062-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a6062-120">活动</span><span class="sxs-lookup"><span data-stu-id="a6062-120">Activity</span></span>|<span data-ttu-id="a6062-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6062-121">xs:string</span></span>|<span data-ttu-id="a6062-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="a6062-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="a6062-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a6062-123">DisplayName</span></span>|<span data-ttu-id="a6062-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6062-124">xs:string</span></span>|<span data-ttu-id="a6062-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="a6062-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="a6062-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="a6062-126">InstanceId</span></span>|<span data-ttu-id="a6062-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6062-127">xs:string</span></span>|<span data-ttu-id="a6062-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="a6062-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="a6062-129">应用程序域</span><span class="sxs-lookup"><span data-stu-id="a6062-129">AppDomain</span></span>|<span data-ttu-id="a6062-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="a6062-130">xs:string</span></span>|<span data-ttu-id="a6062-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="a6062-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

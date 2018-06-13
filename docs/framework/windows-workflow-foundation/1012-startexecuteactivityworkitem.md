---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: d6b330bc454c39584e5027f757fd9d9d3434d941
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510375"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="f2b7e-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="f2b7e-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f2b7e-103">属性</span><span class="sxs-lookup"><span data-stu-id="f2b7e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f2b7e-104">ID</span><span class="sxs-lookup"><span data-stu-id="f2b7e-104">ID</span></span>|<span data-ttu-id="f2b7e-105">1012</span><span class="sxs-lookup"><span data-stu-id="f2b7e-105">1012</span></span>|  
|<span data-ttu-id="f2b7e-106">关键字</span><span class="sxs-lookup"><span data-stu-id="f2b7e-106">Keywords</span></span>|<span data-ttu-id="f2b7e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f2b7e-107">WFRuntime</span></span>|  
|<span data-ttu-id="f2b7e-108">级别</span><span class="sxs-lookup"><span data-stu-id="f2b7e-108">Level</span></span>|<span data-ttu-id="f2b7e-109">详细</span><span class="sxs-lookup"><span data-stu-id="f2b7e-109">Verbose</span></span>|  
|<span data-ttu-id="f2b7e-110">通道</span><span class="sxs-lookup"><span data-stu-id="f2b7e-110">Channel</span></span>|<span data-ttu-id="f2b7e-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="f2b7e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f2b7e-112">描述</span><span class="sxs-lookup"><span data-stu-id="f2b7e-112">Description</span></span>  
 <span data-ttu-id="f2b7e-113">指示 ExecuteActivityWorkItem 正在开始执行。</span><span class="sxs-lookup"><span data-stu-id="f2b7e-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f2b7e-114">消息</span><span class="sxs-lookup"><span data-stu-id="f2b7e-114">Message</span></span>  
 <span data-ttu-id="f2b7e-115">开始为 Activity“%1”、DisplayName“%2”、InstanceId“%3”执行 ExecuteActivityWorkItem。</span><span class="sxs-lookup"><span data-stu-id="f2b7e-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f2b7e-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="f2b7e-116">Details</span></span>  
  
|<span data-ttu-id="f2b7e-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="f2b7e-117">Data Item Name</span></span>|<span data-ttu-id="f2b7e-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="f2b7e-118">Data Item Type</span></span>|<span data-ttu-id="f2b7e-119">描述</span><span class="sxs-lookup"><span data-stu-id="f2b7e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f2b7e-120">Activity</span><span class="sxs-lookup"><span data-stu-id="f2b7e-120">Activity</span></span>|<span data-ttu-id="f2b7e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2b7e-121">xs:string</span></span>|<span data-ttu-id="f2b7e-122">活动的类型名称。</span><span class="sxs-lookup"><span data-stu-id="f2b7e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="f2b7e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f2b7e-123">DisplayName</span></span>|<span data-ttu-id="f2b7e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2b7e-124">xs:string</span></span>|<span data-ttu-id="f2b7e-125">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="f2b7e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="f2b7e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f2b7e-126">InstanceId</span></span>|<span data-ttu-id="f2b7e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2b7e-127">xs:string</span></span>|<span data-ttu-id="f2b7e-128">活动的实例 ID。</span><span class="sxs-lookup"><span data-stu-id="f2b7e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f2b7e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f2b7e-129">AppDomain</span></span>|<span data-ttu-id="f2b7e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="f2b7e-130">xs:string</span></span>|<span data-ttu-id="f2b7e-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="f2b7e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

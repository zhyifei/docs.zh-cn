---
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: d644c25ec2dee06eea4a5fb66c30792bb650f252
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945959"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="fd94a-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="fd94a-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="fd94a-103">属性</span><span class="sxs-lookup"><span data-stu-id="fd94a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd94a-104">Id</span><span class="sxs-lookup"><span data-stu-id="fd94a-104">ID</span></span>|<span data-ttu-id="fd94a-105">57398</span><span class="sxs-lookup"><span data-stu-id="fd94a-105">57398</span></span>|  
|<span data-ttu-id="fd94a-106">关键字</span><span class="sxs-lookup"><span data-stu-id="fd94a-106">Keywords</span></span>|<span data-ttu-id="fd94a-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="fd94a-107">WFServices</span></span>|  
|<span data-ttu-id="fd94a-108">级别</span><span class="sxs-lookup"><span data-stu-id="fd94a-108">Level</span></span>|<span data-ttu-id="fd94a-109">警告</span><span class="sxs-lookup"><span data-stu-id="fd94a-109">Warning</span></span>|  
|<span data-ttu-id="fd94a-110">通道</span><span class="sxs-lookup"><span data-stu-id="fd94a-110">Channel</span></span>|<span data-ttu-id="fd94a-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="fd94a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fd94a-112">描述</span><span class="sxs-lookup"><span data-stu-id="fd94a-112">Description</span></span>  
 <span data-ttu-id="fd94a-113">指示系统达到为限制“MaxConcurrentInstances”设置的限制值。</span><span class="sxs-lookup"><span data-stu-id="fd94a-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fd94a-114">消息</span><span class="sxs-lookup"><span data-stu-id="fd94a-114">Message</span></span>  
 <span data-ttu-id="fd94a-115">系统达到为限制“MaxConcurrentInstances”设置的限制值。</span><span class="sxs-lookup"><span data-stu-id="fd94a-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="fd94a-116">此限制的限制值设置为 %1。</span><span class="sxs-lookup"><span data-stu-id="fd94a-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="fd94a-117">可通过修改 serviceThrottle 元素中的特性“maxConcurrentInstances”或修改行为 ServiceThrottlingBehavior 的“MaxConcurrentInstances”属性来更改限制值。</span><span class="sxs-lookup"><span data-stu-id="fd94a-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fd94a-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="fd94a-118">Details</span></span>  
  
|<span data-ttu-id="fd94a-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="fd94a-119">Data Item Name</span></span>|<span data-ttu-id="fd94a-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="fd94a-120">Data Item Type</span></span>|<span data-ttu-id="fd94a-121">描述</span><span class="sxs-lookup"><span data-stu-id="fd94a-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fd94a-122">名称</span><span class="sxs-lookup"><span data-stu-id="fd94a-122">Name</span></span>|<span data-ttu-id="fd94a-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd94a-123">xs:string</span></span>|<span data-ttu-id="fd94a-124">项的名称。</span><span class="sxs-lookup"><span data-stu-id="fd94a-124">The name of the item.</span></span>|  
|<span data-ttu-id="fd94a-125">应用程序域</span><span class="sxs-lookup"><span data-stu-id="fd94a-125">AppDomain</span></span>|<span data-ttu-id="fd94a-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd94a-126">xs:string</span></span>|<span data-ttu-id="fd94a-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="fd94a-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

---
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: d644c25ec2dee06eea4a5fb66c30792bb650f252
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512546"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="708fb-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="708fb-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="708fb-103">属性</span><span class="sxs-lookup"><span data-stu-id="708fb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="708fb-104">ID</span><span class="sxs-lookup"><span data-stu-id="708fb-104">ID</span></span>|<span data-ttu-id="708fb-105">57398</span><span class="sxs-lookup"><span data-stu-id="708fb-105">57398</span></span>|  
|<span data-ttu-id="708fb-106">关键字</span><span class="sxs-lookup"><span data-stu-id="708fb-106">Keywords</span></span>|<span data-ttu-id="708fb-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="708fb-107">WFServices</span></span>|  
|<span data-ttu-id="708fb-108">级别</span><span class="sxs-lookup"><span data-stu-id="708fb-108">Level</span></span>|<span data-ttu-id="708fb-109">警告</span><span class="sxs-lookup"><span data-stu-id="708fb-109">Warning</span></span>|  
|<span data-ttu-id="708fb-110">通道</span><span class="sxs-lookup"><span data-stu-id="708fb-110">Channel</span></span>|<span data-ttu-id="708fb-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="708fb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="708fb-112">描述</span><span class="sxs-lookup"><span data-stu-id="708fb-112">Description</span></span>  
 <span data-ttu-id="708fb-113">指示系统达到为限制“MaxConcurrentInstances”设置的限制值。</span><span class="sxs-lookup"><span data-stu-id="708fb-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="708fb-114">消息</span><span class="sxs-lookup"><span data-stu-id="708fb-114">Message</span></span>  
 <span data-ttu-id="708fb-115">系统达到为限制“MaxConcurrentInstances”设置的限制值。</span><span class="sxs-lookup"><span data-stu-id="708fb-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="708fb-116">此限制的限制值设置为 %1。</span><span class="sxs-lookup"><span data-stu-id="708fb-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="708fb-117">可通过修改 serviceThrottle 元素中的特性“maxConcurrentInstances”或修改行为 ServiceThrottlingBehavior 的“MaxConcurrentInstances”属性来更改限制值。</span><span class="sxs-lookup"><span data-stu-id="708fb-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="708fb-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="708fb-118">Details</span></span>  
  
|<span data-ttu-id="708fb-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="708fb-119">Data Item Name</span></span>|<span data-ttu-id="708fb-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="708fb-120">Data Item Type</span></span>|<span data-ttu-id="708fb-121">描述</span><span class="sxs-lookup"><span data-stu-id="708fb-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="708fb-122">名称</span><span class="sxs-lookup"><span data-stu-id="708fb-122">Name</span></span>|<span data-ttu-id="708fb-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="708fb-123">xs:string</span></span>|<span data-ttu-id="708fb-124">项的名称。</span><span class="sxs-lookup"><span data-stu-id="708fb-124">The name of the item.</span></span>|  
|<span data-ttu-id="708fb-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="708fb-125">AppDomain</span></span>|<span data-ttu-id="708fb-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="708fb-126">xs:string</span></span>|<span data-ttu-id="708fb-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="708fb-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

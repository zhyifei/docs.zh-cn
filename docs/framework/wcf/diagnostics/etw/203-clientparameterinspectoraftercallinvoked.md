---
title: 203 - ClientParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
ms.openlocfilehash: 57192b44a0c3babc77fcca13ad4a1433b85bfdd7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="08445-102">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="08445-102">203 - ClientParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="08445-103">属性</span><span class="sxs-lookup"><span data-stu-id="08445-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="08445-104">ID</span><span class="sxs-lookup"><span data-stu-id="08445-104">ID</span></span>|<span data-ttu-id="08445-105">203</span><span class="sxs-lookup"><span data-stu-id="08445-105">203</span></span>|  
|<span data-ttu-id="08445-106">关键字</span><span class="sxs-lookup"><span data-stu-id="08445-106">Keywords</span></span>|<span data-ttu-id="08445-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="08445-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="08445-108">级别</span><span class="sxs-lookup"><span data-stu-id="08445-108">Level</span></span>|<span data-ttu-id="08445-109">信息</span><span class="sxs-lookup"><span data-stu-id="08445-109">Information</span></span>|  
|<span data-ttu-id="08445-110">通道</span><span class="sxs-lookup"><span data-stu-id="08445-110">Channel</span></span>|<span data-ttu-id="08445-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="08445-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="08445-112">描述</span><span class="sxs-lookup"><span data-stu-id="08445-112">Description</span></span>  
 <span data-ttu-id="08445-113">服务模型在客户端参数检查器上调用 `AfterCall` 方法之后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="08445-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="08445-114">消息</span><span class="sxs-lookup"><span data-stu-id="08445-114">Message</span></span>  
 <span data-ttu-id="08445-115">调度程序对“%1”类型的 ClientParameterInspector 调用了“AfterCall”。</span><span class="sxs-lookup"><span data-stu-id="08445-115">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="08445-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="08445-116">Details</span></span>  
  
|<span data-ttu-id="08445-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="08445-117">Data Item Name</span></span>|<span data-ttu-id="08445-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="08445-118">Data Item Type</span></span>|<span data-ttu-id="08445-119">描述</span><span class="sxs-lookup"><span data-stu-id="08445-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="08445-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="08445-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="08445-121">所调用检查器的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="08445-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="08445-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="08445-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="08445-123">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="08445-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="08445-124">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="08445-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="08445-125">示例: 默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="08445-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="08445-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="08445-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="08445-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="08445-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

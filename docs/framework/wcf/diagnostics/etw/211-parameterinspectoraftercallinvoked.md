---
title: 211 - ParameterInspectorAfterCallInvoked
ms.date: 03/30/2017
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
ms.openlocfilehash: ada3ced31def2bb821b975e09f50ad83f28d56bf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781857"
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="3fba7-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="3fba7-102">211 - ParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="3fba7-103">属性</span><span class="sxs-lookup"><span data-stu-id="3fba7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3fba7-104">Id</span><span class="sxs-lookup"><span data-stu-id="3fba7-104">ID</span></span>|<span data-ttu-id="3fba7-105">211</span><span class="sxs-lookup"><span data-stu-id="3fba7-105">211</span></span>|  
|<span data-ttu-id="3fba7-106">关键字</span><span class="sxs-lookup"><span data-stu-id="3fba7-106">Keywords</span></span>|<span data-ttu-id="3fba7-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3fba7-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="3fba7-108">级别</span><span class="sxs-lookup"><span data-stu-id="3fba7-108">Level</span></span>|<span data-ttu-id="3fba7-109">信息</span><span class="sxs-lookup"><span data-stu-id="3fba7-109">Information</span></span>|  
|<span data-ttu-id="3fba7-110">通道</span><span class="sxs-lookup"><span data-stu-id="3fba7-110">Channel</span></span>|<span data-ttu-id="3fba7-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="3fba7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3fba7-112">描述</span><span class="sxs-lookup"><span data-stu-id="3fba7-112">Description</span></span>  
 <span data-ttu-id="3fba7-113">服务模型对 `AfterCall` 调用 `ParameterInspector` 方法之后，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="3fba7-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3fba7-114">消息</span><span class="sxs-lookup"><span data-stu-id="3fba7-114">Message</span></span>  
 <span data-ttu-id="3fba7-115">调度程序对“%1”类型的 ParameterInspector 调用了“AfterCall”。</span><span class="sxs-lookup"><span data-stu-id="3fba7-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3fba7-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="3fba7-116">Details</span></span>  
  
|<span data-ttu-id="3fba7-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="3fba7-117">Data Item Name</span></span>|<span data-ttu-id="3fba7-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="3fba7-118">Data Item Type</span></span>|<span data-ttu-id="3fba7-119">描述</span><span class="sxs-lookup"><span data-stu-id="3fba7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3fba7-120">类型名称</span><span class="sxs-lookup"><span data-stu-id="3fba7-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="3fba7-121">所调用 `ParameterInspector` 的类型的 CLR FullName。</span><span class="sxs-lookup"><span data-stu-id="3fba7-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="3fba7-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="3fba7-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="3fba7-123">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="3fba7-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="3fba7-124">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="3fba7-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="3fba7-125">示例:默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="3fba7-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="3fba7-126">应用程序域</span><span class="sxs-lookup"><span data-stu-id="3fba7-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3fba7-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="3fba7-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

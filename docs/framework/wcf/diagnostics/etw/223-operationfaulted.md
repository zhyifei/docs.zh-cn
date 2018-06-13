---
title: 223 - OperationFaulted
ms.date: 03/30/2017
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
ms.openlocfilehash: cf4a455d80a1a0ac09e99bad967c1feba3653842
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459412"
---
# <a name="223---operationfaulted"></a><span data-ttu-id="69992-102">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="69992-102">223 - OperationFaulted</span></span>
## <a name="properties"></a><span data-ttu-id="69992-103">属性</span><span class="sxs-lookup"><span data-stu-id="69992-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="69992-104">Id</span><span class="sxs-lookup"><span data-stu-id="69992-104">ID</span></span>|<span data-ttu-id="69992-105">223</span><span class="sxs-lookup"><span data-stu-id="69992-105">223</span></span>|  
|<span data-ttu-id="69992-106">关键字</span><span class="sxs-lookup"><span data-stu-id="69992-106">Keywords</span></span>|<span data-ttu-id="69992-107">EndToEndMonitoring、HealthMonitoring、疑难解答、ServiceModel</span><span class="sxs-lookup"><span data-stu-id="69992-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="69992-108">级别</span><span class="sxs-lookup"><span data-stu-id="69992-108">Level</span></span>|<span data-ttu-id="69992-109">警告</span><span class="sxs-lookup"><span data-stu-id="69992-109">Warning</span></span>|  
|<span data-ttu-id="69992-110">通道</span><span class="sxs-lookup"><span data-stu-id="69992-110">Channel</span></span>|<span data-ttu-id="69992-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="69992-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="69992-112">描述</span><span class="sxs-lookup"><span data-stu-id="69992-112">Description</span></span>  
 <span data-ttu-id="69992-113">服务模型的默认 `OperationInvoker` 在调用其方法期间出现派生自 `FaultException` 的异常时，将发出此事件。</span><span class="sxs-lookup"><span data-stu-id="69992-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="69992-114">消息</span><span class="sxs-lookup"><span data-stu-id="69992-114">Message</span></span>  
 <span data-ttu-id="69992-115">“%1”方法在由 OperationInvoker 调用时引发了一个 FaultException。</span><span class="sxs-lookup"><span data-stu-id="69992-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="69992-116">该方法调用持续了“%2”毫秒。</span><span class="sxs-lookup"><span data-stu-id="69992-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="69992-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="69992-117">Details</span></span>  
  
|<span data-ttu-id="69992-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="69992-118">Data Item Name</span></span>|<span data-ttu-id="69992-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="69992-119">Data Item Type</span></span>|<span data-ttu-id="69992-120">描述</span><span class="sxs-lookup"><span data-stu-id="69992-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="69992-121">MethodName</span><span class="sxs-lookup"><span data-stu-id="69992-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="69992-122">由 `OperationInvoker` 调用的方法的 CLR 名称。</span><span class="sxs-lookup"><span data-stu-id="69992-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="69992-123">持续时间</span><span class="sxs-lookup"><span data-stu-id="69992-123">Duration</span></span>|`xs:long`|<span data-ttu-id="69992-124">`OperationInvoker` 调用方法所花费的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="69992-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="69992-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="69992-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="69992-126">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="69992-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="69992-127">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="69992-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="69992-128">示例: 默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="69992-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="69992-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="69992-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="69992-130">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="69992-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

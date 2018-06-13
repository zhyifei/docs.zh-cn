---
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: e95b6923d21307b2ef68d4a5369b3cee86540239
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458344"
---
# <a name="205---operationinvoked"></a><span data-ttu-id="2181d-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="2181d-102">205 - OperationInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="2181d-103">属性</span><span class="sxs-lookup"><span data-stu-id="2181d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2181d-104">Id</span><span class="sxs-lookup"><span data-stu-id="2181d-104">ID</span></span>|<span data-ttu-id="2181d-105">205</span><span class="sxs-lookup"><span data-stu-id="2181d-105">205</span></span>|  
|<span data-ttu-id="2181d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="2181d-106">Keywords</span></span>|<span data-ttu-id="2181d-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2181d-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="2181d-108">级别</span><span class="sxs-lookup"><span data-stu-id="2181d-108">Level</span></span>|<span data-ttu-id="2181d-109">信息</span><span class="sxs-lookup"><span data-stu-id="2181d-109">Information</span></span>|  
|<span data-ttu-id="2181d-110">通道</span><span class="sxs-lookup"><span data-stu-id="2181d-110">Channel</span></span>|<span data-ttu-id="2181d-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="2181d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2181d-112">描述</span><span class="sxs-lookup"><span data-stu-id="2181d-112">Description</span></span>  
 <span data-ttu-id="2181d-113">恰好在服务模型的默认 `OperationInvoker` 开始调用方法之前发出此事件。</span><span class="sxs-lookup"><span data-stu-id="2181d-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2181d-114">消息</span><span class="sxs-lookup"><span data-stu-id="2181d-114">Message</span></span>  
 <span data-ttu-id="2181d-115">OperationInvoker 调用了“%1”方法。</span><span class="sxs-lookup"><span data-stu-id="2181d-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="2181d-116">调用方信息:“%2”。</span><span class="sxs-lookup"><span data-stu-id="2181d-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2181d-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="2181d-117">Details</span></span>  
  
|<span data-ttu-id="2181d-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="2181d-118">Data Item Name</span></span>|<span data-ttu-id="2181d-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="2181d-119">Data Item Type</span></span>|<span data-ttu-id="2181d-120">描述</span><span class="sxs-lookup"><span data-stu-id="2181d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2181d-121">方法名</span><span class="sxs-lookup"><span data-stu-id="2181d-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="2181d-122">由 `OperationInvoker` 调用的方法的 CLR 名称。</span><span class="sxs-lookup"><span data-stu-id="2181d-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="2181d-123">调用方信息</span><span class="sxs-lookup"><span data-stu-id="2181d-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="2181d-124">客户端 IP 地址和端口号（格式为“IPAddress:PortNumber”）。</span><span class="sxs-lookup"><span data-stu-id="2181d-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="2181d-125">需要从操作上下文的“System.ServiceModel.Channels.RemoteEndpointMessageProperty”消息属性中检索这两个值。</span><span class="sxs-lookup"><span data-stu-id="2181d-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="2181d-126">请注意，对于非 TCP 绑定，该值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="2181d-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="2181d-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="2181d-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="2181d-128">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="2181d-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2181d-129">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="2181d-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2181d-130">示例: 默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="2181d-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2181d-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2181d-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2181d-132">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="2181d-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

---
title: 216 - MessageSentByTransport
ms.date: 03/30/2017
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
ms.openlocfilehash: fa21568e4c8c38eefe359c417d47ec0a9d30a7c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781805"
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="da41e-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="da41e-102">216 - MessageSentByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="da41e-103">属性</span><span class="sxs-lookup"><span data-stu-id="da41e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da41e-104">Id</span><span class="sxs-lookup"><span data-stu-id="da41e-104">ID</span></span>|<span data-ttu-id="da41e-105">216</span><span class="sxs-lookup"><span data-stu-id="da41e-105">216</span></span>|  
|<span data-ttu-id="da41e-106">关键字</span><span class="sxs-lookup"><span data-stu-id="da41e-106">Keywords</span></span>|<span data-ttu-id="da41e-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="da41e-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="da41e-108">级别</span><span class="sxs-lookup"><span data-stu-id="da41e-108">Level</span></span>|<span data-ttu-id="da41e-109">信息</span><span class="sxs-lookup"><span data-stu-id="da41e-109">Information</span></span>|  
|<span data-ttu-id="da41e-110">通道</span><span class="sxs-lookup"><span data-stu-id="da41e-110">Channel</span></span>|<span data-ttu-id="da41e-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="da41e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="da41e-112">描述</span><span class="sxs-lookup"><span data-stu-id="da41e-112">Description</span></span>  
 <span data-ttu-id="da41e-113">使用基于 TCP 的传输发送消息时发生此事件。</span><span class="sxs-lookup"><span data-stu-id="da41e-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="da41e-114">请注意，在传输级别上，单个操作可在客户端和服务之间交换多条消息。</span><span class="sxs-lookup"><span data-stu-id="da41e-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="da41e-115">这可能是由于基础结构行为的特点，在此方面，安全性是一个很好的例子。</span><span class="sxs-lookup"><span data-stu-id="da41e-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="da41e-116">因此，数**MessageSentByTransport**基于服务的绑定和其配置发出的事件而定。</span><span class="sxs-lookup"><span data-stu-id="da41e-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="da41e-117">消息</span><span class="sxs-lookup"><span data-stu-id="da41e-117">Message</span></span>  
 <span data-ttu-id="da41e-118">传输向“%1”发送了一条消息。</span><span class="sxs-lookup"><span data-stu-id="da41e-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="da41e-119">详细信息</span><span class="sxs-lookup"><span data-stu-id="da41e-119">Details</span></span>  
  
|<span data-ttu-id="da41e-120">数据项名称</span><span class="sxs-lookup"><span data-stu-id="da41e-120">Data Item Name</span></span>|<span data-ttu-id="da41e-121">数据项类型</span><span class="sxs-lookup"><span data-stu-id="da41e-121">Data Item Type</span></span>|<span data-ttu-id="da41e-122">描述</span><span class="sxs-lookup"><span data-stu-id="da41e-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="da41e-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="da41e-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="da41e-124">将请求消息发送到的地址。</span><span class="sxs-lookup"><span data-stu-id="da41e-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="da41e-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="da41e-125">HostReference</span></span>|<span data-ttu-id="da41e-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="da41e-126">xs:string</span></span>|<span data-ttu-id="da41e-127">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="da41e-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="da41e-128">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="da41e-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="da41e-129">示例:默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="da41e-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="da41e-130">应用程序域</span><span class="sxs-lookup"><span data-stu-id="da41e-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="da41e-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="da41e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

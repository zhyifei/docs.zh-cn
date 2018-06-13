---
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: a8ba90b88ef8dbe3c8651bc565da61aae16a0a4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460898"
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="809e8-102">215 - MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="809e8-102">215 - MessageReceivedByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="809e8-103">属性</span><span class="sxs-lookup"><span data-stu-id="809e8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="809e8-104">ID</span><span class="sxs-lookup"><span data-stu-id="809e8-104">ID</span></span>|<span data-ttu-id="809e8-105">215</span><span class="sxs-lookup"><span data-stu-id="809e8-105">215</span></span>|  
|<span data-ttu-id="809e8-106">关键字</span><span class="sxs-lookup"><span data-stu-id="809e8-106">Keywords</span></span>|<span data-ttu-id="809e8-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="809e8-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="809e8-108">级别</span><span class="sxs-lookup"><span data-stu-id="809e8-108">Level</span></span>|<span data-ttu-id="809e8-109">信息</span><span class="sxs-lookup"><span data-stu-id="809e8-109">Information</span></span>|  
|<span data-ttu-id="809e8-110">通道</span><span class="sxs-lookup"><span data-stu-id="809e8-110">Channel</span></span>|<span data-ttu-id="809e8-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="809e8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="809e8-112">描述</span><span class="sxs-lookup"><span data-stu-id="809e8-112">Description</span></span>  
 <span data-ttu-id="809e8-113">基于 TCP 的传输接收消息时将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="809e8-113">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="809e8-114">请注意，在传输级别上，单个操作可在客户端和服务之间交换多条消息。</span><span class="sxs-lookup"><span data-stu-id="809e8-114">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="809e8-115">这可能是由于基础结构行为的特点，在此方面，安全性是一个很好的例子。</span><span class="sxs-lookup"><span data-stu-id="809e8-115">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="809e8-116">因此，发出的 `MessageReceivedByTransport` 事件数目根据服务绑定及其配置而变化。</span><span class="sxs-lookup"><span data-stu-id="809e8-116">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="809e8-117">不会为单向传输发出此事件。</span><span class="sxs-lookup"><span data-stu-id="809e8-117">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="809e8-118">消息</span><span class="sxs-lookup"><span data-stu-id="809e8-118">Message</span></span>  
 <span data-ttu-id="809e8-119">传输从“%1”收到了一条消息。</span><span class="sxs-lookup"><span data-stu-id="809e8-119">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="809e8-120">详细信息</span><span class="sxs-lookup"><span data-stu-id="809e8-120">Details</span></span>  
  
|<span data-ttu-id="809e8-121">数据项名称</span><span class="sxs-lookup"><span data-stu-id="809e8-121">Data Item Name</span></span>|<span data-ttu-id="809e8-122">数据项类型</span><span class="sxs-lookup"><span data-stu-id="809e8-122">Data Item Type</span></span>|<span data-ttu-id="809e8-123">描述</span><span class="sxs-lookup"><span data-stu-id="809e8-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="809e8-124">侦听地址</span><span class="sxs-lookup"><span data-stu-id="809e8-124">Listen Address</span></span>|`xs:string`|<span data-ttu-id="809e8-125">接收了消息的地址。</span><span class="sxs-lookup"><span data-stu-id="809e8-125">The address that received the message.</span></span>|  
|<span data-ttu-id="809e8-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="809e8-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="809e8-127">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="809e8-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="809e8-128">其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。</span><span class="sxs-lookup"><span data-stu-id="809e8-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="809e8-129">示例: 默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。</span><span class="sxs-lookup"><span data-stu-id="809e8-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="809e8-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="809e8-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="809e8-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="809e8-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

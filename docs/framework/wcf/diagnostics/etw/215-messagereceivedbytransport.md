---
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: aa1ad30526aa65501e5d9875d3877631ca00879b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964189"
---
# <a name="215---messagereceivedbytransport"></a><span data-ttu-id="0c6cd-102">215 - MessageReceivedByTransport</span><span class="sxs-lookup"><span data-stu-id="0c6cd-102">215 - MessageReceivedByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="0c6cd-103">属性</span><span class="sxs-lookup"><span data-stu-id="0c6cd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0c6cd-104">Id</span><span class="sxs-lookup"><span data-stu-id="0c6cd-104">ID</span></span>|<span data-ttu-id="0c6cd-105">215</span><span class="sxs-lookup"><span data-stu-id="0c6cd-105">215</span></span>|  
|<span data-ttu-id="0c6cd-106">关键字</span><span class="sxs-lookup"><span data-stu-id="0c6cd-106">Keywords</span></span>|<span data-ttu-id="0c6cd-107">疑难解答，ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0c6cd-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0c6cd-108">级别</span><span class="sxs-lookup"><span data-stu-id="0c6cd-108">Level</span></span>|<span data-ttu-id="0c6cd-109">Information</span><span class="sxs-lookup"><span data-stu-id="0c6cd-109">Information</span></span>|  
|<span data-ttu-id="0c6cd-110">通道</span><span class="sxs-lookup"><span data-stu-id="0c6cd-110">Channel</span></span>|<span data-ttu-id="0c6cd-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="0c6cd-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0c6cd-112">描述</span><span class="sxs-lookup"><span data-stu-id="0c6cd-112">Description</span></span>  
 <span data-ttu-id="0c6cd-113">基于 TCP 的传输接收消息时将发生此事件。</span><span class="sxs-lookup"><span data-stu-id="0c6cd-113">This event occurs when a TCP-based transport receives a message.</span></span> <span data-ttu-id="0c6cd-114">请注意，在传输级别上，单个操作可在客户端和服务之间交换多条消息。</span><span class="sxs-lookup"><span data-stu-id="0c6cd-114">Note that at the transport level, multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="0c6cd-115">这可能是由于基础结构行为的特点，在此方面，安全性是一个很好的例子。</span><span class="sxs-lookup"><span data-stu-id="0c6cd-115">This can be due to infrastructure behavior, security is a good example.</span></span> <span data-ttu-id="0c6cd-116">因此，发出的 `MessageReceivedByTransport` 事件数目根据服务绑定及其配置而变化。</span><span class="sxs-lookup"><span data-stu-id="0c6cd-116">Therefore, the number of `MessageReceivedByTransport` events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c6cd-117">不会为单向传输发出此事件。</span><span class="sxs-lookup"><span data-stu-id="0c6cd-117">This event is not emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0c6cd-118">消息</span><span class="sxs-lookup"><span data-stu-id="0c6cd-118">Message</span></span>  
 <span data-ttu-id="0c6cd-119">传输从“%1”收到了一条消息。</span><span class="sxs-lookup"><span data-stu-id="0c6cd-119">The transport received a message from '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0c6cd-120">详细信息</span><span class="sxs-lookup"><span data-stu-id="0c6cd-120">Details</span></span>  
  
|<span data-ttu-id="0c6cd-121">数据项名称</span><span class="sxs-lookup"><span data-stu-id="0c6cd-121">Data Item Name</span></span>|<span data-ttu-id="0c6cd-122">数据项类型</span><span class="sxs-lookup"><span data-stu-id="0c6cd-122">Data Item Type</span></span>|<span data-ttu-id="0c6cd-123">描述</span><span class="sxs-lookup"><span data-stu-id="0c6cd-123">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0c6cd-124">侦听地址</span><span class="sxs-lookup"><span data-stu-id="0c6cd-124">Listen Address</span></span>|`xs:string`|<span data-ttu-id="0c6cd-125">接收了消息的地址。</span><span class="sxs-lookup"><span data-stu-id="0c6cd-125">The address that received the message.</span></span>|  
|<span data-ttu-id="0c6cd-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="0c6cd-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="0c6cd-127">对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。</span><span class="sxs-lookup"><span data-stu-id="0c6cd-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0c6cd-128">其格式定义为 "网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName"。</span><span class="sxs-lookup"><span data-stu-id="0c6cd-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0c6cd-129">示例:"Default Web Site//Calculatorapplication&#124;/CalculatorService.svc&#124;CalculatorService"。</span><span class="sxs-lookup"><span data-stu-id="0c6cd-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0c6cd-130">应用程序域</span><span class="sxs-lookup"><span data-stu-id="0c6cd-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0c6cd-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="0c6cd-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|

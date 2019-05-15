---
title: 服务示例的 WCF
ms.date: 03/30/2017
ms.assetid: 462a2218-f8c6-4fb7-95bc-64765459c429
ms.openlocfilehash: 4531e72711d17c57bb4e365b458f0b35d6b42577
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637601"
---
# <a name="services"></a><span data-ttu-id="838cc-102">Services</span><span class="sxs-lookup"><span data-stu-id="838cc-102">Services</span></span>

<span data-ttu-id="838cc-103">本节包含演示 Windows Communication Foundation (WCF) 服务的示例。</span><span class="sxs-lookup"><span data-stu-id="838cc-103">This section contains samples that demonstrate Windows Communication Foundation (WCF) services.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="838cc-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="838cc-104">In this section</span></span>

- <span data-ttu-id="838cc-105">[承载](../../../../docs/framework/wcf/feature-details/hosting.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-105">[Hosting](../../../../docs/framework/wcf/feature-details/hosting.md)\\</span></span>
<span data-ttu-id="838cc-106">演示托管 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="838cc-106">Demonstrates hosting WCF services.</span></span>

- <span data-ttu-id="838cc-107">[服务互操作性](service-interoperability.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-107">[Service Interoperability](service-interoperability.md)\\</span></span>
<span data-ttu-id="838cc-108">演示 WCF 和其他服务技术之间的交互。</span><span class="sxs-lookup"><span data-stu-id="838cc-108">Demonstrates interaction between WCF and other service technologies.</span></span>

- <span data-ttu-id="838cc-109">[行为](behaviors.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-109">[Behaviors](behaviors.md)\\</span></span>
<span data-ttu-id="838cc-110">演示 WCF 服务行为。</span><span class="sxs-lookup"><span data-stu-id="838cc-110">Demonstrates WCF service behaviors.</span></span>

- <span data-ttu-id="838cc-111">[服务安全性](service-security.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-111">[Service Security](service-security.md)\\</span></span>
<span data-ttu-id="838cc-112">演示 WCF 服务安全。</span><span class="sxs-lookup"><span data-stu-id="838cc-112">Demonstrates WCF service security.</span></span>

- <span data-ttu-id="838cc-113">[WCF 服务的简化的配置](simplified-configuration-for-wcf-services.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-113">[Simplified Configuration for WCF Services](simplified-configuration-for-wcf-services.md)\\</span></span>
<span data-ttu-id="838cc-114">演示如何实现和配置典型的服务和客户端使用 WCF。</span><span class="sxs-lookup"><span data-stu-id="838cc-114">Demonstrates how to implement and configure a typical service and client using WCF.</span></span>

- <span data-ttu-id="838cc-115">[标准终结点的使用情况](usage-of-standard-endpoints.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-115">[Usage of Standard Endoints](usage-of-standard-endpoints.md)\\</span></span>
<span data-ttu-id="838cc-116">演示如何在服务配置文件中使用标准终结点。</span><span class="sxs-lookup"><span data-stu-id="838cc-116">Demonstrates how to use standard endpoints in service configuration files.</span></span>

- <span data-ttu-id="838cc-117">[扩展的保护策略](extended-protection-policy.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-117">[Extended Protection Policy](extended-protection-policy.md)\\</span></span>
<span data-ttu-id="838cc-118">演示扩展保护，这是一种针对中间人 (MITM) 攻击而提供保护的安全计划。</span><span class="sxs-lookup"><span data-stu-id="838cc-118">Demonstrates Extended Protection, a security initiative for protecting against man-in-the-middle (MITM) attacks.</span></span>

- <span data-ttu-id="838cc-119">[配置通道工厂](configuration-channel-factory.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-119">[Configuration Channel Factory](configuration-channel-factory.md)\\</span></span>
<span data-ttu-id="838cc-120">演示 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 的用法。</span><span class="sxs-lookup"><span data-stu-id="838cc-120">Demonstrates the usage of the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>.</span></span>

- <span data-ttu-id="838cc-121">[寻址](addressing.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-121">[Addressing](addressing.md)\\</span></span>
<span data-ttu-id="838cc-122">演示终结点地址的各个方面和功能。</span><span class="sxs-lookup"><span data-stu-id="838cc-122">Demonstrates various aspects and features of endpoint addresses.</span></span>

- <span data-ttu-id="838cc-123">[命令性](imperative.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-123">[Imperative](imperative.md)\\</span></span>
<span data-ttu-id="838cc-124">演示如何使用代码为服务定义 <xref:System.ServiceModel.WSHttpBinding>，而不是在配置中定义 `wsHttpBinding` 绑定。</span><span class="sxs-lookup"><span data-stu-id="838cc-124">Demonstrates how to define a <xref:System.ServiceModel.WSHttpBinding> for a service using code, instead of defining the `wsHttpBinding` binding in configuration.</span></span>

- <span data-ttu-id="838cc-125">[多个协定](multiple-contracts.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-125">[Multiple Contracts](multiple-contracts.md)\\</span></span>
<span data-ttu-id="838cc-126">演示如何在一个服务上实现多个协定和如何配置终结点以便与每个实现的协定通信。</span><span class="sxs-lookup"><span data-stu-id="838cc-126">Demonstrates how to implement more than one contract on a service and how to configure endpoints for communicating with each of the implemented contracts.</span></span>

- <span data-ttu-id="838cc-127">[多个终结点](multiple-endpoints.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-127">[Multiple Endpoints](multiple-endpoints.md)\\</span></span>
<span data-ttu-id="838cc-128">演示如何在一个服务上配置多个终结点，以及如何从客户端与每个终结点通信。</span><span class="sxs-lookup"><span data-stu-id="838cc-128">Demonstrates how to configure multiple endpoints on a service and how to communicate with each endpoint from a client.</span></span>

- <span data-ttu-id="838cc-129">[在单个 listenuri 中承载的多个终结点](multiple-endpoints-at-a-single-listenuri.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-129">[Multiple Endpoints at a Single ListenUri](multiple-endpoints-at-a-single-listenuri.md)\\</span></span>
<span data-ttu-id="838cc-130">演示一个在单个 `ListenUri` 中承载多个终结点的服务。</span><span class="sxs-lookup"><span data-stu-id="838cc-130">Demonstrates a service that hosts multiple endpoints at a single `ListenUri`.</span></span>

- <span data-ttu-id="838cc-131">[OperationContextScope](operationcontextscope.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-131">[OperationContextScope](operationcontextscope.md)\\</span></span>
<span data-ttu-id="838cc-132">演示如何将 WCF 调用使用标头上的额外信息发送。</span><span class="sxs-lookup"><span data-stu-id="838cc-132">Demonstrates how to send extra information on a WCF call using headers.</span></span>

- <span data-ttu-id="838cc-133">[服务说明](service-description.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-133">[Service Description](service-description.md)\\</span></span>
<span data-ttu-id="838cc-134">演示服务如何在运行时检索其服务说明信息。</span><span class="sxs-lookup"><span data-stu-id="838cc-134">Demonstrates how a service can retrieve its service description information at runtime.</span></span>

- <span data-ttu-id="838cc-135">[ConcurrencyMode.Reentrant](concurrencymode-reentrant.md)\\</span><span class="sxs-lookup"><span data-stu-id="838cc-135">[ConcurrencyMode.Reentrant](concurrencymode-reentrant.md)\\</span></span>
<span data-ttu-id="838cc-136">演示如何在服务实现上使用可重入并发模式。</span><span class="sxs-lookup"><span data-stu-id="838cc-136">Demonstrates how to use the Reentrant concurrency mode on a service implementation.</span></span>

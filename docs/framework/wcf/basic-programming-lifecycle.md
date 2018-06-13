---
title: 基本编程生命周期
ms.date: 03/30/2017
helpviewer_keywords:
- service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
ms.openlocfilehash: b20167ad776f3524e4516b71e43ab8cdb5c2aea4
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803687"
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="57c8d-102">基本编程生命周期</span><span class="sxs-lookup"><span data-stu-id="57c8d-102">Basic Programming Lifecycle</span></span>
<span data-ttu-id="57c8d-103">Windows Communication Foundation (WCF) 使应用程序通报它们是在同一计算机上分布在 Internet 上还是在不同的应用程序平台上。</span><span class="sxs-lookup"><span data-stu-id="57c8d-103">Windows Communication Foundation (WCF) enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="57c8d-104">本主题概述了生成 WCF 应用程序所需的任务。</span><span class="sxs-lookup"><span data-stu-id="57c8d-104">This topic outlines the tasks that are required to build a WCF application.</span></span> <span data-ttu-id="57c8d-105">有关工作示例应用程序，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="57c8d-105">For a working sample application, see [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="57c8d-106">基本任务</span><span class="sxs-lookup"><span data-stu-id="57c8d-106">The Basic Tasks</span></span>  
 <span data-ttu-id="57c8d-107">要执行的基本任务依次为：</span><span class="sxs-lookup"><span data-stu-id="57c8d-107">The basic tasks to perform are, in order:</span></span>  
  
1.  <span data-ttu-id="57c8d-108">定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="57c8d-108">Define the service contract.</span></span> <span data-ttu-id="57c8d-109">服务协定指定服务的签名、服务交换的数据和其他协定要求的数据。</span><span class="sxs-lookup"><span data-stu-id="57c8d-109">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> <span data-ttu-id="57c8d-110">有关详细信息，请参阅[设计服务协定](../../../docs/framework/wcf/designing-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="57c8d-110">For more information, see [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
2.  <span data-ttu-id="57c8d-111">实现协定。</span><span class="sxs-lookup"><span data-stu-id="57c8d-111">Implement the contract.</span></span> <span data-ttu-id="57c8d-112">若要实现服务协定，请创建实现协定的类并指定运行时应具有的自定义行为。</span><span class="sxs-lookup"><span data-stu-id="57c8d-112">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> <span data-ttu-id="57c8d-113">有关详细信息，请参阅[实现服务协定](../../../docs/framework/wcf/implementing-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="57c8d-113">For more information, see [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
3.  <span data-ttu-id="57c8d-114">通过指定终结点和其他行为信息来配置服务。</span><span class="sxs-lookup"><span data-stu-id="57c8d-114">Configure the service by specifying endpoints and other behavior information.</span></span> <span data-ttu-id="57c8d-115">有关详细信息，请参阅[配置服务](../../../docs/framework/wcf/configuring-services.md)。</span><span class="sxs-lookup"><span data-stu-id="57c8d-115">For more information, see [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
4.  <span data-ttu-id="57c8d-116">承载服务。</span><span class="sxs-lookup"><span data-stu-id="57c8d-116">Host the service.</span></span> <span data-ttu-id="57c8d-117">有关详细信息，请参阅[托管服务](../../../docs/framework/wcf/hosting-services.md)。</span><span class="sxs-lookup"><span data-stu-id="57c8d-117">For more information, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
5.  <span data-ttu-id="57c8d-118">生成客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="57c8d-118">Build a client application.</span></span> <span data-ttu-id="57c8d-119">有关详细信息，请参阅[生成客户端](../../../docs/framework/wcf/building-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="57c8d-119">For more information, see [Building Clients](../../../docs/framework/wcf/building-clients.md).</span></span>  
  
 <span data-ttu-id="57c8d-120">尽管本节中的主题遵循此顺序，但是一些方案并不会从头开始。</span><span class="sxs-lookup"><span data-stu-id="57c8d-120">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="57c8d-121">例如，如果想要为预先存在的服务生成客户端，则从步骤 5 开始。</span><span class="sxs-lookup"><span data-stu-id="57c8d-121">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="57c8d-122">或者，如果您是在生成其他人要使用的服务，则可以跳过步骤 5。</span><span class="sxs-lookup"><span data-stu-id="57c8d-122">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="57c8d-123">一旦你熟悉开发服务协定，您还可以阅读[扩展性介绍](../../../docs/framework/wcf/introduction-to-extensibility.md)。</span><span class="sxs-lookup"><span data-stu-id="57c8d-123">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](../../../docs/framework/wcf/introduction-to-extensibility.md).</span></span> <span data-ttu-id="57c8d-124">如果存在与您的服务的问题，请检查[WCF 疑难解答快速入门](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)以查看是否其他具有相同或类似问题。</span><span class="sxs-lookup"><span data-stu-id="57c8d-124">If you have problems with your service, check [WCF Troubleshooting Quickstart](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57c8d-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="57c8d-125">See Also</span></span>  
 [<span data-ttu-id="57c8d-126">实现服务协定</span><span class="sxs-lookup"><span data-stu-id="57c8d-126">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)

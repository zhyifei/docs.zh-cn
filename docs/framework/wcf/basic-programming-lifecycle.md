---
title: "基本编程生命周期"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service creation [WCF]
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: "36"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f17b37b77c157f1ce3d5ee40fd6464ab378039d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="basic-programming-lifecycle"></a><span data-ttu-id="7fb91-102">基本编程生命周期</span><span class="sxs-lookup"><span data-stu-id="7fb91-102">Basic Programming Lifecycle</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="7fb91-103"> 可让应用程序通报它们是在同一台计算机上、分布在 Internet 上还是在不同的应用程序平台上。</span><span class="sxs-lookup"><span data-stu-id="7fb91-103"> enables applications to communicate whether they are on the same computer, across the Internet, or on different application platforms.</span></span> <span data-ttu-id="7fb91-104">本主题概述了生成 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 应用程序所需的任务。</span><span class="sxs-lookup"><span data-stu-id="7fb91-104">This topic outlines the tasks that are required to build a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="7fb91-105">有关工作示例应用程序，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="7fb91-105">For a working sample application, see [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
## <a name="the-basic-tasks"></a><span data-ttu-id="7fb91-106">基本任务</span><span class="sxs-lookup"><span data-stu-id="7fb91-106">The Basic Tasks</span></span>  
 <span data-ttu-id="7fb91-107">要执行的基本任务依次为：</span><span class="sxs-lookup"><span data-stu-id="7fb91-107">The basic tasks to perform are, in order:</span></span>  
  
1.  <span data-ttu-id="7fb91-108">定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="7fb91-108">Define the service contract.</span></span> <span data-ttu-id="7fb91-109">服务协定指定服务的签名、服务交换的数据和其他协定要求的数据。</span><span class="sxs-lookup"><span data-stu-id="7fb91-109">A service contract specifies the signature of a service, the data it exchanges, and other contractually required data.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="7fb91-110">[设计服务协定](../../../docs/framework/wcf/designing-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="7fb91-110"> [Designing Service Contracts](../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
2.  <span data-ttu-id="7fb91-111">实现协定。</span><span class="sxs-lookup"><span data-stu-id="7fb91-111">Implement the contract.</span></span> <span data-ttu-id="7fb91-112">若要实现服务协定，请创建实现协定的类并指定运行时应具有的自定义行为。</span><span class="sxs-lookup"><span data-stu-id="7fb91-112">To implement a service contract, create a class that implements the contract and specify custom behaviors that the runtime should have.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="7fb91-113">[实现服务协定](../../../docs/framework/wcf/implementing-service-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="7fb91-113"> [Implementing Service Contracts](../../../docs/framework/wcf/implementing-service-contracts.md).</span></span>  
  
3.  <span data-ttu-id="7fb91-114">通过指定终结点和其他行为信息来配置服务。</span><span class="sxs-lookup"><span data-stu-id="7fb91-114">Configure the service by specifying endpoints and other behavior information.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="7fb91-115">[配置服务](../../../docs/framework/wcf/configuring-services.md)。</span><span class="sxs-lookup"><span data-stu-id="7fb91-115"> [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
4.  <span data-ttu-id="7fb91-116">承载服务。</span><span class="sxs-lookup"><span data-stu-id="7fb91-116">Host the service.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="7fb91-117">[托管服务](../../../docs/framework/wcf/hosting-services.md)。</span><span class="sxs-lookup"><span data-stu-id="7fb91-117"> [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
5.  <span data-ttu-id="7fb91-118">生成客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="7fb91-118">Build a client application.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="7fb91-119">[生成客户端](../../../docs/framework/wcf/building-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="7fb91-119"> [Building Clients](../../../docs/framework/wcf/building-clients.md).</span></span>  
  
 <span data-ttu-id="7fb91-120">尽管本节中的主题遵循此顺序，但是一些方案并不会从头开始。</span><span class="sxs-lookup"><span data-stu-id="7fb91-120">Although the topics in this section follow this order, some scenarios do not start at the beginning.</span></span> <span data-ttu-id="7fb91-121">例如，如果想要为预先存在的服务生成客户端，则从步骤 5 开始。</span><span class="sxs-lookup"><span data-stu-id="7fb91-121">For example, if you want to build a client for a pre-existing service, you start at step 5.</span></span> <span data-ttu-id="7fb91-122">或者，如果您是在生成其他人要使用的服务，则可以跳过步骤 5。</span><span class="sxs-lookup"><span data-stu-id="7fb91-122">Or if you are building a service that others will use, you may skip step 5.</span></span>  
  
 <span data-ttu-id="7fb91-123">一旦你熟悉开发服务协定，您还可以阅读[扩展性介绍](../../../docs/framework/wcf/introduction-to-extensibility.md)。</span><span class="sxs-lookup"><span data-stu-id="7fb91-123">Once you are familiar with developing service contracts, you can also read [Introduction to Extensibility](../../../docs/framework/wcf/introduction-to-extensibility.md).</span></span> <span data-ttu-id="7fb91-124">如果存在与您的服务的问题，请检查[WCF 疑难解答快速入门](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)以查看是否其他具有相同或类似问题。</span><span class="sxs-lookup"><span data-stu-id="7fb91-124">If you have problems with your service, check [WCF Troubleshooting Quickstart](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) to see whether others have the same or similar problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb91-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fb91-125">See Also</span></span>  
 [<span data-ttu-id="7fb91-126">实现服务协定</span><span class="sxs-lookup"><span data-stu-id="7fb91-126">Implementing Service Contracts</span></span>](../../../docs/framework/wcf/implementing-service-contracts.md)

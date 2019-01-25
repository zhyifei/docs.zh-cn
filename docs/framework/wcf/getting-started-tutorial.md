---
title: 入门 Tutorial1
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], getting started
- Windows Communication Foundation [WCF], getting started
- getting started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: b0abe7a6b127a254c2f5c72dc66fc128d35374fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491358"
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="1bbc9-102">入门教程</span><span class="sxs-lookup"><span data-stu-id="1bbc9-102">Getting Started Tutorial</span></span>
<span data-ttu-id="1bbc9-103">在本部分中包含的主题旨在帮助您快速了解到 Windows Communication Foundation (WCF) 编程体验。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-103">The topics contained in this section are intended to give you quick exposure to the Windows Communication Foundation (WCF) programming experience.</span></span> <span data-ttu-id="1bbc9-104">这些主题要根据本主题底部的列表中的顺序完成。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-104">They are designed to be completed in the order of the list at the bottom of this topic.</span></span> <span data-ttu-id="1bbc9-105">通过本教程中，可以初步了解创建 WCF 服务和客户端应用程序所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-105">Working through this tutorial gives you an introductory understanding of the steps required to create WCF service and client applications.</span></span> <span data-ttu-id="1bbc9-106">服务公开一个或多个终结点，其中每个终结点都公开一项或多项服务操作。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-106">A service exposes one or more endpoints, each of which exposes one or more service operations.</span></span> <span data-ttu-id="1bbc9-107">*终结点*服务的指定的地址，其中可以找到该服务，包含描述如何在客户端必须与该服务，并定义的功能的协定通信的信息的绑定向其客户端提供服务。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-107">The *endpoint* of a service specifies an address where the service can be found, a binding that contains the information that describes how a client must communicate with the service, and a contract that defines the functionality provided by the service to its clients.</span></span>

 <span data-ttu-id="1bbc9-108">在完成本教程中的系列主题之后，您将会得到一个正在运行的服务，以及一个可以调用该服务的客户端。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-108">After you work through the sequence of topics in this tutorial, you will have a running service, and a client that calls the service.</span></span> <span data-ttu-id="1bbc9-109">前三个主题描述如何定义服务协定、如何实现服务协定以及如何承载服务。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-109">The first three topics describe how to define a service contract, how to implement the service contract, and how to host the service.</span></span> <span data-ttu-id="1bbc9-110">创建的服务自承载在控制台应用程序中。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-110">The service that is created is self-hosted within a console application.</span></span> <span data-ttu-id="1bbc9-111">服务还可在 Internet Information Services (IIS) 下承载。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-111">Services can also be hosted under Internet Information Services (IIS).</span></span> <span data-ttu-id="1bbc9-112">有关如何执行此操作的详细信息，请参阅[如何：承载在 IIS 中的 WCF 服务](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-112">For more information about how to do this, see [How to: Host a WCF Service in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span> <span data-ttu-id="1bbc9-113">在代码中配置服务；不过，也可以在配置文件中配置服务。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-113">The service is configured in code; however, services can also be configured within a configuration file.</span></span> <span data-ttu-id="1bbc9-114">有关使用配置文件的详细信息请参阅[使用配置文件配置服务](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-114">For more information about using a configuration file see [Configuring Services Using Configuration Files](../../../docs/framework/wcf/configuring-services-using-configuration-files.md).</span></span>

 <span data-ttu-id="1bbc9-115">后三个主题描述如何创建客户端代理，如何配置客户端应用程序，以及如何使用客户端代理调用由服务公开的操作。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-115">The next three topics describe how to create a client proxy, configure the client application, and use the client proxy to call service operation exposed by the service.</span></span> <span data-ttu-id="1bbc9-116">服务发布定义客户端应用程序与服务进行通信所需信息的元数据。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-116">Services publish metadata that define the information a client application needs to communicate with the service.</span></span> <span data-ttu-id="1bbc9-117">Visual Studio 2012 可访问此元数据的过程进行自动化，并使用它来构建和配置服务的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-117">Visual Studio 2012 automates the process of accessing this metadata and uses it to construct and configure the client application for the service.</span></span> <span data-ttu-id="1bbc9-118">如果不使用 Visual Studio 2012，则可以使用[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)来构建和配置服务的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-118">If you are not using Visual Studio 2012, you can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to construct and configure the client application for the service.</span></span>

<span data-ttu-id="1bbc9-119">在本部分中的主题假定你使用的 Visual Studio 作为开发环境。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-119">The topics in this section assume you are using Visual Studio as the development environment.</span></span> <span data-ttu-id="1bbc9-120">如果使用其他开发环境，忽略的 Visual Studio 的特定说明。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-120">If you are using another development environment, ignore the Visual Studio-specific instructions.</span></span>

<span data-ttu-id="1bbc9-121">有关示例应用程序，可以下载到您的硬盘和运行，请参阅中的主题[Windows Communication Foundation 示例](https://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-121">For sample applications that can be downloaded to your hard disk and run, see the topics in [Windows Communication Foundation Samples](https://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91).</span></span> <span data-ttu-id="1bbc9-122">本主题中，请参阅，特别是，对于[Getting Started](../../../docs/framework/wcf/samples/getting-started-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-122">For this topic, see, in particular, the [Getting Started](../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>

<span data-ttu-id="1bbc9-123">有关创建服务和客户端的更多详细信息，请参阅[基本 WCF 编程](../../../docs/framework/wcf/basic-wcf-programming.md)。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-123">For more in-depth information about creating services and clients, see [Basic WCF Programming](../../../docs/framework/wcf/basic-wcf-programming.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1bbc9-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="1bbc9-124">In This Section</span></span>
 [<span data-ttu-id="1bbc9-125">如何：定义服务协定</span><span class="sxs-lookup"><span data-stu-id="1bbc9-125">How to: Define a Service Contract</span></span>](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)

 <span data-ttu-id="1bbc9-126">介绍如何创建 WCF 协定使用用户定义的接口。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-126">Describes how to create a WCF contract using a user-defined interface.</span></span> <span data-ttu-id="1bbc9-127">协定定义服务所公开的功能。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-127">The contract defines the functionality exposed by the service.</span></span>

 [<span data-ttu-id="1bbc9-128">如何：实现服务协定</span><span class="sxs-lookup"><span data-stu-id="1bbc9-128">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)

 <span data-ttu-id="1bbc9-129">描述如何实现服务协定。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-129">Describes how to implement a service contract.</span></span> <span data-ttu-id="1bbc9-130">一旦定义了某一协定后，必须使用某一服务类实现该协定。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-130">Once a contract is define, it must be implemented with a service class.</span></span>

 [<span data-ttu-id="1bbc9-131">如何：托管并运行基本服务</span><span class="sxs-lookup"><span data-stu-id="1bbc9-131">How to: Host and Run a Basic Service</span></span>](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)

 <span data-ttu-id="1bbc9-132">描述如何在代码中配置服务的终结点，以及如何在控制台应用程序内承载服务。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-132">Describes how to configure an endpoint for the service in code and how to host the service in a console application.</span></span> <span data-ttu-id="1bbc9-133">若要激活服务，必须在运行时环境中配置和承载服务。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-133">To become active, a service must be configured and hosted within a run-time environment.</span></span> <span data-ttu-id="1bbc9-134">此环境将创建服务并控制其上下文和生存期。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-134">This environment creates the service and controls its context and lifetime.</span></span>

 [<span data-ttu-id="1bbc9-135">如何：创建客户端</span><span class="sxs-lookup"><span data-stu-id="1bbc9-135">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)

 <span data-ttu-id="1bbc9-136">介绍如何检索用于创建 WCF 客户端代理从 WCF 服务的元数据。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-136">Describes how to retrieve metadata used to create a WCF client proxy from a WCF service.</span></span> <span data-ttu-id="1bbc9-137">此过程使用 Visual Studio 中的添加服务引用功能。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-137">This process uses the Add Service Reference functionality within Visual Studio.</span></span>

 [<span data-ttu-id="1bbc9-138">如何：配置客户端</span><span class="sxs-lookup"><span data-stu-id="1bbc9-138">How to: Configure a Client</span></span>](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)

 <span data-ttu-id="1bbc9-139">描述如何配置 WCF 客户端。配置客户端需要指定客户端用于访问服务的终结点。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-139">Describes how to configure a WCF client Configuring the client requires specifying the endpoint that the client uses to access the service.</span></span>

 [<span data-ttu-id="1bbc9-140">如何：使用客户端</span><span class="sxs-lookup"><span data-stu-id="1bbc9-140">How to: Use a Client</span></span>](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)

 <span data-ttu-id="1bbc9-141">介绍如何使用 WCF 客户端代理来调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="1bbc9-141">Describes how to use the WCF client proxy to invoke service operations.</span></span>

## <a name="reference"></a><span data-ttu-id="1bbc9-142">参考</span><span class="sxs-lookup"><span data-stu-id="1bbc9-142">Reference</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="related-sections"></a><span data-ttu-id="1bbc9-143">相关章节</span><span class="sxs-lookup"><span data-stu-id="1bbc9-143">Related Sections</span></span>

- [<span data-ttu-id="1bbc9-144">Windows Communication Foundation 示例</span><span class="sxs-lookup"><span data-stu-id="1bbc9-144">Windows Communication Foundation Samples</span></span>](https://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)
- [<span data-ttu-id="1bbc9-145">基本编程生命周期</span><span class="sxs-lookup"><span data-stu-id="1bbc9-145">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)

## <a name="see-also"></a><span data-ttu-id="1bbc9-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="1bbc9-146">See also</span></span>

- [<span data-ttu-id="1bbc9-147">概念性概述</span><span class="sxs-lookup"><span data-stu-id="1bbc9-147">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)
- [<span data-ttu-id="1bbc9-148">文档使用指南</span><span class="sxs-lookup"><span data-stu-id="1bbc9-148">Guide to the Documentation</span></span>](../../../docs/framework/wcf/guide-to-the-documentation.md)
- [<span data-ttu-id="1bbc9-149">什么是 Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="1bbc9-149">What Is Windows Communication Foundation</span></span>](../../../docs/framework/wcf/whats-wcf.md)
- [<span data-ttu-id="1bbc9-150">WCF 功能详细信息</span><span class="sxs-lookup"><span data-stu-id="1bbc9-150">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)
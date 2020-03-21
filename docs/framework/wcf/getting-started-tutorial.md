---
title: 教程：开始使用 Windows 通信基础应用程序
description: 这些教程提供了创建 WCF 应用程序的介绍。
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: df73f953372202796cebce9d3e3f28bd617c67ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184113"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a><span data-ttu-id="c1de9-103">教程：开始使用 Windows 通信基础应用程序</span><span class="sxs-lookup"><span data-stu-id="c1de9-103">Tutorial: Get started with Windows Communication Foundation applications</span></span>
<span data-ttu-id="c1de9-104">以下一系列教程将向您介绍 Windows 通信基础 （WCF） 编程体验。</span><span class="sxs-lookup"><span data-stu-id="c1de9-104">The following series of tutorials introduce you to the Windows Communication Foundation (WCF) programming experience.</span></span> <span data-ttu-id="c1de9-105">按顺序完成这些教程将为您提供对创建 WCF 应用程序所需的步骤的介绍性理解。</span><span class="sxs-lookup"><span data-stu-id="c1de9-105">Working through these tutorials in order will give you an introductory understanding of the steps required to create WCF applications.</span></span> <span data-ttu-id="c1de9-106">完成后，您将有一个正在运行的 WCF 服务和一个 WCF 客户端调用该服务。</span><span class="sxs-lookup"><span data-stu-id="c1de9-106">After you finish, you'll have a running WCF service and a WCF client that calls the service.</span></span>

<span data-ttu-id="c1de9-107">本教程假定您正在使用 Visual Studio 作为开发环境。</span><span class="sxs-lookup"><span data-stu-id="c1de9-107">The tutorial assumes you're using Visual Studio as the development environment.</span></span> <span data-ttu-id="c1de9-108">如果您正在使用其他开发环境，请忽略特定于 Visual Studio 的说明。</span><span class="sxs-lookup"><span data-stu-id="c1de9-108">If you're using another development environment, ignore the Visual Studio-specific instructions.</span></span>

<span data-ttu-id="c1de9-109">有关可以下载和运行的示例 WCF 应用程序，请参阅[Windows 通信基础示例](samples/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c1de9-109">For sample WCF applications that you can download and run, see [Windows Communication Foundation samples](samples/index.md).</span></span> <span data-ttu-id="c1de9-110">有关示例的介绍，请参阅[入门示例](samples/getting-started-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="c1de9-110">For an introduction to the samples, see [Getting started sample](samples/getting-started-sample.md).</span></span>

<span data-ttu-id="c1de9-111">有关创建服务和客户端的深入信息，请参阅[基本 WCF 编程](basic-wcf-programming.md)。</span><span class="sxs-lookup"><span data-stu-id="c1de9-111">For more in-depth information about creating services and clients, see [Basic WCF programming](basic-wcf-programming.md).</span></span>

## <a name="wcf-tutorials"></a><span data-ttu-id="c1de9-112">WCF 教程</span><span class="sxs-lookup"><span data-stu-id="c1de9-112">WCF tutorials</span></span>

<span data-ttu-id="c1de9-113">前三个教程介绍如何定义 WCF 服务协定、如何实现它以及如何托管它。</span><span class="sxs-lookup"><span data-stu-id="c1de9-113">The first three tutorials describe how to define a WCF service contract, how to implement it, and how to host it.</span></span> <span data-ttu-id="c1de9-114">您创建的服务在控制台应用程序中自托管。</span><span class="sxs-lookup"><span data-stu-id="c1de9-114">The service that you create is self-hosted within a console application.</span></span> <span data-ttu-id="c1de9-115">您还可以在 Microsoft 互联网信息服务 （IIS） 下托管服务。</span><span class="sxs-lookup"><span data-stu-id="c1de9-115">You can also host services under Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="c1de9-116">有关详细信息，请参阅[如何：在 IIS 中托管 WCF 服务](feature-details/how-to-host-a-wcf-service-in-iis.md)。</span><span class="sxs-lookup"><span data-stu-id="c1de9-116">For more information, see [How to: Host a WCF Service in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span> <span data-ttu-id="c1de9-117">尽管在本教程中使用代码配置服务，但您也可以[在配置文件中配置服务](configuring-services-using-configuration-files.md)。</span><span class="sxs-lookup"><span data-stu-id="c1de9-117">Although you use code to configure the service in the tutorial, you can also [configure services within a configuration file](configuring-services-using-configuration-files.md).</span></span>

- [<span data-ttu-id="c1de9-118">教程：定义服务协定</span><span class="sxs-lookup"><span data-stu-id="c1de9-118">Tutorial: Define a service contract</span></span>](how-to-define-a-wcf-service-contract.md)

    <span data-ttu-id="c1de9-119">使用用户定义的界面创建 WCF 协定。</span><span class="sxs-lookup"><span data-stu-id="c1de9-119">You create a WCF contract with a user-defined interface.</span></span> <span data-ttu-id="c1de9-120">此协定定义服务公开的功能。</span><span class="sxs-lookup"><span data-stu-id="c1de9-120">This contract defines the functionality that the service exposes.</span></span>

- [<span data-ttu-id="c1de9-121">教程：实现服务合同</span><span class="sxs-lookup"><span data-stu-id="c1de9-121">Tutorial: Implement a service contract</span></span>](how-to-implement-a-wcf-contract.md)

    <span data-ttu-id="c1de9-122">定义协定后，必须使用服务类实现它。</span><span class="sxs-lookup"><span data-stu-id="c1de9-122">After you define a contract, you must implement it with a service class.</span></span>

- [<span data-ttu-id="c1de9-123">教程：托管并运行基本服务</span><span class="sxs-lookup"><span data-stu-id="c1de9-123">Tutorial: Host and run a basic service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)

    <span data-ttu-id="c1de9-124">配置服务的终结点，并在控制台应用程序中托管服务。</span><span class="sxs-lookup"><span data-stu-id="c1de9-124">Configure an endpoint for the service and host the service in a console application.</span></span> <span data-ttu-id="c1de9-125">要使服务处于活动状态，必须配置该服务并在运行时环境中托管它。</span><span class="sxs-lookup"><span data-stu-id="c1de9-125">For a service to become active, you must configure it and host it within a run-time environment.</span></span> <span data-ttu-id="c1de9-126">此运行时环境创建服务并控制其上下文和生存期。</span><span class="sxs-lookup"><span data-stu-id="c1de9-126">This run-time environment creates the service and controls its context and lifetime.</span></span>

<span data-ttu-id="c1de9-127">接下来的两个教程介绍如何创建、配置和使用客户端应用程序来调用服务公开的操作。</span><span class="sxs-lookup"><span data-stu-id="c1de9-127">The next two tutorials describe how to create, configure, and use a client application to call the operations the service exposes.</span></span> <span data-ttu-id="c1de9-128">服务发布定义客户端应用程序与服务进行通信所需信息的元数据。</span><span class="sxs-lookup"><span data-stu-id="c1de9-128">Services publish metadata that define the information a client application needs to communicate with the service.</span></span> <span data-ttu-id="c1de9-129">Visual Studio 自动访问此元数据的过程，并用它来构造服务的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="c1de9-129">Visual Studio automates the process of accessing this metadata and uses it to construct the client application for the service.</span></span> <span data-ttu-id="c1de9-130">如果您决定不使用 Visual Studio，则可以使用[服务模型元数据实用程序工具 （*Svcutil.exe*）。](servicemodel-metadata-utility-tool-svcutil-exe.md)</span><span class="sxs-lookup"><span data-stu-id="c1de9-130">If you decide not to use Visual Studio, you can use the [ServiceModel Metadata Utility tool (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) instead.</span></span>

- [<span data-ttu-id="c1de9-131">教程：创建客户端</span><span class="sxs-lookup"><span data-stu-id="c1de9-131">Tutorial: Create a client</span></span>](how-to-create-a-wcf-client.md)

    <span data-ttu-id="c1de9-132">检索元数据以从 WCF 服务创建 WCF 客户端代理。</span><span class="sxs-lookup"><span data-stu-id="c1de9-132">Retrieve metadata for creating a WCF client proxy from a WCF service.</span></span> <span data-ttu-id="c1de9-133">通过使用 Visual Studio 添加服务引用来检索元数据，或者可以使用服务模型元数据实用程序工具。</span><span class="sxs-lookup"><span data-stu-id="c1de9-133">You retrieve metadata by using Visual Studio to add a service reference or you can use the ServiceModel Metadata Utility tool.</span></span> <span data-ttu-id="c1de9-134">指定客户端用于访问服务的终结点。</span><span class="sxs-lookup"><span data-stu-id="c1de9-134">You specify the endpoint that the client uses to access the service.</span></span>

- [<span data-ttu-id="c1de9-135">教程：使用客户端</span><span class="sxs-lookup"><span data-stu-id="c1de9-135">Tutorial: Use a client</span></span>](how-to-use-a-wcf-client.md)

    <span data-ttu-id="c1de9-136">使用 WCF 客户端代理调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="c1de9-136">Use the WCF client proxy to call the service operations.</span></span>

## <a name="reference"></a><span data-ttu-id="c1de9-137">参考</span><span class="sxs-lookup"><span data-stu-id="c1de9-137">Reference</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a><span data-ttu-id="c1de9-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1de9-138">See also</span></span>

- [<span data-ttu-id="c1de9-139">概念概述</span><span class="sxs-lookup"><span data-stu-id="c1de9-139">Conceptual overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="c1de9-140">文档指南</span><span class="sxs-lookup"><span data-stu-id="c1de9-140">Guide to the documentation</span></span>](guide-to-the-documentation.md)
- [<span data-ttu-id="c1de9-141">什么是 Windows 通信基础</span><span class="sxs-lookup"><span data-stu-id="c1de9-141">What is Windows Communication Foundation</span></span>](whats-wcf.md)
- [<span data-ttu-id="c1de9-142">WCF 功能详细信息</span><span class="sxs-lookup"><span data-stu-id="c1de9-142">WCF feature details</span></span>](feature-details/index.md)
- [<span data-ttu-id="c1de9-143">基本编程生命周期</span><span class="sxs-lookup"><span data-stu-id="c1de9-143">Basic programming lifecycle</span></span>](basic-programming-lifecycle.md)
- [<span data-ttu-id="c1de9-144">构建客户端</span><span class="sxs-lookup"><span data-stu-id="c1de9-144">Building clients</span></span>](building-clients.md)
- [<span data-ttu-id="c1de9-145">基本 WCF 编程</span><span class="sxs-lookup"><span data-stu-id="c1de9-145">Basic WCF programming</span></span>](basic-wcf-programming.md)
- [<span data-ttu-id="c1de9-146">如何：创建双工协定</span><span class="sxs-lookup"><span data-stu-id="c1de9-146">How to: Create a duplex contract</span></span>](feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="c1de9-147">如何：使用双工协定访问服务</span><span class="sxs-lookup"><span data-stu-id="c1de9-147">How to: Access services with a duplex contract</span></span>](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="c1de9-148">服务模型元数据实用程序工具 （Svcutil.exe）</span><span class="sxs-lookup"><span data-stu-id="c1de9-148">ServiceModel Metadata Utility tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="c1de9-149">如何：使用 Svcutil.exe 下载元数据文档</span><span class="sxs-lookup"><span data-stu-id="c1de9-149">How to: Use Svcutil.exe to download metadata documents</span></span>](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [<span data-ttu-id="c1de9-150">如何：使用配置文件发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="c1de9-150">How to: Publish metadata for a service using a configuration file</span></span>](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="c1de9-151">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="c1de9-151">Using bindings to configure services and clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c1de9-152">入门示例</span><span class="sxs-lookup"><span data-stu-id="c1de9-152">Getting started sample</span></span>](samples/getting-started-sample.md)
- [<span data-ttu-id="c1de9-153">Windows 通信基础示例</span><span class="sxs-lookup"><span data-stu-id="c1de9-153">Windows Communication Foundation samples</span></span>](samples/index.md)
- [<span data-ttu-id="c1de9-154">自承载</span><span class="sxs-lookup"><span data-stu-id="c1de9-154">Self-Host</span></span>](samples/self-host.md)

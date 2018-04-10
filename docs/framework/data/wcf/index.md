---
title: WCF 数据服务 4.5
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b5b27a51dcec17f72b86e77a7ee2ab773aec1dc3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="0f3e0-102">WCF 数据服务 4.5</span><span class="sxs-lookup"><span data-stu-id="0f3e0-102">WCF Data Services 4.5</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="0f3e0-103">（以前称为“ADO.NET Data Services”）是 .NET Framework 的一个组件。可以使用此组件创建一些服务，利用 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 借助 [representational state transfer (REST)](http://go.microsoft.com/fwlink/?LinkId=113919)（表述性状态转移 (REST)）语义通过 Web 或 Intranet 公开和使用数据。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-103"> (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](http://go.microsoft.com/fwlink/?LinkId=113919).</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="0f3e0-104"> 将数据公开为可通过 URI 进行寻址的资源。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-104"> exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="0f3e0-105">通过使用标准 HTTP 谓词 GET、PUT、POST 和 DELETE 访问和更改数据。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]<span data-ttu-id="0f3e0-106"> 使用[实体数据模型](../../../../docs/framework/data/adonet/entity-data-model.md)的实体关系约定将资源公开为通过关联相关的实体集。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-106"> uses the entity-relationship conventions of the [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="0f3e0-107">使用 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 协议对资源进行寻址和更新。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-107"> uses the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol for addressing and updating resources.</span></span> <span data-ttu-id="0f3e0-108">通过这种方式，您可以从支持 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 的任何客户端访问这些服务。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-108">In this way, you can access these services from any client that supports [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span></span> <span data-ttu-id="0f3e0-109">通过 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 可以使用以下非常常见的传输格式请求数据以及将数据写入资源，即：Atom 与 JavaScript 对象表示法 (JSON)；前者是将数据作为 XML 进行交换和更新的一组标准，后者是在 AJAX 应用程序中广泛使用的基于文本的数据交换格式。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-109">[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX application.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="0f3e0-110">可以将源自各种源的数据作为 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 源公开。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-110"> can expose data that originates from various sources as [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span> <span data-ttu-id="0f3e0-111">借助于 Visual Studio 工具，可以更轻松地使用 ADO.NET 实体框架数据模型来创建基于 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 的服务。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-111">Visual Studio tools make it easier for you to create an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="0f3e0-112">也可以基于公共语言运行时 (CLR) 类，甚至基于后期绑定的或未类型化的数据，创建 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 源。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-112">You can also create [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="0f3e0-113"> 还包括一组客户端库，一个库用于常规 .NET Framework 客户端应用程序，另一个库专用于基于 Silverlight 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-113"> also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="0f3e0-114">在从 .NET Framework 和 Silverlight 之类的环境访问 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 源时，这些客户端库提供了基于对象的编程模型。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-114">These client libraries provide an object-based programming model when you access an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed from environments such as the .NET Framework and Silverlight.</span></span>  
  
## <a name="where-should-i-start"></a><span data-ttu-id="0f3e0-115">从何处开始？</span><span class="sxs-lookup"><span data-stu-id="0f3e0-115">Where Should I Start?</span></span>  
 <span data-ttu-id="0f3e0-116">根据您的兴趣，可考虑从下列主题之一开始使用 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-116">Depending on your interests, consider getting started with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] in one of the following topics.</span></span>  
  
 <span data-ttu-id="0f3e0-117">我希望直接开始使用…</span><span class="sxs-lookup"><span data-stu-id="0f3e0-117">I want to jump right in…</span></span>  
 -   [<span data-ttu-id="0f3e0-118">快速入门</span><span class="sxs-lookup"><span data-stu-id="0f3e0-118">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [<span data-ttu-id="0f3e0-119">入门</span><span class="sxs-lookup"><span data-stu-id="0f3e0-119">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
  
-   [<span data-ttu-id="0f3e0-120">Silverlight 快速入门</span><span class="sxs-lookup"><span data-stu-id="0f3e0-120">Silverlight Quickstart</span></span>](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [<span data-ttu-id="0f3e0-121">Windows Phone 开发 Silverlight 快速入门</span><span class="sxs-lookup"><span data-stu-id="0f3e0-121">Silverlight Quickstart for Windows Phone Development</span></span>](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
 <span data-ttu-id="0f3e0-122">我只想查看一些代码……</span><span class="sxs-lookup"><span data-stu-id="0f3e0-122">Just show me some code…</span></span>  
 -   [<span data-ttu-id="0f3e0-123">快速入门</span><span class="sxs-lookup"><span data-stu-id="0f3e0-123">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [<span data-ttu-id="0f3e0-124">如何：执行数据服务查询</span><span class="sxs-lookup"><span data-stu-id="0f3e0-124">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
-   [<span data-ttu-id="0f3e0-125">如何：将数据绑定到 Windows Presentation Foundation 元素</span><span class="sxs-lookup"><span data-stu-id="0f3e0-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)  
  
 <span data-ttu-id="0f3e0-126">我希望更多地了解 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]…</span><span class="sxs-lookup"><span data-stu-id="0f3e0-126">I want to know more about [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]…</span></span>  
 -   [<span data-ttu-id="0f3e0-127">白皮书：OData 简介</span><span class="sxs-lookup"><span data-stu-id="0f3e0-127">Whitepaper: Introducing OData</span></span>](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [<span data-ttu-id="0f3e0-128">Open Data Protocol 网站</span><span class="sxs-lookup"><span data-stu-id="0f3e0-128">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
-   [<span data-ttu-id="0f3e0-129">OData：SDK</span><span class="sxs-lookup"><span data-stu-id="0f3e0-129">OData: SDK</span></span>](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
-   [<span data-ttu-id="0f3e0-130">OData：常见问题</span><span class="sxs-lookup"><span data-stu-id="0f3e0-130">OData: Frequently Asked Questions</span></span>](http://go.microsoft.com/fwlink/?LinkId=185867)  
  
 <span data-ttu-id="0f3e0-131">我想要观看一些视频…</span><span class="sxs-lookup"><span data-stu-id="0f3e0-131">I want to watch some videos…</span></span>  
 -   [<span data-ttu-id="0f3e0-132">WCF Data Services 初学者指南</span><span class="sxs-lookup"><span data-stu-id="0f3e0-132">Beginner's Guide to WCF Data Services</span></span>](http://go.microsoft.com/fwlink/?LinkId=220864)  
  
-   [<span data-ttu-id="0f3e0-133">WCF Data Services 开发人员视频</span><span class="sxs-lookup"><span data-stu-id="0f3e0-133">WCF Data Services Developer Videos</span></span>](http://go.microsoft.com/fwlink/?LinkId=220861)  
  
-   [<span data-ttu-id="0f3e0-134">OData：开发人员网站</span><span class="sxs-lookup"><span data-stu-id="0f3e0-134">OData: Developers Web site</span></span>](http://go.microsoft.com/fwlink/?LinkId=185866)  
  
 <span data-ttu-id="0f3e0-135">我想要查看端到端示例</span><span class="sxs-lookup"><span data-stu-id="0f3e0-135">I want to see end-to-end samples</span></span>  
 -   [<span data-ttu-id="0f3e0-136">MSDN 示例库上的 WCF Data Services 文档示例</span><span class="sxs-lookup"><span data-stu-id="0f3e0-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](http://go.microsoft.com/fwlink/?LinkID=220865)  
  
-   [<span data-ttu-id="0f3e0-137">MSDN 示例库上的其他 WCF Data Services 示例</span><span class="sxs-lookup"><span data-stu-id="0f3e0-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](http://go.microsoft.com/fwlink/?LinkId=220866)  
  
-   [<span data-ttu-id="0f3e0-138">OData：SDK</span><span class="sxs-lookup"><span data-stu-id="0f3e0-138">OData: SDK</span></span>](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
 <span data-ttu-id="0f3e0-139">它如何与 Visual Studio 集成？</span><span class="sxs-lookup"><span data-stu-id="0f3e0-139">How does it integrate with Visual Studio?</span></span>  
 -   [<span data-ttu-id="0f3e0-140">生成数据服务客户端库</span><span class="sxs-lookup"><span data-stu-id="0f3e0-140">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
  
-   [<span data-ttu-id="0f3e0-141">创建数据服务</span><span class="sxs-lookup"><span data-stu-id="0f3e0-141">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
  
-   [<span data-ttu-id="0f3e0-142">实体框架提供程序</span><span class="sxs-lookup"><span data-stu-id="0f3e0-142">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
  
 <span data-ttu-id="0f3e0-143">我可以对它执行何种操作？</span><span class="sxs-lookup"><span data-stu-id="0f3e0-143">What can I do with it?</span></span>  
 -   [<span data-ttu-id="0f3e0-144">概述</span><span class="sxs-lookup"><span data-stu-id="0f3e0-144">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
  
-   [<span data-ttu-id="0f3e0-145">白皮书：OData 简介</span><span class="sxs-lookup"><span data-stu-id="0f3e0-145">Whitepaper: Introducing OData</span></span>](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [<span data-ttu-id="0f3e0-146">应用程序方案</span><span class="sxs-lookup"><span data-stu-id="0f3e0-146">Application Scenarios</span></span>](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)  
  
 <span data-ttu-id="0f3e0-147">我想要使用 Silverlight……</span><span class="sxs-lookup"><span data-stu-id="0f3e0-147">I want to use Silverlight…</span></span>  
 -   [<span data-ttu-id="0f3e0-148">Silverlight 快速入门</span><span class="sxs-lookup"><span data-stu-id="0f3e0-148">Silverlight Quickstart</span></span>](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [<span data-ttu-id="0f3e0-149">WCF Data Services (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="0f3e0-149">WCF Data Services (Silverlight)</span></span>](http://go.microsoft.com/fwlink/?LinkID=143149)  
  
-   [<span data-ttu-id="0f3e0-150">Silverlight 入门</span><span class="sxs-lookup"><span data-stu-id="0f3e0-150">Getting Started with Silverlight</span></span>](http://go.microsoft.com/fwlink/?LinkId=148366)  
  
 <span data-ttu-id="0f3e0-151">我要创建 Windows Phone 应用程序…</span><span class="sxs-lookup"><span data-stu-id="0f3e0-151">I want to create a Windows Phone application…</span></span>  
 -   [<span data-ttu-id="0f3e0-152">Windows Phone 开发 Silverlight 快速入门</span><span class="sxs-lookup"><span data-stu-id="0f3e0-152">Silverlight Quickstart for Windows Phone Development</span></span>](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
-   [<span data-ttu-id="0f3e0-153">Windows Phone 的 Open Data Protocol (OData) 客户端</span><span class="sxs-lookup"><span data-stu-id="0f3e0-153">Open Data Protocol (OData) Client for Windows Phone</span></span>](http://go.microsoft.com/fwlink/?LinkID=208749)  
  
 <span data-ttu-id="0f3e0-154">我想要使用 LINQ……</span><span class="sxs-lookup"><span data-stu-id="0f3e0-154">I want to use LINQ…</span></span>  
 -   [<span data-ttu-id="0f3e0-155">查询数据服务</span><span class="sxs-lookup"><span data-stu-id="0f3e0-155">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
  
-   [<span data-ttu-id="0f3e0-156">LINQ 注意事项</span><span class="sxs-lookup"><span data-stu-id="0f3e0-156">LINQ Considerations</span></span>](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)  
  
-   [<span data-ttu-id="0f3e0-157">如何：执行数据服务查询</span><span class="sxs-lookup"><span data-stu-id="0f3e0-157">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
 <span data-ttu-id="0f3e0-158">我还需要了解更多信息…</span><span class="sxs-lookup"><span data-stu-id="0f3e0-158">I still need some more information…</span></span>  
 -   <span data-ttu-id="0f3e0-159">[WCF Data Services Team Blog](http://go.microsoft.com/fwlink/?LinkID=150511)（WCF Data Services 团队博客）</span><span class="sxs-lookup"><span data-stu-id="0f3e0-159">[WCF Data Services Team Blog](http://go.microsoft.com/fwlink/?LinkID=150511)</span></span>  
  
-   [<span data-ttu-id="0f3e0-160">资源</span><span class="sxs-lookup"><span data-stu-id="0f3e0-160">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)  
  
-   [<span data-ttu-id="0f3e0-161">WCF Data Services 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="0f3e0-161">WCF Data Services Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=220868)  
  
-   [<span data-ttu-id="0f3e0-162">Open Data Protocol 网站</span><span class="sxs-lookup"><span data-stu-id="0f3e0-162">Open Data Protocol Web site</span></span>](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
## <a name="in-this-section"></a><span data-ttu-id="0f3e0-163">本节内容</span><span class="sxs-lookup"><span data-stu-id="0f3e0-163">In This Section</span></span>  
 [<span data-ttu-id="0f3e0-164">概述</span><span class="sxs-lookup"><span data-stu-id="0f3e0-164">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
 <span data-ttu-id="0f3e0-165">概述 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 中提供的功能。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-165">Provides an overview of the features and functionality available in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="0f3e0-166">WCF Data Services 新增功能</span><span class="sxs-lookup"><span data-stu-id="0f3e0-166">What's New in WCF Data Services</span></span>](http://msdn.microsoft.com/library/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)  
 <span data-ttu-id="0f3e0-167">说明 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 中的新功能以及对新 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 功能的支持。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-167">Describes new functionality in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] and support for new [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] features.</span></span>  
  
 [<span data-ttu-id="0f3e0-168">入门</span><span class="sxs-lookup"><span data-stu-id="0f3e0-168">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 <span data-ttu-id="0f3e0-169">说明如何使用 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 公开和使用 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 源。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-169">Describes how to expose and consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds by using [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="0f3e0-170">定义 WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="0f3e0-170">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 <span data-ttu-id="0f3e0-171">说明如何创建和配置公开 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 源的数据服务。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-171">Describes how to create and configure a data service that exposes [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span>  
  
 [<span data-ttu-id="0f3e0-172">WCF Data Services 客户端库</span><span class="sxs-lookup"><span data-stu-id="0f3e0-172">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 <span data-ttu-id="0f3e0-173">说明如何使用客户端库从 .NET Framework 客户端应用程序使用 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 源。</span><span class="sxs-lookup"><span data-stu-id="0f3e0-173">Describes how to use client libraries to consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds from a .NET Framework client application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f3e0-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f3e0-174">See Also</span></span>  
 <span data-ttu-id="0f3e0-175">[Representational State Transfer (REST)](http://go.microsoft.com/fwlink/?LinkId=113919)（表述性状态转移 (REST)）</span><span class="sxs-lookup"><span data-stu-id="0f3e0-175">[Representational State Transfer (REST)](http://go.microsoft.com/fwlink/?LinkId=113919)</span></span>

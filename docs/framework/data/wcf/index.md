---
title: WCF 数据服务 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 9ece2fe051855d0fd39556f56a4343ead2c437bc
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43400485"
---
# <a name="wcf-data-services-45"></a><span data-ttu-id="5f357-102">WCF 数据服务 4.5</span><span class="sxs-lookup"><span data-stu-id="5f357-102">WCF Data Services 4.5</span></span>

<span data-ttu-id="5f357-103">WCF 数据服务 （以前称为"ADO.NET 数据服务"） 是一个组件，可创建使用服务的.NET framework[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]公开和使用的语义通过 Web 或 intranet 使用数据[具象状态传输 (REST)](https://go.microsoft.com/fwlink/?LinkId=113919)。</span><span class="sxs-lookup"><span data-stu-id="5f357-103">WCF Data Services (formerly known as "ADO.NET Data Services") is a component of the .NET Framework that enables you to create services that use the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to expose and consume data over the Web or intranet by using the semantics of [representational state transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919).</span></span> <span data-ttu-id="5f357-104">OData 将数据公开为可通过 URI 进行寻址的资源。</span><span class="sxs-lookup"><span data-stu-id="5f357-104">OData exposes data as resources that are addressable by URIs.</span></span> <span data-ttu-id="5f357-105">通过使用标准 HTTP 谓词 GET、PUT、POST 和 DELETE 访问和更改数据。</span><span class="sxs-lookup"><span data-stu-id="5f357-105">Data is accessed and changed by using standard HTTP verbs of GET, PUT, POST, and DELETE.</span></span> <span data-ttu-id="5f357-106">OData 使用的实体关系约定[实体数据模型](../../../../docs/framework/data/adonet/entity-data-model.md)将资源公开为通过关联相关的实体集。</span><span class="sxs-lookup"><span data-stu-id="5f357-106">OData uses the entity-relationship conventions of the [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) to expose resources as sets of entities that are related by associations.</span></span>

<span data-ttu-id="5f357-107">WCF 数据服务使用 OData 协议进行寻址以及更新资源。</span><span class="sxs-lookup"><span data-stu-id="5f357-107">WCF Data Services uses the OData protocol for addressing and updating resources.</span></span> <span data-ttu-id="5f357-108">这样一来，可以从任何支持 OData 的客户端访问这些服务。</span><span class="sxs-lookup"><span data-stu-id="5f357-108">In this way, you can access these services from any client that supports OData.</span></span> <span data-ttu-id="5f357-109">OData 使您能够请求并通过使用众所周知的传输格式将数据写入资源： Atom、 交换和更新数据作为 XML 和 JavaScript 对象表示法 (JSON) 标准的一组在 AJAX 中广泛使用基于文本的数据交换格式应用程序。</span><span class="sxs-lookup"><span data-stu-id="5f357-109">OData enables you to request and write data to resources by using well-known transfer formats: Atom, a set of standards for exchanging and updating data as XML, and JavaScript Object Notation (JSON), a text-based data exchange format used extensively in AJAX application.</span></span>

<span data-ttu-id="5f357-110">WCF 数据服务可以公开源自各种源作为 OData 源的数据。</span><span class="sxs-lookup"><span data-stu-id="5f357-110">WCF Data Services can expose data that originates from various sources as OData feeds.</span></span> <span data-ttu-id="5f357-111">Visual Studio 工具使你更轻松地使用 ADO.NET 实体框架数据模型创建的基于 OData 的服务。</span><span class="sxs-lookup"><span data-stu-id="5f357-111">Visual Studio tools make it easier for you to create an OData-based service by using an ADO.NET Entity Framework data model.</span></span> <span data-ttu-id="5f357-112">此外可以创建基于公共语言运行时 (CLR) 类，甚至基于后期绑定或非类型化数据的 OData 源。</span><span class="sxs-lookup"><span data-stu-id="5f357-112">You can also create OData feeds based on common language runtime (CLR) classes and even late-bound or un-typed data.</span></span>

<span data-ttu-id="5f357-113">WCF Data Services 还包括一组客户端库，一个用于常规.NET Framework 客户端应用程序，另一个专用于基于 Silverlight 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5f357-113">WCF Data Services also includes a set of client libraries, one for general .NET Framework client applications and another specifically for Silverlight-based applications.</span></span> <span data-ttu-id="5f357-114">访问 OData 源从.NET Framework 和 Silverlight 之类的环境时，这些客户端库提供了基于对象的编程模型。</span><span class="sxs-lookup"><span data-stu-id="5f357-114">These client libraries provide an object-based programming model when you access an OData feed from environments such as the .NET Framework and Silverlight.</span></span>

## <a name="where-should-i-start"></a><span data-ttu-id="5f357-115">从何处开始？</span><span class="sxs-lookup"><span data-stu-id="5f357-115">Where Should I Start?</span></span>

<span data-ttu-id="5f357-116">具体取决于您的兴趣，请考虑以下主题之一中的 WCF Data Services 入门。</span><span class="sxs-lookup"><span data-stu-id="5f357-116">Depending on your interests, consider getting started with WCF Data Services in one of the following topics.</span></span>

<span data-ttu-id="5f357-117">我希望直接开始使用...</span><span class="sxs-lookup"><span data-stu-id="5f357-117">I want to jump right in...</span></span>

-   [<span data-ttu-id="5f357-118">快速入门</span><span class="sxs-lookup"><span data-stu-id="5f357-118">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

-   [<span data-ttu-id="5f357-119">入门</span><span class="sxs-lookup"><span data-stu-id="5f357-119">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

-   [<span data-ttu-id="5f357-120">Silverlight 快速入门</span><span class="sxs-lookup"><span data-stu-id="5f357-120">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

-   [<span data-ttu-id="5f357-121">Windows Phone 开发 Silverlight 快速入门</span><span class="sxs-lookup"><span data-stu-id="5f357-121">Silverlight Quickstart for Windows Phone Development</span></span>](https://go.microsoft.com/fwlink/?LinkID=214535)

<span data-ttu-id="5f357-122">只需向我显示一些代码...</span><span class="sxs-lookup"><span data-stu-id="5f357-122">Just show me some code...</span></span>

-   [<span data-ttu-id="5f357-123">快速入门</span><span class="sxs-lookup"><span data-stu-id="5f357-123">Quickstart</span></span>](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

-   [<span data-ttu-id="5f357-124">如何：执行数据服务查询</span><span class="sxs-lookup"><span data-stu-id="5f357-124">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

-   [<span data-ttu-id="5f357-125">如何：将数据绑定到 Windows Presentation Foundation 元素</span><span class="sxs-lookup"><span data-stu-id="5f357-125">How to: Bind Data to Windows Presentation Foundation Elements</span></span>](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)

<span data-ttu-id="5f357-126">我想要了解有关 OData 的详细信息...</span><span class="sxs-lookup"><span data-stu-id="5f357-126">I want to know more about OData...</span></span>

 -   [<span data-ttu-id="5f357-127">白皮书：OData 简介</span><span class="sxs-lookup"><span data-stu-id="5f357-127">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

-   [<span data-ttu-id="5f357-128">Open Data Protocol 网站</span><span class="sxs-lookup"><span data-stu-id="5f357-128">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

-   [<span data-ttu-id="5f357-129">OData：SDK</span><span class="sxs-lookup"><span data-stu-id="5f357-129">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

-   [<span data-ttu-id="5f357-130">OData：常见问题</span><span class="sxs-lookup"><span data-stu-id="5f357-130">OData: Frequently Asked Questions</span></span>](https://go.microsoft.com/fwlink/?LinkId=185867)

<span data-ttu-id="5f357-131">我想要观看一些视频...</span><span class="sxs-lookup"><span data-stu-id="5f357-131">I want to watch some videos...</span></span>

-   [<span data-ttu-id="5f357-132">WCF Data Services 初学者指南</span><span class="sxs-lookup"><span data-stu-id="5f357-132">Beginner's Guide to WCF Data Services</span></span>](https://go.microsoft.com/fwlink/?LinkId=220864)

-   [<span data-ttu-id="5f357-133">WCF Data Services 开发人员视频</span><span class="sxs-lookup"><span data-stu-id="5f357-133">WCF Data Services Developer Videos</span></span>](https://go.microsoft.com/fwlink/?LinkId=220861)

-   [<span data-ttu-id="5f357-134">OData：开发人员网站</span><span class="sxs-lookup"><span data-stu-id="5f357-134">OData: Developers Web site</span></span>](https://go.microsoft.com/fwlink/?LinkId=185866)

<span data-ttu-id="5f357-135">我想要查看端到端示例...</span><span class="sxs-lookup"><span data-stu-id="5f357-135">I want to see end-to-end samples...</span></span>

-   [<span data-ttu-id="5f357-136">MSDN 示例库上的 WCF Data Services 文档示例</span><span class="sxs-lookup"><span data-stu-id="5f357-136">WCF Data Services Documentation Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkID=220865)

-   [<span data-ttu-id="5f357-137">MSDN 示例库上的其他 WCF Data Services 示例</span><span class="sxs-lookup"><span data-stu-id="5f357-137">Other WCF Data Services Samples on MSDN Samples Gallery</span></span>](https://go.microsoft.com/fwlink/?LinkId=220866)

-   [<span data-ttu-id="5f357-138">OData：SDK</span><span class="sxs-lookup"><span data-stu-id="5f357-138">OData: SDK</span></span>](https://go.microsoft.com/fwlink/?LinkID=185248)

<span data-ttu-id="5f357-139">它如何与 Visual Studio 集成？</span><span class="sxs-lookup"><span data-stu-id="5f357-139">How does it integrate with Visual Studio?</span></span>

-   [<span data-ttu-id="5f357-140">生成数据服务客户端库</span><span class="sxs-lookup"><span data-stu-id="5f357-140">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)

-   [<span data-ttu-id="5f357-141">创建数据服务</span><span class="sxs-lookup"><span data-stu-id="5f357-141">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

-   [<span data-ttu-id="5f357-142">实体框架提供程序</span><span class="sxs-lookup"><span data-stu-id="5f357-142">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)

<span data-ttu-id="5f357-143">我可以对它执行何种操作？</span><span class="sxs-lookup"><span data-stu-id="5f357-143">What can I do with it?</span></span>

-   [<span data-ttu-id="5f357-144">概述</span><span class="sxs-lookup"><span data-stu-id="5f357-144">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

-   [<span data-ttu-id="5f357-145">白皮书：OData 简介</span><span class="sxs-lookup"><span data-stu-id="5f357-145">Whitepaper: Introducing OData</span></span>](https://go.microsoft.com/fwlink/?LinkId=220867)

-   [<span data-ttu-id="5f357-146">应用程序方案</span><span class="sxs-lookup"><span data-stu-id="5f357-146">Application Scenarios</span></span>](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)

<span data-ttu-id="5f357-147">我想要使用 Silverlight......</span><span class="sxs-lookup"><span data-stu-id="5f357-147">I want to use Silverlight...</span></span>

-   [<span data-ttu-id="5f357-148">Silverlight 快速入门</span><span class="sxs-lookup"><span data-stu-id="5f357-148">Silverlight Quickstart</span></span>](https://go.microsoft.com/fwlink/?LinkID=192782)

-   [<span data-ttu-id="5f357-149">WCF Data Services (Silverlight)</span><span class="sxs-lookup"><span data-stu-id="5f357-149">WCF Data Services (Silverlight)</span></span>](https://go.microsoft.com/fwlink/?LinkID=143149)

-   [<span data-ttu-id="5f357-150">Silverlight 入门</span><span class="sxs-lookup"><span data-stu-id="5f357-150">Getting Started with Silverlight</span></span>](https://go.microsoft.com/fwlink/?LinkId=148366)

<span data-ttu-id="5f357-151">我想要使用 LINQ......</span><span class="sxs-lookup"><span data-stu-id="5f357-151">I want to use LINQ...</span></span>

-   [<span data-ttu-id="5f357-152">查询数据服务</span><span class="sxs-lookup"><span data-stu-id="5f357-152">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)

-   [<span data-ttu-id="5f357-153">LINQ 注意事项</span><span class="sxs-lookup"><span data-stu-id="5f357-153">LINQ Considerations</span></span>](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)

-   [<span data-ttu-id="5f357-154">如何：执行数据服务查询</span><span class="sxs-lookup"><span data-stu-id="5f357-154">How to: Execute Data Service Queries</span></span>](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

<span data-ttu-id="5f357-155">我仍需要了解一些更多信息...</span><span class="sxs-lookup"><span data-stu-id="5f357-155">I still need some more information...</span></span>

-   <span data-ttu-id="5f357-156">[WCF Data Services Team Blog](https://go.microsoft.com/fwlink/?LinkID=150511)（WCF Data Services 团队博客）</span><span class="sxs-lookup"><span data-stu-id="5f357-156">[WCF Data Services Team Blog](https://go.microsoft.com/fwlink/?LinkID=150511)</span></span>

-   [<span data-ttu-id="5f357-157">资源</span><span class="sxs-lookup"><span data-stu-id="5f357-157">Resources</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)

-   [<span data-ttu-id="5f357-158">WCF Data Services 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="5f357-158">WCF Data Services Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=220868)

-   [<span data-ttu-id="5f357-159">Open Data Protocol 网站</span><span class="sxs-lookup"><span data-stu-id="5f357-159">Open Data Protocol Web site</span></span>](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a><span data-ttu-id="5f357-160">本节内容</span><span class="sxs-lookup"><span data-stu-id="5f357-160">In This Section</span></span>

 [<span data-ttu-id="5f357-161">概述</span><span class="sxs-lookup"><span data-stu-id="5f357-161">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

 <span data-ttu-id="5f357-162">提供的功能和 WCF 数据服务中提供的功能的概述。</span><span class="sxs-lookup"><span data-stu-id="5f357-162">Provides an overview of the features and functionality available in WCF Data Services.</span></span>

 [<span data-ttu-id="5f357-163">WCF Data Services 新增功能</span><span class="sxs-lookup"><span data-stu-id="5f357-163">What's New in WCF Data Services</span></span>](https://msdn.microsoft.com/library/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)

 <span data-ttu-id="5f357-164">介绍 WCF 数据服务和对新 OData 功能的支持中的新功能。</span><span class="sxs-lookup"><span data-stu-id="5f357-164">Describes new functionality in WCF Data Services and support for new OData features.</span></span>

 [<span data-ttu-id="5f357-165">入门</span><span class="sxs-lookup"><span data-stu-id="5f357-165">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

 <span data-ttu-id="5f357-166">介绍如何公开和使用 WCF 数据服务使用 OData 源。</span><span class="sxs-lookup"><span data-stu-id="5f357-166">Describes how to expose and consume OData feeds by using WCF Data Services.</span></span>

 [<span data-ttu-id="5f357-167">定义 WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="5f357-167">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)

 <span data-ttu-id="5f357-168">介绍如何创建和配置公开 OData 源的数据服务。</span><span class="sxs-lookup"><span data-stu-id="5f357-168">Describes how to create and configure a data service that exposes OData feeds.</span></span>

 [<span data-ttu-id="5f357-169">WCF Data Services 客户端库</span><span class="sxs-lookup"><span data-stu-id="5f357-169">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

 <span data-ttu-id="5f357-170">介绍如何使用客户端库使用 OData 源从.NET Framework 客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="5f357-170">Describes how to use client libraries to consume OData feeds from a .NET Framework client application.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f357-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f357-171">See Also</span></span>

- <span data-ttu-id="5f357-172">[Representational State Transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919)（表述性状态转移 (REST)）</span><span class="sxs-lookup"><span data-stu-id="5f357-172">[Representational State Transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919)</span></span>

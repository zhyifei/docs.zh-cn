---
title: 承载数据服务（WCF 数据服务）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, Windows Communication Foundation
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
ms.openlocfilehash: 89f9cc572a6613efba19a93c8d5e441c46a660ac
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43783893"
---
# <a name="hosting-the-data-service-wcf-data-services"></a><span data-ttu-id="bc297-102">承载数据服务（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="bc297-102">Hosting the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="bc297-103">通过使用 WCF 数据服务，可以创建一项服务，数据公开为[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]源。</span><span class="sxs-lookup"><span data-stu-id="bc297-103">By using WCF Data Services, you can create a service that exposes data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> <span data-ttu-id="bc297-104">此数据服务定义为从 <xref:System.Data.Services.DataService%601> 继承的类。</span><span class="sxs-lookup"><span data-stu-id="bc297-104">This data service is defined as a class that inherits from <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="bc297-105">此类提供处理请求消息、 执行对数据源的更新和生成响应消息，OData 所要求的所需的功能。</span><span class="sxs-lookup"><span data-stu-id="bc297-105">This class provides the functionality required to process request messages, perform updates against the data source, and generate responses messages, as required by OData.</span></span> <span data-ttu-id="bc297-106">但是，数据服务不能将绑定到和网络套接字上侦听传入的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="bc297-106">However, a data service cannot bind to and listen on a network socket for incoming HTTP requests.</span></span> <span data-ttu-id="bc297-107">对于这一必需的功能，数据服务依赖于宿主计算机。</span><span class="sxs-lookup"><span data-stu-id="bc297-107">For this required functionality, the data service relies on a hosting component.</span></span>

 <span data-ttu-id="bc297-108">数据服务宿主可代表数据服务执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="bc297-108">The data service host performs the following tasks on behalf of the data service:</span></span>

-   <span data-ttu-id="bc297-109">侦听请求并将这些请求路由到数据服务。</span><span class="sxs-lookup"><span data-stu-id="bc297-109">Listens for requests and routes these requests to the data service.</span></span>

-   <span data-ttu-id="bc297-110">针对每个请求创建数据服务的一个实例。</span><span class="sxs-lookup"><span data-stu-id="bc297-110">Creates an instance of the data service for each request.</span></span>

-   <span data-ttu-id="bc297-111">请求数据服务处理传入的请求。</span><span class="sxs-lookup"><span data-stu-id="bc297-111">Requests that the data service process the incoming request.</span></span>

-   <span data-ttu-id="bc297-112">代表数据服务发送响应。</span><span class="sxs-lookup"><span data-stu-id="bc297-112">Sends the response on behalf of the data service.</span></span>

 <span data-ttu-id="bc297-113">若要简化承载数据服务，WCF 数据服务设计将使用 Windows Communication Foundation (WCF) 进行集成。</span><span class="sxs-lookup"><span data-stu-id="bc297-113">To simplify hosting a data service, WCF Data Services is designed to integrate with Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="bc297-114">数据服务提供一个默认 WCF 实现，可作为数据服务主机中[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="bc297-114">The data service provides a default WCF implementation that serves as the data service host in an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="bc297-115">因此，您可以通过以下方式之一承载数据服务：</span><span class="sxs-lookup"><span data-stu-id="bc297-115">Therefore, you can host a data service in one of the following ways:</span></span>

-   <span data-ttu-id="bc297-116">在 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="bc297-116">In an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application.</span></span>

-   <span data-ttu-id="bc297-117">在支持自承载 WCF 服务的托管应用程序中。</span><span class="sxs-lookup"><span data-stu-id="bc297-117">In a managed application that supports self-hosted WCF services.</span></span>

-   <span data-ttu-id="bc297-118">在其他某些自定义数据服务宿主中。</span><span class="sxs-lookup"><span data-stu-id="bc297-118">In some other custom data service host.</span></span>

## <a name="hosting-a-data-service-in-an-aspnet-application"></a><span data-ttu-id="bc297-119">在 ASP.NET 应用程序中承载数据服务</span><span class="sxs-lookup"><span data-stu-id="bc297-119">Hosting a Data Service in an ASP.NET Application</span></span>

<span data-ttu-id="bc297-120">当你使用**添加新项**对话框在 Visual Studio 2015 在 ASP.NET 应用程序，该工具中定义数据服务在项目中生成两个新文件。</span><span class="sxs-lookup"><span data-stu-id="bc297-120">When you use the **Add New Item** dialog in Visual Studio 2015 to define a data service in an ASP.NET application, the tool generates two new files in the project.</span></span> <span data-ttu-id="bc297-121">第一个文件的扩展名为 `.svc`，并指示 WCF 运行时如何实例化数据服务。</span><span class="sxs-lookup"><span data-stu-id="bc297-121">The first file has a `.svc` extension and instructs the WCF runtime how to instantiate the data service.</span></span> <span data-ttu-id="bc297-122">以下是此文件的创建完成后的 Northwind 示例数据服务示例[快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md):</span><span class="sxs-lookup"><span data-stu-id="bc297-122">The following is an example of this file for the Northwind sample data service created when you complete the [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md):</span></span>

```
<%@ ServiceHost Language="C#"
    Factory="System.Data.Services.DataServiceHostFactory,
            System.Data.Services, Version=4.0.0.0,
            Culture=neutral, PublicKeyToken=b77a5c561934e089"
    Service="NorthwindService.Northwind" %>
```

 <span data-ttu-id="bc297-123">此指令通知应用程序使用 <xref:System.Data.Services.DataServiceHostFactory> 类为命名数据服务类创建服务宿主。</span><span class="sxs-lookup"><span data-stu-id="bc297-123">This directive tells the application to create the service host for the named data service class by using the <xref:System.Data.Services.DataServiceHostFactory> class.</span></span>

 <span data-ttu-id="bc297-124">`.svc` 文件的代码隐藏页包含作为数据服务自身的实现的类，对于 Northwind 示例数据服务，该数据服务的定义如下：</span><span class="sxs-lookup"><span data-stu-id="bc297-124">The code-behind page for the `.svc` file contains the class that is the implementation of the data service itself, which is defined as follows for the Northwind sample data service:</span></span>

 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]

 <span data-ttu-id="bc297-125">由于数据服务的行为与 WCF 服务类似，因此数据服务与 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 集成并遵循 WCF Web 编程模型。</span><span class="sxs-lookup"><span data-stu-id="bc297-125">Because a data service behaves like a WCF service, the data service integrates with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] and follows the WCF Web programming model.</span></span> <span data-ttu-id="bc297-126">有关详细信息，请参阅[WCF 服务和 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)并[WCF Web HTTP 编程模型](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)。</span><span class="sxs-lookup"><span data-stu-id="bc297-126">For more information, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) and [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).</span></span>

## <a name="self-hosted-wcf-services"></a><span data-ttu-id="bc297-127">自承载 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="bc297-127">Self-Hosted WCF Services</span></span>
 <span data-ttu-id="bc297-128">由于它集成了 WCF 实现，WCF 数据服务支持自托管 WCF 服务形式的数据服务。</span><span class="sxs-lookup"><span data-stu-id="bc297-128">Because it incorporates a WCF implementation, WCF Data Services support self-hosting a data service as a WCF service.</span></span> <span data-ttu-id="bc297-129">一个服务可以自承载于任何 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 应用程序中，如控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="bc297-129">A service can be self-hosted in any [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] application, such as a console application.</span></span> <span data-ttu-id="bc297-130">继承自 <xref:System.Data.Services.DataServiceHost> 的 <xref:System.ServiceModel.Web.WebServiceHost> 类用于实例化位于特定地址的数据服务。</span><span class="sxs-lookup"><span data-stu-id="bc297-130">The <xref:System.Data.Services.DataServiceHost> class, which inherits from <xref:System.ServiceModel.Web.WebServiceHost>, is used to instantiate the data service at a specific address.</span></span>

 <span data-ttu-id="bc297-131">自承载功能可用于开发和测试目的，因为通过此功能更易于部署服务和解决服务问题。</span><span class="sxs-lookup"><span data-stu-id="bc297-131">Self-hosting can be used for development and testing because it can make it easier to deploy and troubleshoot the service.</span></span> <span data-ttu-id="bc297-132">但是，这种类型的承载不会提供 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 或 Internet Information Services (IIS) 所提供的高级宿主和管理功能。</span><span class="sxs-lookup"><span data-stu-id="bc297-132">However, this kind of hosting does not provide the advanced hosting and management features provided by [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] or by Internet Information Services (IIS).</span></span> <span data-ttu-id="bc297-133">有关详细信息，请参阅[托管应用程序中承载](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)。</span><span class="sxs-lookup"><span data-stu-id="bc297-133">For more information, see [Hosting in a Managed Application](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>

## <a name="defining-a-custom-data-service-host"></a><span data-ttu-id="bc297-134">定义自定义数据服务主机</span><span class="sxs-lookup"><span data-stu-id="bc297-134">Defining a Custom Data Service Host</span></span>
 <span data-ttu-id="bc297-135">对于 WCF 宿主实现过于受限的情况，您还可以为数据服务定义自定义宿主。</span><span class="sxs-lookup"><span data-stu-id="bc297-135">For cases where the WCF host implementation is too restrictive, you can also define a custom host for a data service.</span></span> <span data-ttu-id="bc297-136">实现 <xref:System.Data.Services.IDataServiceHost> 接口的任何类都可用作数据服务的网络宿主。</span><span class="sxs-lookup"><span data-stu-id="bc297-136">Any class that implements <xref:System.Data.Services.IDataServiceHost> interface can be used as the network host for a data service.</span></span> <span data-ttu-id="bc297-137">自定义宿主必须实现 <xref:System.Data.Services.IDataServiceHost> 接口，并且能够承担数据服务宿主的以下基本责任：</span><span class="sxs-lookup"><span data-stu-id="bc297-137">A custom host must implement the <xref:System.Data.Services.IDataServiceHost> interface and be able to handle the following basic responsibilities of the data service host:</span></span>

-   <span data-ttu-id="bc297-138">向数据服务提供服务根路径。</span><span class="sxs-lookup"><span data-stu-id="bc297-138">Provide the data service with the service root path.</span></span>

-   <span data-ttu-id="bc297-139">处理请求，并向相应的 <xref:System.Data.Services.IDataServiceHost> 成员实现响应标头信息。</span><span class="sxs-lookup"><span data-stu-id="bc297-139">Process request and response headers information to the appropriate <xref:System.Data.Services.IDataServiceHost> member implementation.</span></span>

-   <span data-ttu-id="bc297-140">处理由数据服务引发的异常。</span><span class="sxs-lookup"><span data-stu-id="bc297-140">Handle exceptions raised by the data service.</span></span>

-   <span data-ttu-id="bc297-141">验证查询字符串中的参数。</span><span class="sxs-lookup"><span data-stu-id="bc297-141">Validate parameters in the query string.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc297-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc297-142">See Also</span></span>

- [<span data-ttu-id="bc297-143">定义 WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="bc297-143">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [<span data-ttu-id="bc297-144">将数据公开为服务</span><span class="sxs-lookup"><span data-stu-id="bc297-144">Exposing Your Data as a Service</span></span>](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
- [<span data-ttu-id="bc297-145">配置数据服务</span><span class="sxs-lookup"><span data-stu-id="bc297-145">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)

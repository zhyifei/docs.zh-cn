---
title: 快速入门（WCF 数据服务）
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: f945d33a4fc789b3c73c1c80040fc8527301758b
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121212"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="b2638-102">快速入门（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="b2638-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="b2638-103">此快速入门可帮助您通过一系列支持[入门](getting-started-with-wcf-data-services.md)主题的任务熟悉 WCF 数据服务和开放数据协议 （OData）。</span><span class="sxs-lookup"><span data-stu-id="b2638-103">This quickstart helps you become familiar with WCF Data Services and the Open Data Protocol (OData) through a series of tasks that support the topics in [Getting Started](getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="b2638-104">学习内容</span><span class="sxs-lookup"><span data-stu-id="b2638-104">What you'll learn</span></span>

<span data-ttu-id="b2638-105">此快速入门中的第一个任务演示如何创建数据服务以公开来自北风示例数据库的 OData 源。</span><span class="sxs-lookup"><span data-stu-id="b2638-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="b2638-106">在后面的主题中，您将使用 Web 浏览器访问 OData 源，还可以创建一个 Windows 演示文稿基础 （WPF） 客户端应用程序，该应用程序使用客户端库使用 OData 源。</span><span class="sxs-lookup"><span data-stu-id="b2638-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b2638-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="b2638-107">Prerequisites</span></span>

<span data-ttu-id="b2638-108">要完成此快速入门，请安装以下组件：</span><span class="sxs-lookup"><span data-stu-id="b2638-108">To complete this quickstart, install the following components:</span></span>

- <span data-ttu-id="b2638-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b2638-109">Visual Studio</span></span>

- <span data-ttu-id="b2638-110">SQL 服务器的实例。</span><span class="sxs-lookup"><span data-stu-id="b2638-110">An instance of SQL Server.</span></span> <span data-ttu-id="b2638-111">这包括 SQL Server Express，它包含在 Visual Studio 2015 的默认安装中，或作为 Visual Studio 2017 或更高版本中**的数据存储和处理**工作负载的一部分。</span><span class="sxs-lookup"><span data-stu-id="b2638-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017 or later.</span></span>

- <span data-ttu-id="b2638-112">Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="b2638-112">The Northwind sample database.</span></span> <span data-ttu-id="b2638-113">要安装数据库，请从北风运行 Transact-SQL 脚本[，并为 Microsoft SQL Server 运行 pubs 示例数据库](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)。</span><span class="sxs-lookup"><span data-stu-id="b2638-113">To install the database, run the Transact-SQL script from [Northwind and pubs sample databases for Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="b2638-114">WCF 数据服务快速启动任务</span><span class="sxs-lookup"><span data-stu-id="b2638-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="b2638-115">创建数据服务</span><span class="sxs-lookup"><span data-stu-id="b2638-115">Create the Data Service</span></span>](creating-the-data-service.md)

 <span data-ttu-id="b2638-116">定义 ASP.NET 应用程序，定义数据模型，创建数据服务，并启用对资源的访问。</span><span class="sxs-lookup"><span data-stu-id="b2638-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="b2638-117">从 Web 浏览器访问服务</span><span class="sxs-lookup"><span data-stu-id="b2638-117">Access the Service from a Web Browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="b2638-118">通过 Visual Studio 启动服务，并通过 Web 浏览器向公开的源提交 HTTP GET 请求以访问该服务。</span><span class="sxs-lookup"><span data-stu-id="b2638-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="b2638-119">创建 .NET 框架客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="b2638-119">Create the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="b2638-120">创建 WPF 应用以使用 OData 源、将数据绑定到 Windows 控件、更改绑定控件中的数据，然后将更改发送回数据服务。</span><span class="sxs-lookup"><span data-stu-id="b2638-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="b2638-121">项目文件从已完成版本的快速启动可以从[GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))下载。</span><span class="sxs-lookup"><span data-stu-id="b2638-121">Project files from a completed version of the quickstart can be downloaded from [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b2638-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b2638-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b2638-123">开始快速入门</span><span class="sxs-lookup"><span data-stu-id="b2638-123">Start the quickstart</span></span>](creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="b2638-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2638-124">See also</span></span>

- [<span data-ttu-id="b2638-125">ADO.NET 实体框架</span><span class="sxs-lookup"><span data-stu-id="b2638-125">ADO.NET Entity Framework</span></span>](../adonet/ef/index.md)

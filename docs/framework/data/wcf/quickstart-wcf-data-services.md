---
title: 快速入门（WCF 数据服务）
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: 43cd34ad02f1e2d212ff5e2ff4694591fbed52e5
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900957"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="50a93-102">快速入门（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="50a93-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="50a93-103">本快速入门通过一系列支持[入门](getting-started-with-wcf-data-services.md)中的主题的任务，帮助你熟悉 WCF 数据服务和 Open Data Protocol （OData）。</span><span class="sxs-lookup"><span data-stu-id="50a93-103">This quickstart helps you become familiar with WCF Data Services and the Open Data Protocol (OData) through a series of tasks that support the topics in [Getting Started](getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="50a93-104">学习内容</span><span class="sxs-lookup"><span data-stu-id="50a93-104">What you'll learn</span></span>

<span data-ttu-id="50a93-105">本快速入门中的第一项任务介绍如何创建数据服务以公开 Northwind 示例数据库中的 OData 数据源。</span><span class="sxs-lookup"><span data-stu-id="50a93-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="50a93-106">在后面的主题中，你将使用 Web 浏览器访问 OData 源，并创建使用客户端库使用 OData 源的 Windows Presentation Foundation （WPF）客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="50a93-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="50a93-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="50a93-107">Prerequisites</span></span>

<span data-ttu-id="50a93-108">为了完成本快速入门，必须安装以下组件：</span><span class="sxs-lookup"><span data-stu-id="50a93-108">To complete this quickstart, you must install the following components:</span></span>

- <span data-ttu-id="50a93-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="50a93-109">Visual Studio</span></span>

- <span data-ttu-id="50a93-110">SQL Server 的实例。</span><span class="sxs-lookup"><span data-stu-id="50a93-110">An instance of SQL Server.</span></span> <span data-ttu-id="50a93-111">这包括默认安装的 Visual Studio 2015 或更高版本2017中的**数据存储和处理**工作负荷的一部分 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="50a93-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017 or later.</span></span>

- <span data-ttu-id="50a93-112">Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="50a93-112">The Northwind sample database.</span></span> <span data-ttu-id="50a93-113">若要下载此示例数据库，请访问 [SQL Server 的示例数据库](https://go.microsoft.com/fwlink/?linkid=24758)下载页。</span><span class="sxs-lookup"><span data-stu-id="50a93-113">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="50a93-114">WCF 数据服务快速入门任务</span><span class="sxs-lookup"><span data-stu-id="50a93-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="50a93-115">创建数据服务</span><span class="sxs-lookup"><span data-stu-id="50a93-115">Create the Data Service</span></span>](creating-the-data-service.md)

 <span data-ttu-id="50a93-116">定义 ASP.NET 应用程序，定义数据模型，创建数据服务，并启用对资源的访问。</span><span class="sxs-lookup"><span data-stu-id="50a93-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="50a93-117">从 Web 浏览器访问服务</span><span class="sxs-lookup"><span data-stu-id="50a93-117">Access the Service from a Web Browser</span></span>](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="50a93-118">通过 Visual Studio 启动服务，并通过 Web 浏览器向公开的源提交 HTTP GET 请求以访问该服务。</span><span class="sxs-lookup"><span data-stu-id="50a93-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="50a93-119">创建 .NET Framework 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="50a93-119">Create the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="50a93-120">创建一个使用 OData 源的 WPF 应用程序，将数据绑定到 Windows 控件，在绑定控件中更改数据，然后将更改发送回数据服务。</span><span class="sxs-lookup"><span data-stu-id="50a93-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="50a93-121">可以从[GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))下载完整版本的快速入门中的项目文件。</span><span class="sxs-lookup"><span data-stu-id="50a93-121">Project files from a completed version of the quickstart can be downloaded from [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client)).</span></span>

## <a name="next-steps"></a><span data-ttu-id="50a93-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="50a93-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="50a93-123">启动快速入门</span><span class="sxs-lookup"><span data-stu-id="50a93-123">Start the quickstart</span></span>](creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="50a93-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50a93-124">See also</span></span>

- [<span data-ttu-id="50a93-125">ADO.NET 实体框架</span><span class="sxs-lookup"><span data-stu-id="50a93-125">ADO.NET Entity Framework</span></span>](../adonet/ef/index.md)

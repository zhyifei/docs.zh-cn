---
title: 快速入门（WCF 数据服务）
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
ms.openlocfilehash: 49d11556d3703331b4cdf5bf83a69f6b15bca8ed
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881997"
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="109b9-102">快速入门（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="109b9-102">Quickstart (WCF Data Services)</span></span>

<span data-ttu-id="109b9-103">本快速入门可帮助您熟悉 WCF Data Services 和[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]通过一系列的支持中的主题的任务[Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="109b9-103">This quickstart helps you become familiar with WCF Data Services and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="109b9-104">学习内容</span><span class="sxs-lookup"><span data-stu-id="109b9-104">What you'll learn</span></span>

<span data-ttu-id="109b9-105">本快速入门教程的第一个任务演示如何创建数据服务以公开 OData 源从 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="109b9-105">The first task in this quickstart shows how to create a data service to expose an OData feed from the Northwind sample database.</span></span> <span data-ttu-id="109b9-106">将在后面的主题，访问 OData 源使用 Web 浏览器，并创建 Windows Presentation Foundation (WPF) 客户端应用程序使用 OData 源使用客户端库。</span><span class="sxs-lookup"><span data-stu-id="109b9-106">In later topics, you will access the OData feed by using a Web browser, and also create a Windows Presentation Foundation (WPF) client application that consumes the OData feed by using client libraries.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="109b9-107">系统必备</span><span class="sxs-lookup"><span data-stu-id="109b9-107">Prerequisites</span></span>

<span data-ttu-id="109b9-108">为了完成本快速入门，必须安装以下组件：</span><span class="sxs-lookup"><span data-stu-id="109b9-108">To complete this quickstart, you must install the following components:</span></span>

- <span data-ttu-id="109b9-109">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="109b9-109">Visual Studio</span></span>

- <span data-ttu-id="109b9-110">SQL Server 的实例。</span><span class="sxs-lookup"><span data-stu-id="109b9-110">An instance of SQL Server.</span></span> <span data-ttu-id="109b9-111">这包括 SQL Server Express，它包括在默认安装的 Visual Studio 2015 中，或作为的一部分**数据存储和处理**Visual Studio 2017 中的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="109b9-111">This includes SQL Server Express, which is included in a default installation of Visual Studio 2015, or as part of the **Data storage and processing** workload in Visual Studio 2017.</span></span>

- <span data-ttu-id="109b9-112">Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="109b9-112">The Northwind sample database.</span></span> <span data-ttu-id="109b9-113">若要下载此示例数据库，请访问 [SQL Server 的示例数据库](https://go.microsoft.com/fwlink/?linkid=24758)下载页。</span><span class="sxs-lookup"><span data-stu-id="109b9-113">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="109b9-114">WCF 数据服务快速入门任务</span><span class="sxs-lookup"><span data-stu-id="109b9-114">WCF data services quickstart tasks</span></span>

 [<span data-ttu-id="109b9-115">创建数据服务</span><span class="sxs-lookup"><span data-stu-id="109b9-115">Create the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

 <span data-ttu-id="109b9-116">定义 ASP.NET 应用程序，定义数据模型，创建数据服务，并启用对资源的访问。</span><span class="sxs-lookup"><span data-stu-id="109b9-116">Define the ASP.NET application, define the data model, create the data service, and enable access to resources.</span></span>

 [<span data-ttu-id="109b9-117">从 Web 浏览器访问服务</span><span class="sxs-lookup"><span data-stu-id="109b9-117">Access the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)

 <span data-ttu-id="109b9-118">通过 Visual Studio 启动服务，并通过 Web 浏览器向公开的源提交 HTTP GET 请求以访问该服务。</span><span class="sxs-lookup"><span data-stu-id="109b9-118">Start the service from Visual Studio and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>

 [<span data-ttu-id="109b9-119">创建.NET Framework 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="109b9-119">Create the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

 <span data-ttu-id="109b9-120">创建 WPF 应用程序使用 OData 数据源、 数据绑定到 Windows 控件，更改在绑定控件中的数据，然后发送回数据服务所做的更改。</span><span class="sxs-lookup"><span data-stu-id="109b9-120">Create a WPF app to consume the OData feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>

> [!NOTE]
> <span data-ttu-id="109b9-121">已完成版本的快速入门中的项目文件可从 [WCF 数据服务文档示例](https://go.microsoft.com/fwlink/?LinkId=179994) 网页下载。</span><span class="sxs-lookup"><span data-stu-id="109b9-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](https://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="109b9-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="109b9-122">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="109b9-123">启动快速入门</span><span class="sxs-lookup"><span data-stu-id="109b9-123">Start the quickstart</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)

## <a name="see-also"></a><span data-ttu-id="109b9-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="109b9-124">See also</span></span>

- [<span data-ttu-id="109b9-125">ADO.NET 实体框架</span><span class="sxs-lookup"><span data-stu-id="109b9-125">ADO.NET Entity Framework</span></span>](../../../../docs/framework/data/adonet/ef/index.md)

---
title: "快速入门（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, quick-start example
- WCF Data Services, Entity Data Model (EDM) service
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 08296be1002ee50e18a45c546645f4cc117d6bb5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="quickstart-wcf-data-services"></a><span data-ttu-id="1b9df-102">快速入门（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="1b9df-102">Quickstart (WCF Data Services)</span></span>
<span data-ttu-id="1b9df-103">本快速入门教程可帮助你熟悉[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]和[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]通过一系列支持中的主题的任务[入门](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="1b9df-103">This quickstart helps you become familiar with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] through a series of tasks that support the topics in [Getting Started](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="1b9df-104">学习内容</span><span class="sxs-lookup"><span data-stu-id="1b9df-104">What You Will Learn</span></span>  
 <span data-ttu-id="1b9df-105">本快速入门中的第一项任务介绍如何创建数据服务以公开罗斯文示例数据库中的 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 源。</span><span class="sxs-lookup"><span data-stu-id="1b9df-105">The first task in this quickstart shows how to create a data service to expose an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed from the Northwind sample database.</span></span> <span data-ttu-id="1b9df-106">在后面的主题中，您将使用 Web 浏览器访问 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 源，还将创建一个 [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] 客户端应用程序，它通过客户端库使用 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 源。</span><span class="sxs-lookup"><span data-stu-id="1b9df-106">In later topics, you will access the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by using a Web browser, and also create a [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] client application that consumes the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by using client libraries.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1b9df-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="1b9df-107">Prerequisites</span></span>  
 <span data-ttu-id="1b9df-108">为了完成本快速入门，必须安装以下组件：</span><span class="sxs-lookup"><span data-stu-id="1b9df-108">To complete this quickstart, you must install the following components:</span></span>  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]<span data-ttu-id="1b9df-109">。</span><span class="sxs-lookup"><span data-stu-id="1b9df-109">.</span></span>  
  
-   <span data-ttu-id="1b9df-110">[!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]的一个实例。</span><span class="sxs-lookup"><span data-stu-id="1b9df-110">An instance of [!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1b9df-111">这包含 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]的默认安装中包括的 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="1b9df-111">This includes SQL Server Express, which is included in a default installation of [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
-   <span data-ttu-id="1b9df-112">Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="1b9df-112">The Northwind sample database.</span></span> <span data-ttu-id="1b9df-113">若要下载此示例数据库，请访问 [SQL Server 的示例数据库](http://go.microsoft.com/fwlink/?linkid=24758)下载页。</span><span class="sxs-lookup"><span data-stu-id="1b9df-113">To download this sample database, see the download page, [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span></span>  
  
## <a name="wcf-data-services-quickstart-tasks"></a><span data-ttu-id="1b9df-114">WCF 数据服务快速入门任务</span><span class="sxs-lookup"><span data-stu-id="1b9df-114">WCF Data Services Quickstart Tasks</span></span>  
 [<span data-ttu-id="1b9df-115">创建数据服务</span><span class="sxs-lookup"><span data-stu-id="1b9df-115">Creating the Data Service</span></span>](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
 <span data-ttu-id="1b9df-116">定义 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 应用程序，定义数据模型，创建数据服务，并启用对资源的访问。</span><span class="sxs-lookup"><span data-stu-id="1b9df-116">Define the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application, define the data model, create the data service, and enable access to resources.</span></span>  
  
 [<span data-ttu-id="1b9df-117">从 Web 浏览器访问服务</span><span class="sxs-lookup"><span data-stu-id="1b9df-117">Accessing the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
 <span data-ttu-id="1b9df-118">通过 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 启动服务，并通过 Web 浏览器向公开的源提交 HTTP GET 请求以访问该服务。</span><span class="sxs-lookup"><span data-stu-id="1b9df-118">Start the service from [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] and access the service by submitting HTTP GET requests through a Web browser to the exposed feed.</span></span>  
  
 [<span data-ttu-id="1b9df-119">创建.NET Framework 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="1b9df-119">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
 <span data-ttu-id="1b9df-120">创建一个 [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] 客户端应用程序以使用 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 源，将数据绑定到 Windows 控件，在绑定控件中更改数据，然后将更改发送回数据服务。</span><span class="sxs-lookup"><span data-stu-id="1b9df-120">Create a [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] client application to consume the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, bind data to Windows controls, change data in the bound controls, and then send the changes back to the data service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b9df-121">已完成版本的快速入门中的项目文件可从 [WCF 数据服务文档示例](http://go.microsoft.com/fwlink/?LinkId=179994) 网页下载。</span><span class="sxs-lookup"><span data-stu-id="1b9df-121">Project files from a completed version of the quickstart can be downloaded from the [WCF Data Services Documentation Samples](http://go.microsoft.com/fwlink/?LinkId=179994) page.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1b9df-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1b9df-122">Next Steps</span></span>  
 <span data-ttu-id="1b9df-123">[启动快速入门](../../../../docs/framework/data/wcf/creating-the-data-service.md)。</span><span class="sxs-lookup"><span data-stu-id="1b9df-123">[Start the Quickstart](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b9df-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b9df-124">See Also</span></span>  
 [<span data-ttu-id="1b9df-125">ADO.NET 实体框架</span><span class="sxs-lookup"><span data-stu-id="1b9df-125">ADO.NET Entity Framework</span></span>](../../../../docs/framework/data/adonet/ef/index.md)

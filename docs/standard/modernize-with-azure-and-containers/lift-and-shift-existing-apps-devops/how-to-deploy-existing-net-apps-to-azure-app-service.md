---
title: 如何将现有的.NET 应用程序部署到 Azure App Service
description: 为容器化的.NET 应用程序的.NET 微服务体系结构 |如何将现有的.NET 应用程序部署到 Azure App Service
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 74f4d4b1812976d2e2b1581e10134fa57938bffc
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-deploy-existing-net-apps-to-azure-app-service"></a><span data-ttu-id="4200a-103">如何将现有的.NET 应用程序部署到 Azure App Service</span><span class="sxs-lookup"><span data-stu-id="4200a-103">How to deploy existing .NET apps to Azure App Service</span></span> 

<span data-ttu-id="4200a-104">Azure App Service Web Apps 功能是一个完全托管的计算平台，用于托管网站和 web 应用进行了优化。</span><span class="sxs-lookup"><span data-stu-id="4200a-104">The Web Apps feature of Azure App Service is a fully managed compute platform that is optimized for hosting websites and web apps.</span></span> <span data-ttu-id="4200a-105">此 PaaS 产品/服务在 Microsoft Azure 可让你专注于业务逻辑，而 Azure 负责基础结构来运行和缩放你的应用。</span><span class="sxs-lookup"><span data-stu-id="4200a-105">This PaaS offering in Microsoft Azure lets you focus on your business logic, while Azure takes care of the infrastructure to run and scale your apps.</span></span>

## <a name="validate-sites-and-migrate-to-app-service-with-azure-app-service-migration-assistant"></a><span data-ttu-id="4200a-106">验证站点和迁移到与 Azure 应用程序服务迁移助手的 App Service</span><span class="sxs-lookup"><span data-stu-id="4200a-106">Validate sites and migrate to App Service with Azure App Service Migration Assistant</span></span>

<span data-ttu-id="4200a-107">当在 Visual Studio 中，通常将应用程序移到 App Service 中创建新的应用程序非常简单。</span><span class="sxs-lookup"><span data-stu-id="4200a-107">When you create a new application in Visual Studio, moving the app to App Service usually is straightforward.</span></span> <span data-ttu-id="4200a-108">但是，如果你打算迁移现有应用程序为 App Service，首先你需要评估应用程序的所有依赖关系是否与应用程序服务兼容。</span><span class="sxs-lookup"><span data-stu-id="4200a-108">However, if you are planning to migrate an existing application to App Service, first you need to evaluate whether all your application's dependencies are compatible with App Service.</span></span> <span data-ttu-id="4200a-109">这包括如 server 操作系统和服务器安装任何第三方软件依赖项。</span><span class="sxs-lookup"><span data-stu-id="4200a-109">This includes dependencies like server OS and any third-party software that's installed on the server.</span></span>

<span data-ttu-id="4200a-110">你可以使用[Azure 应用程序服务迁移助手](https://www.migratetoazure.net/)来分析站点，然后将它们迁移从 Windows 和 Linux 的 web 服务器到 App Service。</span><span class="sxs-lookup"><span data-stu-id="4200a-110">You can use [Azure App Service Migration Assistant](https://www.migratetoazure.net/) to analyze sites and then migrate them from Windows and Linux web servers to App Service.</span></span> <span data-ttu-id="4200a-111">作为迁移的一部分，该工具可创建 web 应用和 Azure 上的数据库根据需要发布内容，并发布你的数据库。</span><span class="sxs-lookup"><span data-stu-id="4200a-111">As part of the migration, the tool creates web apps and databases on Azure as needed, publishes content, and publishes your database.</span></span>

<span data-ttu-id="4200a-112">Azure 的应用程序服务迁移助手，则支持从 IIS 到云在 Windows Server 上运行迁移。</span><span class="sxs-lookup"><span data-stu-id="4200a-112">Azure App Service Migration Assistant supports migrating from IIS running on Windows Server to the cloud.</span></span> <span data-ttu-id="4200a-113">App Service 支持 Windows Server 2003 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="4200a-113">App Service supports Windows Server 2003 and later versions.</span></span>

> ![https://www.migratetoazure.net/Images/ImageCanvas.png](./media/image5.png)
>
> <span data-ttu-id="4200a-114">**图 4-5。**</span><span class="sxs-lookup"><span data-stu-id="4200a-114">**Figure 4-5.**</span></span> <span data-ttu-id="4200a-115">使用 Azure App Service 迁移助手</span><span class="sxs-lookup"><span data-stu-id="4200a-115">Using Azure App Service Migration Assistant</span></span>

<span data-ttu-id="4200a-116">应用程序服务迁移助手是一个工具，将网站从你的 web 服务器移到 Azure 云。</span><span class="sxs-lookup"><span data-stu-id="4200a-116">App Service Migration Assistant is a tool that moves your websites from your web servers to the Azure cloud.</span></span>

<span data-ttu-id="4200a-117">网站迁移至 App Service 后，站点将拥有所需安全而高效地运行的一切。</span><span class="sxs-lookup"><span data-stu-id="4200a-117">After a website is migrated to App Service, the site has everything it needs to run safely and efficiently.</span></span> <span data-ttu-id="4200a-118">站点设置和在 Azure 云 PaaS 服务 （应用程序服务） 中自动运行。</span><span class="sxs-lookup"><span data-stu-id="4200a-118">Sites are set up and run automatically in the Azure cloud PaaS service (App Service).</span></span>

<span data-ttu-id="4200a-119">App Service 迁移工具可以分析您的网站和其转移到 App Service 的兼容性报告。</span><span class="sxs-lookup"><span data-stu-id="4200a-119">The App Service migration tool can analyze your websites and report on their compatibility for moving to App Service.</span></span> <span data-ttu-id="4200a-120">如果你满意分析，你可以让应用程序服务迁移助手迁移内容、 数据和为你的设置。</span><span class="sxs-lookup"><span data-stu-id="4200a-120">If you're happy with the analysis, you can let App Service Migration Assistant migrate content, data, and settings for you.</span></span> <span data-ttu-id="4200a-121">如果站点并不完全兼容，迁移工具将告诉你需要进行调整，使其工作内容。</span><span class="sxs-lookup"><span data-stu-id="4200a-121">If a site is not quite compatible, the migration tool tells you what you need to adjust to make it work.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4200a-122">其他资源</span><span class="sxs-lookup"><span data-stu-id="4200a-122">Additional resources</span></span>

- <span data-ttu-id="4200a-123">**Azure App Service 迁移助手**</span><span class="sxs-lookup"><span data-stu-id="4200a-123">**Azure App Service Migration Assistant**</span></span>

    [https://www.migratetoazure.net/](https://www.migratetoazure.net/)

>[!div class="step-by-step"]
<span data-ttu-id="4200a-124">[上一页](what-about-cloud-optimized-applications.md)
[下一页](deploy-existing-net-apps-as-windows-containers.md)</span><span class="sxs-lookup"><span data-stu-id="4200a-124">[Previous](what-about-cloud-optimized-applications.md)
[Next](deploy-existing-net-apps-as-windows-containers.md)</span></span>

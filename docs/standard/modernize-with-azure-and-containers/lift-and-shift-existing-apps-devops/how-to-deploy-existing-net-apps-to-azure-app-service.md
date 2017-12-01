---
title: "如何将现有的.NET 应用程序部署到 Azure App Service"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |如何将现有的.NET 应用程序部署到 Azure App Service"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: c83703c6f3dede0f92263e0d46bf48525c3eefaf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-deploy-existing-net-apps-to-azure-app-service"></a>如何将现有的.NET 应用程序部署到 Azure App Service 

Azure App Service Web Apps 功能是一个完全托管的计算平台，用于托管网站和 web 应用进行了优化。 此 PaaS 产品/服务在 Microsoft Azure 可让你专注于业务逻辑，而 Azure 负责基础结构来运行和缩放你的应用。

## <a name="validate-sites-and-migrate-to-app-service-with-azure-app-service-migration-assistant"></a>验证站点和迁移到与 Azure 应用程序服务迁移助手的 App Service

当在 Visual Studio 中，通常将应用程序移到 App Service 中创建新的应用程序非常简单。 但是，如果你打算迁移现有应用程序为 App Service，首先你需要评估应用程序的所有依赖关系是否与应用程序服务兼容。 这包括如 server 操作系统和服务器安装任何第三方软件依赖项。

你可以使用[Azure 应用程序服务迁移助手](https://www.migratetoazure.net/)来分析站点，然后将它们迁移从 Windows 和 Linux 的 web 服务器到 App Service。 作为迁移的一部分，该工具可创建 web 应用和 Azure 上的数据库根据需要发布内容，并发布你的数据库。

Azure 的应用程序服务迁移助手，则支持从 IIS 到云在 Windows Server 上运行迁移。 App Service 支持 Windows Server 2003 和更高版本。

> ![https://www.migratetoazure.net/Images/ImageCanvas.png](./media/image5.png)
>
> **图 4-5。** 使用 Azure App Service 迁移助手

应用程序服务迁移助手是一个工具，将网站从你的 web 服务器移到 Azure 云。

网站迁移至 App Service 后，站点将拥有所需安全而高效地运行的一切。 站点设置和在 Azure 云 PaaS 服务 （应用程序服务） 中自动运行。

App Service 迁移工具可以分析您的网站和其转移到 App Service 的兼容性报告。 如果你满意分析，你可以让应用程序服务迁移助手迁移内容、 数据和为你的设置。 如果站点并不完全兼容，迁移工具将告诉你需要进行调整，使其工作内容。

### <a name="additional-resources"></a>其他资源

-   **Azure App Service 迁移助手**

    [https://www.migratetoazure.net/](https://www.migratetoazure.net/)

>[!div class="step-by-step"]
[上一页](what-about-cloud-optimized-applications.md)
[下一页](deploy-existing-net-apps-as-windows-containers.md)

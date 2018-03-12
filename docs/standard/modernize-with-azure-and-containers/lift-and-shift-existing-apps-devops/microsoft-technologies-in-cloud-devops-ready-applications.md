---
title: "云 devops 通用应用程序中的 Microsoft 技术"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |云 DevOps 通用应用程序中的 Microsoft 技术"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 66579905ad2694cf08950d0c0a69e2405ab2c1ee
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-technologies-in-cloud-devops-ready-applications"></a>云 devops 通用应用程序中的 Microsoft 技术

以下列表介绍工具、 技术以及被识别为云就绪 DevOps 应用要求的解决方案。 可以采用云就绪 DevOps 应用有选择地或逐渐，具体取决于你的工作。

-   **云基础结构**： 提供计算平台、 操作系统、 网络和存储的基础结构。 Microsoft Azure 定位在此级别。

-   **运行时**： 此层提供要运行的应用程序的环境。 如果你使用的容器，此层通常基于[Docker 引擎](https://docs.docker.com/engine/)，Linux 主机上或在 Windows 主机上运行。 ([Windows 容器](https://docs.microsoft.com/virtualization/windowscontainers/about/)支持从 Windows Server 2016 开始。 Windows 容器是在 Windows 运行的现有.NET Framework 应用程序的最佳选择。）

-   **托管云**： 当你选择托管的云选项时，你可以避免的费用和复杂性的管理和支持的基础的基础结构，Vm，OS 修补程序，以及网络配置。 如果你选择通过使用 IaaS 迁移，你负责为所有这些任务和关联的成本。 在托管的云选项中，你可以管理的应用程序和开发的服务。 云服务提供商通常管理其他所有内容。 在 Azure 中托管的云服务的示例包括[Azure SQL 数据库](https://azure.microsoft.com/services/sql-database)， [Azure Redis 缓存](https://azure.microsoft.com/services/cache/)， [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/)， [Azure 存储空间](https://azure.microsoft.com/services/storage/)，[MySQL 的 azure 数据库](https://azure.microsoft.com/services/mysql/)， [PostgreSQL 的 Azure 数据库](https://azure.microsoft.com/services/postgresql/)， [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)，并管理等的计算服务[VM 扩展设置](https://azure.microsoft.com/services/virtual-machine-scale-sets/)， [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)， [Azure App Service](https://azure.microsoft.com/services/app-service/)，和[Azure 容器服务](https://azure.microsoft.com/services/container-service/)。

-   **应用程序开发**： 你可以从许多语言时选择你生成应用程序在容器中运行。 在本指南中，我们重点[.NET](https://www.microsoft.com/net)，但你可以通过使用 Node.js、 Python，之类的其他语言开发容器基于应用 Spring/Java 或 GoLang。

-   **监视，遥测，日志记录，和审核**： 对监视器和审核的应用程序和在云中运行的容器的功能至关重要的任何云 DevOps 就绪应用程序。 [Azure 的 Application Insights](https://azure.microsoft.com/services/application-insights/)和[Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite)所用的云就绪 DevOps 应用提供监视和审核的主要 Microsoft 工具。

-   **设置**： 自动化工具帮助你设置基础结构和应用程序部署到多个环境 （生产、 测试、 过渡）。 Chef 和 Puppet 之类的工具可用于管理应用程序的配置和环境。 此外可以通过使用更简单且更直接的方法实现这一层。 例如，你可以部署直接通过使用 Azure 命令行界面 (Azure CLI) 工具，然后使用连续部署和版本管理中的管道[Visual Studio Team Services](https://www.visualstudio.com/team-services/)。

-   **应用程序生命周期**: [Visual Studio Team Services](https://www.visualstudio.com/team-services/)和其他工具，如 Jenkins，均可帮助你生成自动化服务器实现 CI/CD 管道，包括版本管理。

本章节中和相关的演练中的后续部分专门重点介绍有关运行时层 （Windows 容器） 的详细信息。 本指南介绍你可以部署 Windows Server 2016 （和更高版本） 上的 Windows 容器 Vm 的方式。 它还介绍了更高级的 orchestrator 层，如 Azure Service Fabric、 Kubernetes 和 Azure 容器服务。 设置 orchestrator 层是对 modernizing 现有.NET Framework （基于 Windows 的） 应用程序作为云 DevOps 通用应用程序的基本要求。

## <a name="monolithic-applications-can-be-cloud-devops-ready"></a>整体应用程序*可以*为云 DevOps 就绪

务必要突出显示的整体应用程序 （不基于微服务的应用程序）*可以*是云 DevOps 就绪应用程序。 你可以生成并运行充分利用云计算模型的容器、 持续交付和 DevOps 结合使用的单一应用程序。 如果您的业务目标为右现有整体应用程序，你可以更新它，并使其云 DevOps 就绪。

同样，如果单一应用程序可以将云 DevOps 通用应用程序，类似于 N 层应用程序的其他、 更复杂的体系结构还可以将得到改进作为云 DevOps 通用应用程序。

>[!div class="step-by-step"]
[上一页](reasons-to-lift-and-shift-existing-net-apps-to-cloud-devops-ready-applications.md)
[下一页](what-about-cloud-optimized-applications.md)

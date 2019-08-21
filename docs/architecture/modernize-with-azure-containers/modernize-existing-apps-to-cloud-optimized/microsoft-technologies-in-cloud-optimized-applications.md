---
title: 云优化应用程序中的 Microsoft 技术
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |云优化应用程序中的 Microsoft 技术
ms.date: 04/28/2018
ms.openlocfilehash: 915aa99d2331c5b9c46eabef3335fb809baa9370
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578220"
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a>云优化应用程序中的 Microsoft 技术

以下列表描述了可识别为云优化应用程序要求的工具、技术和解决方案。 您可以根据自己的优先级有选择地或逐步地采用云优化的元素。

- **云基础结构**:提供计算平台、操作系统、网络和存储的基础结构。 Microsoft Azure 位于此级别。

- **运行时**:此层提供应用程序运行的环境。 如果使用的是容器, 则该层通常基于[Docker 引擎](https://docs.docker.com/engine/), 该引擎在 Linux 主机或 Windows 主机上运行。 (从 Windows Server 2016 开始支持[Windows 容器](https://docs.microsoft.com/virtualization/windowscontainers/about/)。 Windows 容器是在 Windows 上运行的现有 .NET Framework 应用程序的最佳选择。)

- **托管云**:选择托管云选项后, 你可以避免管理和支持底层基础结构、Vm、OS 修补程序和网络配置的开销和复杂性。 如果选择使用 IaaS 进行迁移, 则需要负责所有这些任务以及相关的成本。 在托管云选项中, 只管理你开发的应用程序和服务。 云服务提供商通常会管理其他所有内容。 Azure 中托管云服务的示例包括[AZURE SQL 数据库](https://azure.microsoft.com/services/sql-database)、 [azure Redis 缓存](https://azure.microsoft.com/services/cache/)、 [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/)、 [azure 存储](https://azure.microsoft.com/services/storage/)、 [Azure Database for MySQL](https://azure.microsoft.com/services/mysql/)、 [Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/)、 [azure Active目录](https://azure.microsoft.com/services/active-directory/)和托管计算服务, 例如[VM 规模集](https://azure.microsoft.com/services/virtual-machine-scale-sets/)、 [Azure App Service](https://azure.microsoft.com/services/app-service/)和[Azure Kubernetes 服务](https://azure.microsoft.com/services/container-service/)。

- **应用程序开发**:生成在容器中运行的应用程序时, 可以选择多种语言。 本指南重点介绍[.net](https://www.microsoft.com/net), 但你可以使用其他语言 (如 Node.js、Python、弹簧/Java 或中转) 来开发基于容器的应用。

- **监视、遥测、日志记录和审核**:在云中运行的应用程序和容器的监视和审核功能对于任何云优化的应用程序而言至关重要。 [Azure 应用程序 Insights](https://azure.microsoft.com/services/application-insights/)和[Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite)是为云优化应用提供监视和审核的主要 Microsoft 工具。

- **预配**:自动化工具可帮助你预配基础结构和将应用程序部署到多个环境 (生产、测试、过渡)。 你可以使用 Chef 和 Puppet 之类的工具来管理应用程序的配置和环境。 此层还可以通过使用更简单、更直接的方法来实现。 例如, 你可以使用 Azure 命令行接口 (Azure CLI) 工具直接部署, 然后在[Azure DevOps Services](https://azure.microsoft.com/services/devops/)中使用连续部署和发布管理管道。

- **应用程序生命周期**:[Azure DevOps Services](https://azure.microsoft.com/services/devops/)和其他工具 (如 Jenkins) 都是构建自动化服务器, 可帮助你实现 CI/CD 管道, 包括 release management。

本章的后续部分以及相关演练专门针对有关运行时层 (Windows 容器) 的详细信息。 本指南介绍了在 Windows Server 2016 (及更高版本) Vm 和 Azure 容器实例上部署 Windows 容器的方式。 它还介绍了更高级的 PaaS 平台, 如 Azure App Service 和 orchestrator, 如 Azure Kubernetes Service。

## <a name="monolithic-applications-can-be-cloud-optimized"></a>单个应用程序*可以*进行云优化

重要的是, 重点强调单一应用程序 (不基于微服务的应用程序)*可以*是云优化的应用程序。 你可以使用容器、持续交付和 DevOps 的组合来构建和运行利用云计算模型的单一应用程序。 如果现有的单一应用程序适用于你的业务目标, 则可以将其现代化, 并使其成为云优化的应用程序。

同样, 如果单一应用程序可以是云优化的应用程序, 其他更复杂的体系结构 (如 N 层应用程序) 也可以现代化为云优化的应用程序。

>[!div class="step-by-step"]
>[上一页](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
>[下一页](what-about-cloud-native-applications.md)

---
title: 将现有 .NET 应用部署为 Windows 容器
description: 通过 Azure 云和 Windows 容器实现现有 .NET 应用程序的现代化 |将现有 .NET 应用部署为 Windows 容器
ms.date: 04/29/2018
ms.openlocfilehash: 997b32e51272be2126bd824de1f8f026d77ca203
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318653"
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>将现有 .NET 应用部署为 Windows 容器

基于 Windows 容器的部署适用于云优化的应用程序和云本机应用程序。

但是，在本指南中，特别是在以下部分中，主要介绍如何使用适用于*云优化*应用程序的 Windows 容器，而无需重塑应用程序。

## <a name="what-are-containers-linux-or-windows"></a>什么是容器？ （Linux 或 Windows）

容器是将应用程序打包到其自己的独立包中的一种方法。 在容器中，应用程序不受容器外部的应用程序或进程影响。 应用程序所依赖的所有内容在容器内作为进程成功运行。 无论在何处移动容器，都将始终满足应用程序的要求，因为它与需要运行的所有内容（库依赖项、运行时等）捆绑在一起。

容器的主要特性是，它使环境在不同的部署中是相同的，因为容器本身附带了所需的所有依赖项。 您可以在您的计算机上调试应用程序，然后将其部署到另一台计算机上，并且保证相同的环境。

容器是容器映像的实例。 容器映像是打包应用或服务（如快照）的一种方式，并以可靠且可重现的方式对其进行部署。 你可能会说，Docker 不仅是一项技术，它也是一个理念和一个过程。

每日的容器变得越来越常见，它们成为行业范围内的部署单元。

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>容器的优点（Linux 或 Windows 上的 Docker 引擎）

使用容器构建应用程序（也可能定义为轻型构建基块）在任何基础结构中，为生成、传送和运行任何应用程序提供显著的灵活性。

借助容器，你可以将任何应用程序从开发到生产环境，只需很少或无需更改代码，因为跨 Microsoft 开发人员工具、操作系统和云的 Docker 集成。

部署到普通 Vm 时，可能已有一个用于将 ASP.NET 应用程序部署到 Vm 的方法。 不过，您的方法很可能涉及使用 Puppet 或类似工具之类的部署工具执行多个手动步骤或复杂的自动化过程。 你可能需要执行一些任务，如修改配置项目、在服务器之间复制应用程序内容以及基于 .msi 设置运行交互式安装程序，然后进行测试。 部署中的所有步骤会将时间和风险添加到部署中。 当目标环境中不存在依赖关系时，将会出现故障。

在 Windows 容器中，打包应用程序的过程是完全自动进行的。 Windows 容器基于 Docker 平台，该平台为容器部署提供自动更新和回滚功能。 使用 Docker 引擎所获得的主要改进就是创建映像，这些映像类似于应用程序的快照及其所有依赖项。 映像是 Docker 映像（在本例中为 Windows 容器映像）。 映像在容器中运行 ASP.NET 应用，而无需返回到源代码。 容器快照成为部署单元。

许多组织正在容器化现有的单一应用程序，原因如下：

- **通过改进的部署来释放灵活性**。 容器在开发和操作之间提供一致的部署协定。 使用容器时，不会听到开发人员说： "它在我的计算机上工作，为什么不在生产中？" 它们可以说，"它作为容器运行，因此它将在生产环境中运行。" 打包的应用程序及其所有依赖项可在任何支持的基于容器的环境中执行。 它将运行在所有部署目标（开发、QA、过渡、生产）中运行的方式。 当容器从一个阶段移到下一个阶段时，它们会消除大多数摩擦，这大大改进了部署，并且可以更快地交付。

- **降低成本**。 容器可通过合并和删除现有硬件，或以更高密度的方式在每个硬件上运行应用程序，从而降低成本。

- 可**移植性**。 容器是模块化的，并且是可移植的。 Docker 容器在任何服务器操作系统（Linux 和 Windows）上、在任何主要公有云（Microsoft Azure、Amazon AWS、Google、IBM）以及本地和私有或混合云环境中都受支持。

- **控件**。 容器提供在容器级别控制的灵活安全的环境。 可以通过在容器上设置执行约束策略来保护、隔离、甚至限制容器。 如有关 Windows 容器的部分中所述，Windows Server 2016 和 Hyper-v 容器提供其他企业支持选项。

当你使用容器开发和维护应用程序时，灵活性、可移植性和控制能力的重大改进最终会导致显著降低成本。

## <a name="what-is-docker"></a>什么是 Docker？

[Docker](https://www.docker.com/)是一种[开源项目](https://github.com/docker/docker)，可自动将应用程序部署为可在云中或本地运行的、可移植的独立容器。 Docker 也是一家促进和发展这项技术的[公司](https://www.docker.com/)。 公司与云、Linux 和 Windows 供应商（包括 Microsoft）合作。

![显示 Docker 如何在混合云中部署容器的关系图。](./media/deploy-existing-net-apps-as-windows-containers/docker-deploys-containers-all-layers.png)

**图4-6。** Docker 在混合云的所有层上部署容器

对于熟悉虚拟机的人而言，容器可能看起来非常相似。 容器运行操作系统，具有文件系统，并且可以通过网络访问，就像物理或虚拟计算机系统一样。 不过，容器背后的技术和概念与虚拟机截然不同。 从开发人员的角度来看，容器必须处理得更像是一个过程。 事实上，容器具有一个进程的单一入口点。

Docker 容器（对于简单起见，*容器*）可以在 Linux 和 Windows 上本机运行。 运行常规容器时，Windows 容器只能在 Windows 主机（主机服务器或 VM）上运行，而 Linux 容器只能在 Linux 主机上运行。 但是，在最新版本的 Windows Server 和 Hyper-v 容器中，Linux 容器还可以使用目前仅在 Windows Server 容器中可用的 Hyper-v 隔离技术，在 Windows Server 上本机运行。

在不久的将来，具有 Linux 和 Windows 容器的混合环境可能会甚至很常见。

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>适用于现有 .NET 应用程序的 Windows 容器的优点

使用 Windows 容器的好处从根本上与容器的优点相同。 使用 Windows 容器可大大提高灵活性、可移植性和控制能力。

现有的 .NET 应用程序引用使用 .NET Framework 创建的那些应用程序。 例如，它们可能是传统的 ASP.NET web 应用程序-不使用.NET Core，后者是较新，并运行跨平台在 Linux、 Windows 和 MacOS 上。

.NET Framework 中的主要依赖项为 Windows。 它还具有辅助依赖项（如 IIS）和传统 ASP.NET 中的 system.web。

必须在 Windows、period 上运行 .NET Framework 应用程序。 如果你想要化现有.NET Framework 应用程序并且你不能或不希望投资迁移到.NET Core （"如果它能正常工作，不将其迁移"），你有针对容器是唯一选择是使用 Windows 容器。

因此，Windows 容器的一个主要优点是，它们为你提供了一种方法来现代化在 Windows 上运行的现有 .NET Framework 应用程序（通过容器化）。 最终，Windows 容器通过使用容器获得所需的优势-灵活性、可移植性和更好的控制。

## <a name="choose-an-os-to-target-with-net-based-containers"></a>选择要作为目标的操作系统。基于网络的容器

给定的操作系统支持 Docker，以及.NET Framework 和.NET Core 之间的差异的多样性，应针对特定操作系统和基于正在使用的 framework 的特定版本。

对于 Windows，可使用 Windows Server Core 或 Windows Nano Server。 这些 Windows 版本提供 .NET Framework 或 .NET Core 应用程序可能需要的不同特性（例如 IIS）和自承载 web 服务器（如 Kestrel）。

对于 Linux，正式的 .NET Docker 映像（如 Debian）中提供并支持多个发行版本。

图4-7 显示了可以定位的操作系统版本，具体取决于应用程序的 .NET Framework 版本。

![根据 .NET Framework 版本显示目标目标的关系图。](./media/deploy-existing-net-apps-as-windows-containers/dotnet-framework-operating-systems.png)

**图4-7。** 基于 .NET Framework 版本的目标操作系统

在基于 .NET Framework 应用程序的现有应用程序或旧应用程序的迁移方案中，主要依赖项位于 Windows 和 IIS 上。 唯一的选择是使用基于 Windows Server Core 和 .NET Framework 的 Docker 映像。

将映像名称添加到 Dockerfile 文件时，可以使用标记选择操作系统和版本，如以下基于 .NET Framework 的 Windows 容器映像的示例中所示：

> | **符** | **系统和版本** |
> |---|---|
> | **microsoft/dotnet-framework:4.x-windowsservercore** | Windows Server Core 上的 .NET Framework 4。x |
> | **microsoft/aspnet:4.x-windowsservercore** | Windows Server Core 上的 .NET Framework ASP.NET 的附加自定义设置 |

为.NET Core （适用于 Linux 和 Windows 跨平台），标记将如下所示：

> | **符** | **系统和版本**
> |---|---|
> | **microsoft/dotnet:2.0.0-runtime** | .NET Core 2.0 仅运行时在 Linux 上 |
> | **microsoft/dotnet:2.0.0-runtime-nanoserver** | .NET Core 2.0 仅运行时在 Windows Nano Server 上 |

### <a name="multi-arch-images"></a>多个三维图像

从 2017 中旬开始，你还可以使用新功能在 Docker 调用中[多体系结构](https://github.com/moby/moby/issues/15866)映像。 .NET Core Docker 映像可以使用多 arch 标记。 Dockerfile 不再文件需定义你面向的操作系统。 使用多 arch 功能，用于跨多个计算机配置的单个标记。 例如，多体系结构，您可以使用一个通用的标签： **microsoft/dotnet:2.0.0-runtime**。 如果请求 Linux 容器环境中的使用该标记时，获取基于 Debian 的映像。 如果请求 Windows 容器环境中使用该标记时，获取基于 Nano Server 的映像。

对于 .NET Framework 映像，因为传统 .NET Framework 仅支持 Windows，所以不能使用多核功能。

## <a name="windows-container-types"></a>Windows 容器类型

与 Linux 容器类似，Windows Server 容器使用 Docker 引擎进行管理。 与 Linux 容器不同，Windows 容器包括两个不同的容器类型或运行时间-Windows Server 容器和 Hyper-v 隔离。

**Windows Server 容器**：通过进程和命名空间隔离技术提供应用程序隔离。 Windows Server 容器与容器主机和在主机上运行的所有容器共享内核。 这些容器不提供恶意安全边界，且不应用于隔离不受信任的代码。 由于共享内核空间，这些容器需要相同的内核版本和配置。

**Hyper-v 隔离**：通过在高度优化的虚拟机上运行每个容器，在 Windows Server 容器提供的隔离上扩展。 在此配置中，容器主机的内核不与同一主机上的其他容器共享。 这些容器专用于恶意多租户托管，具有 VM 的相同安全保障。 由于这些容器不与主机或主机上的其他容器共享内核，因此它们可以运行具有不同版本和配置的内核（支持的版本）。 例如，Windows 10 上的所有 Windows 容器使用 Hyper-v 隔离来利用 Windows Server 内核版本和配置。

在 Windows 上运行带有或不带 Hyper-v 隔离的容器是一个运行时决定。 您可以选择最初使用 Hyper-v 隔离创建容器，并在运行时选择将其作为 Windows Server 容器运行。

### <a name="additional-resources"></a>其他资源

- **Windows 容器文档**

    <https://docs.microsoft.com/virtualization/windowscontainers/>

- **Windows 容器基础知识**

    <https://docs.microsoft.com/virtualization/windowscontainers/about/>

- **Infographic：Microsoft 和容器 @ no__t-0

    <https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf>

## <a name="the-container-ecosystem-in-azure"></a>Azure 中的容器生态系统

在前面的部分中，已介绍了 Docker 容器的优点，以及适用于 .NET 应用程序的特定容器映像的详细信息。 为了开发或容器化应用程序，所有这些通用信息都是基本信息。
但是，在考虑生产部署环境乃至 QA 和开发/测试环境时，Microsoft Azure 提供了一种开放且广泛的选择，即云中的完整容器生态系统（如下图所示）。 根据具体的应用程序需求，应选择一个或另一个 Azure 产品。

![Azure 中的容器生态系统示意图。](./media/deploy-existing-net-apps-as-windows-containers/azure-container-ecosystem.png)

**图 4-7.5。** Azure 中的容器生态系统

在 Azure 中的容器生态系统中，以下产品支持被视为基础结构的容器：

- **Azure 容器实例 (ACI)**
- **Azure 虚拟机**（包含容器的支持）
- **Azure 虚拟机规模集**（包含容器的支持）

从这三个角度来看，ACI 带来了极大的好处，这就是不需要维护基础操作系统、无需升级/修补等的情况，但 ACI 仍位于基础结构级别，如本书后面的部分中所述。

Azure 中支持容器的产品，这些容器在 PaaS （平台即服务）级别中的位置更多：

- **Azure 应用服务**
- **Azure Kubernetes 服务（AKS 和 ACS）**
- **Azure Batch** 

接下来，Azure 容器注册表是 Azure 中托管的高度可缩放容器注册表，可在注册和部署自定义容器映像时在以前的所有产品中使用。

此外，在容器中，可以在 azure 中使用其他托管服务，如 Azure SQL 数据库、Azure Redis 缓存、Azure Cosmos DB 等。 此外还有 Azure Marketplace 中提供的第三方解决方案/平台，如 Cloud Foundry 和 OpenShift，还可以在 Azure 中使用容器。 

在接下来的部分中，你可以浏览 Microsoft 的建议，这些建议针对的是在面向 Windows 容器时特别使用的每个 Azure 产品和解决方案。

>[!div class="step-by-step"]
>[上一页](what-about-cloud-native-applications.md)
>[下一页](when-not-to-deploy-to-windows-containers.md)

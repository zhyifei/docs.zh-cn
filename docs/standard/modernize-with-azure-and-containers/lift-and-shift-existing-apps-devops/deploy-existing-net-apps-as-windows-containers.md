---
title: 将现有的.NET 应用程序部署为 Windows 容器
description: 为容器化的.NET 应用程序的.NET 微服务体系结构 |将现有的.NET 应用程序部署为 Windows 容器
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6c70e30c10674c086e6ad880b97151ae1918ed87
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="deploy-existing-net-apps-as-windows-containers"></a>将现有的.NET 应用程序部署为 Windows 容器

基于 Windows 容器的部署都适用于云优化应用程序、 云本机应用程序和云 DevOps 通用应用程序。

本指南中和的以下部分中的重点是使用 Windows 容器的*云就绪 DevOps*应用程序，当提升和移动现有的.NET 应用程序。

## <a name="what-are-containers-linux-or-windows"></a>什么是容器 （Linux 或 Windows）

容器是一种方法完成其自己的独立包到应用程序。 在其容器中，应用程序不受应用程序或存在于容器之外的进程。 所有内容应用程序取决于以运行已成功为进程是在容器内。 容器可能移动任何位置，则应用程序将始终满足要求，根据直接的依赖关系，因为它与它需要运行 （库依赖项、 运行时，等） 的所有内容捆绑在一起。

容器的主要特征在于，它使得环境相同跨不同部署因为容器本身附带它需要的所有依赖项。 也就是说，你可以在您的计算机上进行调试应用程序，然后将其部署到另一台计算机，与相同的环境保证。

容器是容器映像的实例。 容器映像是一种方法，包的应用或服务 （如快照），然后将它部署可靠且可重现的方式。 你可以假定 Docker 不仅技术-it 还的基本原理和进程。

当容器每天变得更加常见，这些访客成为行业范围内"单元的部署。

## <a name="benefits-of-containers-docker-engine-on-linux-or-windows"></a>容器 （在 Linux 或 Windows 上的 Docker 引擎） 的优点

通过使用容器，以生成应用程序也可能是定义为轻量的构建基块提供显著提高了用于构建、 传送，和运行任何应用程序，在任何基础结构的灵活性。

与容器，您可以采取任何应用程序从开发到生产环境进行很少或没有代码更改后，在 Microsoft 开发人员工具、 操作系统和云之间的 Docker 集成感谢。

当你将部署到纯 Vm 时，你可能已在用于将 ASP.NET 应用程序部署到你的 Vm 的位置的一个方法。 很可能，不过，你的方法使用 Puppet，之类的部署工具或类似的工具，包括多个手动步骤或复杂的自动化的进程。 你可能需要执行任务，例如修改配置项目、 复制，在服务器之间的应用程序内容和运行基于跟测试的.msi 设置的交互式安装程序。 在部署中的所有这些步骤将添加到部署的时间和风险。 每当依赖项不存在于目标环境，则将出现故障。

在 Windows 容器中的打包应用程序过程是完全自动的。 Windows 容器基于 Docker 平台，提供自动更新和容器部署的回滚。 获得使用 Docker 引擎的主改进是你创建映像，就像你的应用程序的快照，包括其所有依赖项。 映像是 Docker 映像 （Windows 容器映像，在此情况下）。 映像不追溯到源代码的情况下，在容器中，运行的 ASP.NET 应用程序。 容器快照将成为部署单元。

大量的组织 containerizing 现有的单一应用程序，原因如下：

-   **释放通过提高部署灵活性**。 容器提供一致的部署之间开发和操作协定。 当使用容器时，您将听到开发人员说，"It works 我在计算机上，不要在生产中？" 他们可以简单地说，"它作为运行一个容器，因此它将在生产中运行。" 打包应用程序，包括其所有依赖项，可以在任何支持的基于容器的环境中执行。 它将运行它本来就在所有的部署目标 （开发、 QA、 过渡或生产） 中运行的方式。 容器消除大多数 frictions，当它们移到下一步，极大地提高了部署，从一个阶段时，你可以将更快地发运。

-   **成本降低**。 容器会导致降低成本，通过合并和删除的现有硬件，或者在更高的密度，每个单位硬件运行应用程序。

-   **可移植性**。 容器是模块化且可移植。 Docker 容器支持对任何服务器操作系统 （Linux 和 Windows），请在任何的主要公共云 （Microsoft Azure、 Amazon AWS、 Google、 IBM），在本地和私有或混合云环境。

-   **控件**。 容器提供灵活可靠的环境，在容器级别控制。 可以保护、 隔离，并且即使在容器上设置执行约束策略受限制容器。 有关 Windows 容器的部分所述，Windows Server 2016 和 HYPER-V 容器提供额外的企业级支持选项。

使用容器来开发和维护应用程序时，灵活性、 可移植性和控件中的重大改进最终导致显著降低成本。

## <a name="what-is-docker"></a>什么是 Docker？

[Docker](https://www.docker.com/)是[开放源代码项目](https://github.com/docker/docker)自动化作为可移植的足可以在云或本地运行的容器应用程序的部署。 Docker 也是[公司](https://www.docker.com/)，提升和发展此技术。 该公司在与云，Linux 和 Windows 供应商，包括 Microsoft 协作工作正常。

![](./media/image6.png)

> **图 4-6。** Docker 在混合云的所有层部署容器

某个人可以使用熟悉的虚拟机，容器可能看起来非常类似。 容器在操作系统上运行，具有文件系统，并且可以访问通过网络，就像物理或虚拟计算机系统一样。 但是，该技术以及容器背后的概念是大大不同于虚拟机。 从开发人员的角度来看，容器必须被视为多单个进程。 事实上，容器都有一个进程的单入口点。

Docker 容器 (为简单起见，*容器*) 可以本机 Linux 和 Windows 上运行。 Windows 容器时正在运行的正则容器，可以仅在 Windows 主机 （主机服务器或 VM） 上运行和 Linux 容器可以仅在 Linux 主机上运行。 但是，在最新版本的 Windows Server 和 HYPER-V 容器，Linux 容器还可以运行本机在 Windows Server 上使用目前仅在 Windows Server 容器中可用的 HYPER-V 隔离技术。

在不久的将来，具有 Linux 和 Windows 容器的混合的环境将可能并常见。

## <a name="benefits-of-windows-containers-for-your-existing-net-applications"></a>为你现有的.NET 应用程序的 Windows 容器的优点

使用 Windows 容器的好处本质都是相同的好处一般情况下获取来自容器。 使用 Windows 容器是有关从而大大提高灵活性、 可移植性和控制。

当我们谈现有的.NET 应用程序时，主要是指的传统应用程序使用.NET Framework 创建的。 例如，它们可能是传统的 ASP.NET web 应用程序-不使用.NET 核心，后者是较新，并运行跨平台在 Linux、 Windows 和 MacOS 上。

.NET Framework 中的主要依赖关系是 Windows。 它还具有传统 ASP.NET 中的辅助依赖项，如 IIS 和 System.Web。

.NET Framework 应用程序必须运行在 Windows 上，时间段所示。 如果你想要化现有.NET Framework 应用程序并且你不能或不希望投资迁移到.NET 核心 （"如果它能正常工作，不将其迁移"），你有针对容器是唯一选择是使用 Windows 容器。

因此，Windows 容器的主要好处之一是，它们提供了一种方法来提升你现有的.NET Framework 应用程序在 Windows 通过容器化上运行。 从根本上讲，Windows 容器，让你通过使用容器灵活性、 可移植性和更好地控制正在寻找的好处。

## <a name="choose-an-os-to-target-with-net-based-containers"></a>选择为目标的 OS。基于网络的容器

给定的操作系统支持 Docker，以及.NET Framework 和.NET 核心之间的差异的多样性，应针对特定操作系统和基于正在使用的 framework 的特定版本。

对于 Windows，可使用 Windows Server Core 或 Windows Nano Server。 这些 Windows 版本提供需要的.NET Framework 或.NET Core 应用程序的不同特征 （如与自承载的 web 服务器 Kestrel 例如 IIS)。

对于 Linux，正式的 .NET Docker 映像（如 Debian）中提供并支持多个发行版本。

图 4-7 显示你可以面向，具体取决于应用的.NET Framework 版本的操作系统版本。

![](./media/image7.png)

> **图 4-7。** 指向基于.NET Framework 版本的操作系统

在基于.NET Framework 应用程序的现有或旧应用程序的迁移方案，主要依赖项是在 Windows 和 IIS 上。 唯一的选项是使用基于 Windows Server Core 和.NET Framework 的 Docker 映像。

当映像名称添加到 Dockerfile 文件时，可以通过使用的标记，如下面的示例基于.NET Framework 的 Windows 容器映像中选择的操作系统和版本：

> | **标记** | **系统和版本** |
> |---|---|
> | **microsoft/dotnet-framework:4.x-windowsservercore** | .NET framework 4.x 在 Windows Server Core 上 |
> | **microsoft/aspnet:4.x-windowsservercore** | .NET framework 4.x 使用其他 ASP.NET 自定义，在 Windows Server Core 上 |

为.NET 核心 （适用于 Linux 和 Windows 跨平台），标记将如下所示：

> | **标记** | **系统和版本**
> |---|---|
> | **microsoft/dotnet:2.0.0-runtime** | .NET 核心 2.0 仅运行时在 Linux 上 |
> | **microsoft/dotnet:2.0.0-runtime-nanoserver** | .NET 核心 2.0 仅运行时在 Windows Nano Server 上 |

### <a name="multi-arch-images"></a>多 arch 映像

从 2017 中旬开始，你还可以使用新功能在 Docker 调用中[多体系结构](https://github.com/moby/moby/issues/15866)映像。 .NET 核心 Docker 映像可以使用多 arch 标记。 Dockerfile 不再文件需定义你面向的操作系统。 使用多 arch 功能，用于跨多个计算机配置的单个标记。 例如，多体系结构，您可以使用一个通用的标签： **microsoft/dotnet:2.0.0-runtime**。 如果请求 Linux 容器环境中的使用该标记时，获取基于 Debian 的映像。 如果请求 Windows 容器环境中使用该标记时，获取基于 Nano Server 的映像。

对于.NET Framework 映像，因为传统的.NET Framework 支持仅 Windows 中，不能使用多 arch 功能。

## <a name="windows-container-types"></a>Windows 容器类型

Linux 容器，如 Windows Server 容器通过使用 Docker 引擎管理。 与 Linux 容器不同 Windows 容器包括两种不同的容器类型，或运行时间 Windows Server 容器和 HYPER-V 隔离。

**Windows Server 容器**： 提供通过进程和命名空间隔离技术的应用程序隔离。 Windows Server 容器与容器主机和主机运行的所有容器共享内核。 这些容器不提供恶意的安全边界，不应该用于隔离不受信任的代码。 由于共享的内核空间，因此这些容器需要相同的内核版本和配置。

**HYPER-V 隔离**： 通过在高度优化的虚拟机上运行每个容器由 Windows Server 容器提供的隔离上扩展。 在此配置中，容器主机的内核不与同一主机上的其他容器共享。 这些容器专门用于恶意多租户托管，与 VM 的相同安全保证。 由于这些容器不与主机或主机上的其他容器共享内核，它们可以使用不同版本和 （具有支持的版本） 的配置运行内核。 例如，Windows 10 上的所有 Windows 容器都使用 HYPER-V 隔离以利用 Windows Server 内核版本和配置。

在 Windows 上运行一个容器，或 HYPER-V 隔离不是运行时决定。 可能会选择最初，创建具有 HYPER-V 隔离容器，并在运行时，选择为改为运行 Windows Server 容器。

### <a name="additional-resources"></a>其他资源

-   **Windows 容器文档**

    [https://docs.microsoft.com/virtualization/windowscontainers/](https://docs.microsoft.com/virtualization/windowscontainers/)

-   **Windows 容器基础知识**

    [https://docs.microsoft.com/virtualization/windowscontainers/about/](https://docs.microsoft.com/virtualization/windowscontainers/about/)

-   **信息图： Microsoft 和容器**

    [https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf](https://info.microsoft.com/rs/157-GQE-382/images/Container%20infographic%201.4.17.pdf)

>[!div class="step-by-step"]
[上一页](how-to-deploy-existing-net-apps-to-azure-app-service.md)
[下一页](when-not-to-deploy-to-windows-containers.md)

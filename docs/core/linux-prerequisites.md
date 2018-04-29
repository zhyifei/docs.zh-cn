---
title: Linux 上 .NET Core 的先决条件
description: 支持的 Linux 版本和 .NET Core 依赖项，用于在 Linux 计算机上开发、部署和运行 .NET Core 应用程序。
author: jralexander
ms.author: johalex
ms.date: 04/19/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 9d986ed56bbc6f803988fde4b5500cd5d5364050
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="prerequisites-for-net-core-on-linux"></a>Linux 上 .NET Core 的先决条件

本文介绍了在 Linux 上开发 .NET Core 应用程序所需的依赖项。 支持的 Linux 发行版本/版本和依赖项适用于在 Linux 上开发 .NET Core 应用程序的两种方法：

* [结合使用命令行和常用编辑器](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code](https://code.visualstudio.com/)

> [!NOTE]
> 生产服务器/环境不需要 .NET Core SDK 包。 部署到生产环境的应用只需要 .NET Core 运行时包。 .NET Core 运行时与应用一同部署为独立部署的一部分，但是，对于依赖框架的部署应用，它必须单独部署。 有关依赖框架和独立部署类型的更多信息，请参阅 [.NET Core 应用程序部署](./deploying/index.md)。 另请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)，了解特定准则。

## <a name="supported-linux-versions"></a>支持的 Linux 版本

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.x 将 Linux 视为一个操作系统。 支持的 Linux 分发都对应有一个 Linux 内部版本（根据芯片体系结构）。

以下 Linux 64 位（`x86_64` 或 `amd64`）发行版本/版本支持 NET Core 2.x：

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 27、26
* Debian 9、8.7 或更高版本
* Ubuntu 17.10、16.04、14.04
* Linux Mint 18、17
* openSUSE 42.3 或更高版本
* SUSE Enterprise Linux (SLES) 12 Service Pack 2 或更高版本

有关 .NET Core 2.x 支持的操作系统、分发和版本、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 2.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)。

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

以下 Linux 64 位（`x86_64` 或 `amd64`）发行版本/版本支持 .NET Core 1.x：

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 26
* Debian 8.2 或更高版本
* Ubuntu 16.04、14.04
* Linux Mint 18、17
* openSUSE 42.3 或更高版本 (.NET Core 1.1)

有关支持 .NET Core 1.x 的操作系统、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 1.x - 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)。

---

## <a name="linux-distribution-dependencies"></a>Linux 发行版本依赖项

以下各项用作示例。 确切的版本和名称可能因所选 Linux 发行版本略有不同。

### <a name="ubuntu"></a>Ubuntu

Ubuntu 发行版本需要安装以下库：

* libunwind8
* liblttng-ust0
* libcurl3
* libssl1.0.0
* libuuid1
* libkrb5-3
* zlib1g
* libicu52（针对 14.x）
* libicu55（针对 16.x）
* libicu57（针对 17.x）

### <a name="centos"></a>CentOS

CentOS 发行版本需要安装以下库：

* libunwind
* lttng-ust
* libcurl
* openssl-libs
* libuuid
* krb5-libs
* libicu
* zlib

有关依赖项的详细信息，请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)。

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>使用本机安装程序安装 .NET Core 依赖项

.NET Core 本机安装程序适用于支持的 Linux 发行版本/版本。 本机安装程序需要拥有对服务器的管理员 (sudo) 访问权限。 使用本机安装程序的优势在于，可以安装所有 .NET Core 本机依赖项。 本机安装程序还会在整个系统内安装 .NET Core SDK。

在 Linux 上，安装程序包有两种使用方式：

* 使用基于源的包管理器，如适用于 Ubuntu 的 apt-get，或适用于 CentOS/RHEL 的 yum。
* 使用包本身（DEB 或 RPM）。

### <a name="scripting-installs-with-the-net-core-installer-script"></a>使用 .NET Core 安装程序脚本编写安装脚本

[dotnet-install 脚本](./tools/dotnet-install-script.md)用于执行 CLI 工具链和共享运行时的非管理员安装。 可通过 [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh) 下载脚本。

安装程序 bash 脚本用于自动化方案和非管理员安装。 此脚本也读取 PowerShell 开关，因此可以与 Linux/OS X 系统上的脚本结合使用。

## <a name="install-net-core-for-supported-red-hat-enterprise-linux-rhel-versions"></a>为支持的 Red Hat Enterprise Linux (RHEL) 版本安装 .NET Core

在支持的 RHEL 版本上安装 .NET Core：

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

为确保获得最新的安装信息，请遵循适用于支持的 RHEL 版本的 [.NET Core 2.x SDK 和 Runtime 安装程序说明](https://www.microsoft.com/net/download/linux-package-manager/rhel/sdk-current)。

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**.NET Core 1.1**

1. 从系统中删除 .NET Core 的所有旧预览版本。

2.  有关 Red Hat Enterprise Linux 上最新的 .NET Core 1.1 安装信息，请参阅 [.NET Core 1.1 入门指南](https://access.redhat.com/documentation/en-us/net_core/1.1/html/getting_started_guide/)
     
**.NET Core 1.0**

1. 从系统中删除 .NET Core 的所有旧预览版本。

2.  有关 Red Hat Enterprise Linux 上最新的 .NET Core 1.0 安装信息，请参阅 [.NET Core 1.0 入门指南](https://access.redhat.com/documentation/en-us/net_core/1.0/html/getting_started_guide/)

若要获取 Red Hat .NET 通道访问注册方面的帮助，请参阅 Red Hat 提供的 [.NET Core 1.1 入门指南的第 1 章](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/)。

---

## <a name="install-net-core-for-supported-ubuntu-and-linux-mint-distributionsversions-64-bit"></a>为支持的 Ubuntu 和 Linux Mint 分发/版本（64 位）安装 .NET Core

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. 从系统中删除 .NET Core 的所有旧预览版本。

2. 在支持的 Ubuntu 和 Linux Mint 分发/版本（64 位）上安装 .NET Core 2.x：

**.NET Core 2.0**

|Runtime / SDK          |Ubuntu 17.10  |Ubuntu 16.04 / Linux Mint 18|Ubuntu 14.04 / Linux Mint 17|
|-------------------------|--------------|----------------------------|----------------------------|
|.NET Core Runtime 2.0.6  |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.6)|[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.6)          |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.6)            |
|.NET Core Runtime 2.0.5  |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.5)|[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.5)          |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.5)            |
|.NET Core SDK 2.1.103    |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.103)|[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.103)            |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.103)            |
|.NET Core SDK 2.0.3      |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.3)|[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.3)          |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.3)            |

**.NET Core 2.1**

>[!IMPORTANT]
> 若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview)。

|Runtime / SDK                  |Ubuntu 17.10    |Ubuntu 16.04 / Linux Mint 18|Ubuntu 14.04 / Linux Mint 17|
|---------------------------------|----------------|----------------------------|----------------------------|
|.NET Core Runtime 2.1.0-preview2 |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-preview2)|[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-preview2)            |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-preview2)            |
|.NET Core Runtime 2.1.0-preview1 |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0-preview1)|[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0-preview1)            |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0-preview1)            |
|.NET Core SDK 2.1.300-preview2   |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-preview2)|[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-preview2)            |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-preview2)
|.NET Core SDK 2.1.300-preview1   |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300-preview1)|[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300-preview1)            |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300-preview1)            |


# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. 从系统中删除 .NET Core 的所有旧预览版本。

2. 在支持的 Ubuntu 和 Linux Mint 分发/版本（64 位）上安装 .NET Core 1.x：

| Runtime / SDK         |Ubuntu 16.04 / Linux Mint 18|Ubuntu 14.04 / Linux Mint 17|
|-------------------------|----------------------------|----------------------------|
|.NET Core Runtime 1.1.7  |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core Runtime 1.1.6  |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-16.04-x64-binaries)            |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core Runtime 1.0.10 |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-16.04-x64-binaries)            |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core Runtime 1.0.9  |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-16.04-x64-binaries)            |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.1.8      |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-16.04-x64-binaries)            |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.1.7      |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.0.4      |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-16.04-x64-binaries)            |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-14.04-x64-binaries)            |
|.NET Core SDK 1.0.1      |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-16.04-x64-binaries)            |[安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-14.04-x64-binaries)            |

---

## <a name="install-net-core-for-supported-debian-versions-64-bit"></a>为支持的 Debian 版本（64 位）安装 .NET Core

在支持的 Debian 版本（64 位）上安装 .NET Core：

> [!NOTE]
> 必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. 从系统中删除 .NET Core 的所有旧预览版本。

2. 在支持的 Debian 版本（64 位）上安装 .NET Core 2.x：

**.NET Core 2.0**

|Runtime / SDK          |Debian 9       |Debian 8       |
|-------------------------|---------------|---------------|
|.NET Core Runtime 2.0.6  |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.6)   |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.6)   |
|.NET Core Runtime 2.0.5  |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.5)   |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.5)   |
|.NET Core SDK 2.1.103    |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.103)   |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.103)   |
|.NET Core SDK 2.0.3      |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.3)   |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.3)   |

**.NET Core 2.1**

>[!IMPORTANT]
> 若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview)。

|Runtime / SDK                  |Debian 9       |Debian 8       |
|---------------------------------|---------------|---------------|
|.NET Core Runtime 2.1.0-preview2 |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-preview2)   |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-preview2)   |
|.NET Core Runtime 2.1.0-preview1 |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0-preview1)   |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0-preview1)   |
|.NET Core SDK 2.1.300-preview2   |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-preview2)   |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-preview2)   |
|.NET Core SDK 2.1.300-preview1   |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300-preview1)   |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300-preview1)   |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. 从系统中删除 .NET Core 的所有旧预览版本。

2. 在 Debian 9 或 Debian 8 上安装 .NET Core 1.x：

* .NET Core Runtime 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-debian-x64-binaries)
* .NET Core Runtime 1.1.6 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-debian-x64-binaries)
* .NET Core Runtime 1.0.10 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-debian-x64-binaries)
* .NET Core Runtime 1.0.9 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-debian-x64-binaries)
* .NET Core SDK 1.1.8 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-debian-x64-binaries)
* .NET Core SDK 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-debian-x64-binaries)
* .NET Core SDK 1.0.4 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-debian-x64-binaries)
* .NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)

---

## <a name="install-net-core-for-supported-fedora-versions-64-bit"></a>为支持的 Fedora 版本（64 位）安装 .NET Core

在支持的 Fedora 版本上安装 .NET Core：

> [!NOTE]
> 必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. 从系统中删除 .NET Core 的所有旧预览版本。

2. 在支持的 Fedora 版本（64 位）上安装 .NET Core 2.x：

**.NET Core 2.0**

|Runtime / SDK          |Fedora 26 或更高版本 |Fedora 25 或以前版本 |
|-------------------------|-------------------|----------------------|
|.NET Core Runtime 2.0.6  |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.6)       |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.6)           |
|.NET Core Runtime 2.0.5  |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.5)       |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.5)           |
|.NET Core SDK 2.1.103    |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.103)       |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.103)           |
|.NET Core SDK 2.0.3      |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.0.3)       |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.0.3)           |

**.NET Core 2.1**

>[!IMPORTANT]
> 若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview)。

|Runtime / SDK                  |Fedora 26 或更高版本 |Fedora 25 或以前版本 |
|---------------------------------|-------------------|----------------------|
|.NET Core Runtime 2.1.0-preview2 |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview2)       |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.1.0-preview2)           |
|.NET Core Runtime 2.1.0-preview1 |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.1.0-preview1)       |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.1.0-preview1)           |
|.NET Core SDK 2.1.300-preview2   |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.300-preview2)       |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.300-preview2)           |
|.NET Core SDK 2.1.300-preview1   |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.300-preview1)       |[安装链接](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.300-preview1)           |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. 从系统中删除 .NET Core 的所有旧预览版本。

2. 在支持的 Fedora 版本（64 位）上安装 .NET Core 1.x：

**Fedora 24**

* .NET Core Runtime 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-fedora-24-x64-binaries)
* .NET Core Runtime 1.1.6 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-fedora-24-x64-binaries)
* .NET Core SDK 1.1.8 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-fedora-24-x64-binaries)
* .NET Core SDK 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-fedora-24-x64-binaries)
* .NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)

**Fedora 23**

* .NET Core Runtime 1.0.9 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-fedora-23-x64-binaries)
* .NET Core SDK 1.0.4 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-fedora-23-x64-binaries)
* .NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-fedora-23-x64-binaries)

---

## <a name="install-net-core-for-supported-centos-and-oracle-linux-distributionsversions-64-bit"></a>为支持的 CentOS 和 Oracle Linux 分发/版本（64 位）安装 .NET Core

为支持的 CentOS 和 Oracle Linux 分发/版本（64 位）安装 .NET Core：

> [!NOTE]
> 必须有用户控制目录，才能通过 tar.gz 在 Linux 系统上进行安装。

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. 从系统中删除 .NET Core 的所有旧预览版本。

2. 在支持的 CentOS 和 Oracle Linux 分发/版本（64 位）上安装 .NET Core 2.x：

**.NET Core 2.0**

* .NET Core Runtime 2.0.6 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6)
* .NET Core Runtime 2.0.5 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.5)
* .NET Core SDK 2.1.103 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.103)
* .NET Core SDK 2.0.3 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.3)
 
**.NET Core 2.1**

>[!IMPORTANT]
> 若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview/)。

* .NET Core Runtime 2.1.0-preview2 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview2)
* .NET Core Runtime 2.1.0-preview1 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0-preview1)
* .NET Core SDK 2.1.300-preview2 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview2)
* .NET Core SDK 2.1.300-preview1 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300-preview1)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. 从系统中删除 .NET Core 的所有旧预览版本。

2. 在支持的 CentOS 和 Oracle Linux 发行版本/版本（64 位）上安装 .NET Core 1.x：

* .NET Core Runtime 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-centos-x64-binaries)
* .NET Core Runtime 1.1.6 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-centos-x64-binaries)
* .NET Core Runtime 1.0.10 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-centos-x64-binaries)
* .NET Core Runtime 1.0.9 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-centos-x64-binaries)
* .NET Core SDK 1.1.8 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-centos-x64-binaries)
* .NET Core SDK 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-centos-x64-binaries)
* .NET Core SDK 1.0.4 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-centos-x64-binaries)
* .NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-centos-x64-binaries)

---

## <a name="install-net-core-for-supported-suse-linux-enterprise-server-and-opensuse-distributionsversions-64-bit"></a>为支持的 SUSE Linux Enterprise Server 和 OpenSUSE 发行版本/版本（64 位）安装 .NET Core

为支持的 SUSE Linux Enterprise Server 和 OpenSUSE 发行版本/版本（64 位）安装 .NET Core 2.x：

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. 从系统中删除 .NET Core 的所有旧预览版本。

2. 在支持的 SUSE Linux Enterprise Server 和 OpenSUSE 发行版本/版本（64 位）上安装 .NET Core 2.x：

**.NET Core 2.0**

* .NET Core Runtime 2.0.6 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.6)
* .NET Core Runtime 2.0.5 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.5)
* .NET Core SDK 2.1.103 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.103)
* .NET Core SDK 2.0.3 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.3)
 
**.NET Core 2.1**

>[!IMPORTANT]
> 若要将 .NET Core 2.1 与 Visual Studio 一起使用，需要[安装 Visual Studio 2017 15.7 Preview 1 或更高版本](https://www.visualstudio.com/vs/preview)。

* .NET Core Runtime 2.1.0-preview2 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview2)
* .NET Core Runtime 2.1.0-preview1 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0-preview1)
* .NET Core SDK 2.1.300-preview2 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview2)
* .NET Core SDK 2.1.300-preview1 [安装链接](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300-preview1)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. 从系统中删除 .NET Core 的所有旧预览版本。

2. 在支持的 SUSE Linux Enterprise Server 和 OpenSUSE 发行版本/版本（64 位）上安装 .NET Core 1.x：

**SUSE Linux Enterprise Server 13.2**

* .NET Core Runtime 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-opensuse-13.2-x64-binaries)
* .NET Core Runtime 1.1.6 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-opensuse-13.2-x64-binaries)
* .NET Core SDK 1.1.7 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-opensuse-13.2-x64-binaries)

**openSUSE 24**

* .NET Core SDK 1.0.4 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-opensuse-24-x64-binaries)
* .NET Core SDK 1.0.1 [安装链接](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-opensuse-24-x64-binaries)

---

> [!IMPORTANT]
> 若对在支持的 Linux 分发/版本上安装 .NET Core 有疑问，请参阅下方你所安装的分发/版本的相应主题：
> * [.NET Core 2.1 已知问题](https://github.com/dotnet/core/tree/master/release-notes/2.1)
> * [.NET Core 2.0 已知问题](https://github.com/dotnet/core/tree/master/release-notes/2.0)
> * [.NET Core 1.1 已知问题](https://github.com/dotnet/core/blob/master/release-notes/1.1)
> * [.NET Core 1.0 已知问题](https://github.com/dotnet/core/blob/master/release-notes/1.0)
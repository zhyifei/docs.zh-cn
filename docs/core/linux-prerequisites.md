---
title: Linux 上 .NET Core 的先决条件
description: 支持的 Linux 版本和 .NET Core 依赖项，用于在 Linux 计算机上开发、部署和运行 .NET Core 应用程序。
author: leecow
ms.author: leecow
ms.date: 10/11/2019
ms.openlocfilehash: 0e798e86fcf88a1b7a67f50c2301e10ad725fad8
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72521485"
---
# <a name="prerequisites-for-net-core-on-linux"></a>Linux 上 .NET Core 的先决条件

本文介绍了在 Linux 上开发 .NET Core 应用程序所需的依赖项。 支持的 Linux 发行版本/版本和依赖项适用于在 Linux 上开发 .NET Core 应用程序的两种方法：

- [结合使用命令行和常用编辑器](tutorials/using-with-xplat-cli.md)
- [Visual Studio Code](https://code.visualstudio.com/)

> [!NOTE]
> 生产服务器/环境不需要 .NET Core SDK 包。 部署到生产环境的应用只需要 .NET Core 运行时包。 .NET Core 运行时与应用一同部署为独立部署的一部分，但是，对于依赖框架的部署应用，它必须单独部署。 有关依赖框架和独立部署类型的更多信息，请参阅 [.NET Core 应用程序部署](./deploying/index.md)。 另请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)，了解特定准则。

## <a name="supported-linux-versions"></a>支持的 Linux 版本

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

.NET Core 3.0 将 Linux 视为一个操作系统。 支持的 Linux 分发都对应有一个 Linux 内部版本（根据芯片体系结构）。 

有关下载链接和详细信息，请参阅 [.NET Core 3.0 下载](https://dotnet.microsoft.com/download/dotnet-core/3.0)。

以下 Linux 发行版本/版本支持 .NET Core 3.0：

> [!NOTE]
> `+` 表示最低版本。

| (OS)                             | Version               | 体系结构    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6+、7                 | X64 |
| Oracle Linux                   | 7                     | X64 |
| CentOS                         | 7                     | X64 |
| Fedora                         | 29+                   | X64 |
| Debian                         | 9+                    | x64、ARM32、ARM64 |
| Ubuntu                         | 16.04+                | x64、ARM32、ARM64 |
| Linux Mint                     | 18+                   | X64 |
| openSUSE                       | 15+                   | X64 |
| SUSE Enterprise Linux (SLES)   | 12 SP2+               | X64 |
| Alpine Linux                   | 3.8+                  | x64、ARM64 |

有关 .NET Core 3.0 支持的操作系统、发行版本和版本、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。

有关如何在 ARM64 上安装 .NET Core 3.0 的详细信息，请参阅[在 Linux ARM64 上安装 .NET Core 3.0](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)。

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

.NET Core 2.2 将 Linux 视为一个操作系统。 支持的 Linux 分发都对应有一个 Linux 内部版本（根据芯片体系结构）。

有关下载链接和详细信息，请参阅 [.NET Core 2.2 下载](https://dotnet.microsoft.com/download/dotnet-core/2.2)。

以下 Linux 发行版本/版本支持 .NET Core 2.2：

> [!NOTE]
> `+` 表示最低版本。

| (OS)                             |  Version                |  体系结构   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6、7                   | X64 |
| Oracle Linux                   |  7                      | X64 |
| CentOS                         |  7                      | X64 |
| Fedora                         |  29、30                 | X64 |
| Debian                         |  9                      | x64、ARM32 |
| Ubuntu                         |  16.04、18.04、18.10    | x64、ARM32 |
| Linux Mint                     |  17、18                 | X64 |
| openSUSE                       |  15+                    | X64 |
| SUSE Enterprise Linux (SLES)   |  12 SP2+                | X64 |
| Alpine Linux                   |  3.7+                   | X64 |

要在完整列表中了解 .NET Core 2.2 支持的操作系统、发行版本和版本、生命周期策略链接和不支持的 OS 版本，请参阅 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1 将 Linux 视为一个操作系统。 支持的 Linux 分发都对应有一个 Linux 内部版本（根据芯片体系结构）。

有关下载链接和详细信息，请参阅 [.NET Core 2.1 下载](https://dotnet.microsoft.com/download/dotnet-core/2.1)。

以下 Linux 发行版本/版本支持 .NET Core 2.1：

| (OS)                             |  Version                |  体系结构   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6、7、8                | X64 |
| Oracle Linux                   |  7                      | X64 |
| CentOS                         |  7                      | X64 |
| Fedora                         |  29、30                 | X64 |
| Debian                         |  9                      | x64、ARM32 |
| Ubuntu                         |  16.04、18.04、19.04    | x64、ARM32 |
| Linux Mint                     |  17、18                 | X64 |
| openSUSE                       |  42.3+                  | X64 |
| SUSE Enterprise Linux (SLES)   |  12 SP2+                | X64 |
| Alpine Linux                   |  3.7+                   | X64 |

有关 .NET Core 2.1 支持的操作系统、发行版本和版本、不支持的 OS 版本和生命周期策略链接的完整列表，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。

---

## <a name="linux-distribution-dependencies"></a>Linux 发行版本依赖项

以下各项用作示例。 确切的版本和名称可能因所选 Linux 发行版本略有不同。

### <a name="ubuntu"></a>Ubuntu

Ubuntu 发行版本需要安装以下库：

- liblttng-ust0
- libcurl3（针对 14.x 和 16.x）
- libcurl4（针对 18.x）
- libssl1.0.0
- libkrb5-3
- zlib1g
- libicu52（针对 14.x）
- libicu55（针对 16.x）
- libicu57（针对 17.x）
- libicu60（针对 18.x）

对于 .NET Core 2.1 之前的版本，还需要以下依赖项：

- libunwind8
- libuuid1

对于使用 System.Drawing.Common  程序集的 .NET Core 应用程序，还需要以下依赖项：

* libgdiplus（版本 6.0.1 或更高版本）

> [!NOTE]
> 大多数 Ubuntu 版本都包含 libgdiplus 的早期版本。 可以通过将 Mono 存储库添加到系统来安装最新版 libgdiplus。 有关详细信息，请参阅 <https://www.mono-project.com/download/stable/>。

### <a name="centos-and-fedora"></a>CentOS 和 Fedora

CentOS 发行版本需要安装以下库：

- lttng-ust
- libcurl
- openssl-libs
- krb5-libs
- libicu
- zlib

Fedora 用户：如果 openssl 的版本为 1.1 及以上版本，则需要安装 compat-openssl10。

对于 .NET Core 2.1 之前的版本，还需要以下依赖项：

- libunwind
- libuuid

有关依赖项的详细信息，请参阅[独立式 Linux 应用程序](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)。

对于使用 System.Drawing.Common  程序集的 .NET Core 应用程序，还需要以下依赖项：

* libgdiplus（版本 6.0.1 或更高版本）

> [!NOTE]
> CentOS 和 Fedora 的大多数版本都包含 libgdiplus 的早期版本。 可以通过将 Mono 存储库添加到系统来安装最新版 libgdiplus。 有关详细信息，请参阅 <https://www.mono-project.com/download/stable/>。

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>使用本机安装程序安装 .NET Core 依赖项

.NET Core 本机安装程序适用于支持的 Linux 发行版本/版本。 本机安装程序需要拥有对服务器的管理员 (sudo) 访问权限。 使用本机安装程序的优势在于，可以安装所有 .NET Core 本机依赖项。 本机安装程序还会在整个系统内安装 .NET Core SDK。

在 Linux 上，安装程序包有两种使用方式：

- 使用基于源的包管理器，如适用于 Ubuntu 的 apt-get，或适用于 CentOS/RHEL 的 yum。
- 使用包本身（DEB 或 RPM）。

### <a name="scripting-installs-with-the-net-core-installer-script"></a>使用 .NET Core 安装程序脚本编写安装脚本

[dotnet-install 脚本](./tools/dotnet-install-script.md)用于执行 CLI 工具链和共享运行时的非管理员安装。 可通过 <https://dot.net/v1/dotnet-install.sh> 下载脚本。

此脚本会默认安装最新的“LTS”版本，当前为 .NET Core 1.1。 要安装 .NET Core 2.1，请使用以下开关运行脚本：

```bash
./dotnet-install.sh -c Current
```

安装程序 bash 脚本用于自动化方案和非管理员安装。 此脚本也读取 PowerShell 开关，因此可以与 Linux/OS X 系统上的脚本结合使用。

## <a name="troubleshoot"></a>疑难解答

若对在支持的 Linux 分发/版本上安装 .NET Core 有疑问，请参阅下方你所安装的分发/版本的相应主题：

- [.NET Core 3.0 已知问题](https://github.com/dotnet/core/tree/master/release-notes/3.0)
- [.NET Core 2.2 已知问题](https://github.com/dotnet/core/tree/master/release-notes/2.2)
- [.NET Core 2.1 已知问题](https://github.com/dotnet/core/tree/master/release-notes/2.1)
- [.NET Core 1.1 已知问题](https://github.com/dotnet/core/blob/master/release-notes/1.1)
- [.NET Core 1.0 已知问题](https://github.com/dotnet/core/blob/master/release-notes/1.0)

---
title: .NET Core SDK 和运行时依赖项 - .NET Core
description: 详细介绍在 Windows、Linux 和 macOS 上安装 .NET Core SDK 和运行时的操作系统和 CPU 体系结构先决条件。
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: a535048fc8756b55068098ad61fdc37fc8c1f04e
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74999007"
---
# <a name="net-core-dependencies-and-requirements"></a>.NET Core 依赖项和要求

本文详细介绍了 .NET Core 支持的操作系统和 CPU 体系结构。

## <a name="supported-operating-systems"></a>支持的操作系统

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31tabnetcore31"></a>[.NET Core 3.1](#tab/netcore31)

.NET Core 3.1 支持下列 Windows 版本：

> [!NOTE]
> `+` 表示最低版本。

| (OS)                            | Version                        | 体系结构   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows 客户端                | 7 SP1+、8.1                    | x64、x86        |
| Windows 10 客户端             | 版本 1607+                  | x64、x86        |
| Windows Server                | 2012 R2+                       | x64、x86        |
| Nano Server                   | 版本 1803+                  | x64、ARM32      |

有关 .NET Core 3.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)。

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

.NET Core 3.0 支持下列 Windows 版本：

> [!NOTE]
> `+` 表示最低版本。

| (OS)                            | Version                        | 体系结构   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows 客户端                | 7 SP1+、8.1                    | x64、x86        |
| Windows 10 客户端             | 版本 1607+                  | x64、x86        |
| Windows Server                | 2012 R2+                       | x64、x86        |
| Nano Server                   | 版本 1803+                  | x64、ARM32      |

有关 .NET Core 3.0 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

.NET Core 2.2 支持下列 Windows 版本：

> [!NOTE]
> `+` 表示最低版本。

| (OS)                            | Version                        | 体系结构   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows 客户端                | 7 SP1+、8.1                    | x64、x86        |
| Windows 10 客户端             | 版本 1607+                  | x64、x86        |
| Windows Server                | 2008 R2 SP1+                   | x64、x86        |
| Nano Server                   | 版本 1803+                   | x64、ARM32      |

有关 .NET Core 2.2 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1 支持下列 Windows 版本：

> [!NOTE]
> `+` 表示最低版本。

| (OS)                            | Version                        | 体系结构   |
| ----------------------------- | ------------------------------ | --------------- |
| Windows 客户端                | 7 SP1+、8.1                    | x64、x86        |
| Windows 10 客户端             | 版本 1607+                  | x64、x86        |
| Windows Server                | 2008 R2 SP1+                   | x64、x86        |
| Nano Server                   | 版本 1803+                  | x64            |

有关 .NET Core 2.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a>Windows 7/Vista/8.1/Server 2008 R2

如果要在以下 Windows 版本上安装 .NET SDK 或运行时，则需要其他依赖项：

- Windows 7 SP1
- Windows Vista SP 2
- Windows 8.1
- Windows Server 2008 R2
- Windows Server 2012 R2

安装以下组件：

- [Microsoft Visual C++ 2015 Redistributable 更新 3](https://www.microsoft.com/download/details.aspx?id=52685)。
- [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

如果遇到一个以下错误，也需要满足上述要求：

> 此程序无法启动，因为计算机上缺少 api-ms-win-crt-runtime-l1-1-0.dll  。 尝试重新安装该程序以解决此问题。
>
> \- 或 -
>
> 已找到库 hostfxr.dll  ，但未能将其从 C:\\\<path_to_app>\\hostfxr.dll 中加载  。

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31tabnetcore31"></a>[.NET Core 3.1](#tab/netcore31)

.NET Core 3.1 将 Linux 视为一个操作系统。 对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。

以下 Linux 发行版/版本支持 .NET Core 3.1：

> [!NOTE]
> `+` 表示最低版本。

| (OS)                             | Version               | 体系结构    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6、7、8               | X64 |
| CentOS                         | 7+                    | X64 |
| Oracle Linux                   | 7+                    | X64 |
| Fedora                         | 29+                   | X64 |
| Debian                         | 9+                    | x64、ARM32、ARM64 |
| Ubuntu                         | 16.04+                | x64、ARM32、ARM64 |
| Linux Mint                     | 18+                   | X64 |
| openSUSE                       | 15+                   | X64 |
| SUSE Enterprise Linux (SLES)   | 12 SP2+               | X64 |
| Alpine Linux                   | 3.10+                 | x64、ARM64 |

有关 .NET Core 3.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md)。

有关如何在 ARM64（内核 4.14+）上安装 .NET Core 3.1 的详细信息，请参阅[在 Linux ARM64 上安装 .NET Core 3.0](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)。

> [!IMPORTANT]
> ARM64 支持需要 Linux 内核 4.14 或更高版本。 某些 linux 发行版满足此要求，而另一些则不满足。 例如，支持 Ubuntu 18.04，但不支持 Ubuntu 16.04。

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

.NET Core 3.0 将 Linux 视为一个操作系统。 对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。

以下 Linux 发行版本/版本支持 .NET Core 3.0：

> [!NOTE]
> `+` 表示最低版本。

| (OS)                             | Version               | 体系结构    |
| ------------------------------ | --------------------- | ---------------- |
| Red Hat Enterprise Linux       | 6、7、8               | X64 |
| CentOS                         | 7+                    | X64 |
| Oracle Linux                   | 7+                    | X64 |
| Fedora                         | 29+                   | X64 |
| Debian                         | 9+                    | x64、ARM32、ARM64 |
| Ubuntu                         | 16.04+                | x64、ARM32、ARM64 |
| Linux Mint                     | 18+                   | X64 |
| openSUSE                       | 15+                   | X64 |
| SUSE Enterprise Linux (SLES)   | 12 SP2+               | X64 |
| Alpine Linux                   | 3.8+                  | x64、ARM64 |

有关 .NET Core 3.0 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 3.0 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)。

有关如何在 ARM64 上安装 .NET Core 3.0 的详细信息，请参阅[在 Linux ARM64 上安装 .NET Core 3.0](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213)。

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

.NET Core 2.2 将 Linux 视为一个操作系统。 对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。

以下 Linux 发行版本/版本支持 .NET Core 2.2：

> [!NOTE]
> `+` 表示最低版本。

| (OS)                             |  Version                |  体系结构   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6、7                   | X64 |
| CentOS                         |  7                      | X64 |
| Oracle Linux                   |  7                      | X64 |
| Fedora                         |  29、30                 | X64 |
| Debian                         |  9                      | x64、ARM32 |
| Ubuntu                         |  16.04、18.04、18.10、19.04    | x64、ARM32 |
| Linux Mint                     |  17、18                 | X64 |
| openSUSE                       |  15+                    | X64 |
| SUSE Enterprise Linux (SLES)   |  12 SP2+                | X64 |
| Alpine Linux                   |  3.8+                   | X64 |

有关 .NET Core 2.2 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.2 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)。

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1 将 Linux 视为一个操作系统。 对于支持的 Linux 发行版，每芯片体系结构都对应有一个 Linux 内部版本。

以下 Linux 发行版本/版本支持 .NET Core 2.1：

> [!NOTE]
> `+` 表示最低版本。

| (OS)                             |  Version                |  体系结构   |
| ------------------------------ | ----------------------- | ---------------- |
| Red Hat Enterprise Linux       |  6、7、8                | X64 |
| CentOS                         |  7+                     | X64 |
| Oracle Linux                   |  7+                     | X64 |
| Fedora                         |  29+                    | X64 |
| Debian                         |  9                      | x64、ARM32 |
| Ubuntu                         |  16.04、18.04、19.04、19.10    | x64、ARM32 |
| Linux Mint                     |  17+                    | X64 |
| openSUSE                       |  15+                    | X64 |
| SUSE Enterprise Linux (SLES)   |  12 SP2+                | X64 |
| Alpine Linux                   |  3.8+                   | X64 |

有关 .NET Core 2.1 支持的操作系统、发行版和生命周期策略的详细信息，请参阅 [.NET Core 2.1 支持的 OS 版本](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)。

---

## <a name="linux-distribution-dependencies"></a>Linux 发行版本依赖项

根据 Linux 发行版，你可能需要安装其他依赖项。

> [!IMPORTANT]
> 确切的版本和名称可能因所选 Linux 发行版本略有不同。

### <a name="ubuntu"></a>Ubuntu

Ubuntu 发行版需要安装以下库：

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

对于使用 System.Drawing.Common  程序集的 .NET Core 应用，还需要以下依赖项：

- libgdiplus（版本 6.0.1 或更高版本）

> [!WARNING]
> 大多数 Ubuntu 版本都包含 libgdiplus 的早期版本。 可以通过将 Mono 存储库添加到系统来安装最新版 libgdiplus。 有关详细信息，请参阅 <https://www.mono-project.com/download/stable/>。

### <a name="centos-and-fedora"></a>CentOS 和 Fedora

CentOS 发行版本需要安装以下库：

- lttng-ust
- libcurl
- openssl-libs
- krb5-libs
- libicu
- zlib

Fedora 用户：如果 OpenSSL 的版本为 1.1 及更高版本，则需要安装 compat-openssl10  。

对于 .NET Core 2.0，还需要以下依赖项：

- libunwind
- libuuid

有关依赖项的详细信息，请参阅[独立式 Linux 应用](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)。

对于使用 System.Drawing.Common  程序集的 .NET Core 应用，还需要以下依赖项：

- libgdiplus（版本 6.0.1 或更高版本）

> [!WARNING]
> CentOS 和 Fedora 的大多数版本都包含 libgdiplus 的早期版本。 可以通过将 Mono 存储库添加到系统来安装最新版 libgdiplus。 有关详细信息，请参阅 <https://www.mono-project.com/download/stable/>。

::: zone-end

::: zone pivot="os-macos"

以下 macOS 版本支持 .NET Core：

> [!NOTE]
> `+` 表示最低版本。

| .NET Core 版本 | macOS                 | 体系结构 |     |
| ----------------- | --------------------- | --------------| --- |
| 3.1               | High Sierra (10.13+)  | X64 | [详细信息](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| 3.0               | High Sierra (10.13+)  | X64 | [详细信息](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| 2.2               | Sierra (10.12+)       | X64 | [详细信息](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| 2.1               | Sierra (10.12+)       | X64 | [详细信息](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

## <a name="libgdiplus"></a>libgdiplus

使用 System.Drawing.Common  程序集的 .NET Core 应用程序要求安装 libgdiplus。

获取 libgdiplus 的一个简单方法是使用适用于 macOS 的 [Homebrew (“brew”)](https://brew.sh/) 包。 在安装 brew 后，通过在终端（命令）提示符处执行以下命令来安装 libgdiplus  ：

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a>后续步骤

- 若要开发并运行应用，请安装 [.NET Core SDK](sdk.md)（包括运行时）。
- 若要运行其他人创建的应用，请安装 [.NET Core 运行时](runtime.md)。

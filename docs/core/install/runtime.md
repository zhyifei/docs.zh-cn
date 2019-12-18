---
title: 在 Windows、Linux 和 macOS 上安装 .NET Core 运行时 - .NET Core
description: 了解如何在 Windows、Linux 和 macOS 上安装 .NET Core。 发现运行 .NET Core 应用所需的依赖项。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 8f4a895ad66dea3063a32f785e4c521196266978
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998887"
---
# <a name="install-the-net-core-runtime"></a>安装 .NET Core 运行时

本文介绍如何下载和安装 .NET Core 运行时。 .NET Core 运行时用于运行使用 .NET Core 创建的应用。

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a>使用安装程序安装

Windows 具有独立的安装程序，可用于安装 .NET Core 3.1 运行时：

- [x64（64 位）CPU](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [x86（32 位）CPU](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a>使用安装程序安装

macOS 具有独立的安装程序，可用于安装 .NET Core 3.1 运行时：

- [x64（64 位）CPU](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a>使用包管理器安装

可使用许多常见的 Linux 包管理器安装 .NET Core 运行时。 有关详细信息，请参阅 [Linux 包管理器 - 安装 .NET Core](linux-package-manager-rhel7.md)。

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>使用 PowerShell 自动化安装

[dotnet-install 脚本](../tools/dotnet-install-script.md)用于运行时的自动化和非管理员安装。 可从 [dotnet-install 脚本引用页](../tools/dotnet-install-script.md)下载该脚本。

此脚本默认安装最新的[长期支持 (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 版本，即 .NET Core 3.1。 可通过指定 `Channel` 开关以选择特定版本。 包括 `Runtime` 开关以安装运行时。 否则，该脚本安装 [SDK](sdk.md)。

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> 以上命令安装 ASP.NET Core 运行时，用于实现最大的兼容性。 ASP.NET Core 运行时还包括标准 .NET Core 运行时。

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a>使用 Bash 自动化安装

[dotnet-install 脚本](../tools/dotnet-install-script.md)用于运行时的自动化和非管理员安装。 可从 [dotnet-install 脚本引用页](../tools/dotnet-install-script.md)下载该脚本。

此脚本默认安装最新的[长期支持 (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 版本，即 .NET Core 3.1。 可通过指定 `current` 开关以选择特定版本。 包括 `runtime` 开关以安装运行时。 否则，该脚本安装 [SDK](sdk.md)。

```bash
./dotnet-install.sh --current 3.1 --runtime aspnetcore
```

> [!NOTE]
> 以上命令安装 ASP.NET Core 运行时，用于实现最大的兼容性。 ASP.NET Core 运行时还包括标准 .NET Core 运行时。

::: zone-end

## <a name="all-net-core-downloads"></a>所有 .NET Core 下载项

可直接通过以下链接之一下载和安装 .NET Core：

- [.NET Core 3.1 下载](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [.NET Core 3.0 下载](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [.NET Core 2.2 下载](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [.NET Core 2.1 下载](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a>Docker

容器提供了一种将应用程序与主机系统的其余部分隔离的轻量级方法。 同一计算机上的容器只共享内核，并使用为应用程序提供的资源。

.NET Core 可在 Docker 容器中运行。 官方 .NET Core Docker 映像发布到 Microsoft 容器注册表 (MCR)，用户可以在 [Microsoft.NET Core Docker 中心存储库](https://hub.docker.com/_/microsoft-dotnet-core/)中找到这些映像。 每个存储库包含 .NET（SDK 或运行时）和可以使用的操作系统的不同组合的映像。

Microsoft 提供适合特定场景的映像。 例如，[ASP.NET Core 存储库](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)提供针对在生产环境中运行 ASP.NET Core 应用生成的映像。

有关在 Docker 容器中使用 .NET Core 的详细信息，请参阅 [.NET 和 Docker 简介](../docker/introduction.md)和[示例](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)。

## <a name="next-steps"></a>后续步骤

- [如何检查是否已安装 .NET Core](how-to-detect-installed-versions.md)。

---
title: 在 SLES 12 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 SLES 12 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 8358107c682274fc2b75bf72689eaa4b168a86c5
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134222"
---
# <a name="sles-12-package-manager---install-net-core"></a>SLES 12 包管理器 - 安装 .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

本文介绍如何使用包管理器在 SLES 12 上安装 .NET Core。

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a>注册 Microsoft 密钥和源

安装 .NET 之前，需要：

- 注册 Microsoft 密钥。
- 注册产品存储库。
- 安装必需的依赖项。

每台计算机只需要执行一次此操作。

打开终端并运行以下命令。

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a>安装 .NET Core SDK

更新可供安装的产品，然后安装 .NET Core SDK。 在终端中，运行以下命令。

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>安装 ASP.NET Core 运行时

更新可供安装的产品，然后安装 ASP.NET 运行时。 在终端中，运行以下命令。

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>安装 .NET Core 运行时

更新可供安装的产品，然后安装 .NET Core 运行时。 在终端中，运行以下命令。

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>如何安装其他版本

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>包管理器疑难解答

本部分提供有关使用程序包管理器安装 .NET Core 时可能会遇到的常见错误的信息。

### <a name="failed-to-fetch"></a>未能提取

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

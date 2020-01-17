---
title: 在 openSUSE 15 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 openSUSE 15 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 12/26/2019
ms.openlocfilehash: cba07bafc32cc71a1cdaec08902284e105af4776
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740672"
---
# <a name="opensuse-15-package-manager---install-net-core"></a>openSUSE 15 包管理器 - 安装 .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

本文介绍如何使用包管理器在 openSUSE 15 上安装 .NET Core。 如果要安装该运行时，建议安装 [ASP.NET Core 运行时](#install-the-aspnet-core-runtime)，因为它同时包括 .NET Core 和 ASP.NET Core 运行时。

## <a name="register-microsoft-key-and-feed"></a>注册 Microsoft 密钥和源

安装 .NET 之前，需要：

- 注册 Microsoft 密钥。
- 注册产品存储库。
- 安装必需的依赖项。

每台计算机只需要执行一次此操作。

打开终端并运行以下命令。

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget -q https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="dependency-error-with-net-core-31"></a>.NET Core 3.1 中的依赖项错误

openSUSE 的 .NET Core 3.1 包源存在 krb5 依赖项的问题。 使用以下命令在安装 .NET Core 3.1 或 ASP.NET Core 3.1 之前安装正确的依赖项。

```bash
sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
```

## <a name="install-the-net-core-sdk"></a>安装 .NET Core SDK

更新可供安装的产品，然后安装 .NET Core SDK。 在终端中，运行以下命令。

```bash
sudo zypper install dotnet-sdk-3.1
```

> [!IMPORTANT]
> openSUSE 的 .NET Core 3.1 包源存在 krb5 依赖项的问题。 使用以下命令先安装正确的依赖项再安装 .NET Core 3.1 SDK。
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-aspnet-core-runtime"></a>安装 ASP.NET Core 运行时

更新可供安装的产品，然后安装 ASP.NET 运行时。 在终端中，运行以下命令。

```bash
sudo zypper install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> openSUSE 的 .NET Core 3.1 包源存在 krb5 依赖项的问题。 使用以下命令先安装正确的依赖项再安装 ASP.NET Core 3.1 运行时。
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-net-core-runtime"></a>安装 .NET Core 运行时

更新可供安装的产品，然后安装 .NET Core 运行时。 在终端中，运行以下命令。

```bash
sudo zypper install dotnet-runtime-3.1
```

> [!IMPORTANT]
> openSUSE 的 .NET Core 3.1 包源存在 krb5 依赖项的问题。 使用以下命令先安装正确的依赖项再安装 .NET Core 3.1 运行时。
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="how-to-install-other-versions"></a>如何安装其他版本

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

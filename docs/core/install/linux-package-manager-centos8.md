---
title: 在 Linux CentOS 8 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 CentOS 8 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 05/01/2020
ms.openlocfilehash: b4cf5975e18aa8dfa8649c0d038caf38d648ad86
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728503"
---
# <a name="centos-8-package-manager---install-net-core"></a>CentOS 8 包管理器 - 安装 .NET Core

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

本文介绍如何使用包管理器在 CentOS 8 上安装 .NET Core。

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="install-the-net-core-sdk"></a>安装 .NET Core SDK

在终端中，运行以下命令。

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>安装 ASP.NET Core 运行时

在终端中，运行以下命令。

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>安装 .NET Core 运行时

在终端中，运行以下命令。

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>如何安装其他版本

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

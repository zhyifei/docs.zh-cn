---
title: 在 Fedora 32 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 Fedora 32 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
ms.openlocfilehash: e5a69bf00e7e2969143e044aea4c9938fd5a610d
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624950"
---
# <a name="fedora-32-package-manager---install-net-core"></a>Fedora 32 包管理器 - 安装 .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

本文介绍如何使用包管理器在 Fedora 32 上安装 .NET Core。

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

从 Fedora 32 开始，.NET Core 3.1 在 Fedora 的默认包存储库中提供。

## <a name="install-the-net-core-sdk"></a>安装 .NET Core SDK

安装 .NET Core SDK。 在终端中，运行以下命令。

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>安装 ASP.NET Core 运行时

安装 ASP.NET 运行时。 在终端中，运行以下命令。

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>安装 .NET Core 运行时

安装 .NET Core 运行时。 在终端中，运行以下命令。

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>如何安装其他版本

若要安装其他版本的 .NET Core，请手动安装 [.NET Core SDK](sdk.md?pivots=os-linux#download-and-manually-install) 或 [.NET Core 运行时](runtime.md?pivots=os-linux#download-and-manually-install)。

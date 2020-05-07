---
title: 在 Linux RHEL 8 包管理器上安装 .NET Core - .NET Core
description: 使用包管理器在 RHEL 8 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 05/01/2020
ms.openlocfilehash: 8829e842e920e6abd4184b5140f80bb016acace2
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728231"
---
# <a name="rhel-8-package-manager---install-net-core"></a>RHEL 8 包管理器 - 安装 .NET Core

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

本文介绍如何使用包管理器在 Red Hat Enterprise Linux (RHEL) 8 上安装 .NET Core。

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a>注册 Red Hat 订阅

若要在 RHEL 上从 Red Hat 安装 .NET Core，首先需要使用 Red Hat 订阅管理器进行注册。 如果未在系统上完成此操作，或者不确定是否完成了此操作，请参阅[适用于 .NET Core 的 Red Hat 产品文档](https://access.redhat.com/documentation/net_core/)。

## <a name="install-the-net-core-sdk"></a>安装 .NET Core SDK

向订阅管理器注册后，你就可安装并启用 .NET Core SDK。 在终端中，运行以下命令。

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>安装 ASP.NET Core 运行时

向订阅管理器注册后，你就可安装并启用 ASP.NET Core 运行时。 在终端中，运行以下命令。

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>安装 .NET Core 运行时

向订阅管理器注册后，你就可安装并启用 .NET Core 运行时。 在终端中，运行以下命令。

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>如何安装其他版本

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="see-also"></a>请参阅

- [在 Red Hat Enterprise Linux 8 上使用 .NET Core 3.1](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)

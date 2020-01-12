---
title: 在 Linux RHEL 8.1 包管理器上安装 .NET Core - .NET Core
description: 使用包管理器在 RHEL 8.1 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 8781d6bd14daf975fcc602fd2924a333750d4256
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714378"
---
# <a name="rhel-81-package-manager---install-net-core"></a>RHEL 8.1 包管理器 - 安装 .NET Core

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

本文介绍如何使用包管理器在 RHEL 8.1 上安装 .NET Core。 对于 RHEL 8.1，.NET Core 3.1 尚不可用。

> [!NOTE]
> RHEL 8.0 不包括 .NET Core 3.0。 使用命令 `yum upgrade` 更新到 RHEL 8.1。

## <a name="register-your-red-hat-subscription"></a>注册 Red Hat 订阅

若要在 RHEL 上从 Red Hat 安装 .NET Core，首先需要使用 Red Hat 订阅管理器进行注册。 如果未在系统上完成此操作，或者不确定是否完成了此操作，请参阅[适用于 .NET Core 的 Red Hat 产品文档](https://access.redhat.com/documentation/net_core/)。

## <a name="install-the-net-core-sdk"></a>安装 .NET Core SDK

向订阅管理器注册后，你就可安装并启用 .NET Core SDK。 在终端中，运行以下命令。

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a>安装 ASP.NET Core 运行时

向订阅管理器注册后，你就可安装并启用 ASP.NET Core 运行时。 在终端中，运行以下命令。

```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a>安装 .NET Core 运行时

向订阅管理器注册后，你就可安装并启用 .NET Core 运行时。 在终端中，运行以下命令。

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a>请参阅

- [在 Red Hat Enterprise Linux 8 上使用 .NET Core 3.0](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)

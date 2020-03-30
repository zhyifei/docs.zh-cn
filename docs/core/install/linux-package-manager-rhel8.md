---
title: 在 Linux RHEL 8 包管理器上安装 .NET Core - .NET Core
description: 使用包管理器在 RHEL 8 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: b564a386eb67b6e414a832ad3bca10d3d09022bd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134195"
---
# <a name="rhel-8-package-manager---install-net-core"></a><span data-ttu-id="7b414-103">RHEL 8 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="7b414-103">RHEL 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="7b414-104">本文介绍如何使用包管理器在 RHEL 8 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="7b414-104">This article describes how to use a package manager to install .NET Core on RHEL 8.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="7b414-105">注册 Red Hat 订阅</span><span class="sxs-lookup"><span data-stu-id="7b414-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="7b414-106">若要在 RHEL 上从 Red Hat 安装 .NET Core，首先需要使用 Red Hat 订阅管理器进行注册。</span><span class="sxs-lookup"><span data-stu-id="7b414-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="7b414-107">如果未在系统上完成此操作，或者不确定是否完成了此操作，请参阅[适用于 .NET Core 的 Red Hat 产品文档](https://access.redhat.com/documentation/net_core/)。</span><span class="sxs-lookup"><span data-stu-id="7b414-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="7b414-108">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="7b414-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="7b414-109">向订阅管理器注册后，你就可安装并启用 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="7b414-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="7b414-110">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="7b414-110">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="7b414-111">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="7b414-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="7b414-112">向订阅管理器注册后，你就可安装并启用 ASP.NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="7b414-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="7b414-113">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="7b414-113">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="7b414-114">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="7b414-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="7b414-115">向订阅管理器注册后，你就可安装并启用 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="7b414-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="7b414-116">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="7b414-116">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-runtime-3.1
```

## <a name="see-also"></a><span data-ttu-id="7b414-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b414-117">See also</span></span>

- [<span data-ttu-id="7b414-118">在 Red Hat Enterprise Linux 8 上使用 .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7b414-118">Using .NET Core 3.1 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)

---
title: 在 Linux RHEL 8 包管理器上安装 .NET Core - .NET Core
description: 使用包管理器在 RHEL 8 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 054494a9b77e1c7803e42c947e067d3eb290f73c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "78849794"
---
# <a name="rhel-8-package-manager---install-net-core"></a><span data-ttu-id="e1e5e-103">RHEL 8 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="e1e5e-103">RHEL 8 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="e1e5e-104">本文介绍如何使用包管理器在 RHEL 8 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="e1e5e-104">This article describes how to use a package manager to install .NET Core on RHEL 8.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="e1e5e-105">注册 Red Hat 订阅</span><span class="sxs-lookup"><span data-stu-id="e1e5e-105">Register your Red Hat subscription</span></span>

<span data-ttu-id="e1e5e-106">若要在 RHEL 上从 Red Hat 安装 .NET Core，首先需要使用 Red Hat 订阅管理器进行注册。</span><span class="sxs-lookup"><span data-stu-id="e1e5e-106">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="e1e5e-107">如果未在系统上完成此操作，或者不确定是否完成了此操作，请参阅[适用于 .NET Core 的 Red Hat 产品文档](https://access.redhat.com/documentation/net_core/)。</span><span class="sxs-lookup"><span data-stu-id="e1e5e-107">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="e1e5e-108">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="e1e5e-108">Install the .NET Core SDK</span></span>

<span data-ttu-id="e1e5e-109">向订阅管理器注册后，你就可安装并启用 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="e1e5e-109">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="e1e5e-110">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e1e5e-110">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="e1e5e-111">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="e1e5e-111">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="e1e5e-112">向订阅管理器注册后，你就可安装并启用 ASP.NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="e1e5e-112">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="e1e5e-113">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e1e5e-113">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="e1e5e-114">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="e1e5e-114">Install the .NET Core Runtime</span></span>

<span data-ttu-id="e1e5e-115">向订阅管理器注册后，你就可安装并启用 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="e1e5e-115">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="e1e5e-116">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e1e5e-116">In your terminal, run the following commands.</span></span>

```bash
sudo dnf update
sudo dnf install dotnet-runtime-3.1
```

## <a name="see-also"></a><span data-ttu-id="e1e5e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1e5e-117">See also</span></span>

- [<span data-ttu-id="e1e5e-118">在 Red Hat Enterprise Linux 8 上使用 .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="e1e5e-118">Using .NET Core 3.1 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/developing_.net_applications_in_rhel_8/index)

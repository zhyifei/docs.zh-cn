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
# <a name="rhel-81-package-manager---install-net-core"></a><span data-ttu-id="8a490-103">RHEL 8.1 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="8a490-103">RHEL 8.1 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

<span data-ttu-id="8a490-104">本文介绍如何使用包管理器在 RHEL 8.1 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="8a490-104">This article describes how to use a package manager to install .NET Core on RHEL 8.1.</span></span> <span data-ttu-id="8a490-105">对于 RHEL 8.1，.NET Core 3.1 尚不可用。</span><span class="sxs-lookup"><span data-stu-id="8a490-105">.NET Core 3.1 is not yet available for RHEL 8.1.</span></span>

> [!NOTE]
> <span data-ttu-id="8a490-106">RHEL 8.0 不包括 .NET Core 3.0。</span><span class="sxs-lookup"><span data-stu-id="8a490-106">RHEL 8.0 does not include .NET Core 3.0.</span></span> <span data-ttu-id="8a490-107">使用命令 `yum upgrade` 更新到 RHEL 8.1。</span><span class="sxs-lookup"><span data-stu-id="8a490-107">Use the command `yum upgrade` to update to RHEL 8.1.</span></span>

## <a name="register-your-red-hat-subscription"></a><span data-ttu-id="8a490-108">注册 Red Hat 订阅</span><span class="sxs-lookup"><span data-stu-id="8a490-108">Register your Red Hat subscription</span></span>

<span data-ttu-id="8a490-109">若要在 RHEL 上从 Red Hat 安装 .NET Core，首先需要使用 Red Hat 订阅管理器进行注册。</span><span class="sxs-lookup"><span data-stu-id="8a490-109">To install .NET Core from Red Hat on RHEL, you first need to register using the Red Hat Subscription Manager.</span></span> <span data-ttu-id="8a490-110">如果未在系统上完成此操作，或者不确定是否完成了此操作，请参阅[适用于 .NET Core 的 Red Hat 产品文档](https://access.redhat.com/documentation/net_core/)。</span><span class="sxs-lookup"><span data-stu-id="8a490-110">If this hasn't been done on your system, or if you're unsure, see the [Red Hat Product Documentation for .NET Core](https://access.redhat.com/documentation/net_core/).</span></span>

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="8a490-111">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="8a490-111">Install the .NET Core SDK</span></span>

<span data-ttu-id="8a490-112">向订阅管理器注册后，你就可安装并启用 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="8a490-112">After registering with the Subscription Manager, you're ready to install and enable the .NET Core SDK.</span></span> <span data-ttu-id="8a490-113">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="8a490-113">In your terminal, run the following commands.</span></span>

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="8a490-114">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="8a490-114">Install the ASP.NET Core Runtime</span></span>

<span data-ttu-id="8a490-115">向订阅管理器注册后，你就可安装并启用 ASP.NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="8a490-115">After registering with the Subscription Manager, you're ready to install and enable the ASP.NET Core Runtime.</span></span> <span data-ttu-id="8a490-116">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="8a490-116">In your terminal, run the following commands.</span></span>

```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="8a490-117">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="8a490-117">Install the .NET Core Runtime</span></span>

<span data-ttu-id="8a490-118">向订阅管理器注册后，你就可安装并启用 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="8a490-118">After registering with the Subscription Manager, you're ready to install and enable the .NET Core Runtime.</span></span> <span data-ttu-id="8a490-119">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="8a490-119">In your terminal, run the following commands.</span></span>

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a><span data-ttu-id="8a490-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a490-120">See also</span></span>

- [<span data-ttu-id="8a490-121">在 Red Hat Enterprise Linux 8 上使用 .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="8a490-121">Using .NET Core 3.0 on Red Hat Enterprise Linux 8</span></span>](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)

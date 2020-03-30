---
title: 在 Fedora 30 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 Fedora 30 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 41ea47a8f473d69df6ca9823623646968e895de7
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134257"
---
# <a name="fedora-30-package-manager---install-net-core"></a><span data-ttu-id="825fa-103">Fedora 30 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="825fa-103">Fedora 30 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="825fa-104">本文介绍如何使用包管理器在 Fedora 30 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="825fa-104">This article describes how to use a package manager to install .NET Core on Fedora 30.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="825fa-105">注册 Microsoft 密钥和源</span><span class="sxs-lookup"><span data-stu-id="825fa-105">Register Microsoft key and feed</span></span>

<span data-ttu-id="825fa-106">安装 .NET 之前，需要：</span><span class="sxs-lookup"><span data-stu-id="825fa-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="825fa-107">注册 Microsoft 密钥。</span><span class="sxs-lookup"><span data-stu-id="825fa-107">Register the Microsoft key.</span></span>
- <span data-ttu-id="825fa-108">注册产品存储库。</span><span class="sxs-lookup"><span data-stu-id="825fa-108">Register the product repository.</span></span>
- <span data-ttu-id="825fa-109">安装必需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="825fa-109">Install required dependencies.</span></span>

<span data-ttu-id="825fa-110">每台计算机只需要执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="825fa-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="825fa-111">打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="825fa-111">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="825fa-112">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="825fa-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="825fa-113">更新可供安装的产品，然后安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="825fa-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="825fa-114">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="825fa-114">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="825fa-115">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="825fa-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="825fa-116">更新可供安装的产品，然后安装 ASP.NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="825fa-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="825fa-117">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="825fa-117">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="825fa-118">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="825fa-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="825fa-119">更新可供安装的产品，然后安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="825fa-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="825fa-120">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="825fa-120">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="825fa-121">如何安装其他版本</span><span class="sxs-lookup"><span data-stu-id="825fa-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="825fa-122">包管理器疑难解答</span><span class="sxs-lookup"><span data-stu-id="825fa-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="825fa-123">本部分提供有关使用程序包管理器安装 .NET Core 时可能会遇到的常见错误的信息。</span><span class="sxs-lookup"><span data-stu-id="825fa-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="825fa-124">未能提取</span><span class="sxs-lookup"><span data-stu-id="825fa-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

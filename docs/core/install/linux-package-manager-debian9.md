---
title: 在 Debian 9 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 Debian 9 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 32b152ff9be5135cf0ca7f8914bc9ee4f78000be
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920841"
---
# <a name="debian-9-package-manager---install-net-core"></a><span data-ttu-id="ca53e-103">Debian 9 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="ca53e-103">Debian 9 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="ca53e-104">本文介绍如何使用包管理器在 Debian 9 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="ca53e-104">This article describes how to use a package manager to install .NET Core on Debian 9.</span></span> <span data-ttu-id="ca53e-105">如果要安装该运行时，建议安装 [ASP.NET Core 运行时](#install-the-aspnet-core-runtime)，因为它同时包括 .NET Core 和 ASP.NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="ca53e-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="ca53e-106">注册 Microsoft 密钥和源</span><span class="sxs-lookup"><span data-stu-id="ca53e-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="ca53e-107">安装 .NET 之前，需要：</span><span class="sxs-lookup"><span data-stu-id="ca53e-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="ca53e-108">注册 Microsoft 密钥。</span><span class="sxs-lookup"><span data-stu-id="ca53e-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="ca53e-109">注册产品存储库。</span><span class="sxs-lookup"><span data-stu-id="ca53e-109">Register the product repository.</span></span>
- <span data-ttu-id="ca53e-110">安装必需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="ca53e-110">Install required dependencies.</span></span>

<span data-ttu-id="ca53e-111">每台计算机只需要执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="ca53e-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="ca53e-112">打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="ca53e-112">Open a terminal and run the following commands.</span></span>

```bash
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget -q https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="ca53e-113">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="ca53e-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="ca53e-114">更新可供安装的产品，然后安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="ca53e-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="ca53e-115">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="ca53e-115">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="ca53e-116">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="ca53e-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="ca53e-117">更新可供安装的产品，然后安装 ASP.NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="ca53e-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="ca53e-118">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="ca53e-118">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="ca53e-119">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="ca53e-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="ca53e-120">更新可供安装的产品，然后安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="ca53e-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="ca53e-121">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="ca53e-121">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="ca53e-122">如何安装其他版本</span><span class="sxs-lookup"><span data-stu-id="ca53e-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="ca53e-123">包管理器疑难解答</span><span class="sxs-lookup"><span data-stu-id="ca53e-123">Troubleshoot the package manager</span></span>

<span data-ttu-id="ca53e-124">本部分提供有关使用程序包管理器安装 .NET Core 时可能会遇到的常见错误的信息。</span><span class="sxs-lookup"><span data-stu-id="ca53e-124">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="ca53e-125">未能提取</span><span class="sxs-lookup"><span data-stu-id="ca53e-125">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

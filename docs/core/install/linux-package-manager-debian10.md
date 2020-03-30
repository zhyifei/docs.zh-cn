---
title: 在 Debian 10 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 Debian 10 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: fd6f42684aa9fb3ea9429b80f858459698a1b825
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134319"
---
# <a name="debian-10-package-manager---install-net-core"></a><span data-ttu-id="2e742-103">Debian 10 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="2e742-103">Debian 10 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="2e742-104">本文介绍如何使用包管理器在 Debian 10 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="2e742-104">This article describes how to use a package manager to install .NET Core on Debian 10.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="2e742-105">注册 Microsoft 密钥和源</span><span class="sxs-lookup"><span data-stu-id="2e742-105">Register Microsoft key and feed</span></span>

<span data-ttu-id="2e742-106">安装 .NET 之前，需要：</span><span class="sxs-lookup"><span data-stu-id="2e742-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="2e742-107">注册 Microsoft 密钥。</span><span class="sxs-lookup"><span data-stu-id="2e742-107">Register the Microsoft key.</span></span>
- <span data-ttu-id="2e742-108">注册产品存储库。</span><span class="sxs-lookup"><span data-stu-id="2e742-108">Register the product repository.</span></span>
- <span data-ttu-id="2e742-109">安装必需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="2e742-109">Install required dependencies.</span></span>

<span data-ttu-id="2e742-110">每台计算机只需要执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="2e742-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="2e742-111">打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="2e742-111">Open a terminal and run the following commands.</span></span>

```bash
wget -O- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="2e742-112">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="2e742-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="2e742-113">更新可供安装的产品，然后安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="2e742-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="2e742-114">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="2e742-114">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="2e742-115">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="2e742-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="2e742-116">更新可供安装的产品，然后安装 ASP.NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="2e742-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="2e742-117">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="2e742-117">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="2e742-118">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="2e742-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="2e742-119">更新可供安装的产品，然后安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="2e742-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="2e742-120">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="2e742-120">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="2e742-121">如何安装其他版本</span><span class="sxs-lookup"><span data-stu-id="2e742-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="2e742-122">包管理器疑难解答</span><span class="sxs-lookup"><span data-stu-id="2e742-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="2e742-123">本部分提供有关使用程序包管理器安装 .NET Core 时可能会遇到的常见错误的信息。</span><span class="sxs-lookup"><span data-stu-id="2e742-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="2e742-124">未能提取</span><span class="sxs-lookup"><span data-stu-id="2e742-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

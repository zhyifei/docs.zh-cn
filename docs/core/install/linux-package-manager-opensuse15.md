---
title: 在 openSUSE 15 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 openSUSE 15 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 3b5f51161dad4b0d7851421810506d6ed9f676f9
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134234"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="0d8da-103">openSUSE 15 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="0d8da-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="0d8da-104">本文介绍如何使用包管理器在 openSUSE 15 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="0d8da-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="0d8da-105">注册 Microsoft 密钥和源</span><span class="sxs-lookup"><span data-stu-id="0d8da-105">Register Microsoft key and feed</span></span>

<span data-ttu-id="0d8da-106">安装 .NET 之前，需要：</span><span class="sxs-lookup"><span data-stu-id="0d8da-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="0d8da-107">注册 Microsoft 密钥。</span><span class="sxs-lookup"><span data-stu-id="0d8da-107">Register the Microsoft key.</span></span>
- <span data-ttu-id="0d8da-108">注册产品存储库。</span><span class="sxs-lookup"><span data-stu-id="0d8da-108">Register the product repository.</span></span>
- <span data-ttu-id="0d8da-109">安装必需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="0d8da-109">Install required dependencies.</span></span>

<span data-ttu-id="0d8da-110">每台计算机只需要执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="0d8da-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="0d8da-111">打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="0d8da-111">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="0d8da-112">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="0d8da-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="0d8da-113">更新可供安装的产品，然后安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="0d8da-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="0d8da-114">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="0d8da-114">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="0d8da-115">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="0d8da-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="0d8da-116">更新可供安装的产品，然后安装 ASP.NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="0d8da-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="0d8da-117">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="0d8da-117">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="0d8da-118">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="0d8da-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="0d8da-119">更新可供安装的产品，然后安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="0d8da-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="0d8da-120">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="0d8da-120">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="0d8da-121">如何安装其他版本</span><span class="sxs-lookup"><span data-stu-id="0d8da-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="0d8da-122">包管理器疑难解答</span><span class="sxs-lookup"><span data-stu-id="0d8da-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="0d8da-123">本部分提供有关使用程序包管理器安装 .NET Core 时可能会遇到的常见错误的信息。</span><span class="sxs-lookup"><span data-stu-id="0d8da-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="0d8da-124">未能提取</span><span class="sxs-lookup"><span data-stu-id="0d8da-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

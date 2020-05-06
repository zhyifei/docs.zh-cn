---
title: 在 openSUSE 15 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 openSUSE 15 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: fc4c9e30ddb0cfd3e6fe79fa4f78206f4700eeee
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645667"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="9af46-103">openSUSE 15 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="9af46-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="9af46-104">本文介绍如何使用包管理器在 openSUSE 15 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="9af46-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="9af46-105">添加 Microsoft 存储库密钥和源</span><span class="sxs-lookup"><span data-stu-id="9af46-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="9af46-106">安装 .NET 之前，需要：</span><span class="sxs-lookup"><span data-stu-id="9af46-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="9af46-107">将 Microsoft 包签名密钥添加到受信任密钥列表。</span><span class="sxs-lookup"><span data-stu-id="9af46-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="9af46-108">将此存储库添加到包管理器。</span><span class="sxs-lookup"><span data-stu-id="9af46-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="9af46-109">安装必需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="9af46-109">Install required dependencies.</span></span>

<span data-ttu-id="9af46-110">每台计算机只需要执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="9af46-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="9af46-111">打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9af46-111">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="9af46-112">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="9af46-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="9af46-113">更新可供安装的产品，然后安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="9af46-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="9af46-114">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9af46-114">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="9af46-115">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="9af46-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="9af46-116">更新可供安装的产品，然后安装 ASP.NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="9af46-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="9af46-117">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9af46-117">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="9af46-118">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="9af46-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="9af46-119">更新可供安装的产品，然后安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="9af46-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="9af46-120">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9af46-120">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="9af46-121">如何安装其他版本</span><span class="sxs-lookup"><span data-stu-id="9af46-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="9af46-122">包管理器疑难解答</span><span class="sxs-lookup"><span data-stu-id="9af46-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="9af46-123">本部分提供有关使用程序包管理器安装 .NET Core 时可能会遇到的常见错误的信息。</span><span class="sxs-lookup"><span data-stu-id="9af46-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="9af46-124">未能提取</span><span class="sxs-lookup"><span data-stu-id="9af46-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

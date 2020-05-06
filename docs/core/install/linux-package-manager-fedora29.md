---
title: 在 Fedora 29 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 Fedora 29 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: d1cbe38f4f104a8e178d8bcfd1fa1bd6d7645261
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645299"
---
# <a name="fedora-29-package-manager---install-net-core"></a><span data-ttu-id="b5a5c-103">Fedora 29 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="b5a5c-103">Fedora 29 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="b5a5c-104">本文介绍如何使用包管理器在 Fedora 29 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="b5a5c-104">This article describes how to use a package manager to install .NET Core on Fedora 29.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="b5a5c-105">添加 Microsoft 存储库密钥和源</span><span class="sxs-lookup"><span data-stu-id="b5a5c-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="b5a5c-106">安装 .NET 之前，需要：</span><span class="sxs-lookup"><span data-stu-id="b5a5c-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="b5a5c-107">将 Microsoft 包签名密钥添加到受信任密钥列表。</span><span class="sxs-lookup"><span data-stu-id="b5a5c-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="b5a5c-108">将此存储库添加到包管理器。</span><span class="sxs-lookup"><span data-stu-id="b5a5c-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="b5a5c-109">安装必需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="b5a5c-109">Install required dependencies.</span></span>

<span data-ttu-id="b5a5c-110">每台计算机只需要执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="b5a5c-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="b5a5c-111">打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="b5a5c-111">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="b5a5c-112">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="b5a5c-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="b5a5c-113">更新可供安装的产品，然后安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="b5a5c-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="b5a5c-114">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="b5a5c-114">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="b5a5c-115">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="b5a5c-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="b5a5c-116">更新可供安装的产品，然后安装 ASP.NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="b5a5c-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="b5a5c-117">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="b5a5c-117">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="b5a5c-118">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="b5a5c-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="b5a5c-119">更新可供安装的产品，然后安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="b5a5c-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="b5a5c-120">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="b5a5c-120">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="b5a5c-121">如何安装其他版本</span><span class="sxs-lookup"><span data-stu-id="b5a5c-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="b5a5c-122">包管理器疑难解答</span><span class="sxs-lookup"><span data-stu-id="b5a5c-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="b5a5c-123">本部分提供有关使用程序包管理器安装 .NET Core 时可能会遇到的常见错误的信息。</span><span class="sxs-lookup"><span data-stu-id="b5a5c-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="b5a5c-124">未能提取</span><span class="sxs-lookup"><span data-stu-id="b5a5c-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

---
title: 在 SLES 12 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 SLES 12 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: a6c10c6b11bc57ae4bbe814c66c563b85ce3c22b
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920735"
---
# <a name="sles-12-package-manager---install-net-core"></a><span data-ttu-id="817b0-103">SLES 12 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="817b0-103">SLES 12 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="817b0-104">本文介绍如何使用包管理器在 SLES 12 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="817b0-104">This article describes how to use a package manager to install .NET Core on SLES 12.</span></span> <span data-ttu-id="817b0-105">如果要安装该运行时，建议安装 [ASP.NET Core 运行时](#install-the-aspnet-core-runtime)，因为它同时包括 .NET Core 和 ASP.NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="817b0-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="817b0-106">注册 Microsoft 密钥和源</span><span class="sxs-lookup"><span data-stu-id="817b0-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="817b0-107">安装 .NET 之前，需要：</span><span class="sxs-lookup"><span data-stu-id="817b0-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="817b0-108">注册 Microsoft 密钥。</span><span class="sxs-lookup"><span data-stu-id="817b0-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="817b0-109">注册产品存储库。</span><span class="sxs-lookup"><span data-stu-id="817b0-109">Register the product repository.</span></span>
- <span data-ttu-id="817b0-110">安装必需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="817b0-110">Install required dependencies.</span></span>

<span data-ttu-id="817b0-111">每台计算机只需要执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="817b0-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="817b0-112">打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="817b0-112">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="817b0-113">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="817b0-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="817b0-114">更新可供安装的产品，然后安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="817b0-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="817b0-115">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="817b0-115">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="817b0-116">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="817b0-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="817b0-117">更新可供安装的产品，然后安装 ASP.NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="817b0-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="817b0-118">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="817b0-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="817b0-119">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="817b0-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="817b0-120">更新可供安装的产品，然后安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="817b0-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="817b0-121">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="817b0-121">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="817b0-122">如何安装其他版本</span><span class="sxs-lookup"><span data-stu-id="817b0-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="817b0-123">包管理器疑难解答</span><span class="sxs-lookup"><span data-stu-id="817b0-123">Troubleshoot the package manager</span></span>

<span data-ttu-id="817b0-124">本部分提供有关使用程序包管理器安装 .NET Core 时可能会遇到的常见错误的信息。</span><span class="sxs-lookup"><span data-stu-id="817b0-124">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="817b0-125">未能提取</span><span class="sxs-lookup"><span data-stu-id="817b0-125">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

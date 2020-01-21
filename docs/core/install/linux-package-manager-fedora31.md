---
title: 在 Fedora 31 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 Fedora 31 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 12/17/2019
ms.openlocfilehash: 25c670694ed2d9e89fe37cedf0b06efd8bc93293
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116950"
---
# <a name="fedora-31-package-manager---install-net-core"></a><span data-ttu-id="76252-103">Fedora 31 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="76252-103">Fedora 31 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="76252-104">本文介绍如何使用包管理器在 Fedora 31 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="76252-104">This article describes how to use a package manager to install .NET Core on Fedora 31.</span></span> <span data-ttu-id="76252-105">如果要安装该运行时，建议安装 [ASP.NET Core 运行时](#install-the-aspnet-core-runtime)，因为它同时包括 .NET Core 和 ASP.NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="76252-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="76252-106">注册 Microsoft 密钥和源</span><span class="sxs-lookup"><span data-stu-id="76252-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="76252-107">安装 .NET 之前，需要：</span><span class="sxs-lookup"><span data-stu-id="76252-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="76252-108">注册 Microsoft 密钥。</span><span class="sxs-lookup"><span data-stu-id="76252-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="76252-109">注册产品存储库。</span><span class="sxs-lookup"><span data-stu-id="76252-109">Register the product repository.</span></span>
- <span data-ttu-id="76252-110">安装必需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="76252-110">Install required dependencies.</span></span>

<span data-ttu-id="76252-111">每台计算机只需要执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="76252-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="76252-112">打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="76252-112">Open a terminal and run the following commands.</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -q -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="76252-113">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="76252-113">Install the .NET Core SDK</span></span>

<span data-ttu-id="76252-114">更新可供安装的产品，然后安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="76252-114">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="76252-115">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="76252-115">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="76252-116">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="76252-116">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="76252-117">更新可供安装的产品，然后安装 ASP.NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="76252-117">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="76252-118">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="76252-118">In your terminal, run the following command.</span></span>

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="76252-119">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="76252-119">Install the .NET Core runtime</span></span>

<span data-ttu-id="76252-120">更新可供安装的产品，然后安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="76252-120">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="76252-121">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="76252-121">In your terminal, run the following command.</span></span>

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="76252-122">如何安装其他版本</span><span class="sxs-lookup"><span data-stu-id="76252-122">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

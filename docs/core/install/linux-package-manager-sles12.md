---
title: 在 SLES 12 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 SLES 12 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: 314688d60fb77e1b569dd037fb1d78c3f1f94dbc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645650"
---
# <a name="sles-12-package-manager---install-net-core"></a><span data-ttu-id="d4d92-103">SLES 12 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="d4d92-103">SLES 12 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="d4d92-104">本文介绍如何使用包管理器在 SLES 12 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d4d92-104">This article describes how to use a package manager to install .NET Core on SLES 12.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="d4d92-105">添加 Microsoft 存储库密钥和源</span><span class="sxs-lookup"><span data-stu-id="d4d92-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="d4d92-106">安装 .NET 之前，需要：</span><span class="sxs-lookup"><span data-stu-id="d4d92-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="d4d92-107">将 Microsoft 包签名密钥添加到受信任密钥列表。</span><span class="sxs-lookup"><span data-stu-id="d4d92-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="d4d92-108">将此存储库添加到包管理器。</span><span class="sxs-lookup"><span data-stu-id="d4d92-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="d4d92-109">安装必需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="d4d92-109">Install required dependencies.</span></span>

<span data-ttu-id="d4d92-110">每台计算机只需要执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="d4d92-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="d4d92-111">打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="d4d92-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="d4d92-112">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="d4d92-112">Install the .NET Core SDK</span></span>

<span data-ttu-id="d4d92-113">更新可供安装的产品，然后安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="d4d92-113">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="d4d92-114">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="d4d92-114">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="d4d92-115">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="d4d92-115">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="d4d92-116">更新可供安装的产品，然后安装 ASP.NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="d4d92-116">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="d4d92-117">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="d4d92-117">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="d4d92-118">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="d4d92-118">Install the .NET Core runtime</span></span>

<span data-ttu-id="d4d92-119">更新可供安装的产品，然后安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="d4d92-119">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="d4d92-120">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="d4d92-120">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="d4d92-121">如何安装其他版本</span><span class="sxs-lookup"><span data-stu-id="d4d92-121">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="d4d92-122">包管理器疑难解答</span><span class="sxs-lookup"><span data-stu-id="d4d92-122">Troubleshoot the package manager</span></span>

<span data-ttu-id="d4d92-123">本部分提供有关使用程序包管理器安装 .NET Core 时可能会遇到的常见错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d4d92-123">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="d4d92-124">未能提取</span><span class="sxs-lookup"><span data-stu-id="d4d92-124">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

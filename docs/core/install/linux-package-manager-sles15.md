---
title: 在 SLES 15 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 SLES 15 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: be5a21db8c3942bfe8827dfbce41bcf88aec342a
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595599"
---
# <a name="sles-15-package-manager---install-net-core"></a><span data-ttu-id="3c313-103">SLES 15 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="3c313-103">SLES 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="3c313-104">本文介绍如何使用包管理器在 SLES 15 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="3c313-104">This article describes how to use a package manager to install .NET Core on SLES 15.</span></span>

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a><span data-ttu-id="3c313-105">添加 Microsoft 存储库密钥和源</span><span class="sxs-lookup"><span data-stu-id="3c313-105">Add Microsoft repository key and feed</span></span>

<span data-ttu-id="3c313-106">安装 .NET 之前，需要：</span><span class="sxs-lookup"><span data-stu-id="3c313-106">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="3c313-107">将 Microsoft 包签名密钥添加到受信任密钥列表。</span><span class="sxs-lookup"><span data-stu-id="3c313-107">Add the Microsoft package signing key to the list of trusted keys.</span></span>
- <span data-ttu-id="3c313-108">将此存储库添加到包管理器。</span><span class="sxs-lookup"><span data-stu-id="3c313-108">Add the repository to the package manager.</span></span>
- <span data-ttu-id="3c313-109">安装必需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="3c313-109">Install required dependencies.</span></span>

<span data-ttu-id="3c313-110">每台计算机只需要执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="3c313-110">This only needs to be done once per machine.</span></span>

<span data-ttu-id="3c313-111">打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="3c313-111">Open a terminal and run the following command.</span></span>

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="3c313-112">目前，SLES 15 Microsoft 存储库安装包会将 microsoft-prod.repo 文件安装到错误的目录，从而导致 zypper 找不到 .NET Core 包  。</span><span class="sxs-lookup"><span data-stu-id="3c313-112">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="3c313-113">若要解决此问题，请在正确的目录中创建一个符号链接。</span><span class="sxs-lookup"><span data-stu-id="3c313-113">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="3c313-114">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="3c313-114">Install the .NET Core SDK</span></span>

<span data-ttu-id="3c313-115">更新可供安装的产品，然后安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="3c313-115">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="3c313-116">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="3c313-116">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="3c313-117">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="3c313-117">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="3c313-118">更新可供安装的产品，然后安装 ASP.NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="3c313-118">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="3c313-119">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="3c313-119">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="3c313-120">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="3c313-120">Install the .NET Core runtime</span></span>

<span data-ttu-id="3c313-121">更新可供安装的产品，然后安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="3c313-121">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="3c313-122">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="3c313-122">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="3c313-123">如何安装其他版本</span><span class="sxs-lookup"><span data-stu-id="3c313-123">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="3c313-124">包管理器疑难解答</span><span class="sxs-lookup"><span data-stu-id="3c313-124">Troubleshoot the package manager</span></span>

<span data-ttu-id="3c313-125">本部分提供有关使用程序包管理器安装 .NET Core 时可能会遇到的常见错误的信息。</span><span class="sxs-lookup"><span data-stu-id="3c313-125">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="3c313-126">未能提取</span><span class="sxs-lookup"><span data-stu-id="3c313-126">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-rpm.md)]

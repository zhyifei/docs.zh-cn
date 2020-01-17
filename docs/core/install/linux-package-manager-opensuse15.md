---
title: 在 openSUSE 15 上安装 .NET Core - 包管理器 - .NET Core
description: 使用包管理器在 openSUSE 15 上安装 .NET Core SDK 和运行时。
author: thraka
ms.author: adegeo
ms.date: 12/26/2019
ms.openlocfilehash: cba07bafc32cc71a1cdaec08902284e105af4776
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740672"
---
# <a name="opensuse-15-package-manager---install-net-core"></a><span data-ttu-id="e5bc1-103">openSUSE 15 包管理器 - 安装 .NET Core</span><span class="sxs-lookup"><span data-stu-id="e5bc1-103">openSUSE 15 Package Manager - Install .NET Core</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

<span data-ttu-id="e5bc1-104">本文介绍如何使用包管理器在 openSUSE 15 上安装 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-104">This article describes how to use a package manager to install .NET Core on openSUSE 15.</span></span> <span data-ttu-id="e5bc1-105">如果要安装该运行时，建议安装 [ASP.NET Core 运行时](#install-the-aspnet-core-runtime)，因为它同时包括 .NET Core 和 ASP.NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-105">If you're installing the runtime, we suggest you install the [ASP.NET Core runtime](#install-the-aspnet-core-runtime), as it includes both .NET Core and ASP.NET Core runtimes.</span></span>

## <a name="register-microsoft-key-and-feed"></a><span data-ttu-id="e5bc1-106">注册 Microsoft 密钥和源</span><span class="sxs-lookup"><span data-stu-id="e5bc1-106">Register Microsoft key and feed</span></span>

<span data-ttu-id="e5bc1-107">安装 .NET 之前，需要：</span><span class="sxs-lookup"><span data-stu-id="e5bc1-107">Before installing .NET, you'll need to:</span></span>

- <span data-ttu-id="e5bc1-108">注册 Microsoft 密钥。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-108">Register the Microsoft key.</span></span>
- <span data-ttu-id="e5bc1-109">注册产品存储库。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-109">Register the product repository.</span></span>
- <span data-ttu-id="e5bc1-110">安装必需的依赖项。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-110">Install required dependencies.</span></span>

<span data-ttu-id="e5bc1-111">每台计算机只需要执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-111">This only needs to be done once per machine.</span></span>

<span data-ttu-id="e5bc1-112">打开终端并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-112">Open a terminal and run the following commands.</span></span>

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget -q https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="dependency-error-with-net-core-31"></a><span data-ttu-id="e5bc1-113">.NET Core 3.1 中的依赖项错误</span><span class="sxs-lookup"><span data-stu-id="e5bc1-113">Dependency error with .NET Core 3.1</span></span>

<span data-ttu-id="e5bc1-114">openSUSE 的 .NET Core 3.1 包源存在 krb5 依赖项的问题。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-114">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="e5bc1-115">使用以下命令在安装 .NET Core 3.1 或 ASP.NET Core 3.1 之前安装正确的依赖项。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-115">Use the following command to install the correct dependencies prior to installing .NET Core 3.1 or ASP.NET Core 3.1.</span></span>

```bash
sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
```

## <a name="install-the-net-core-sdk"></a><span data-ttu-id="e5bc1-116">安装 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="e5bc1-116">Install the .NET Core SDK</span></span>

<span data-ttu-id="e5bc1-117">更新可供安装的产品，然后安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-117">Update the products available for installation, then install the .NET Core SDK.</span></span> <span data-ttu-id="e5bc1-118">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-118">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-sdk-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="e5bc1-119">openSUSE 的 .NET Core 3.1 包源存在 krb5 依赖项的问题。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-119">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="e5bc1-120">使用以下命令先安装正确的依赖项再安装 .NET Core 3.1 SDK。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-120">Use the following command to install the correct dependencies, then install the .NET Core 3.1 SDK.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-aspnet-core-runtime"></a><span data-ttu-id="e5bc1-121">安装 ASP.NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="e5bc1-121">Install the ASP.NET Core runtime</span></span>

<span data-ttu-id="e5bc1-122">更新可供安装的产品，然后安装 ASP.NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-122">Update the products available for installation, then install the ASP.NET runtime.</span></span> <span data-ttu-id="e5bc1-123">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-123">In your terminal, run the following command.</span></span>

```bash
sudo zypper install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="e5bc1-124">openSUSE 的 .NET Core 3.1 包源存在 krb5 依赖项的问题。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-124">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="e5bc1-125">使用以下命令先安装正确的依赖项再安装 ASP.NET Core 3.1 运行时。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-125">Use the following command to install the correct dependencies, then install the ASP.NET Core 3.1 runtime.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-net-core-runtime"></a><span data-ttu-id="e5bc1-126">安装 .NET Core 运行时</span><span class="sxs-lookup"><span data-stu-id="e5bc1-126">Install the .NET Core runtime</span></span>

<span data-ttu-id="e5bc1-127">更新可供安装的产品，然后安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-127">Update the products available for installation, then install the .NET Core runtime.</span></span> <span data-ttu-id="e5bc1-128">在终端中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-128">In your terminal, run the following command.</span></span>

```bash
sudo zypper install dotnet-runtime-3.1
```

> [!IMPORTANT]
> <span data-ttu-id="e5bc1-129">openSUSE 的 .NET Core 3.1 包源存在 krb5 依赖项的问题。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-129">The .NET Core 3.1 package feed for openSUSE has a problem with the **krb5** dependency.</span></span> <span data-ttu-id="e5bc1-130">使用以下命令先安装正确的依赖项再安装 .NET Core 3.1 运行时。</span><span class="sxs-lookup"><span data-stu-id="e5bc1-130">Use the following command to install the correct dependencies, then install the .NET Core 3.1 runtime.</span></span>
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="how-to-install-other-versions"></a><span data-ttu-id="e5bc1-131">如何安装其他版本</span><span class="sxs-lookup"><span data-stu-id="e5bc1-131">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

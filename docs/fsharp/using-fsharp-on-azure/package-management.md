---
title: "使用 Azure 使用 F # 包管理"
description: "使用 Paket 或 Nuget 来管理 F # Azure 依赖关系"
keywords: "visual f #、 f # 中，函数编程，.NET，.NET 核心，Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dd32ef9c-5416-467e-9fa3-c9ee3bb08456
ms.openlocfilehash: d1a807053f5c4c45492f206739922aacdf6d4122
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="9edbb-104">F# Azure 依赖项的包管理</span><span class="sxs-lookup"><span data-stu-id="9edbb-104">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="9edbb-105">当你使用的程序包管理器时，很容易获取进行 Azure 开发的包。</span><span class="sxs-lookup"><span data-stu-id="9edbb-105">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="9edbb-106">有两个选项[Paket](https://fsprojects.github.io/Paket/)和[NuGet](https://www.nuget.org/)。</span><span class="sxs-lookup"><span data-stu-id="9edbb-106">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="9edbb-107">使用 Paket</span><span class="sxs-lookup"><span data-stu-id="9edbb-107">Using Paket</span></span>

<span data-ttu-id="9edbb-108">如果你使用[Paket](https://fsprojects.github.io/Paket/)作为依赖项管理器中，你可以使用`paket.exe`工具，用于添加 Azure 依赖关系。</span><span class="sxs-lookup"><span data-stu-id="9edbb-108">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="9edbb-109">例如:</span><span class="sxs-lookup"><span data-stu-id="9edbb-109">For example:</span></span>

    > paket add nuget WindowsAzure.Storage

<span data-ttu-id="9edbb-110">或者，如果你使用[Mono](https://www.mono-project.com/)用于跨平台.NET 开发：</span><span class="sxs-lookup"><span data-stu-id="9edbb-110">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

    > mono paket.exe add nuget WindowsAzure.Storage

<span data-ttu-id="9edbb-111">这将添加`WindowsAzure.Storage`到当前目录中的项目的包依赖项集，修改`paket.dependencies`文件中，并下载包。</span><span class="sxs-lookup"><span data-stu-id="9edbb-111">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="9edbb-112">如果在以前设置了依赖项，或正在使用项目其中依赖项已经设置了由另一个开发人员，你可以解决并安装本地如下的依赖项：</span><span class="sxs-lookup"><span data-stu-id="9edbb-112">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > paket install

<span data-ttu-id="9edbb-113">或者，对于 Mono 开发：</span><span class="sxs-lookup"><span data-stu-id="9edbb-113">Or, for Mono development:</span></span>

    > mono paket.exe install

<span data-ttu-id="9edbb-114">你可以像这样的最新版本更新所有包依赖项：</span><span class="sxs-lookup"><span data-stu-id="9edbb-114">You can update all your package dependencies to the latest version like this:</span></span>

    > paket update

<span data-ttu-id="9edbb-115">或者，对于 Mono 开发：</span><span class="sxs-lookup"><span data-stu-id="9edbb-115">Or, for Mono development:</span></span>

    > mono paket.exe update

## <a name="using-nuget"></a><span data-ttu-id="9edbb-116">使用 Nuget</span><span class="sxs-lookup"><span data-stu-id="9edbb-116">Using Nuget</span></span>

<span data-ttu-id="9edbb-117">如果你使用[NuGet](https://www.nuget.org/)作为依赖项管理器中，你可以使用`nuget.exe`工具，用于添加 Azure 依赖关系。</span><span class="sxs-lookup"><span data-stu-id="9edbb-117">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="9edbb-118">例如:</span><span class="sxs-lookup"><span data-stu-id="9edbb-118">For example:</span></span>

    > nuget install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="9edbb-119">或者，对于 Mono 开发：</span><span class="sxs-lookup"><span data-stu-id="9edbb-119">Or, for Mono development:</span></span>

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="9edbb-120">这将添加`WindowsAzure.Storage`到包中的当前目录，并下载包的项目的依赖项集。</span><span class="sxs-lookup"><span data-stu-id="9edbb-120">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="9edbb-121">如果在以前设置了依赖项，或正在使用项目其中依赖项已经设置了由另一个开发人员，你可以解决并安装本地如下的依赖项：</span><span class="sxs-lookup"><span data-stu-id="9edbb-121">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > nuget restore 

<span data-ttu-id="9edbb-122">或者，对于 Mono 开发：</span><span class="sxs-lookup"><span data-stu-id="9edbb-122">Or, for Mono development:</span></span>

    > mono nuget.exe restore

<span data-ttu-id="9edbb-123">你可以像这样的最新版本更新所有包依赖项：</span><span class="sxs-lookup"><span data-stu-id="9edbb-123">You can update all your package dependencies to the latest version like this:</span></span>

    > nuget update

<span data-ttu-id="9edbb-124">或者，对于 Mono 开发：</span><span class="sxs-lookup"><span data-stu-id="9edbb-124">Or, for Mono development:</span></span>

    > mono nuget.exe update

## <a name="referencing-assemblies"></a><span data-ttu-id="9edbb-125">引用程序集</span><span class="sxs-lookup"><span data-stu-id="9edbb-125">Referencing Assemblies</span></span>

<span data-ttu-id="9edbb-126">若要在 F # 脚本中使用的包，则需要引用中使用的包附带的程序集`#r`指令。</span><span class="sxs-lookup"><span data-stu-id="9edbb-126">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="9edbb-127">例如:</span><span class="sxs-lookup"><span data-stu-id="9edbb-127">For example:</span></span>

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

<span data-ttu-id="9edbb-128">如你所见，你将需要指定的 DLL，并可能不完全相同的包名称的完整 DLL 名称的相对路径。</span><span class="sxs-lookup"><span data-stu-id="9edbb-128">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="9edbb-129">路径将包括的 framework 版本和可能的包版本号。</span><span class="sxs-lookup"><span data-stu-id="9edbb-129">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="9edbb-130">若要查找所有已安装的程序集，可以在 Windows 命令行上使用类似如下内容：</span><span class="sxs-lookup"><span data-stu-id="9edbb-130">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

<span data-ttu-id="9edbb-131">或在 Unix shell，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="9edbb-131">Or in a Unix shell, something like this:</span></span>

    > find packages/WindowsAzure.Storage -name "*.dll"

<span data-ttu-id="9edbb-132">这将为您路径到已安装的程序集。</span><span class="sxs-lookup"><span data-stu-id="9edbb-132">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="9edbb-133">在这里，你可以为 framework 版本选择正确的路径。</span><span class="sxs-lookup"><span data-stu-id="9edbb-133">From there, you can select the correct path for your framework version.</span></span>

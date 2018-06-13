---
title: '使用 Azure 使用 F # 包管理'
description: '使用 Paket 或 Nuget 来管理 F # Azure 依赖关系'
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fd9c4a15ab0741d44d6d5cf909b7219d310affb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566961"
---
# <a name="package-management-for-f-azure-dependencies"></a><span data-ttu-id="ab5fa-103">F# Azure 依赖项的包管理</span><span class="sxs-lookup"><span data-stu-id="ab5fa-103">Package Management for F# Azure Dependencies</span></span>

<span data-ttu-id="ab5fa-104">当你使用的程序包管理器时，很容易获取进行 Azure 开发的包。</span><span class="sxs-lookup"><span data-stu-id="ab5fa-104">Obtaining packages for Azure development is easy when you use a package manager.</span></span> <span data-ttu-id="ab5fa-105">有两个选项[Paket](https://fsprojects.github.io/Paket/)和[NuGet](https://www.nuget.org/)。</span><span class="sxs-lookup"><span data-stu-id="ab5fa-105">The two options are [Paket](https://fsprojects.github.io/Paket/) and [NuGet](https://www.nuget.org/).</span></span>

## <a name="using-paket"></a><span data-ttu-id="ab5fa-106">使用 Paket</span><span class="sxs-lookup"><span data-stu-id="ab5fa-106">Using Paket</span></span>

<span data-ttu-id="ab5fa-107">如果你使用[Paket](https://fsprojects.github.io/Paket/)作为依赖项管理器中，你可以使用`paket.exe`工具，用于添加 Azure 依赖关系。</span><span class="sxs-lookup"><span data-stu-id="ab5fa-107">If you're using [Paket](https://fsprojects.github.io/Paket/) as your dependency manager, you can use the `paket.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="ab5fa-108">例如：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-108">For example:</span></span>

    > paket add nuget WindowsAzure.Storage

<span data-ttu-id="ab5fa-109">或者，如果你使用[Mono](https://www.mono-project.com/)用于跨平台.NET 开发：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-109">Or, if you're using [Mono](https://www.mono-project.com/) for cross-platform .NET development:</span></span>

    > mono paket.exe add nuget WindowsAzure.Storage

<span data-ttu-id="ab5fa-110">这将添加`WindowsAzure.Storage`到当前目录中的项目的包依赖项集，修改`paket.dependencies`文件中，并下载包。</span><span class="sxs-lookup"><span data-stu-id="ab5fa-110">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, modify the `paket.dependencies` file, and download the package.</span></span> <span data-ttu-id="ab5fa-111">如果在以前设置了依赖项，或正在使用项目其中依赖项已经设置了由另一个开发人员，你可以解决并安装本地如下的依赖项：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-111">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > paket install

<span data-ttu-id="ab5fa-112">或者，对于 Mono 开发：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-112">Or, for Mono development:</span></span>

    > mono paket.exe install

<span data-ttu-id="ab5fa-113">你可以像这样的最新版本更新所有包依赖项：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-113">You can update all your package dependencies to the latest version like this:</span></span>

    > paket update

<span data-ttu-id="ab5fa-114">或者，对于 Mono 开发：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-114">Or, for Mono development:</span></span>

    > mono paket.exe update

## <a name="using-nuget"></a><span data-ttu-id="ab5fa-115">使用 Nuget</span><span class="sxs-lookup"><span data-stu-id="ab5fa-115">Using Nuget</span></span>

<span data-ttu-id="ab5fa-116">如果你使用[NuGet](https://www.nuget.org/)作为依赖项管理器中，你可以使用`nuget.exe`工具，用于添加 Azure 依赖关系。</span><span class="sxs-lookup"><span data-stu-id="ab5fa-116">If you're using [NuGet](https://www.nuget.org/) as your dependency manager, you can use the `nuget.exe` tool to add Azure dependencies.</span></span> <span data-ttu-id="ab5fa-117">例如：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-117">For example:</span></span>

    > nuget install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="ab5fa-118">或者，对于 Mono 开发：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-118">Or, for Mono development:</span></span>

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

<span data-ttu-id="ab5fa-119">这将添加`WindowsAzure.Storage`到包中的当前目录，并下载包的项目的依赖项集。</span><span class="sxs-lookup"><span data-stu-id="ab5fa-119">This will add `WindowsAzure.Storage` to your set of package dependencies for the project in the current directory, and download the package.</span></span> <span data-ttu-id="ab5fa-120">如果在以前设置了依赖项，或正在使用项目其中依赖项已经设置了由另一个开发人员，你可以解决并安装本地如下的依赖项：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-120">If you have previously set up dependencies, or are working with a project where dependencies have been set up by another developer, you can resolve and install dependencies locally like this:</span></span>

    > nuget restore 

<span data-ttu-id="ab5fa-121">或者，对于 Mono 开发：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-121">Or, for Mono development:</span></span>

    > mono nuget.exe restore

<span data-ttu-id="ab5fa-122">你可以像这样的最新版本更新所有包依赖项：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-122">You can update all your package dependencies to the latest version like this:</span></span>

    > nuget update

<span data-ttu-id="ab5fa-123">或者，对于 Mono 开发：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-123">Or, for Mono development:</span></span>

    > mono nuget.exe update

## <a name="referencing-assemblies"></a><span data-ttu-id="ab5fa-124">引用程序集</span><span class="sxs-lookup"><span data-stu-id="ab5fa-124">Referencing Assemblies</span></span>

<span data-ttu-id="ab5fa-125">若要在 F # 脚本中使用的包，则需要引用中使用的包附带的程序集`#r`指令。</span><span class="sxs-lookup"><span data-stu-id="ab5fa-125">In order to use your packages in your F# script, you need to reference the assemblies included in the packages using a `#r` directive.</span></span> <span data-ttu-id="ab5fa-126">例如：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-126">For example:</span></span>

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

<span data-ttu-id="ab5fa-127">如你所见，你将需要指定的 DLL，并可能不完全相同的包名称的完整 DLL 名称的相对路径。</span><span class="sxs-lookup"><span data-stu-id="ab5fa-127">As you can see, you'll need to specify the relative path to the DLL and the full DLL name, which may not be exactly the same as the package name.</span></span> <span data-ttu-id="ab5fa-128">路径将包括的 framework 版本和可能的包版本号。</span><span class="sxs-lookup"><span data-stu-id="ab5fa-128">The path will include a framework version and possibly a package version number.</span></span> <span data-ttu-id="ab5fa-129">若要查找所有已安装的程序集，可以在 Windows 命令行上使用类似如下内容：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-129">To find all the installed assemblies, you can use something like this on a Windows command line:</span></span>

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

<span data-ttu-id="ab5fa-130">或在 Unix shell，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="ab5fa-130">Or in a Unix shell, something like this:</span></span>

    > find packages/WindowsAzure.Storage -name "*.dll"

<span data-ttu-id="ab5fa-131">这将为您路径到已安装的程序集。</span><span class="sxs-lookup"><span data-stu-id="ab5fa-131">This will give you the paths to the installed assemblies.</span></span> <span data-ttu-id="ab5fa-132">在这里，你可以为 framework 版本选择正确的路径。</span><span class="sxs-lookup"><span data-stu-id="ab5fa-132">From there, you can select the correct path for your framework version.</span></span>

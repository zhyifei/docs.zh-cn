---
title: dotnet store 命令
description: “dotnet store”命令可将指定的程序集存储到运行时包存储区。
author: bleroy
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 54654522207157f7d49bb86223b7986acccf51ee
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696320"
---
# <a name="dotnet-store"></a><span data-ttu-id="5de20-103">dotnet store</span><span class="sxs-lookup"><span data-stu-id="5de20-103">dotnet store</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="5de20-104">name</span><span class="sxs-lookup"><span data-stu-id="5de20-104">Name</span></span>

<span data-ttu-id="5de20-105">`dotnet store` - 将指定的程序集存储到[运行时包存储区](../deploying/runtime-store.md)。</span><span class="sxs-lookup"><span data-stu-id="5de20-105">`dotnet store` - Stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span>

## <a name="synopsis"></a><span data-ttu-id="5de20-106">摘要</span><span class="sxs-lookup"><span data-stu-id="5de20-106">Synopsis</span></span>

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a><span data-ttu-id="5de20-107">描述</span><span class="sxs-lookup"><span data-stu-id="5de20-107">Description</span></span>

<span data-ttu-id="5de20-108">`dotnet store` 将指定的程序集存储到[运行时包存储区](../deploying/runtime-store.md)。</span><span class="sxs-lookup"><span data-stu-id="5de20-108">`dotnet store` stores the specified assemblies in the [runtime package store](../deploying/runtime-store.md).</span></span> <span data-ttu-id="5de20-109">默认情况下，程序集更适用于目标运行时和框架。</span><span class="sxs-lookup"><span data-stu-id="5de20-109">By default, assemblies are optimized for the target runtime and framework.</span></span> <span data-ttu-id="5de20-110">有关详细信息，请参阅[运行时包存储区](../deploying/runtime-store.md)主题。</span><span class="sxs-lookup"><span data-stu-id="5de20-110">For more information, see the [runtime package store](../deploying/runtime-store.md) topic.</span></span>

## <a name="required-options"></a><span data-ttu-id="5de20-111">必需选项</span><span class="sxs-lookup"><span data-stu-id="5de20-111">Required options</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="5de20-112">指定[目标框架](../../standard/frameworks.md)。</span><span class="sxs-lookup"><span data-stu-id="5de20-112">Specifies the [target framework](../../standard/frameworks.md).</span></span>

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="5de20-113">包存储区清单文件是包含要存储的包列表的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="5de20-113">The *package store manifest file* is an XML file that contains the list of packages to store.</span></span> <span data-ttu-id="5de20-114">清单文件的格式与 SDK 样式项目格式兼容。</span><span class="sxs-lookup"><span data-stu-id="5de20-114">The format of the manifest file is compatible with the SDK-style project format.</span></span> <span data-ttu-id="5de20-115">因此，引用所需的包的项目文件能够与 `-m|--manifest` 选项结合使用，以便于将程序集存储到运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="5de20-115">So, a project file that references the desired packages can be used with the `-m|--manifest` option to store assemblies in the runtime package store.</span></span> <span data-ttu-id="5de20-116">若要指定多个清单文件，请为各个文件重复指定选项和路径。</span><span class="sxs-lookup"><span data-stu-id="5de20-116">To specify multiple manifest files, repeat the option and path for each file.</span></span> <span data-ttu-id="5de20-117">例如：`--manifest packages1.csproj --manifest packages2.csproj`。</span><span class="sxs-lookup"><span data-stu-id="5de20-117">For example: `--manifest packages1.csproj --manifest packages2.csproj`.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="5de20-118">目标[运行时标识符](../rid-catalog.md)。</span><span class="sxs-lookup"><span data-stu-id="5de20-118">The [runtime identifier](../rid-catalog.md) to target.</span></span>

## <a name="optional-options"></a><span data-ttu-id="5de20-119">可选选项</span><span class="sxs-lookup"><span data-stu-id="5de20-119">Optional options</span></span>

`--framework-version <FRAMEWORK_VERSION>`

<span data-ttu-id="5de20-120">指定 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="5de20-120">Specifies the .NET Core SDK version.</span></span> <span data-ttu-id="5de20-121">使用此选项，可以选择特定的框架版本，不再局限于 `-f|--framework` 选项指定的框架。</span><span class="sxs-lookup"><span data-stu-id="5de20-121">This option enables you to select a specific framework version beyond the framework specified by the `-f|--framework` option.</span></span>

`-h|--help`

<span data-ttu-id="5de20-122">显示帮助信息。</span><span class="sxs-lookup"><span data-stu-id="5de20-122">Shows help information.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="5de20-123">指定运行时包存储区的路径。</span><span class="sxs-lookup"><span data-stu-id="5de20-123">Specifies the path to the runtime package store.</span></span> <span data-ttu-id="5de20-124">如果未指定，默认路径为用户配置文件 .NET Core 安装目录的 store 子目录。</span><span class="sxs-lookup"><span data-stu-id="5de20-124">If not specified, it defaults to the *store* subdirectory of the user profile .NET Core installation directory.</span></span>

`--skip-optimization`

<span data-ttu-id="5de20-125">跳过优化阶段。</span><span class="sxs-lookup"><span data-stu-id="5de20-125">Skips the optimization phase.</span></span>

`--skip-symbols`

<span data-ttu-id="5de20-126">跳过符号生成。</span><span class="sxs-lookup"><span data-stu-id="5de20-126">Skips symbol generation.</span></span> <span data-ttu-id="5de20-127">目前，只能在 Windows 和 Linux 上生成符号。</span><span class="sxs-lookup"><span data-stu-id="5de20-127">Currently, you can only generate symbols on Windows and Linux.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="5de20-128">设置命令的详细级别。</span><span class="sxs-lookup"><span data-stu-id="5de20-128">Sets the verbosity level of the command.</span></span> <span data-ttu-id="5de20-129">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="5de20-129">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

<span data-ttu-id="5de20-130">此命令使用的工作目录。</span><span class="sxs-lookup"><span data-stu-id="5de20-130">The working directory used by the command.</span></span> <span data-ttu-id="5de20-131">如果未指定，使用当前目录的 obj 子目录。</span><span class="sxs-lookup"><span data-stu-id="5de20-131">If not specified, it uses the *obj* subdirectory of the current directory.</span></span>

## <a name="examples"></a><span data-ttu-id="5de20-132">示例</span><span class="sxs-lookup"><span data-stu-id="5de20-132">Examples</span></span>

<span data-ttu-id="5de20-133">存储 packages.csproj 项目文件中为 .NET Core 2.0.0 指定的包：</span><span class="sxs-lookup"><span data-stu-id="5de20-133">Store the packages specified in the *packages.csproj* project file for .NET Core 2.0.0:</span></span>

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

<span data-ttu-id="5de20-134">存储 packages.csproj 中指定的包，但不进行优化：</span><span class="sxs-lookup"><span data-stu-id="5de20-134">Store the packages specified in the *packages.csproj* without optimization:</span></span>

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a><span data-ttu-id="5de20-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="5de20-135">See also</span></span>

[<span data-ttu-id="5de20-136">运行时包存储</span><span class="sxs-lookup"><span data-stu-id="5de20-136">Runtime package store</span></span>](../deploying/runtime-store.md)
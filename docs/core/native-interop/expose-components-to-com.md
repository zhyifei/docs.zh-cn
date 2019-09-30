---
title: 向 COM 公开 .NET Core 组件
ms.date: 07/12/2019
helpviewer_keywords:
- exposing .NET Core components to COM
- interoperation with unmanaged code, exposing .NET Core components
- COM interop, exposing COM components
ms.assetid: 21271167-fe7f-46ba-a81f-a6812ea649d4
author: jkoritzinsky
ms.author: jekoritz
ms.openlocfilehash: 8f9624414a2b423bd43e8790d11b70ae1ca6286d
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216223"
---
# <a name="exposing-net-core-components-to-com"></a><span data-ttu-id="e70d5-102">向 COM 公开 .NET Core 组件</span><span class="sxs-lookup"><span data-stu-id="e70d5-102">Exposing .NET Core components to COM</span></span>

<span data-ttu-id="e70d5-103">在 .NET Core 中，与 .NET Framework 相比，向 COM 公开 .NET 对象的过程已明显简化。</span><span class="sxs-lookup"><span data-stu-id="e70d5-103">In .NET Core, the process for exposing your .NET objects to COM has been significantly streamlined in comparison to .NET Framework.</span></span> <span data-ttu-id="e70d5-104">下面的过程将引导你如何向 COM 公开类。</span><span class="sxs-lookup"><span data-stu-id="e70d5-104">The following process will walk you through how to expose a class to COM.</span></span> <span data-ttu-id="e70d5-105">本教程介绍了如何：</span><span class="sxs-lookup"><span data-stu-id="e70d5-105">This tutorial shows you how to:</span></span>

- <span data-ttu-id="e70d5-106">从 .NET Core 向 COM 公开类。</span><span class="sxs-lookup"><span data-stu-id="e70d5-106">Expose a class to COM from .NET Core.</span></span>
- <span data-ttu-id="e70d5-107">生成 COM 服务器作为构建 .NET Core 库的一部分。</span><span class="sxs-lookup"><span data-stu-id="e70d5-107">Generate a COM server as part of building your .NET Core library.</span></span>
- <span data-ttu-id="e70d5-108">自动为无注册表 COM 生成并行服务器清单。</span><span class="sxs-lookup"><span data-stu-id="e70d5-108">Automatically generate a side-by-side server manifest for Registry-Free COM.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e70d5-109">系统必备</span><span class="sxs-lookup"><span data-stu-id="e70d5-109">Prerequisites</span></span>

- <span data-ttu-id="e70d5-110">安装 [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e70d5-110">Install [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) or a newer version.</span></span>

## <a name="create-the-library"></a><span data-ttu-id="e70d5-111">创建库</span><span class="sxs-lookup"><span data-stu-id="e70d5-111">Create the library</span></span>

<span data-ttu-id="e70d5-112">第一步是创建库。</span><span class="sxs-lookup"><span data-stu-id="e70d5-112">The first step is to create the library.</span></span>

1. <span data-ttu-id="e70d5-113">创建新文件夹，并在该文件夹中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e70d5-113">Create a new folder, and in that folder run the following command:</span></span>
    
    ```dotnetcli
    dotnet new classlib
    ```

2. <span data-ttu-id="e70d5-114">打开 `Class1.cs`。</span><span class="sxs-lookup"><span data-stu-id="e70d5-114">Open `Class1.cs`.</span></span>
3. <span data-ttu-id="e70d5-115">将 `using System.Runtime.InteropServices;` 添加到文件顶部。</span><span class="sxs-lookup"><span data-stu-id="e70d5-115">Add `using System.Runtime.InteropServices;` to the top of the file.</span></span>
4. <span data-ttu-id="e70d5-116">创建名为 `IServer` 的接口。</span><span class="sxs-lookup"><span data-stu-id="e70d5-116">Create an interface named `IServer`.</span></span> <span data-ttu-id="e70d5-117">例如:</span><span class="sxs-lookup"><span data-stu-id="e70d5-117">For example:</span></span>

   [!code-csharp[The IServer interface](~/samples/core/extensions/COMServerDemo/COMContract/IServer.cs)]

5. <span data-ttu-id="e70d5-118">将 `[Guid("<IID>")]` 属性添加到接口，包含要实现的 COM 接口的接口 GUID。</span><span class="sxs-lookup"><span data-stu-id="e70d5-118">Add the `[Guid("<IID>")]` attribute to the interface, with the interface GUID for the COM interface you're implementing.</span></span> <span data-ttu-id="e70d5-119">例如 `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`。</span><span class="sxs-lookup"><span data-stu-id="e70d5-119">For example, `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span></span> <span data-ttu-id="e70d5-120">请注意，此 GUID 必须唯一，因为它是 COM 的此接口的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e70d5-120">Note that this GUID needs to be unique since it is the only identifier of this interface for COM.</span></span> <span data-ttu-id="e70d5-121">在 Visual Studio 中，可通过转到“工具”>“创建 GUID”以打开“创建 GUID”工具来生成 GUID。</span><span class="sxs-lookup"><span data-stu-id="e70d5-121">In Visual Studio, you can generate a GUID by going to Tools > Create GUID to open the Create GUID tool.</span></span>
6. <span data-ttu-id="e70d5-122">将 `[InterfaceType]` 属性添加到接口，并指定接口应实现的基本 COM 接口。</span><span class="sxs-lookup"><span data-stu-id="e70d5-122">Add the `[InterfaceType]` attribute to the interface and specify what base COM interfaces your interface should implement.</span></span>
7. <span data-ttu-id="e70d5-123">创建用于实现 `IServer` 的名为 `Server` 的类。</span><span class="sxs-lookup"><span data-stu-id="e70d5-123">Create a class named `Server` that implements `IServer`.</span></span>
8. <span data-ttu-id="e70d5-124">将 `[Guid("<CLSID>")]` 属性添加到类，包含要实现的 COM 类的类标识符 GUID。</span><span class="sxs-lookup"><span data-stu-id="e70d5-124">Add the `[Guid("<CLSID>")]` attribute to the class, with the class identifier GUID for the COM class you're implementing.</span></span> <span data-ttu-id="e70d5-125">例如 `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`。</span><span class="sxs-lookup"><span data-stu-id="e70d5-125">For example, `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span></span> <span data-ttu-id="e70d5-126">与接口 GUID 一样，此 GUID 必须唯一，因为它是 COM 的此接口的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e70d5-126">As with the interface GUID, this GUID must be unique since it is the only identifier of this interface to COM.</span></span>
9. <span data-ttu-id="e70d5-127">将 `[ComVisible(true)]` 属性添加到接口和类。</span><span class="sxs-lookup"><span data-stu-id="e70d5-127">Add the `[ComVisible(true)]` attribute to both the interface and the class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e70d5-128">与 .NET Framework 不同，.NET Core 要求指定想要通过 COM 激活的任何类的 CLSID。</span><span class="sxs-lookup"><span data-stu-id="e70d5-128">Unlike in .NET Framework, .NET Core requires you to specify the CLSID of any class you want to be activatable via COM.</span></span>

## <a name="generate-the-com-host"></a><span data-ttu-id="e70d5-129">生成 COM 主机</span><span class="sxs-lookup"><span data-stu-id="e70d5-129">Generate the COM host</span></span>

1. <span data-ttu-id="e70d5-130">打开 `.csproj` 项目文件并在 `<PropertyGroup></PropertyGroup>` 标记中添加 `<EnableComHosting>true</EnableComHosting>`。</span><span class="sxs-lookup"><span data-stu-id="e70d5-130">Open the `.csproj` project file and add `<EnableComHosting>true</EnableComHosting>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="e70d5-131">生成项目。</span><span class="sxs-lookup"><span data-stu-id="e70d5-131">Build the project.</span></span>

<span data-ttu-id="e70d5-132">生成的输出将具有 `ProjectName.dll`、`ProjectName.deps.json`、`ProjectName.runtimeconfig.json` 和 `ProjectName.comhost.dll` 文件。</span><span class="sxs-lookup"><span data-stu-id="e70d5-132">The resulting output will have a `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` and `ProjectName.comhost.dll` file.</span></span>

## <a name="register-the-com-host-for-com"></a><span data-ttu-id="e70d5-133">为 COM 注册 COM 主机</span><span class="sxs-lookup"><span data-stu-id="e70d5-133">Register the COM host for COM</span></span>

<span data-ttu-id="e70d5-134">打开提升的命令提示符，然后运行 `regsvr32 ProjectName.comhost.dll`。</span><span class="sxs-lookup"><span data-stu-id="e70d5-134">Open an elevated command prompt and run `regsvr32 ProjectName.comhost.dll`.</span></span> <span data-ttu-id="e70d5-135">这将使用 COM 注册所有公开的 .NET 对象。</span><span class="sxs-lookup"><span data-stu-id="e70d5-135">That will register all of your exposed .NET objects with COM.</span></span>

## <a name="enabling-regfree-com"></a><span data-ttu-id="e70d5-136">启用 RegFree COM</span><span class="sxs-lookup"><span data-stu-id="e70d5-136">Enabling RegFree COM</span></span>

1. <span data-ttu-id="e70d5-137">打开 `.csproj` 项目文件并在 `<PropertyGroup></PropertyGroup>` 标记中添加 `<EnableRegFreeCom>true</EnableRegFreeCom>`。</span><span class="sxs-lookup"><span data-stu-id="e70d5-137">Open the `.csproj` project file and add `<EnableRegFreeCom>true</EnableRegFreeCom>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="e70d5-138">生成项目。</span><span class="sxs-lookup"><span data-stu-id="e70d5-138">Build the project.</span></span>

<span data-ttu-id="e70d5-139">生成的输出现在还将具有 `ProjectName.X.manifest` 文件。</span><span class="sxs-lookup"><span data-stu-id="e70d5-139">The resulting output will now also have a `ProjectName.X.manifest` file.</span></span> <span data-ttu-id="e70d5-140">此文件是用于无注册表的 COM 的并行清单。</span><span class="sxs-lookup"><span data-stu-id="e70d5-140">This file is the side-by-side manifest for use with Registry-Free COM.</span></span>

## <a name="sample"></a><span data-ttu-id="e70d5-141">示例</span><span class="sxs-lookup"><span data-stu-id="e70d5-141">Sample</span></span>

<span data-ttu-id="e70d5-142">GitHub 上的 dotnet/samples 存储库中有一个正常运行的 [COM 服务器示例](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo)。</span><span class="sxs-lookup"><span data-stu-id="e70d5-142">There is a fully functional [COM server sample](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) in the dotnet/samples repository on GitHub.</span></span>

## <a name="additional-notes"></a><span data-ttu-id="e70d5-143">附加说明</span><span class="sxs-lookup"><span data-stu-id="e70d5-143">Additional notes</span></span>

<span data-ttu-id="e70d5-144">与 .NET Framework 不同，.NET Core 不支持从 .NET Core 程序集生成 COM 类型库 (TLB)。</span><span class="sxs-lookup"><span data-stu-id="e70d5-144">Unlike in .NET Framework, there is no support in .NET Core for generating a COM Type Library (TLB) from a .NET Core assembly.</span></span> <span data-ttu-id="e70d5-145">对于接口的本机声明，必须手动编写 IDL 文件或 C++ 标头。</span><span class="sxs-lookup"><span data-stu-id="e70d5-145">You will either have to manually write an IDL file or a C++ header for the native declarations of your interfaces.</span></span>

<span data-ttu-id="e70d5-146">此外，不支持将 .NET Framework 和 .NET Core 加载到同一进程中，因此，不支持将 .NET Core COM 服务器加载到 .NET Framework COM 客户端进程，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="e70d5-146">Additionally, loading both .NET Framework and .NET Core into the same process is unsupported, and as a result loading a .NET Core COM server into a .NET Framework COM client process or vice versa is not supported.</span></span>

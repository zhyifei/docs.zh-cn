---
title: 非托管库加载算法 - .NET Core
description: .NET Core 中非托管程序集加载算法的详细说明
ms.date: 10/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: c651aa6e0f37a968e6f8b26d1909def6fa488ccd
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2019
ms.locfileid: "72303694"
---
# <a name="unmanaged-native-library-loading-algorithm"></a><span data-ttu-id="518b9-103">非托管（本机）库加载算法</span><span class="sxs-lookup"><span data-stu-id="518b9-103">Unmanaged (native) library loading algorithm</span></span>

<span data-ttu-id="518b9-104">非托管库与涉及不同阶段的算法一起定位并加载。</span><span class="sxs-lookup"><span data-stu-id="518b9-104">Unmanaged libraries are located and loaded with an algorithm involving various stages.</span></span>

<span data-ttu-id="518b9-105">以下算法描述如何通过 `PInvoke` 加载本机库。</span><span class="sxs-lookup"><span data-stu-id="518b9-105">The following algorithm describes how native libraries are loaded through `PInvoke`.</span></span>

## <a name="pinvoke-load-library-algorithm"></a><span data-ttu-id="518b9-106">`PInvoke` 加载库算法</span><span class="sxs-lookup"><span data-stu-id="518b9-106">`PInvoke` load library algorithm</span></span>

<span data-ttu-id="518b9-107">`PInvoke` 在尝试加载非托管程序集时使用以下算法：</span><span class="sxs-lookup"><span data-stu-id="518b9-107">`PInvoke` uses the following algorithm when attempting to load an unmanaged assembly:</span></span>

1. <span data-ttu-id="518b9-108">确定 `active` <xref:System.Runtime.Loader.AssemblyLoadContext>。</span><span class="sxs-lookup"><span data-stu-id="518b9-108">Determine the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>.</span></span> <span data-ttu-id="518b9-109">对于非托管加载库，`active` AssemblyLoadContext 是具有定义 `PInvoke` 的程序集的算法。</span><span class="sxs-lookup"><span data-stu-id="518b9-109">For an unmanaged load library, the `active` AssemblyLoadContext is the one with the assembly that defines the `PInvoke`.</span></span>

2. <span data-ttu-id="518b9-110">对于 `active` <xref:System.Runtime.Loader.AssemblyLoadContext>，尝试通过以下方式按优先级排序来查找程序集：</span><span class="sxs-lookup"><span data-stu-id="518b9-110">For the `active` <xref:System.Runtime.Loader.AssemblyLoadContext>, try to find the assembly in priority order by:</span></span>
    * <span data-ttu-id="518b9-111">检查其缓存。</span><span class="sxs-lookup"><span data-stu-id="518b9-111">Checking its cache.</span></span>

    * <span data-ttu-id="518b9-112">调用由 <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> 函数设置的当前 <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> 委托。</span><span class="sxs-lookup"><span data-stu-id="518b9-112">Calling the current <xref:System.Runtime.InteropServices.DllImportResolver?displayProperty=nameWithType> delegate set by the <xref:System.Runtime.InteropServices.NativeLibrary.SetDllImportResolver(System.Reflection.Assembly,System.Runtime.InteropServices.DllImportResolver)?displayProperty=nameWithType> function.</span></span>

    * <span data-ttu-id="518b9-113">对 `active` AssemblyLoadContext 调用 <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> 函数。</span><span class="sxs-lookup"><span data-stu-id="518b9-113">Calling the <xref:System.Runtime.Loader.AssemblyLoadContext.LoadUnmanagedDll%2A?displayProperty=nameWithType> function on the `active` AssemblyLoadContext.</span></span>

    * <span data-ttu-id="518b9-114">检查 <xref:System.AppDomain> 实例的缓存并运行[非托管（本机）库探测](default-probing.md#unmanaged-native-library-probing)逻辑。</span><span class="sxs-lookup"><span data-stu-id="518b9-114">Checking the <xref:System.AppDomain> instance's cache and running the [Unmanaged (native) library probing](default-probing.md#unmanaged-native-library-probing) logic.</span></span>

    * <span data-ttu-id="518b9-115">引发 `active` AssemblyLoadContext 的 <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> 事件。</span><span class="sxs-lookup"><span data-stu-id="518b9-115">Raising the <xref:System.Runtime.Loader.AssemblyLoadContext.ResolvingUnmanagedDll?displayProperty=nameWithType> event for the `active` AssemblyLoadContext.</span></span>

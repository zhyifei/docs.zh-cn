---
title: "外部函数 (F#)"
description: "了解如何为本机代码中调用函数的 F # 语言支持。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c26b6124-ceaa-471c-9dc9-861b4dfa332a
ms.openlocfilehash: 69b73983a91bc6c7cc38fa34484a3c89fc01858f
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2017
---
# <a name="external-functions"></a><span data-ttu-id="e3039-104">外部函数</span><span class="sxs-lookup"><span data-stu-id="e3039-104">External Functions</span></span>

<span data-ttu-id="e3039-105">本主题介绍为本机代码中调用函数的 F # 语言支持。</span><span class="sxs-lookup"><span data-stu-id="e3039-105">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="e3039-106">语法</span><span class="sxs-lookup"><span data-stu-id="e3039-106">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="e3039-107">备注</span><span class="sxs-lookup"><span data-stu-id="e3039-107">Remarks</span></span>

<span data-ttu-id="e3039-108">在上述语法中，*参数*表示自变量，则提供给`System.Runtime.InteropServices.DllImportAttribute`属性。</span><span class="sxs-lookup"><span data-stu-id="e3039-108">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="e3039-109">第一个参数是一个字符串，表示包含此函数，而无需.dll 扩展名的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="e3039-109">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="e3039-110">可以为任何的公共属性提供其他参数`System.Runtime.InteropServices.DllImportAttribute`类，如的调用约定。</span><span class="sxs-lookup"><span data-stu-id="e3039-110">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="e3039-111">假定你具有本机 c + + DLL，它包含以下导出的函数。</span><span class="sxs-lookup"><span data-stu-id="e3039-111">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="e3039-112">可以通过使用下面的代码从 F # 中调用此函数。</span><span class="sxs-lookup"><span data-stu-id="e3039-112">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="e3039-113">与本机代码的互操作性称为*平台调用*，并且是 CLR 的功能。</span><span class="sxs-lookup"><span data-stu-id="e3039-113">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="e3039-114">有关详细信息，请参阅[与非托管代码交互操作](../../../../docs/framework/interop/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e3039-114">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="e3039-115">该部分中的信息都适用于 F #。</span><span class="sxs-lookup"><span data-stu-id="e3039-115">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="e3039-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3039-116">See Also</span></span>

[<span data-ttu-id="e3039-117">函数</span><span class="sxs-lookup"><span data-stu-id="e3039-117">Functions</span></span>](index.md)

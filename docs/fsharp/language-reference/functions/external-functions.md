---
title: 外部函数 (F#)
description: '了解如何为本机代码中调用函数的 F # 语言支持。'
ms.date: 05/16/2016
ms.openlocfilehash: 398697c5e0deab7f8d81ec5198ab1918bd865e13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564477"
---
# <a name="external-functions"></a><span data-ttu-id="99795-103">外部函数</span><span class="sxs-lookup"><span data-stu-id="99795-103">External Functions</span></span>

<span data-ttu-id="99795-104">本主题介绍为本机代码中调用函数的 F # 语言支持。</span><span class="sxs-lookup"><span data-stu-id="99795-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="99795-105">语法</span><span class="sxs-lookup"><span data-stu-id="99795-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="99795-106">备注</span><span class="sxs-lookup"><span data-stu-id="99795-106">Remarks</span></span>

<span data-ttu-id="99795-107">在上述语法中，*参数*表示自变量，则提供给`System.Runtime.InteropServices.DllImportAttribute`属性。</span><span class="sxs-lookup"><span data-stu-id="99795-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="99795-108">第一个参数是一个字符串，表示包含此函数，而无需.dll 扩展名的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="99795-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="99795-109">可以为任何的公共属性提供其他参数`System.Runtime.InteropServices.DllImportAttribute`类，如的调用约定。</span><span class="sxs-lookup"><span data-stu-id="99795-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="99795-110">假定你具有本机 c + + DLL，它包含以下导出的函数。</span><span class="sxs-lookup"><span data-stu-id="99795-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="99795-111">可以通过使用下面的代码从 F # 中调用此函数。</span><span class="sxs-lookup"><span data-stu-id="99795-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="99795-112">与本机代码的互操作性称为*平台调用*，并且是 CLR 的功能。</span><span class="sxs-lookup"><span data-stu-id="99795-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="99795-113">有关详细信息，请参阅[与非托管代码交互操作](../../../../docs/framework/interop/index.md)。</span><span class="sxs-lookup"><span data-stu-id="99795-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="99795-114">该部分中的信息都适用于 F #。</span><span class="sxs-lookup"><span data-stu-id="99795-114">The information in that section is applicable to F#.</span></span>


## <a name="see-also"></a><span data-ttu-id="99795-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="99795-115">See Also</span></span>

[<span data-ttu-id="99795-116">函数</span><span class="sxs-lookup"><span data-stu-id="99795-116">Functions</span></span>](index.md)

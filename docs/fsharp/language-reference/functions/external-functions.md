---
title: 外部函数
description: 了解如何F#在本机代码中调用函数的语言支持。
ms.date: 05/16/2016
ms.openlocfilehash: 86ea78844fb812361233f8360c377465d83be203
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611720"
---
# <a name="external-functions"></a><span data-ttu-id="4b15e-103">外部函数</span><span class="sxs-lookup"><span data-stu-id="4b15e-103">External Functions</span></span>

<span data-ttu-id="4b15e-104">本主题介绍F#在本机代码中调用函数的语言支持。</span><span class="sxs-lookup"><span data-stu-id="4b15e-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="4b15e-105">语法</span><span class="sxs-lookup"><span data-stu-id="4b15e-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="4b15e-106">备注</span><span class="sxs-lookup"><span data-stu-id="4b15e-106">Remarks</span></span>

<span data-ttu-id="4b15e-107">在上述语法中，*自变量*表示参数提供给`System.Runtime.InteropServices.DllImportAttribute`属性。</span><span class="sxs-lookup"><span data-stu-id="4b15e-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="4b15e-108">第一个参数是一个字符串，表示包含此函数，不带.dll 扩展名的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="4b15e-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="4b15e-109">可以提供其他参数的公共属性的任何`System.Runtime.InteropServices.DllImportAttribute`类，如调用约定。</span><span class="sxs-lookup"><span data-stu-id="4b15e-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="4b15e-110">假设您有一个本机 c + + DLL，其中包含以下导出的函数。</span><span class="sxs-lookup"><span data-stu-id="4b15e-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="4b15e-111">可以调用该函数从F#通过使用下面的代码。</span><span class="sxs-lookup"><span data-stu-id="4b15e-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="4b15e-112">与本机代码互操作性称为*平台调用*，并且是 CLR 的功能。</span><span class="sxs-lookup"><span data-stu-id="4b15e-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="4b15e-113">有关详细信息，请参阅[与非托管代码交互操作](../../../../docs/framework/interop/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4b15e-113">For more information, see [Interoperating with Unmanaged Code](../../../../docs/framework/interop/index.md).</span></span> <span data-ttu-id="4b15e-114">该部分中的信息是适用于F#。</span><span class="sxs-lookup"><span data-stu-id="4b15e-114">The information in that section is applicable to F#.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b15e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b15e-115">See also</span></span>

- [<span data-ttu-id="4b15e-116">函数</span><span class="sxs-lookup"><span data-stu-id="4b15e-116">Functions</span></span>](index.md)
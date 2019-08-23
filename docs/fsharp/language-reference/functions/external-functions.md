---
title: 外部函数
description: 了解如何在F#本机代码中调用函数的语言支持。
ms.date: 05/16/2016
ms.openlocfilehash: 3c8edaba25e07b6ca2c44a58c4b55dc98a13b4fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968731"
---
# <a name="external-functions"></a><span data-ttu-id="415b3-103">外部函数</span><span class="sxs-lookup"><span data-stu-id="415b3-103">External Functions</span></span>

<span data-ttu-id="415b3-104">本主题介绍F#在本机代码中调用函数的语言支持。</span><span class="sxs-lookup"><span data-stu-id="415b3-104">This topic describes F# language support for calling functions in native code.</span></span>

## <a name="syntax"></a><span data-ttu-id="415b3-105">语法</span><span class="sxs-lookup"><span data-stu-id="415b3-105">Syntax</span></span>

```fsharp
[<DllImport( arguments )>]
extern declaration
```

## <a name="remarks"></a><span data-ttu-id="415b3-106">备注</span><span class="sxs-lookup"><span data-stu-id="415b3-106">Remarks</span></span>

<span data-ttu-id="415b3-107">在前面的语法中,*参数*表示提供给`System.Runtime.InteropServices.DllImportAttribute`特性的参数。</span><span class="sxs-lookup"><span data-stu-id="415b3-107">In the previous syntax, *arguments* represents arguments that are supplied to the `System.Runtime.InteropServices.DllImportAttribute` attribute.</span></span> <span data-ttu-id="415b3-108">第一个参数是一个字符串, 表示包含此函数的 DLL 的名称, 但不包含 .dll 扩展名。</span><span class="sxs-lookup"><span data-stu-id="415b3-108">The first argument is a string that represents the name of the DLL that contains this function, without the .dll extension.</span></span> <span data-ttu-id="415b3-109">可以为`System.Runtime.InteropServices.DllImportAttribute`类的任何公共属性 (如调用约定) 提供其他参数。</span><span class="sxs-lookup"><span data-stu-id="415b3-109">Additional arguments can be supplied for any of the public properties of the `System.Runtime.InteropServices.DllImportAttribute` class, such as the calling convention.</span></span>

<span data-ttu-id="415b3-110">假设你有一个包含C++以下导出函数的本机 DLL。</span><span class="sxs-lookup"><span data-stu-id="415b3-110">Assume you have a native C++ DLL that contains the following exported function.</span></span>

```cpp
#include <stdio.h>
extern "C" void __declspec(dllexport) HelloWorld()
{
    printf("Hello world, invoked by F#!\n");
}
```

<span data-ttu-id="415b3-111">您可以通过使用以下代码F#从调用此函数。</span><span class="sxs-lookup"><span data-stu-id="415b3-111">You can call this function from F# by using the following code.</span></span>

```fsharp
open System.Runtime.InteropServices

module InteropWithNative =
    [<DllImport(@"C:\bin\nativedll", CallingConvention = CallingConvention.Cdecl)>]
    extern void HelloWorld()

InteropWithNative.HelloWorld()
```

<span data-ttu-id="415b3-112">与本机代码的互操作性称为*平台调用*, 是 CLR 的一项功能。</span><span class="sxs-lookup"><span data-stu-id="415b3-112">Interoperability with native code is referred to as *platform invoke* and is a feature of the CLR.</span></span> <span data-ttu-id="415b3-113">有关详细信息，请参阅[与非托管代码交互操作](../../../framework/interop/index.md)。</span><span class="sxs-lookup"><span data-stu-id="415b3-113">For more information, see [Interoperating with Unmanaged Code](../../../framework/interop/index.md).</span></span> <span data-ttu-id="415b3-114">此部分中的信息适用于F#。</span><span class="sxs-lookup"><span data-stu-id="415b3-114">The information in that section is applicable to F#.</span></span>

## <a name="see-also"></a><span data-ttu-id="415b3-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="415b3-115">See also</span></span>

- [<span data-ttu-id="415b3-116">函数</span><span class="sxs-lookup"><span data-stu-id="415b3-116">Functions</span></span>](index.md)

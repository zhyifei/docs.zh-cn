---
title: 'Fixed 的关键字 （F #）'
description: '了解如何可以固定到堆栈本地，若要防止收集使用 F # fixed 关键字。'
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 8c1d486ec754335dfbaeec439b1eb949494e4241
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="302ed-103">Fixed 的关键字</span><span class="sxs-lookup"><span data-stu-id="302ed-103">The Fixed Keyword</span></span>

<span data-ttu-id="302ed-104">F # 4.1 引入了`fixed`关键字，可用于"固定"到堆栈上的本地，以防止其被收集或在垃圾回收期间移动。</span><span class="sxs-lookup"><span data-stu-id="302ed-104">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="302ed-105">它用于低级别编程方案。</span><span class="sxs-lookup"><span data-stu-id="302ed-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="302ed-106">语法</span><span class="sxs-lookup"><span data-stu-id="302ed-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="302ed-107">备注</span><span class="sxs-lookup"><span data-stu-id="302ed-107">Remarks</span></span>

<span data-ttu-id="302ed-108">这将扩展的语法的表达式，以允许提取一个指针，并将其绑定到已阻止正在收集或在垃圾回收期间移动的名称。</span><span class="sxs-lookup"><span data-stu-id="302ed-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="302ed-109">表达式中的指针固定通过`fixed`关键字绑定到通过标识符`use`关键字。</span><span class="sxs-lookup"><span data-stu-id="302ed-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="302ed-110">此语义是类似于通过资源管理`use`关键字。</span><span class="sxs-lookup"><span data-stu-id="302ed-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="302ed-111">指针被固定在范围内，而超出范围后，它不再被固定。</span><span class="sxs-lookup"><span data-stu-id="302ed-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="302ed-112">`fixed` 不能使用的上下文之外`use`绑定。</span><span class="sxs-lookup"><span data-stu-id="302ed-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="302ed-113">必须将该指针绑定到的名称与`use`。</span><span class="sxs-lookup"><span data-stu-id="302ed-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="302ed-114">利用`fixed`必须在函数或方法中的表达式中执行。</span><span class="sxs-lookup"><span data-stu-id="302ed-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="302ed-115">它不能在脚本级别或模块级别的作用域。</span><span class="sxs-lookup"><span data-stu-id="302ed-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="302ed-116">像所有的指针代码，这是不安全的功能，将发出警告时使用。</span><span class="sxs-lookup"><span data-stu-id="302ed-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="302ed-117">示例</span><span class="sxs-lookup"><span data-stu-id="302ed-117">Example</span></span>

```fsharp
open Microsoft.FSharp.NativeInterop

type Point = { mutable X: int; mutable Y: int}

let squareWithPointer (p: nativeptr<int>) =
    // Dereference the pointer at the 0th address.
    let mutable value = NativePtr.get p 0

    // Perform some work
    value <- value * value

    // Set the value in the pointer at the 0th address.
    NativePtr.set p 0 value

let pnt = { X = 1; Y = 2 }
printfn "pnt before - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 2

// Note that the use of 'fixed' is inside a function.
// You cannot fix a pointer at a script-level or module-level scope.
let doPointerWork() =
    use ptr = fixed &pnt.Y

    // Square the Y value
    squareWithPointer ptr
    printfn "pnt after - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 4

doPointerWork()
```

## <a name="see-also"></a><span data-ttu-id="302ed-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="302ed-118">See Also</span></span>

[<span data-ttu-id="302ed-119">NativePtr 模块</span><span class="sxs-lookup"><span data-stu-id="302ed-119">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)

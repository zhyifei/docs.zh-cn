---
title: "Fixed 的关键字 （F #）"
description: "了解如何可以固定到堆栈本地，若要防止收集使用 F # fixed 关键字。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5795ce1f-11bf-4798-9f1f-6e44ffa1477e
ms.openlocfilehash: 1605603bc35941e21c798600140036fb678869b5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="0b6d3-104">Fixed 的关键字</span><span class="sxs-lookup"><span data-stu-id="0b6d3-104">The Fixed Keyword</span></span>

<span data-ttu-id="0b6d3-105">F # 4.1 引入了`fixed`关键字，可用于"固定"到堆栈上的本地，以防止其被收集或在垃圾回收期间移动。</span><span class="sxs-lookup"><span data-stu-id="0b6d3-105">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="0b6d3-106">它用于低级别编程方案。</span><span class="sxs-lookup"><span data-stu-id="0b6d3-106">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="0b6d3-107">语法</span><span class="sxs-lookup"><span data-stu-id="0b6d3-107">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="0b6d3-108">备注</span><span class="sxs-lookup"><span data-stu-id="0b6d3-108">Remarks</span></span>

<span data-ttu-id="0b6d3-109">这将扩展的语法的表达式，以允许提取一个指针，并将其绑定到已阻止正在收集或在垃圾回收期间移动的名称。</span><span class="sxs-lookup"><span data-stu-id="0b6d3-109">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="0b6d3-110">表达式中的指针固定通过`fixed`关键字绑定到通过标识符`use`关键字。</span><span class="sxs-lookup"><span data-stu-id="0b6d3-110">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="0b6d3-111">此语义是类似于通过资源管理`use`关键字。</span><span class="sxs-lookup"><span data-stu-id="0b6d3-111">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="0b6d3-112">指针被固定在范围内，而超出范围后，它不再被固定。</span><span class="sxs-lookup"><span data-stu-id="0b6d3-112">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="0b6d3-113">`fixed`不能使用的上下文之外`use`绑定。</span><span class="sxs-lookup"><span data-stu-id="0b6d3-113">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="0b6d3-114">必须将该指针绑定到的名称与`use`。</span><span class="sxs-lookup"><span data-stu-id="0b6d3-114">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="0b6d3-115">利用`fixed`必须在函数或方法中的表达式中执行。</span><span class="sxs-lookup"><span data-stu-id="0b6d3-115">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="0b6d3-116">它不能在脚本级别或模块级别的作用域。</span><span class="sxs-lookup"><span data-stu-id="0b6d3-116">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="0b6d3-117">像所有的指针代码，这是不安全的功能，将发出警告时使用。</span><span class="sxs-lookup"><span data-stu-id="0b6d3-117">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="0b6d3-118">示例</span><span class="sxs-lookup"><span data-stu-id="0b6d3-118">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0b6d3-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b6d3-119">See Also</span></span>

[<span data-ttu-id="0b6d3-120">NativePtr 模块</span><span class="sxs-lookup"><span data-stu-id="0b6d3-120">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)

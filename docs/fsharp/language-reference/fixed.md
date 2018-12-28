---
title: Fixed 的关键字
description: 了解如何将 pin 到堆栈上的本地，以防止具有集合F#固定关键字。
ms.date: 04/24/2017
ms.openlocfilehash: 7fdf66560f3e2ab7584b00c7e4584d7f6c161858
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614324"
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="000f0-103">Fixed 的关键字</span><span class="sxs-lookup"><span data-stu-id="000f0-103">The fixed keyword</span></span>

<span data-ttu-id="000f0-104">F#4.1 中引入了`fixed`关键字，以便您可以"固定"到堆栈上的本地，以防止其被收集或在垃圾回收期间移动。</span><span class="sxs-lookup"><span data-stu-id="000f0-104">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="000f0-105">它用于低级别的编程方案。</span><span class="sxs-lookup"><span data-stu-id="000f0-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="000f0-106">语法</span><span class="sxs-lookup"><span data-stu-id="000f0-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="000f0-107">备注</span><span class="sxs-lookup"><span data-stu-id="000f0-107">Remarks</span></span>

<span data-ttu-id="000f0-108">这将扩展表达式，以允许提取一个指针，并将其绑定到会阻止正在收集或在垃圾回收期间移动名称的语法。</span><span class="sxs-lookup"><span data-stu-id="000f0-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="000f0-109">通过固定的表达式中的指针`fixed`关键字将绑定到通过标识符`use`关键字。</span><span class="sxs-lookup"><span data-stu-id="000f0-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="000f0-110">此语义是类似于通过资源管理`use`关键字。</span><span class="sxs-lookup"><span data-stu-id="000f0-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="000f0-111">指针被固定在范围内，而超出范围后，它不再被固定。</span><span class="sxs-lookup"><span data-stu-id="000f0-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="000f0-112">`fixed` 不能使用上下文的外部`use`绑定。</span><span class="sxs-lookup"><span data-stu-id="000f0-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="000f0-113">必须为具有名称绑定指针`use`。</span><span class="sxs-lookup"><span data-stu-id="000f0-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="000f0-114">使用`fixed`必须在函数或方法中的表达式中执行。</span><span class="sxs-lookup"><span data-stu-id="000f0-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="000f0-115">它不能在脚本级别或模块级别范围内使用。</span><span class="sxs-lookup"><span data-stu-id="000f0-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="000f0-116">如所有指针代码，这是不安全的功能，将发出警告时使用。</span><span class="sxs-lookup"><span data-stu-id="000f0-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="000f0-117">示例</span><span class="sxs-lookup"><span data-stu-id="000f0-117">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="000f0-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="000f0-118">See also</span></span>

- [<span data-ttu-id="000f0-119">NativePtr 模块</span><span class="sxs-lookup"><span data-stu-id="000f0-119">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)

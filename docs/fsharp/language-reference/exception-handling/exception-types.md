---
title: "异常类型 (F#)"
description: "了解如何定义和使用 F # 异常类型。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e850205a-b8da-459e-8f6d-cb3510f8f173
ms.openlocfilehash: a0864218841396c0ebdf26c7585e0e5bb778f83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="exception-types"></a><span data-ttu-id="1c4dd-104">异常类型</span><span class="sxs-lookup"><span data-stu-id="1c4dd-104">Exception Types</span></span>

<span data-ttu-id="1c4dd-105">有两个类别的 F # 中的异常：.NET 异常类型和 F # 异常类型。</span><span class="sxs-lookup"><span data-stu-id="1c4dd-105">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="1c4dd-106">本主题介绍如何定义和使用 F # 异常类型。</span><span class="sxs-lookup"><span data-stu-id="1c4dd-106">This topic describes how to define and use F# exception types.</span></span>


## <a name="syntax"></a><span data-ttu-id="1c4dd-107">语法</span><span class="sxs-lookup"><span data-stu-id="1c4dd-107">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="1c4dd-108">备注</span><span class="sxs-lookup"><span data-stu-id="1c4dd-108">Remarks</span></span>
<span data-ttu-id="1c4dd-109">在上述语法中，*异常类型*是新的 F # 异常类型，名称和*自变量类型*表示时引发此类型的异常可以提供自变量的类型。</span><span class="sxs-lookup"><span data-stu-id="1c4dd-109">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="1c4dd-110">你可以使用的元组类型来指定多个自变量*自变量类型*。</span><span class="sxs-lookup"><span data-stu-id="1c4dd-110">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="1c4dd-111">F # 异常的典型定义如下所示。</span><span class="sxs-lookup"><span data-stu-id="1c4dd-111">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="1c4dd-112">你可以通过使用生成此类型的异常`raise`函数，如下。</span><span class="sxs-lookup"><span data-stu-id="1c4dd-112">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="1c4dd-113">你可以在中的筛选器中直接使用 F # 异常类型`try...with`表达式，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="1c4dd-113">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="1c4dd-114">使用定义的异常类型`exception`F # 中的关键字是一种新类型，继承自`System.Exception`。</span><span class="sxs-lookup"><span data-stu-id="1c4dd-114">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>


## <a name="see-also"></a><span data-ttu-id="1c4dd-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c4dd-115">See Also</span></span>
[<span data-ttu-id="1c4dd-116">异常处理</span><span class="sxs-lookup"><span data-stu-id="1c4dd-116">Exception Handling</span></span>](index.md)

[<span data-ttu-id="1c4dd-117">异常：`raise` 函数</span><span class="sxs-lookup"><span data-stu-id="1c4dd-117">Exceptions: the `raise` Function</span></span>](the-raise-function.md)

[<span data-ttu-id="1c4dd-118">异常层次结构</span><span class="sxs-lookup"><span data-stu-id="1c4dd-118">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)

---
title: 异常类型 (F#)
description: '了解如何定义和使用 F # 异常类型。'
ms.date: 05/16/2016
ms.openlocfilehash: b8d648a3649153a3604856deb61ce41db8c40bf2
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "43858816"
---
# <a name="exception-types"></a><span data-ttu-id="98c25-103">异常类型</span><span class="sxs-lookup"><span data-stu-id="98c25-103">Exception Types</span></span>

<span data-ttu-id="98c25-104">有两个类别的 F # 中的异常：.NET 异常类型和 F # 异常类型。</span><span class="sxs-lookup"><span data-stu-id="98c25-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="98c25-105">本主题介绍如何定义和使用 F # 异常类型。</span><span class="sxs-lookup"><span data-stu-id="98c25-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="98c25-106">语法</span><span class="sxs-lookup"><span data-stu-id="98c25-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="98c25-107">备注</span><span class="sxs-lookup"><span data-stu-id="98c25-107">Remarks</span></span>

<span data-ttu-id="98c25-108">在上述语法中，*异常类型*是新的 F # 异常类型、 名称和*自变量类型*表示当引发此类型的异常时，可以提供的参数的类型。</span><span class="sxs-lookup"><span data-stu-id="98c25-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="98c25-109">可以使用的元组类型来指定多个自变量*自变量类型*。</span><span class="sxs-lookup"><span data-stu-id="98c25-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="98c25-110">F # 异常的典型定义如下所示。</span><span class="sxs-lookup"><span data-stu-id="98c25-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="98c25-111">可以使用生成此类型的异常`raise`函数，请按如下所示。</span><span class="sxs-lookup"><span data-stu-id="98c25-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="98c25-112">您可以直接在筛选器中使用 F # 异常类型`try...with`表达式，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="98c25-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="98c25-113">使用定义的异常类型`exception`F # 中的关键字是继承的新类型`System.Exception`。</span><span class="sxs-lookup"><span data-stu-id="98c25-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="98c25-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="98c25-114">See also</span></span>

- [<span data-ttu-id="98c25-115">异常处理</span><span class="sxs-lookup"><span data-stu-id="98c25-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="98c25-116">异常：`raise` 函数</span><span class="sxs-lookup"><span data-stu-id="98c25-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="98c25-117">异常层次结构</span><span class="sxs-lookup"><span data-stu-id="98c25-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)

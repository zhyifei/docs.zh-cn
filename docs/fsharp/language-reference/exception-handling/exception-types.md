---
title: 异常类型
description: 了解如何定义和使用F#异常类型。
ms.date: 05/16/2016
ms.openlocfilehash: ed721dd0dc46a486fafeac2fa4c096800995ccb7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772718"
---
# <a name="exception-types"></a><span data-ttu-id="f4334-103">异常类型</span><span class="sxs-lookup"><span data-stu-id="f4334-103">Exception Types</span></span>

<span data-ttu-id="f4334-104">有两个类别中的异常的F#:.NET 异常类型和F#异常类型。</span><span class="sxs-lookup"><span data-stu-id="f4334-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="f4334-105">本主题介绍如何定义和使用F#异常类型。</span><span class="sxs-lookup"><span data-stu-id="f4334-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="f4334-106">语法</span><span class="sxs-lookup"><span data-stu-id="f4334-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="f4334-107">备注</span><span class="sxs-lookup"><span data-stu-id="f4334-107">Remarks</span></span>

<span data-ttu-id="f4334-108">在上述语法中，*异常类型*的新名称F#异常类型和*自变量类型*表示当引发此类型的异常时，可以提供的参数的类型。</span><span class="sxs-lookup"><span data-stu-id="f4334-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="f4334-109">可以使用的元组类型来指定多个自变量*自变量类型*。</span><span class="sxs-lookup"><span data-stu-id="f4334-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="f4334-110">典型定义F#异常将如下所示。</span><span class="sxs-lookup"><span data-stu-id="f4334-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="f4334-111">可以使用生成此类型的异常`raise`函数，请按如下所示。</span><span class="sxs-lookup"><span data-stu-id="f4334-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="f4334-112">可以使用F#直接在中的筛选器中的异常类型`try...with`表达式，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="f4334-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="f4334-113">使用定义的异常类型`exception`中的关键字F#是一种新类型，继承自`System.Exception`。</span><span class="sxs-lookup"><span data-stu-id="f4334-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4334-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4334-114">See also</span></span>

- [<span data-ttu-id="f4334-115">异常处理</span><span class="sxs-lookup"><span data-stu-id="f4334-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="f4334-116">异常：`raise` 函数</span><span class="sxs-lookup"><span data-stu-id="f4334-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="f4334-117">异常层次结构</span><span class="sxs-lookup"><span data-stu-id="f4334-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
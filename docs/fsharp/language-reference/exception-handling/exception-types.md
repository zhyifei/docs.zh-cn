---
title: 异常类型
description: 了解如何定义和使用F#异常类型。
ms.date: 05/16/2016
ms.openlocfilehash: 8545fab50ff6338d1f1621710a838a200f9ac705
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630309"
---
# <a name="exception-types"></a><span data-ttu-id="42230-103">异常类型</span><span class="sxs-lookup"><span data-stu-id="42230-103">Exception Types</span></span>

<span data-ttu-id="42230-104">中F#有两类异常: .net 异常类型和F#异常类型。</span><span class="sxs-lookup"><span data-stu-id="42230-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="42230-105">本主题介绍如何定义和使用F#异常类型。</span><span class="sxs-lookup"><span data-stu-id="42230-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="42230-106">语法</span><span class="sxs-lookup"><span data-stu-id="42230-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="42230-107">备注</span><span class="sxs-lookup"><span data-stu-id="42230-107">Remarks</span></span>

<span data-ttu-id="42230-108">在前面的语法中, *exception 类型*是新F#异常类型的名称,*参数类型*表示在引发此类型的异常时可以提供的参数的类型。</span><span class="sxs-lookup"><span data-stu-id="42230-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="42230-109">您可以通过使用*参数类型*的元组类型指定多个参数。</span><span class="sxs-lookup"><span data-stu-id="42230-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="42230-110">F#异常的典型定义如下所示。</span><span class="sxs-lookup"><span data-stu-id="42230-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="42230-111">您可以使用`raise`函数生成此类型的异常, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="42230-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="42230-112">您可以直接在F# `try...with`表达式的筛选器中使用异常类型, 如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="42230-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="42230-113">使用中`exception` F#的关键字定义的异常类型是从`System.Exception`继承的新类型。</span><span class="sxs-lookup"><span data-stu-id="42230-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="42230-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="42230-114">See also</span></span>

- [<span data-ttu-id="42230-115">异常处理</span><span class="sxs-lookup"><span data-stu-id="42230-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="42230-116">异常：`raise` 函数</span><span class="sxs-lookup"><span data-stu-id="42230-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="42230-117">异常层次结构</span><span class="sxs-lookup"><span data-stu-id="42230-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)

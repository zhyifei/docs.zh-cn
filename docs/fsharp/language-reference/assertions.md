---
title: 断言
description: 了解如何使用 "assert" 表达式作为F#编程语言中的测试表达式的调试功能。
ms.date: 10/22/2019
ms.openlocfilehash: 430db20e5ca307ba43a72e678a0424e03b0ac381
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799061"
---
# <a name="assertions"></a><span data-ttu-id="5c0ea-103">断言</span><span class="sxs-lookup"><span data-stu-id="5c0ea-103">Assertions</span></span>

<span data-ttu-id="5c0ea-104">`assert` 表达式是一种可用于测试表达式的调试功能。</span><span class="sxs-lookup"><span data-stu-id="5c0ea-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="5c0ea-105">在调试模式中遇到故障时，断言将生成一个系统错误对话框。</span><span class="sxs-lookup"><span data-stu-id="5c0ea-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="5c0ea-106">语法</span><span class="sxs-lookup"><span data-stu-id="5c0ea-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="5c0ea-107">备注</span><span class="sxs-lookup"><span data-stu-id="5c0ea-107">Remarks</span></span>

<span data-ttu-id="5c0ea-108">`assert` 表达式的类型为 `bool -> unit`。</span><span class="sxs-lookup"><span data-stu-id="5c0ea-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="5c0ea-109">`assert` 函数可解析为 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="5c0ea-109">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5c0ea-110">这意味着，其行为等同于直接调用 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="5c0ea-110">This means its behavior is identical to having called <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> directly.</span></span>

<span data-ttu-id="5c0ea-111">仅当在调试模式下进行编译时，才启用断言检查;也就是说，如果定义了常量 `DEBUG`。</span><span class="sxs-lookup"><span data-stu-id="5c0ea-111">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="5c0ea-112">在项目系统中，默认情况下，`DEBUG` 常数是在调试配置中定义的，而不是在发布配置中定义的。</span><span class="sxs-lookup"><span data-stu-id="5c0ea-112">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="5c0ea-113">使用F#异常处理无法捕获断言失败错误。</span><span class="sxs-lookup"><span data-stu-id="5c0ea-113">The assertion failure error cannot be caught by using F# exception handling.</span></span>

## <a name="example"></a><span data-ttu-id="5c0ea-114">示例</span><span class="sxs-lookup"><span data-stu-id="5c0ea-114">Example</span></span>

<span data-ttu-id="5c0ea-115">下面的代码示例演示了 `assert` 表达式的用法。</span><span class="sxs-lookup"><span data-stu-id="5c0ea-115">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="5c0ea-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c0ea-116">See also</span></span>

- [<span data-ttu-id="5c0ea-117">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="5c0ea-117">F# Language Reference</span></span>](index.md)

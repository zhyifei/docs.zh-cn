---
title: 断言
description: 了解如何使用 "assert" 表达式作为F#编程语言中的测试表达式的调试功能。
ms.date: 05/16/2016
ms.openlocfilehash: b8b7e9662143b432d650f87515d4af31cced4149
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630034"
---
# <a name="assertions"></a><span data-ttu-id="26f49-103">断言</span><span class="sxs-lookup"><span data-stu-id="26f49-103">Assertions</span></span>

<span data-ttu-id="26f49-104">`assert`表达式是一种可用于测试表达式的调试功能。</span><span class="sxs-lookup"><span data-stu-id="26f49-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="26f49-105">在调试模式中遇到故障时，断言将生成一个系统错误对话框。</span><span class="sxs-lookup"><span data-stu-id="26f49-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="26f49-106">语法</span><span class="sxs-lookup"><span data-stu-id="26f49-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="26f49-107">备注</span><span class="sxs-lookup"><span data-stu-id="26f49-107">Remarks</span></span>

<span data-ttu-id="26f49-108">表达式`assert`的类型`bool -> unit`为。</span><span class="sxs-lookup"><span data-stu-id="26f49-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="26f49-109">在前面的语法中, *condition*表示要测试的布尔表达式。</span><span class="sxs-lookup"><span data-stu-id="26f49-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="26f49-110">如果表达式的计算结果`true`为, 则继续不受影响。</span><span class="sxs-lookup"><span data-stu-id="26f49-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="26f49-111">如果计算结果为`false`, 则会生成系统错误对话框。</span><span class="sxs-lookup"><span data-stu-id="26f49-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="26f49-112">错误对话框的标题包含字符串**断言失败**。</span><span class="sxs-lookup"><span data-stu-id="26f49-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="26f49-113">该对话框包含一个堆栈跟踪, 指示断言失败发生的位置。</span><span class="sxs-lookup"><span data-stu-id="26f49-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="26f49-114">仅当在调试模式下进行编译时, 才启用断言检查;也就是说, 如果定义了常数`DEBUG` 。</span><span class="sxs-lookup"><span data-stu-id="26f49-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="26f49-115">在项目系统中, 默认情况下, `DEBUG`常量在调试配置中定义, 而不是在发布配置中定义。</span><span class="sxs-lookup"><span data-stu-id="26f49-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="26f49-116">使用F#异常处理无法捕获断言失败错误。</span><span class="sxs-lookup"><span data-stu-id="26f49-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

> [!NOTE]
> <span data-ttu-id="26f49-117">函数解析为<xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>。 `assert`</span><span class="sxs-lookup"><span data-stu-id="26f49-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="26f49-118">示例</span><span class="sxs-lookup"><span data-stu-id="26f49-118">Example</span></span>

<span data-ttu-id="26f49-119">下面的代码示例演示如何使用`assert`表达式。</span><span class="sxs-lookup"><span data-stu-id="26f49-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="26f49-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="26f49-120">See also</span></span>

- [<span data-ttu-id="26f49-121">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="26f49-121">F# Language Reference</span></span>](index.md)

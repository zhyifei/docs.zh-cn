---
title: 断言
description: 了解如何使用 assert 表达式作为一种调试功能测试中的表达式F#编程语言。
ms.date: 05/16/2016
ms.openlocfilehash: c2d97386e87e9b915da490a78fff9aedb9def616
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610198"
---
# <a name="assertions"></a><span data-ttu-id="2eefe-103">断言</span><span class="sxs-lookup"><span data-stu-id="2eefe-103">Assertions</span></span>

<span data-ttu-id="2eefe-104">`assert`表达式是一个可用于测试表达式的调试功能。</span><span class="sxs-lookup"><span data-stu-id="2eefe-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="2eefe-105">在调试模式中遇到故障时，断言将生成一个系统错误对话框。</span><span class="sxs-lookup"><span data-stu-id="2eefe-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="2eefe-106">语法</span><span class="sxs-lookup"><span data-stu-id="2eefe-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="2eefe-107">备注</span><span class="sxs-lookup"><span data-stu-id="2eefe-107">Remarks</span></span>

<span data-ttu-id="2eefe-108">`assert`表达式具有类型`bool -> unit`。</span><span class="sxs-lookup"><span data-stu-id="2eefe-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="2eefe-109">在上述语法中，*条件*表示是要测试的布尔表达式。</span><span class="sxs-lookup"><span data-stu-id="2eefe-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="2eefe-110">如果表达式计算结果为`true`，执行将继续不受影响。</span><span class="sxs-lookup"><span data-stu-id="2eefe-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="2eefe-111">如果其计算结果为`false`，则会生成系统的错误对话框。</span><span class="sxs-lookup"><span data-stu-id="2eefe-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="2eefe-112">错误对话框中已包含的字符串的标题**断言失败**。</span><span class="sxs-lookup"><span data-stu-id="2eefe-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="2eefe-113">对话框中包含指示出现了断言失败的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="2eefe-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="2eefe-114">在调试模式下; 编译时，才会启用断言检查也就是说，如果常量`DEBUG`定义。</span><span class="sxs-lookup"><span data-stu-id="2eefe-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="2eefe-115">在项目系统中，默认情况下，`DEBUG`常量在调试配置中而不是在发布配置定义。</span><span class="sxs-lookup"><span data-stu-id="2eefe-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="2eefe-116">不能通过使用捕获断言失败错误F#异常处理。</span><span class="sxs-lookup"><span data-stu-id="2eefe-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

> [!NOTE]
> <span data-ttu-id="2eefe-117">`assert`函数将解析为<xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="2eefe-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="2eefe-118">示例</span><span class="sxs-lookup"><span data-stu-id="2eefe-118">Example</span></span>

<span data-ttu-id="2eefe-119">下面的代码示例演示如何使用`assert`表达式。</span><span class="sxs-lookup"><span data-stu-id="2eefe-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="2eefe-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2eefe-120">See also</span></span>

- [<span data-ttu-id="2eefe-121">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="2eefe-121">F# Language Reference</span></span>](index.md)
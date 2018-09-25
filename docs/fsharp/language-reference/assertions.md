---
title: 断言 (F#)
description: '了解如何在 F # 编程语言中测试表达式 assert 表达式用作一种调试功能。'
ms.date: 05/16/2016
ms.openlocfilehash: 85b1e839bfd19bada48b7f1821d15ddd8fa77754
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47079709"
---
# <a name="assertions"></a><span data-ttu-id="74423-103">断言</span><span class="sxs-lookup"><span data-stu-id="74423-103">Assertions</span></span>

<span data-ttu-id="74423-104">`assert`表达式是一个可用于测试表达式的调试功能。</span><span class="sxs-lookup"><span data-stu-id="74423-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="74423-105">在调试模式中遇到故障时，断言将生成一个系统错误对话框。</span><span class="sxs-lookup"><span data-stu-id="74423-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="74423-106">语法</span><span class="sxs-lookup"><span data-stu-id="74423-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="74423-107">备注</span><span class="sxs-lookup"><span data-stu-id="74423-107">Remarks</span></span>

<span data-ttu-id="74423-108">`assert`表达式具有类型`bool -> unit`。</span><span class="sxs-lookup"><span data-stu-id="74423-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="74423-109">在上述语法中，*条件*表示是要测试的布尔表达式。</span><span class="sxs-lookup"><span data-stu-id="74423-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="74423-110">如果表达式计算结果为`true`，执行将继续不受影响。</span><span class="sxs-lookup"><span data-stu-id="74423-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="74423-111">如果其计算结果为`false`，则会生成系统的错误对话框。</span><span class="sxs-lookup"><span data-stu-id="74423-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="74423-112">错误对话框中已包含的字符串的标题**断言失败**。</span><span class="sxs-lookup"><span data-stu-id="74423-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="74423-113">对话框中包含指示出现了断言失败的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="74423-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="74423-114">在调试模式下; 编译时，才会启用断言检查也就是说，如果常量`DEBUG`定义。</span><span class="sxs-lookup"><span data-stu-id="74423-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="74423-115">在项目系统中，默认情况下，`DEBUG`常量在调试配置中而不是在发布配置定义。</span><span class="sxs-lookup"><span data-stu-id="74423-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="74423-116">不能通过使用 F # 异常处理捕获断言失败错误。</span><span class="sxs-lookup"><span data-stu-id="74423-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

>[!NOTE]
<span data-ttu-id="74423-117">`assert`函数将解析为<xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="74423-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="74423-118">示例</span><span class="sxs-lookup"><span data-stu-id="74423-118">Example</span></span>

<span data-ttu-id="74423-119">下面的代码示例演示如何使用`assert`表达式。</span><span class="sxs-lookup"><span data-stu-id="74423-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="74423-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="74423-120">See also</span></span>

- [<span data-ttu-id="74423-121">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="74423-121">F# Language Reference</span></span>](index.md)

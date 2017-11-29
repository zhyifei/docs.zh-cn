---
title: "断言 (F#)"
description: "了解如何在 F # 编程语言测试表达式断言表达式用作一种调试功能。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2badaad7-f086-47e7-99c1-91f35117da83
ms.openlocfilehash: 56891769602afaa765ebfe7e7822a179c7a22968
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="assertions"></a><span data-ttu-id="b03e4-104">断言</span><span class="sxs-lookup"><span data-stu-id="b03e4-104">Assertions</span></span>

<span data-ttu-id="b03e4-105">`assert`表达式是一种调试功能，可用于测试表达式。</span><span class="sxs-lookup"><span data-stu-id="b03e4-105">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="b03e4-106">在调试模式中遇到故障时，断言将生成一个系统错误对话框。</span><span class="sxs-lookup"><span data-stu-id="b03e4-106">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="b03e4-107">语法</span><span class="sxs-lookup"><span data-stu-id="b03e4-107">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="b03e4-108">备注</span><span class="sxs-lookup"><span data-stu-id="b03e4-108">Remarks</span></span>

<span data-ttu-id="b03e4-109">`assert`表达式具有类型`bool -> unit`。</span><span class="sxs-lookup"><span data-stu-id="b03e4-109">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="b03e4-110">在上述语法中，*条件*表示将要测试的布尔表达式。</span><span class="sxs-lookup"><span data-stu-id="b03e4-110">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="b03e4-111">如果表达式计算结果为`true`，执行会继续不受影响。</span><span class="sxs-lookup"><span data-stu-id="b03e4-111">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="b03e4-112">如果其计算结果为`false`，则会生成系统的错误对话框。</span><span class="sxs-lookup"><span data-stu-id="b03e4-112">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="b03e4-113">错误对话框中具有的标题中包含字符串**断言失败**。</span><span class="sxs-lookup"><span data-stu-id="b03e4-113">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="b03e4-114">对话框中包含堆栈跟踪，该值指示出现了断言失败。</span><span class="sxs-lookup"><span data-stu-id="b03e4-114">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="b03e4-115">在调试模式下; 编译时，才会启用断言检查也就是说，如果常量`DEBUG`定义。</span><span class="sxs-lookup"><span data-stu-id="b03e4-115">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="b03e4-116">在项目系统中，默认情况下，`DEBUG`调试配置中但不是在发布配置定义常量。</span><span class="sxs-lookup"><span data-stu-id="b03e4-116">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="b03e4-117">断言失败错误不能捕获了使用 F # 异常处理。</span><span class="sxs-lookup"><span data-stu-id="b03e4-117">The assertion failure error cannot be caught by using F# exception handling.</span></span>

>[!NOTE]
<span data-ttu-id="b03e4-118">`assert`函数将解析为<xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="b03e4-118">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="b03e4-119">示例</span><span class="sxs-lookup"><span data-stu-id="b03e4-119">Example</span></span>

<span data-ttu-id="b03e4-120">下面的代码示例演示如何使用`assert`表达式。</span><span class="sxs-lookup"><span data-stu-id="b03e4-120">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a><span data-ttu-id="b03e4-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b03e4-121">See Also</span></span>

[<span data-ttu-id="b03e4-122">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="b03e4-122">F# Language Reference</span></span>](index.md)

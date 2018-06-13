---
title: C# 语句 - C# 语言介绍
description: 使用语句创建 C# 程序操作
ms.date: 11/06/2016
ms.assetid: 5409c379-5622-4fae-88b5-1654276ea8d4
ms.openlocfilehash: 2f25c07ccc0af27a503465b9414bf607c61d1b2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351974"
---
# <a name="statements"></a><span data-ttu-id="753b8-103">语句</span><span class="sxs-lookup"><span data-stu-id="753b8-103">Statements</span></span>

<span data-ttu-id="753b8-104">程序操作使用*语句*进行表示。</span><span class="sxs-lookup"><span data-stu-id="753b8-104">The actions of a program are expressed using *statements*.</span></span> <span data-ttu-id="753b8-105">C# 支持几种不同的语句，其中许多语句是从嵌入语句的角度来定义的。</span><span class="sxs-lookup"><span data-stu-id="753b8-105">C# supports several different kinds of statements, a number of which are defined in terms of embedded statements.</span></span>

<span data-ttu-id="753b8-106">使用*代码块*，可以在允许编写一个语句的上下文中编写多个语句。</span><span class="sxs-lookup"><span data-stu-id="753b8-106">A *block* permits multiple statements to be written in contexts where a single statement is allowed.</span></span> <span data-ttu-id="753b8-107">代码块是由一系列在分隔符 `{` 和 `}` 内编写的语句组成。</span><span class="sxs-lookup"><span data-stu-id="753b8-107">A block consists of a list of statements written between the delimiters `{` and `}`.</span></span>

<span data-ttu-id="753b8-108">*声明语句*用于声明局部变量和常量。</span><span class="sxs-lookup"><span data-stu-id="753b8-108">*Declaration statements* are used to declare local variables and constants.</span></span>

<span data-ttu-id="753b8-109">*表达式语句*用于计算表达式。</span><span class="sxs-lookup"><span data-stu-id="753b8-109">*Expression statements* are used to evaluate expressions.</span></span> <span data-ttu-id="753b8-110">可用作语句的表达式包括方法调用、使用 `new` 运算符的对象分配、使用 `=` 和复合赋值运算符的赋值、使用 `++` 和 `--` 运算符和 `await` 表达式的递增和递减运算。</span><span class="sxs-lookup"><span data-stu-id="753b8-110">Expressions that can be used as statements include method invocations, object allocations using the `new` operator, assignments using `=` and the compound assignment operators, increment and decrement operations using the `++` and `--` operators and `await` expressions.</span></span>

<span data-ttu-id="753b8-111">*选择语句*用于根据一些表达式的值从多个可能的语句中选择一个以供执行。</span><span class="sxs-lookup"><span data-stu-id="753b8-111">*Selection statements* are used to select one of a number of possible statements for execution based on the value of some expression.</span></span> <span data-ttu-id="753b8-112">这一类语句包括 `if` 和 `switch` 语句。</span><span class="sxs-lookup"><span data-stu-id="753b8-112">In this group are the `if` and `switch` statements.</span></span>

<span data-ttu-id="753b8-113">*迭代语句*用于重复执行嵌入语句。</span><span class="sxs-lookup"><span data-stu-id="753b8-113">*Iteration statements* are used to execute repeatedly an embedded statement.</span></span> <span data-ttu-id="753b8-114">这一类语句包括 `while`、`do`、`for` 和 `foreach` 语句。</span><span class="sxs-lookup"><span data-stu-id="753b8-114">In this group are the `while`, `do`, `for`, and `foreach` statements.</span></span>

<span data-ttu-id="753b8-115">*跳转语句*用于转移控制权。</span><span class="sxs-lookup"><span data-stu-id="753b8-115">*Jump statements* are used to transfer control.</span></span> <span data-ttu-id="753b8-116">这一类语句包括 `break`、`continue`、`goto`、`throw`、`return` 和 `yield` 语句。</span><span class="sxs-lookup"><span data-stu-id="753b8-116">In this group are the `break`, `continue`, `goto`, `throw`, `return`, and `yield` statements.</span></span>

<span data-ttu-id="753b8-117">`try`...`catch` 语句用于捕获在代码块执行期间发生的异常，`try`...`finally` 语句用于指定始终执行的最终代码，无论异常发生与否。</span><span class="sxs-lookup"><span data-stu-id="753b8-117">The `try`...`catch` statement is used to catch exceptions that occur during execution of a block, and the `try`...`finally` statement is used to specify finalization code that is always executed, whether an exception occurred or not.</span></span>

<span data-ttu-id="753b8-118">`checked` 和 `unchecked` 语句用于控制整型类型算术运算和转换的溢出检查上下文。</span><span class="sxs-lookup"><span data-stu-id="753b8-118">The `checked` and `unchecked` statements are used to control the overflow-checking context for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="753b8-119">`lock` 语句用于获取给定对象的相互排斥锁定，执行语句，然后解除锁定。</span><span class="sxs-lookup"><span data-stu-id="753b8-119">The `lock` statement is used to obtain the mutual-exclusion lock for a given object, execute a statement, and then release the lock.</span></span>

<span data-ttu-id="753b8-120">`using` 语句用于获取资源，执行语句，然后释放资源。</span><span class="sxs-lookup"><span data-stu-id="753b8-120">The `using` statement is used to obtain a resource, execute a statement, and then dispose of that resource.</span></span>

<span data-ttu-id="753b8-121">下面列出了可以使用的各种语句，以及每种语句的示例。</span><span class="sxs-lookup"><span data-stu-id="753b8-121">The following lists the kinds of statements that can be used, and provides an example for each.</span></span>

* <span data-ttu-id="753b8-122">局部变量声明：</span><span class="sxs-lookup"><span data-stu-id="753b8-122">Local variable declaration:</span></span>

 [!code-csharp[Declarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L9-L15)]

* <span data-ttu-id="753b8-123">局部常量声明：</span><span class="sxs-lookup"><span data-stu-id="753b8-123">Local constant declaration:</span></span>

 [!code-csharp[ConstantDeclarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L17-L22)]

* <span data-ttu-id="753b8-124">表达式语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-124">Expression statement:</span></span>

 [!code-csharp[Expressions](../../../samples/snippets/csharp/tour/statements/Program.cs#L24-L31)]

* <span data-ttu-id="753b8-125">`if` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-125">`if` statement:</span></span>

 [!code-csharp[IfStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L33-L43)]

* <span data-ttu-id="753b8-126">`switch` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-126">`switch` statement:</span></span>

 [!code-csharp[SwitchStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L45-L60)]

* <span data-ttu-id="753b8-127">`while` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-127">`while` statement:</span></span>

 [!code-csharp[WhileStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L62-L70)]

* <span data-ttu-id="753b8-128">`do` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-128">`do` statement:</span></span>

 [!code-csharp[DoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L72-L81)]

* <span data-ttu-id="753b8-129">`for` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-129">`for` statement:</span></span>

 [!code-csharp[ForStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L83-L89)]

* <span data-ttu-id="753b8-130">`foreach` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-130">`foreach` statement:</span></span>

 [!code-csharp[ForEachStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L91-L97)]

* <span data-ttu-id="753b8-131">`break` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-131">`break` statement:</span></span>

 [!code-csharp[BreakStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L99-L108)]

* <span data-ttu-id="753b8-132">`continue` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-132">`continue` statement:</span></span>

 [!code-csharp[ContinueStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L110-L118)]

* <span data-ttu-id="753b8-133">`goto` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-133">`goto` statement:</span></span>

 [!code-csharp[GotoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L120-L129)]

* <span data-ttu-id="753b8-134">`return` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-134">`return` statement:</span></span>

 [!code-csharp[ReturnStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L131-L139)]

* <span data-ttu-id="753b8-135">`yield` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-135">`yield` statement:</span></span>

 [!code-csharp[YieldStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L141-L155)]

* <span data-ttu-id="753b8-136">`throw` 和 `try` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-136">`throw` statements and `try` statements:</span></span>

 [!code-csharp[TryThrow](../../../samples/snippets/csharp/tour/statements/Program.cs#L157-L183)]

* <span data-ttu-id="753b8-137">`checked` 和 `unchecked` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-137">`checked` and `unchecked` statements:</span></span>

 [!code-csharp[CheckedUncheckedStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L185-L196)]

* <span data-ttu-id="753b8-138">`lock` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-138">`lock` statement:</span></span>

 [!code-csharp[LockStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L257-L273)]

* <span data-ttu-id="753b8-139">`using` 语句：</span><span class="sxs-lookup"><span data-stu-id="753b8-139">`using` statement:</span></span>

 [!code-csharp[UsingStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L198-L206)]

>[!div class="step-by-step"]
<span data-ttu-id="753b8-140">[上一页](expressions.md)
[下一页](classes-and-objects.md)</span><span class="sxs-lookup"><span data-stu-id="753b8-140">[Previous](expressions.md)
[Next](classes-and-objects.md)</span></span>

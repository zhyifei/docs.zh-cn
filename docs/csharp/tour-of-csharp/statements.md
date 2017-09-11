---
title: "C# 语句 - C# 语言介绍"
description: "使用语句创建 C# 程序操作"
keywords: ".NET, C#, 语句, 语法"
author: BillWagner
ms.author: wiwagn
ms.date: 11/06/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 5409c379-5622-4fae-88b5-1654276ea8d4
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 99ec2489daf89926da9b8c4e148965412826a8a6
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="statements"></a><span data-ttu-id="2eebc-104">语句</span><span class="sxs-lookup"><span data-stu-id="2eebc-104">Statements</span></span>

<span data-ttu-id="2eebc-105">程序操作使用*语句*进行表示。</span><span class="sxs-lookup"><span data-stu-id="2eebc-105">The actions of a program are expressed using *statements*.</span></span> <span data-ttu-id="2eebc-106">C# 支持几种不同的语句，其中许多语句是从嵌入语句的角度来定义的。</span><span class="sxs-lookup"><span data-stu-id="2eebc-106">C# supports several different kinds of statements, a number of which are defined in terms of embedded statements.</span></span>

<span data-ttu-id="2eebc-107">使用*代码块*，可以在允许编写一个语句的上下文中编写多个语句。</span><span class="sxs-lookup"><span data-stu-id="2eebc-107">A *block* permits multiple statements to be written in contexts where a single statement is allowed.</span></span> <span data-ttu-id="2eebc-108">代码块是由一系列在分隔符 `{` 和 `}` 内编写的语句组成。</span><span class="sxs-lookup"><span data-stu-id="2eebc-108">A block consists of a list of statements written between the delimiters `{` and `}`.</span></span>

<span data-ttu-id="2eebc-109">*声明语句*用于声明局部变量和常量。</span><span class="sxs-lookup"><span data-stu-id="2eebc-109">*Declaration statements* are used to declare local variables and constants.</span></span>

<span data-ttu-id="2eebc-110">*表达式语句*用于计算表达式。</span><span class="sxs-lookup"><span data-stu-id="2eebc-110">*Expression statements* are used to evaluate expressions.</span></span> <span data-ttu-id="2eebc-111">可用作语句的表达式包括方法调用、使用 `new` 运算符的对象分配、使用 `=` 和复合赋值运算符的赋值、使用 `++` 和 `--` 运算符和 `await` 表达式的递增和递减运算。</span><span class="sxs-lookup"><span data-stu-id="2eebc-111">Expressions that can be used as statements include method invocations, object allocations using the `new` operator, assignments using `=` and the compound assignment operators, increment and decrement operations using the `++` and `--` operators and `await` expressions.</span></span>

<span data-ttu-id="2eebc-112">*选择语句*用于根据一些表达式的值从多个可能的语句中选择一个以供执行。</span><span class="sxs-lookup"><span data-stu-id="2eebc-112">*Selection statements* are used to select one of a number of possible statements for execution based on the value of some expression.</span></span> <span data-ttu-id="2eebc-113">这一类语句包括 `if` 和 `switch` 语句。</span><span class="sxs-lookup"><span data-stu-id="2eebc-113">In this group are the `if` and `switch` statements.</span></span>

<span data-ttu-id="2eebc-114">*迭代语句*用于重复执行嵌入语句。</span><span class="sxs-lookup"><span data-stu-id="2eebc-114">*Iteration statements* are used to execute repeatedly an embedded statement.</span></span> <span data-ttu-id="2eebc-115">这一类语句包括 `while`、`do`、`for` 和 `foreach` 语句。</span><span class="sxs-lookup"><span data-stu-id="2eebc-115">In this group are the `while`, `do`, `for`, and `foreach` statements.</span></span>

<span data-ttu-id="2eebc-116">*跳转语句*用于转移控制权。</span><span class="sxs-lookup"><span data-stu-id="2eebc-116">*Jump statements* are used to transfer control.</span></span> <span data-ttu-id="2eebc-117">这一类语句包括 `break`、`continue`、`goto`、`throw`、`return` 和 `yield` 语句。</span><span class="sxs-lookup"><span data-stu-id="2eebc-117">In this group are the `break`, `continue`, `goto`, `throw`, `return`, and `yield` statements.</span></span>

<span data-ttu-id="2eebc-118">`try`...`catch` 语句用于捕获在代码块执行期间发生的异常，`try`...`finally` 语句用于指定始终执行的最终代码，无论异常发生与否。</span><span class="sxs-lookup"><span data-stu-id="2eebc-118">The `try`...`catch` statement is used to catch exceptions that occur during execution of a block, and the `try`...`finally` statement is used to specify finalization code that is always executed, whether an exception occurred or not.</span></span>

<span data-ttu-id="2eebc-119">`checked` 和 `unchecked` 语句用于控制整型类型算术运算和转换的溢出检查上下文。</span><span class="sxs-lookup"><span data-stu-id="2eebc-119">The `checked` and `unchecked` statements are used to control the overflow-checking context for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="2eebc-120">`lock` 语句用于获取给定对象的相互排斥锁定，执行语句，然后解除锁定。</span><span class="sxs-lookup"><span data-stu-id="2eebc-120">The `lock` statement is used to obtain the mutual-exclusion lock for a given object, execute a statement, and then release the lock.</span></span>

<span data-ttu-id="2eebc-121">`using` 语句用于获取资源，执行语句，然后释放资源。</span><span class="sxs-lookup"><span data-stu-id="2eebc-121">The `using` statement is used to obtain a resource, execute a statement, and then dispose of that resource.</span></span>

<span data-ttu-id="2eebc-122">下面列出了可以使用的各种语句，以及每种语句的示例。</span><span class="sxs-lookup"><span data-stu-id="2eebc-122">The following lists the kinds of statements that can be used, and provides an example for each.</span></span>

* <span data-ttu-id="2eebc-123">局部变量声明：</span><span class="sxs-lookup"><span data-stu-id="2eebc-123">Local variable declaration:</span></span>

 <span data-ttu-id="2eebc-124">[!code-csharp[Declarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L9-L15)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-124">[!code-csharp[Declarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L9-L15)]</span></span>

* <span data-ttu-id="2eebc-125">局部常量声明：</span><span class="sxs-lookup"><span data-stu-id="2eebc-125">Local constant declaration:</span></span>

 <span data-ttu-id="2eebc-126">[!code-csharp[ConstantDeclarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L17-L22)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-126">[!code-csharp[ConstantDeclarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L17-L22)]</span></span>

* <span data-ttu-id="2eebc-127">表达式语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-127">Expression statement:</span></span>

 <span data-ttu-id="2eebc-128">[!code-csharp[Expressions](../../../samples/snippets/csharp/tour/statements/Program.cs#L24-L31)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-128">[!code-csharp[Expressions](../../../samples/snippets/csharp/tour/statements/Program.cs#L24-L31)]</span></span>

* <span data-ttu-id="2eebc-129">`if` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-129">`if` statement:</span></span>

 <span data-ttu-id="2eebc-130">[!code-csharp[IfStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L33-L43)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-130">[!code-csharp[IfStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L33-L43)]</span></span>

* <span data-ttu-id="2eebc-131">`switch` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-131">`switch` statement:</span></span>

 <span data-ttu-id="2eebc-132">[!code-csharp[SwitchStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L45-L60)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-132">[!code-csharp[SwitchStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L45-L60)]</span></span>

* <span data-ttu-id="2eebc-133">`while` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-133">`while` statement:</span></span>

 <span data-ttu-id="2eebc-134">[!code-csharp[WhileStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L62-L70)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-134">[!code-csharp[WhileStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L62-L70)]</span></span>

* <span data-ttu-id="2eebc-135">`do` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-135">`do` statement:</span></span>

 <span data-ttu-id="2eebc-136">[!code-csharp[DoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L72-L81)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-136">[!code-csharp[DoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L72-L81)]</span></span>

* <span data-ttu-id="2eebc-137">`for` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-137">`for` statement:</span></span>

 <span data-ttu-id="2eebc-138">[!code-csharp[ForStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L83-L89)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-138">[!code-csharp[ForStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L83-L89)]</span></span>

* <span data-ttu-id="2eebc-139">`foreach` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-139">`foreach` statement:</span></span>

 <span data-ttu-id="2eebc-140">[!code-csharp[ForEachStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L91-L97)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-140">[!code-csharp[ForEachStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L91-L97)]</span></span>

* <span data-ttu-id="2eebc-141">`break` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-141">`break` statement:</span></span>

 <span data-ttu-id="2eebc-142">[!code-csharp[BreakStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L99-L108)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-142">[!code-csharp[BreakStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L99-L108)]</span></span>

* <span data-ttu-id="2eebc-143">`continue` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-143">`continue` statement:</span></span>

 <span data-ttu-id="2eebc-144">[!code-csharp[ContinueStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L110-L118)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-144">[!code-csharp[ContinueStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L110-L118)]</span></span>

* <span data-ttu-id="2eebc-145">`goto` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-145">`goto` statement:</span></span>

 <span data-ttu-id="2eebc-146">[!code-csharp[GotoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L120-L129)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-146">[!code-csharp[GotoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L120-L129)]</span></span>

* <span data-ttu-id="2eebc-147">`return` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-147">`return` statement:</span></span>

 <span data-ttu-id="2eebc-148">[!code-csharp[ReturnStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L131-L139)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-148">[!code-csharp[ReturnStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L131-L139)]</span></span>

* <span data-ttu-id="2eebc-149">`yield` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-149">`yield` statement:</span></span>

 <span data-ttu-id="2eebc-150">[!code-csharp[YieldStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L141-L155)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-150">[!code-csharp[YieldStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L141-L155)]</span></span>

* <span data-ttu-id="2eebc-151">`throw` 和 `try` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-151">`throw` statements and `try` statements:</span></span>

 <span data-ttu-id="2eebc-152">[!code-csharp[TryThrow](../../../samples/snippets/csharp/tour/statements/Program.cs#L157-L183)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-152">[!code-csharp[TryThrow](../../../samples/snippets/csharp/tour/statements/Program.cs#L157-L183)]</span></span>

* <span data-ttu-id="2eebc-153">`checked` 和 `unchecked` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-153">`checked` and `unchecked` statements:</span></span>

 <span data-ttu-id="2eebc-154">[!code-csharp[CheckedUncheckedStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L185-L196)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-154">[!code-csharp[CheckedUncheckedStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L185-L196)]</span></span>

* <span data-ttu-id="2eebc-155">`lock` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-155">`lock` statement:</span></span>

 <span data-ttu-id="2eebc-156">[!code-csharp[LockStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L257-L273)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-156">[!code-csharp[LockStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L257-L273)]</span></span>

* <span data-ttu-id="2eebc-157">`using` 语句：</span><span class="sxs-lookup"><span data-stu-id="2eebc-157">`using` statement:</span></span>

 <span data-ttu-id="2eebc-158">[!code-csharp[UsingStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L198-L206)]</span><span class="sxs-lookup"><span data-stu-id="2eebc-158">[!code-csharp[UsingStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L198-L206)]</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="2eebc-159">[上一页](expressions.md)
[下一页](classes-and-objects.md)</span><span class="sxs-lookup"><span data-stu-id="2eebc-159">[Previous](expressions.md)
[Next](classes-and-objects.md)</span></span>


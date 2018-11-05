---
title: 异常：try...with 表达式 (F#)
description: 了解如何使用 F# 的 try...使用表达式用于异常处理。
ms.date: 05/16/2016
ms.openlocfilehash: 588960c0f8ccedb431c37d0f1314bf1a293b638c
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "44042161"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="545eb-103">异常：try...with 表达式</span><span class="sxs-lookup"><span data-stu-id="545eb-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="545eb-104">本主题介绍`try...with`表达式，用于在 F# 语言中的异常处理的表达式。</span><span class="sxs-lookup"><span data-stu-id="545eb-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>

## <a name="syntax"></a><span data-ttu-id="545eb-105">语法</span><span class="sxs-lookup"><span data-stu-id="545eb-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="545eb-106">备注</span><span class="sxs-lookup"><span data-stu-id="545eb-106">Remarks</span></span>

<span data-ttu-id="545eb-107">`try...with`表达式用于在 F# 中处理异常。</span><span class="sxs-lookup"><span data-stu-id="545eb-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="545eb-108">它相当于`try...catch`C# 中的语句。</span><span class="sxs-lookup"><span data-stu-id="545eb-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="545eb-109">在上述语法中的代码*expression1*可能会生成异常。</span><span class="sxs-lookup"><span data-stu-id="545eb-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="545eb-110">`try...with`表达式将返回一个值。</span><span class="sxs-lookup"><span data-stu-id="545eb-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="545eb-111">如果不引发任何异常，则整个表达式返回的值*expression1*。</span><span class="sxs-lookup"><span data-stu-id="545eb-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="545eb-112">如果引发异常，每个*模式*异常，以及相应的第一个匹配模式的反过来相比*表达式*，称为*异常处理程序*，则执行该分支，并总体表达式该异常处理程序中返回的表达式的值。</span><span class="sxs-lookup"><span data-stu-id="545eb-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="545eb-113">如果没有模式匹配，该异常将传播到调用堆栈，直到找到匹配的处理程序。</span><span class="sxs-lookup"><span data-stu-id="545eb-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="545eb-114">从异常处理程序中的每个表达式返回的值的类型必须匹配从中的表达式返回的类型`try`块。</span><span class="sxs-lookup"><span data-stu-id="545eb-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="545eb-115">通常情况下，还发生了错误的事实意味着没有有效的值可以返回的每个异常处理程序中的表达式。</span><span class="sxs-lookup"><span data-stu-id="545eb-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="545eb-116">常见模式是表达式的将是表达式的选项类型类型。</span><span class="sxs-lookup"><span data-stu-id="545eb-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="545eb-117">下面的代码示例说明了此模式。</span><span class="sxs-lookup"><span data-stu-id="545eb-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="545eb-118">异常可以是.NET 异常，或它们可以是 F# 异常。</span><span class="sxs-lookup"><span data-stu-id="545eb-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="545eb-119">您可以通过使用定义 F# 异常`exception`关键字。</span><span class="sxs-lookup"><span data-stu-id="545eb-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="545eb-120">可以使用各种模式要筛选的异常类型和其他条件;下表总结了选项。</span><span class="sxs-lookup"><span data-stu-id="545eb-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>

|<span data-ttu-id="545eb-121">模式</span><span class="sxs-lookup"><span data-stu-id="545eb-121">Pattern</span></span>|<span data-ttu-id="545eb-122">描述</span><span class="sxs-lookup"><span data-stu-id="545eb-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="545eb-123">:?</span><span class="sxs-lookup"><span data-stu-id="545eb-123">:?</span></span> <span data-ttu-id="545eb-124">*异常类型*</span><span class="sxs-lookup"><span data-stu-id="545eb-124">*exception-type*</span></span>|<span data-ttu-id="545eb-125">与指定的.NET 异常类型匹配。</span><span class="sxs-lookup"><span data-stu-id="545eb-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="545eb-126">:?</span><span class="sxs-lookup"><span data-stu-id="545eb-126">:?</span></span> <span data-ttu-id="545eb-127">*异常类型*作为*标识符*</span><span class="sxs-lookup"><span data-stu-id="545eb-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="545eb-128">匹配指定的.NET 异常类型，但为异常提供了一个命名的值。</span><span class="sxs-lookup"><span data-stu-id="545eb-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="545eb-129">*异常名称*(*自变量*)</span><span class="sxs-lookup"><span data-stu-id="545eb-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="545eb-130">与 F# 异常类型匹配并将自变量绑定。</span><span class="sxs-lookup"><span data-stu-id="545eb-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="545eb-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="545eb-131">*identifier*</span></span>|<span data-ttu-id="545eb-132">匹配任何异常并将名称绑定到的异常对象。</span><span class="sxs-lookup"><span data-stu-id="545eb-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="545eb-133">等效于 \**:？System.Exception 为 \* \* \* 标识符*</span><span class="sxs-lookup"><span data-stu-id="545eb-133">Equivalent to \**:? System.Exception as\*\*\*identifier*</span></span>|
|<span data-ttu-id="545eb-134">*标识符*时*条件*</span><span class="sxs-lookup"><span data-stu-id="545eb-134">*identifier* when *condition*</span></span>|<span data-ttu-id="545eb-135">如果条件为 true，则匹配的任何异常。</span><span class="sxs-lookup"><span data-stu-id="545eb-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="545eb-136">示例</span><span class="sxs-lookup"><span data-stu-id="545eb-136">Examples</span></span>

<span data-ttu-id="545eb-137">下面的代码示例演示了使用各种异常处理程序模式。</span><span class="sxs-lookup"><span data-stu-id="545eb-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

>[!NOTE]
<span data-ttu-id="545eb-138">`try...with`构造是从单独的表达式`try...finally`表达式。</span><span class="sxs-lookup"><span data-stu-id="545eb-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="545eb-139">因此，如果你的代码需要两`with`块和一个`finally`块中，必须将嵌套两个表达式。</span><span class="sxs-lookup"><span data-stu-id="545eb-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

>[!NOTE]
<span data-ttu-id="545eb-140">可以使用`try...with`在异步工作流和其他计算表达式，在这种情况下自定义的版本的`try...with`使用表达式。</span><span class="sxs-lookup"><span data-stu-id="545eb-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="545eb-141">有关详细信息，请参阅[异步工作流](../asynchronous-workflows.md)，并[计算表达式](../computation-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="545eb-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="545eb-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="545eb-142">See also</span></span>

- [<span data-ttu-id="545eb-143">异常处理</span><span class="sxs-lookup"><span data-stu-id="545eb-143">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="545eb-144">异常类型</span><span class="sxs-lookup"><span data-stu-id="545eb-144">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="545eb-145">异常：`try...finally` 表达式</span><span class="sxs-lookup"><span data-stu-id="545eb-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)

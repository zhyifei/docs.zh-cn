---
title: 异常：try...with 表达式 (F#)
description: '了解如何使用 F # try … 与表达式用于异常处理。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 06e40b79fc1958918dc0615ce9d1004e0a6e74a5
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="1106c-103">异常：try...with 表达式</span><span class="sxs-lookup"><span data-stu-id="1106c-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="1106c-104">本主题介绍`try...with`表达式，用于对 F # 语言中的异常处理的表达式。</span><span class="sxs-lookup"><span data-stu-id="1106c-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>


## <a name="syntax"></a><span data-ttu-id="1106c-105">语法</span><span class="sxs-lookup"><span data-stu-id="1106c-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="1106c-106">备注</span><span class="sxs-lookup"><span data-stu-id="1106c-106">Remarks</span></span>
<span data-ttu-id="1106c-107">`try...with`使用表达式来处理 F # 中的异常。</span><span class="sxs-lookup"><span data-stu-id="1106c-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="1106c-108">它是类似于`try...catch`C# 中的语句。</span><span class="sxs-lookup"><span data-stu-id="1106c-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="1106c-109">在前面的语法中中的代码*expression1*可能会生成异常。</span><span class="sxs-lookup"><span data-stu-id="1106c-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="1106c-110">`try...with`表达式返回一个值。</span><span class="sxs-lookup"><span data-stu-id="1106c-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="1106c-111">如果不引发任何异常，则整个表达式返回的值*expression1*。</span><span class="sxs-lookup"><span data-stu-id="1106c-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="1106c-112">如果将引发异常，每个*模式*有例外，并为第一个匹配的模式，相应反过来比较*表达式*、 称为*异常处理程序*，会执行该分支，并在该异常处理程序中，整个表达式返回表达式的值。</span><span class="sxs-lookup"><span data-stu-id="1106c-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="1106c-113">如果没有模式匹配，则直到找到匹配的处理时，异常将传播到调用堆栈中。</span><span class="sxs-lookup"><span data-stu-id="1106c-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="1106c-114">从异常处理程序中的每个表达式返回的值的类型必须匹配中的表达式返回的类型`try`块。</span><span class="sxs-lookup"><span data-stu-id="1106c-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="1106c-115">通常情况下，还发生了错误的事实意味着没有有效值可从每个异常处理程序中的表达式返回的。</span><span class="sxs-lookup"><span data-stu-id="1106c-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="1106c-116">常见模式是设置表达式的类型是选项类型。</span><span class="sxs-lookup"><span data-stu-id="1106c-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="1106c-117">下面的代码示例说明了此模式。</span><span class="sxs-lookup"><span data-stu-id="1106c-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="1106c-118">异常可以是.NET 异常，或它们可以是 F # 异常。</span><span class="sxs-lookup"><span data-stu-id="1106c-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="1106c-119">你可以通过定义 F # 例外`exception`关键字。</span><span class="sxs-lookup"><span data-stu-id="1106c-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="1106c-120">你可以使用各种模式要作为筛选依据的异常类型和其他条件;下表中概括了选项。</span><span class="sxs-lookup"><span data-stu-id="1106c-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>


|<span data-ttu-id="1106c-121">模式</span><span class="sxs-lookup"><span data-stu-id="1106c-121">Pattern</span></span>|<span data-ttu-id="1106c-122">描述</span><span class="sxs-lookup"><span data-stu-id="1106c-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="1106c-123">:?</span><span class="sxs-lookup"><span data-stu-id="1106c-123">:?</span></span> <span data-ttu-id="1106c-124">*异常类型*</span><span class="sxs-lookup"><span data-stu-id="1106c-124">*exception-type*</span></span>|<span data-ttu-id="1106c-125">与指定的.NET 异常类型匹配。</span><span class="sxs-lookup"><span data-stu-id="1106c-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="1106c-126">:?</span><span class="sxs-lookup"><span data-stu-id="1106c-126">:?</span></span> <span data-ttu-id="1106c-127">*异常类型*作为*标识符*</span><span class="sxs-lookup"><span data-stu-id="1106c-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="1106c-128">匹配指定的.NET 异常类型，但会命名的值的异常。</span><span class="sxs-lookup"><span data-stu-id="1106c-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="1106c-129">*异常名称*(*参数*)</span><span class="sxs-lookup"><span data-stu-id="1106c-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="1106c-130">匹配 F # 异常类型和绑定参数。</span><span class="sxs-lookup"><span data-stu-id="1106c-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="1106c-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="1106c-131">*identifier*</span></span>|<span data-ttu-id="1106c-132">与任何异常匹配，并绑定到的异常对象的名称。</span><span class="sxs-lookup"><span data-stu-id="1106c-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="1106c-133">等效于 **:？作为 System.Exception * * * 标识符*</span><span class="sxs-lookup"><span data-stu-id="1106c-133">Equivalent to **:? System.Exception as***identifier*</span></span>|
|<span data-ttu-id="1106c-134">*标识符*时*条件*</span><span class="sxs-lookup"><span data-stu-id="1106c-134">*identifier* when *condition*</span></span>|<span data-ttu-id="1106c-135">如果条件为 true，则匹配的任何异常。</span><span class="sxs-lookup"><span data-stu-id="1106c-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="1106c-136">示例</span><span class="sxs-lookup"><span data-stu-id="1106c-136">Examples</span></span>
<span data-ttu-id="1106c-137">下面的代码示例说明了各种异常处理程序模式的用法。</span><span class="sxs-lookup"><span data-stu-id="1106c-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]
    
>[!NOTE] 
<span data-ttu-id="1106c-138">`try...with`构造是从单独的表达式`try...finally`表达式。</span><span class="sxs-lookup"><span data-stu-id="1106c-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="1106c-139">因此，如果你的代码同时需要`with`块和一个`finally`块中，你将需要嵌套两个表达式。</span><span class="sxs-lookup"><span data-stu-id="1106c-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

>[!NOTE] 
<span data-ttu-id="1106c-140">你可以使用`try...with`在异步工作流和其他计算表达式，在这种情况下的自定义的版本`try...with`使用表达式。</span><span class="sxs-lookup"><span data-stu-id="1106c-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="1106c-141">有关详细信息，请参阅[异步工作流](../asynchronous-workflows.md)，和[计算表达式](../computation-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="1106c-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="1106c-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="1106c-142">See Also</span></span>
[<span data-ttu-id="1106c-143">异常处理</span><span class="sxs-lookup"><span data-stu-id="1106c-143">Exception Handling</span></span>](index.md)

[<span data-ttu-id="1106c-144">异常类型</span><span class="sxs-lookup"><span data-stu-id="1106c-144">Exception Types</span></span>](exception-types.md)

[<span data-ttu-id="1106c-145">异常：`try...finally` 表达式</span><span class="sxs-lookup"><span data-stu-id="1106c-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)

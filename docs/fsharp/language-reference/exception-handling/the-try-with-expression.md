---
title: 异常：try...with 表达式
description: 了解如何使用F# "try .。。带有用于异常处理的 "表达式"。
ms.date: 05/16/2016
ms.openlocfilehash: e4d615086a93e26b76cca460e797659ca13792b5
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630247"
---
# <a name="exceptions-the-trywith-expression"></a><span data-ttu-id="1ec51-103">异常：try...with 表达式</span><span class="sxs-lookup"><span data-stu-id="1ec51-103">Exceptions: The try...with Expression</span></span>

<span data-ttu-id="1ec51-104">本主题介绍`try...with`表达式, 该表达式用于F#语言中的异常处理。</span><span class="sxs-lookup"><span data-stu-id="1ec51-104">This topic describes the `try...with` expression, the expression that is used for exception handling in the F# language.</span></span>

## <a name="syntax"></a><span data-ttu-id="1ec51-105">语法</span><span class="sxs-lookup"><span data-stu-id="1ec51-105">Syntax</span></span>

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a><span data-ttu-id="1ec51-106">备注</span><span class="sxs-lookup"><span data-stu-id="1ec51-106">Remarks</span></span>

<span data-ttu-id="1ec51-107">表达式用于处理中F#的异常。 `try...with`</span><span class="sxs-lookup"><span data-stu-id="1ec51-107">The `try...with` expression is used to handle exceptions in F#.</span></span> <span data-ttu-id="1ec51-108">它与中`try...catch` C#的语句类似。</span><span class="sxs-lookup"><span data-stu-id="1ec51-108">It is similar to the `try...catch` statement in C#.</span></span> <span data-ttu-id="1ec51-109">在上述语法中,*表达式*a 中的代码可能会生成异常。</span><span class="sxs-lookup"><span data-stu-id="1ec51-109">In the preceding syntax, the code in *expression1* might generate an exception.</span></span> <span data-ttu-id="1ec51-110">表达式`try...with`将返回一个值。</span><span class="sxs-lookup"><span data-stu-id="1ec51-110">The `try...with` expression returns a value.</span></span> <span data-ttu-id="1ec51-111">如果没有引发异常, 则整个表达式将返回*表达式表达式*的值。</span><span class="sxs-lookup"><span data-stu-id="1ec51-111">If no exception is thrown, the whole expression returns the value of *expression1*.</span></span> <span data-ttu-id="1ec51-112">如果引发了异常, 则每个*模式*将依次与异常进行比较, 对于第一个匹配模式, 将执行对应的*表达式*(称为 "*异常处理程序*"), 并在整个表达式中返回该异常处理程序中的表达式的值。</span><span class="sxs-lookup"><span data-stu-id="1ec51-112">If an exception is thrown, each *pattern* is compared in turn with the exception, and for the first matching pattern, the corresponding *expression*, known as the *exception handler*, for that branch is executed, and the overall expression returns the value of the expression in that exception handler.</span></span> <span data-ttu-id="1ec51-113">如果没有模式匹配, 则异常将在调用堆栈中向上传播, 直到找到匹配的处理程序。</span><span class="sxs-lookup"><span data-stu-id="1ec51-113">If no pattern matches, the exception propagates up the call stack until a matching handler is found.</span></span> <span data-ttu-id="1ec51-114">从异常处理程序中的每个表达式返回的值的类型必须与从`try`块中的表达式返回的类型匹配。</span><span class="sxs-lookup"><span data-stu-id="1ec51-114">The types of the values returned from each expression in the exception handlers must match the type returned from the expression in the `try` block.</span></span>

<span data-ttu-id="1ec51-115">通常, 发生错误的一种情况是, 不存在可以从每个异常处理程序中的表达式返回的有效值。</span><span class="sxs-lookup"><span data-stu-id="1ec51-115">Frequently, the fact that an error occurred also means that there is no valid value that can be returned from the expressions in each exception handler.</span></span> <span data-ttu-id="1ec51-116">常见的模式是将表达式的类型作为选项类型。</span><span class="sxs-lookup"><span data-stu-id="1ec51-116">A frequent pattern is to have the type of the expression be an option type.</span></span> <span data-ttu-id="1ec51-117">下面的代码示例演示了此模式。</span><span class="sxs-lookup"><span data-stu-id="1ec51-117">The following code example illustrates this pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

<span data-ttu-id="1ec51-118">异常可能是 .NET 异常, 也可能是F#异常。</span><span class="sxs-lookup"><span data-stu-id="1ec51-118">Exceptions can be .NET exceptions, or they can be F# exceptions.</span></span> <span data-ttu-id="1ec51-119">您可以使用F# `exception`关键字来定义异常。</span><span class="sxs-lookup"><span data-stu-id="1ec51-119">You can define F# exceptions by using the `exception` keyword.</span></span>

<span data-ttu-id="1ec51-120">您可以使用多种模式筛选异常类型和其他条件;下表汇总了这些选项。</span><span class="sxs-lookup"><span data-stu-id="1ec51-120">You can use a variety of patterns to filter on the exception type and other conditions; the options are summarized in the following table.</span></span>

|<span data-ttu-id="1ec51-121">模式</span><span class="sxs-lookup"><span data-stu-id="1ec51-121">Pattern</span></span>|<span data-ttu-id="1ec51-122">描述</span><span class="sxs-lookup"><span data-stu-id="1ec51-122">Description</span></span>|
|-------|-----------|
|<span data-ttu-id="1ec51-123">:?</span><span class="sxs-lookup"><span data-stu-id="1ec51-123">:?</span></span> <span data-ttu-id="1ec51-124">*exception-type*</span><span class="sxs-lookup"><span data-stu-id="1ec51-124">*exception-type*</span></span>|<span data-ttu-id="1ec51-125">匹配指定的 .NET 异常类型。</span><span class="sxs-lookup"><span data-stu-id="1ec51-125">Matches the specified .NET exception type.</span></span>|
|<span data-ttu-id="1ec51-126">:?</span><span class="sxs-lookup"><span data-stu-id="1ec51-126">:?</span></span> <span data-ttu-id="1ec51-127">*异常类型*作为*标识符*</span><span class="sxs-lookup"><span data-stu-id="1ec51-127">*exception-type* as *identifier*</span></span>|<span data-ttu-id="1ec51-128">与指定的 .NET 异常类型匹配, 但为异常提供一个命名值。</span><span class="sxs-lookup"><span data-stu-id="1ec51-128">Matches the specified .NET exception type, but gives the exception a named value.</span></span>|
|<span data-ttu-id="1ec51-129">*exception-name*(*arguments*)</span><span class="sxs-lookup"><span data-stu-id="1ec51-129">*exception-name*(*arguments*)</span></span>|<span data-ttu-id="1ec51-130">匹配F#异常类型并绑定自变量。</span><span class="sxs-lookup"><span data-stu-id="1ec51-130">Matches an F# exception type and binds the arguments.</span></span>|
|<span data-ttu-id="1ec51-131">*identifier*</span><span class="sxs-lookup"><span data-stu-id="1ec51-131">*identifier*</span></span>|<span data-ttu-id="1ec51-132">匹配任何异常并将名称绑定到 exception 对象。</span><span class="sxs-lookup"><span data-stu-id="1ec51-132">Matches any exception and binds the name to the exception object.</span></span> <span data-ttu-id="1ec51-133">等效于 **:？Exception 作为**_标识符_</span><span class="sxs-lookup"><span data-stu-id="1ec51-133">Equivalent to **:? System.Exception as**_identifier_</span></span>|
|<span data-ttu-id="1ec51-134">*条件*时*标识符*</span><span class="sxs-lookup"><span data-stu-id="1ec51-134">*identifier* when *condition*</span></span>|<span data-ttu-id="1ec51-135">如果条件为 true, 则匹配任何异常。</span><span class="sxs-lookup"><span data-stu-id="1ec51-135">Matches any exception if the condition is true.</span></span>|

## <a name="examples"></a><span data-ttu-id="1ec51-136">示例</span><span class="sxs-lookup"><span data-stu-id="1ec51-136">Examples</span></span>

<span data-ttu-id="1ec51-137">下面的代码示例演示如何使用各种异常处理程序模式。</span><span class="sxs-lookup"><span data-stu-id="1ec51-137">The following code examples illustrate the use of the various exception handler patterns.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]

> [!NOTE]
> <span data-ttu-id="1ec51-138">构造是一个独立`try...finally`于表达式的表达式。 `try...with`</span><span class="sxs-lookup"><span data-stu-id="1ec51-138">The `try...with` construct is a separate expression from the `try...finally` expression.</span></span> <span data-ttu-id="1ec51-139">因此, 如果代码需要`with`块`finally`和块, 则必须嵌套两个表达式。</span><span class="sxs-lookup"><span data-stu-id="1ec51-139">Therefore, if your code requires both a `with` block and a `finally` block, you will have to nest the two expressions.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec51-140">可以在异步`try...with`工作流和其他计算表达式中使用, 在这种情况下, 将`try...with`使用自定义版本的表达式。</span><span class="sxs-lookup"><span data-stu-id="1ec51-140">You can use `try...with` in asynchronous workflows and other computation expressions, in which case a customized version of the `try...with` expression is used.</span></span> <span data-ttu-id="1ec51-141">有关详细信息, 请参阅[异步工作流](../asynchronous-workflows.md)和[计算表达式](../computation-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="1ec51-141">For more information, see [Asynchronous Workflows](../asynchronous-workflows.md), and [Computation Expressions](../computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1ec51-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ec51-142">See also</span></span>

- [<span data-ttu-id="1ec51-143">异常处理</span><span class="sxs-lookup"><span data-stu-id="1ec51-143">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="1ec51-144">异常类型</span><span class="sxs-lookup"><span data-stu-id="1ec51-144">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="1ec51-145">异常：`try...finally`表达式</span><span class="sxs-lookup"><span data-stu-id="1ec51-145">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)

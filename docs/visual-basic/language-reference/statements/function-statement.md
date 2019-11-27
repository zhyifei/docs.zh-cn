---
title: Function 语句
ms.date: 05/12/2018
f1_keywords:
- vb.Function
helpviewer_keywords:
- procedures [Visual Basic], creating
- Function procedures [Visual Basic], Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword [Visual Basic], Function statements
- Private keyword [Visual Basic], Function statements
- declarations [Visual Basic], procedures
- procedures [Visual Basic], declaration
- Public keyword [Visual Basic], in Function statement
- ByVal keyword [Visual Basic], Function statements
- procedures [Visual Basic], recursive
- Implements keyword [Visual Basic], Function statements
- procedures [Visual Basic], returning values
- Exit statement [Visual Basic], in Function procedures
- recursive procedures
- As keyword [Visual Basic], in Function statement
- Optional keyword [Visual Basic], Function statements
- Function statement [Visual Basic]
- Visual Basic code, Function procedures
- procedures [Visual Basic], function
- ByRef keyword [Visual Basic], Function statements
- Friend keyword [Visual Basic], Function statements
- End keyword [Visual Basic], Function statements
- Handles keyword [Visual Basic], Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
ms.openlocfilehash: 8140c7e6267e66c69c20d413a11d04372400c581
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345923"
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="0a230-102">Function 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a230-102">Function Statement (Visual Basic)</span></span>

<span data-ttu-id="0a230-103">声明定义 `Function` 过程的名称、参数和代码。</span><span class="sxs-lookup"><span data-stu-id="0a230-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="0a230-104">语法</span><span class="sxs-lookup"><span data-stu-id="0a230-104">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Function ]
    [ statements ]
End Function
```

## <a name="parts"></a><span data-ttu-id="0a230-105">部件</span><span class="sxs-lookup"><span data-stu-id="0a230-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="0a230-106">可选。</span><span class="sxs-lookup"><span data-stu-id="0a230-106">Optional.</span></span> <span data-ttu-id="0a230-107">请参阅[特性列表](attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-107">See [Attribute List](attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="0a230-108">可选。</span><span class="sxs-lookup"><span data-stu-id="0a230-108">Optional.</span></span> <span data-ttu-id="0a230-109">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="0a230-109">Can be one of the following:</span></span>

  - [<span data-ttu-id="0a230-110">Public</span><span class="sxs-lookup"><span data-stu-id="0a230-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="0a230-111">Protected</span><span class="sxs-lookup"><span data-stu-id="0a230-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="0a230-112">Friend</span><span class="sxs-lookup"><span data-stu-id="0a230-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="0a230-113">Private</span><span class="sxs-lookup"><span data-stu-id="0a230-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="0a230-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="0a230-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="0a230-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="0a230-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="0a230-116">请参阅 [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="0a230-117">可选。</span><span class="sxs-lookup"><span data-stu-id="0a230-117">Optional.</span></span> <span data-ttu-id="0a230-118">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="0a230-118">Can be one of the following:</span></span>

  - [<span data-ttu-id="0a230-119">Overloads</span><span class="sxs-lookup"><span data-stu-id="0a230-119">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)

  - [<span data-ttu-id="0a230-120">Overrides</span><span class="sxs-lookup"><span data-stu-id="0a230-120">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)

  - [<span data-ttu-id="0a230-121">Overrides</span><span class="sxs-lookup"><span data-stu-id="0a230-121">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)

  - [<span data-ttu-id="0a230-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="0a230-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)

  - [<span data-ttu-id="0a230-123">MyBase</span><span class="sxs-lookup"><span data-stu-id="0a230-123">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="0a230-124">可选。</span><span class="sxs-lookup"><span data-stu-id="0a230-124">Optional.</span></span> <span data-ttu-id="0a230-125">请参阅[共享](../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-125">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="0a230-126">可选。</span><span class="sxs-lookup"><span data-stu-id="0a230-126">Optional.</span></span> <span data-ttu-id="0a230-127">请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-127">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="0a230-128">可选。</span><span class="sxs-lookup"><span data-stu-id="0a230-128">Optional.</span></span> <span data-ttu-id="0a230-129">请参阅[Async](../../../visual-basic/language-reference/modifiers/async.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-129">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>

- `Iterator`

  <span data-ttu-id="0a230-130">可选。</span><span class="sxs-lookup"><span data-stu-id="0a230-130">Optional.</span></span> <span data-ttu-id="0a230-131">请参阅[迭代器](../../../visual-basic/language-reference/modifiers/iterator.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-131">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="0a230-132">必需。</span><span class="sxs-lookup"><span data-stu-id="0a230-132">Required.</span></span> <span data-ttu-id="0a230-133">过程的名称。</span><span class="sxs-lookup"><span data-stu-id="0a230-133">Name of the procedure.</span></span> <span data-ttu-id="0a230-134">请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="0a230-135">可选。</span><span class="sxs-lookup"><span data-stu-id="0a230-135">Optional.</span></span> <span data-ttu-id="0a230-136">泛型过程的类型参数的列表。</span><span class="sxs-lookup"><span data-stu-id="0a230-136">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="0a230-137">请参阅[类型列表](type-list.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-137">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="0a230-138">可选。</span><span class="sxs-lookup"><span data-stu-id="0a230-138">Optional.</span></span> <span data-ttu-id="0a230-139">表示此过程参数的本地变量名称列表。</span><span class="sxs-lookup"><span data-stu-id="0a230-139">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="0a230-140">请参阅[参数列表](parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-140">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="0a230-141">如果 `Option Strict` `On`，则为必需。</span><span class="sxs-lookup"><span data-stu-id="0a230-141">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="0a230-142">此过程返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="0a230-142">Data type of the value returned by this procedure.</span></span>

- `Implements`

  <span data-ttu-id="0a230-143">可选。</span><span class="sxs-lookup"><span data-stu-id="0a230-143">Optional.</span></span> <span data-ttu-id="0a230-144">指示此过程实现一个或多个 `Function` 过程，每个过程都在此过程的包含类或结构实现的接口中定义。</span><span class="sxs-lookup"><span data-stu-id="0a230-144">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="0a230-145">请参阅[Implements 语句](implements-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-145">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="0a230-146">如果提供 `Implements`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="0a230-146">Required if `Implements` is supplied.</span></span> <span data-ttu-id="0a230-147">所实现的 `Function` 过程的列表。</span><span class="sxs-lookup"><span data-stu-id="0a230-147">List of `Function` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="0a230-148">每个 `implementedprocedure` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="0a230-148">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="0a230-149">部件</span><span class="sxs-lookup"><span data-stu-id="0a230-149">Part</span></span>|<span data-ttu-id="0a230-150">说明</span><span class="sxs-lookup"><span data-stu-id="0a230-150">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="0a230-151">必需。</span><span class="sxs-lookup"><span data-stu-id="0a230-151">Required.</span></span> <span data-ttu-id="0a230-152">此过程的包含类或结构实现的接口的名称。</span><span class="sxs-lookup"><span data-stu-id="0a230-152">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="0a230-153">必需。</span><span class="sxs-lookup"><span data-stu-id="0a230-153">Required.</span></span> <span data-ttu-id="0a230-154">在 `interface` 中用于定义过程的名称。</span><span class="sxs-lookup"><span data-stu-id="0a230-154">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="0a230-155">可选。</span><span class="sxs-lookup"><span data-stu-id="0a230-155">Optional.</span></span> <span data-ttu-id="0a230-156">指示此过程可以处理一个或多个特定事件。</span><span class="sxs-lookup"><span data-stu-id="0a230-156">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="0a230-157">请参阅[句柄](handles-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-157">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="0a230-158">如果提供 `Handles`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="0a230-158">Required if `Handles` is supplied.</span></span> <span data-ttu-id="0a230-159">此过程处理的事件列表。</span><span class="sxs-lookup"><span data-stu-id="0a230-159">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="0a230-160">每个 `eventspecifier` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="0a230-160">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="0a230-161">部件</span><span class="sxs-lookup"><span data-stu-id="0a230-161">Part</span></span>|<span data-ttu-id="0a230-162">说明</span><span class="sxs-lookup"><span data-stu-id="0a230-162">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="0a230-163">必需。</span><span class="sxs-lookup"><span data-stu-id="0a230-163">Required.</span></span> <span data-ttu-id="0a230-164">用引发事件的类或结构的数据类型声明的对象变量。</span><span class="sxs-lookup"><span data-stu-id="0a230-164">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="0a230-165">必需。</span><span class="sxs-lookup"><span data-stu-id="0a230-165">Required.</span></span> <span data-ttu-id="0a230-166">此过程处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="0a230-166">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="0a230-167">可选。</span><span class="sxs-lookup"><span data-stu-id="0a230-167">Optional.</span></span> <span data-ttu-id="0a230-168">要在此过程中执行的语句块。</span><span class="sxs-lookup"><span data-stu-id="0a230-168">Block of statements to be executed within this procedure.</span></span>

- `End Function`

  <span data-ttu-id="0a230-169">终止此过程的定义。</span><span class="sxs-lookup"><span data-stu-id="0a230-169">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="0a230-170">备注</span><span class="sxs-lookup"><span data-stu-id="0a230-170">Remarks</span></span>

<span data-ttu-id="0a230-171">所有可执行代码都必须在过程内。</span><span class="sxs-lookup"><span data-stu-id="0a230-171">All executable code must be inside a procedure.</span></span> <span data-ttu-id="0a230-172">反过来，每个过程都在类、结构或模块（称为包含类、结构或模块）中声明。</span><span class="sxs-lookup"><span data-stu-id="0a230-172">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>

<span data-ttu-id="0a230-173">若要将值返回到调用代码，请使用 `Function` 过程;否则，请使用 `Sub` 过程。</span><span class="sxs-lookup"><span data-stu-id="0a230-173">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>

## <a name="defining-a-function"></a><span data-ttu-id="0a230-174">定义函数</span><span class="sxs-lookup"><span data-stu-id="0a230-174">Defining a Function</span></span>

<span data-ttu-id="0a230-175">只能在模块级别定义 `Function` 过程。</span><span class="sxs-lookup"><span data-stu-id="0a230-175">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="0a230-176">因此，函数的声明上下文必须是类、结构、模块或接口，不能是源文件、命名空间、过程或块。</span><span class="sxs-lookup"><span data-stu-id="0a230-176">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="0a230-177">有关详细信息，请参阅[声明上下文和默认访问级别](declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-177">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="0a230-178">`Function` 过程默认为公共访问。</span><span class="sxs-lookup"><span data-stu-id="0a230-178">`Function` procedures default to public access.</span></span> <span data-ttu-id="0a230-179">您可以使用访问修饰符调整其访问级别。</span><span class="sxs-lookup"><span data-stu-id="0a230-179">You can adjust their access levels with the access modifiers.</span></span>

<span data-ttu-id="0a230-180">`Function` 过程可以声明过程返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="0a230-180">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="0a230-181">您可以指定任何数据类型或枚举、结构、类或接口的名称。</span><span class="sxs-lookup"><span data-stu-id="0a230-181">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="0a230-182">如果未指定 `returntype` 参数，则该过程将返回 `Object`。</span><span class="sxs-lookup"><span data-stu-id="0a230-182">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>

<span data-ttu-id="0a230-183">如果此过程使用 `Implements` 关键字，则包含类或结构还必须具有紧跟其 `Class` 或 `Structure` 语句的 `Implements` 语句。</span><span class="sxs-lookup"><span data-stu-id="0a230-183">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="0a230-184">`Implements` 语句必须包括 `implementslist`中指定的每个接口。</span><span class="sxs-lookup"><span data-stu-id="0a230-184">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="0a230-185">但是，接口用于定义 `Function` 的名称（在 `definedname`中）无需与此过程的名称匹配（在 `name`中）。</span><span class="sxs-lookup"><span data-stu-id="0a230-185">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>

> [!NOTE]
> <span data-ttu-id="0a230-186">您可以使用 lambda 表达式来定义内联函数表达式。</span><span class="sxs-lookup"><span data-stu-id="0a230-186">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="0a230-187">有关详细信息，请参阅[函数表达式](../../../visual-basic/language-reference/operators/function-expression.md)和[Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-187">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>

## <a name="returning-from-a-function"></a><span data-ttu-id="0a230-188">从函数返回</span><span class="sxs-lookup"><span data-stu-id="0a230-188">Returning from a Function</span></span>

<span data-ttu-id="0a230-189">当 `Function` 过程返回到调用代码时，执行将继续执行调用该过程的语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="0a230-189">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>

<span data-ttu-id="0a230-190">若要从函数返回值，可以将值分配给函数名称，或者将其包含在 `Return` 语句中。</span><span class="sxs-lookup"><span data-stu-id="0a230-190">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>

<span data-ttu-id="0a230-191">`Return` 语句同时分配返回值并退出函数，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="0a230-191">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

<span data-ttu-id="0a230-192">下面的示例将返回值分配给函数名称 `myFunction`，然后使用 `Exit Function` 语句返回。</span><span class="sxs-lookup"><span data-stu-id="0a230-192">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

<span data-ttu-id="0a230-193">`Exit Function` 和 `Return` 语句导致立即退出 `Function` 过程。</span><span class="sxs-lookup"><span data-stu-id="0a230-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="0a230-194">任意数量的 `Exit Function` 和 `Return` 语句可以出现在过程中的任何位置，并且可以混合 `Exit Function` 和 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="0a230-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>

<span data-ttu-id="0a230-195">如果在不指定 `name`值的情况下使用 `Exit Function`，则该过程将返回 `returntype`中指定的数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="0a230-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="0a230-196">如果未指定 `returntype`，则该过程将返回 `Nothing`，这是 `Object`的默认值。</span><span class="sxs-lookup"><span data-stu-id="0a230-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>

## <a name="calling-a-function"></a><span data-ttu-id="0a230-197">调用函数</span><span class="sxs-lookup"><span data-stu-id="0a230-197">Calling a Function</span></span>

<span data-ttu-id="0a230-198">通过在表达式中使用过程名称后跟括号中的参数列表，可以调用 `Function` 过程。</span><span class="sxs-lookup"><span data-stu-id="0a230-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="0a230-199">仅当未提供任何参数时，才可以省略括号。</span><span class="sxs-lookup"><span data-stu-id="0a230-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="0a230-200">但是，如果你始终包含括号，你的代码将更具可读性。</span><span class="sxs-lookup"><span data-stu-id="0a230-200">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="0a230-201">调用 `Function` 过程的方式与调用任何库函数（如 `Sqrt`、`Cos`或 `ChrW`）的方式相同。</span><span class="sxs-lookup"><span data-stu-id="0a230-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>

<span data-ttu-id="0a230-202">还可以通过使用 `Call` 关键字调用函数。</span><span class="sxs-lookup"><span data-stu-id="0a230-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="0a230-203">在这种情况下，将忽略返回值。</span><span class="sxs-lookup"><span data-stu-id="0a230-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="0a230-204">在大多数情况下不建议使用 `Call` 关键字。</span><span class="sxs-lookup"><span data-stu-id="0a230-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="0a230-205">有关详细信息，请参阅[Call 语句](call-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-205">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="0a230-206">Visual Basic 有时会重新排列算术表达式以提高内部效率。</span><span class="sxs-lookup"><span data-stu-id="0a230-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="0a230-207">出于此原因，当函数更改同一表达式中变量的值时，不应使用算术表达式中的 `Function` 过程。</span><span class="sxs-lookup"><span data-stu-id="0a230-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>

## <a name="async-functions"></a><span data-ttu-id="0a230-208">异步函数</span><span class="sxs-lookup"><span data-stu-id="0a230-208">Async Functions</span></span>

<span data-ttu-id="0a230-209">使用*异步*功能可以调用异步函数，而无需使用显式回调或在多个函数或 lambda 表达式中手动拆分代码。</span><span class="sxs-lookup"><span data-stu-id="0a230-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="0a230-210">如果使用[Async](../../../visual-basic/language-reference/modifiers/async.md)修饰符标记函数，则可以在函数中使用[Await](../../../visual-basic/language-reference/operators/await-operator.md)运算符。</span><span class="sxs-lookup"><span data-stu-id="0a230-210">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="0a230-211">当控件在 `Async` 函数中到达 `Await` 表达式时，控件将返回到调用方，并且在等待的任务完成之前，将挂起该函数中的进度。</span><span class="sxs-lookup"><span data-stu-id="0a230-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="0a230-212">任务完成后，可以在函数中继续执行。</span><span class="sxs-lookup"><span data-stu-id="0a230-212">When the task is complete, execution can resume in the function.</span></span>

> [!NOTE]
> <span data-ttu-id="0a230-213">当某个 `Async` 过程遇到尚未完成的第一个等待对象时，它将返回到调用方，或者到达 `Async` 过程的末尾，以先发生者为准。</span><span class="sxs-lookup"><span data-stu-id="0a230-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>

<span data-ttu-id="0a230-214">`Async` 函数的返回类型可以是 <xref:System.Threading.Tasks.Task%601> 或 <xref:System.Threading.Tasks.Task>。</span><span class="sxs-lookup"><span data-stu-id="0a230-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="0a230-215">下面提供了返回类型为 <xref:System.Threading.Tasks.Task%601> 的 `Async` 函数的示例。</span><span class="sxs-lookup"><span data-stu-id="0a230-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>

<span data-ttu-id="0a230-216">`Async` 函数不能声明任何[ByRef](../../../visual-basic/language-reference/modifiers/byref.md)参数。</span><span class="sxs-lookup"><span data-stu-id="0a230-216">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="0a230-217">还可以使用 `Async` 修饰符来标记[Sub 语句](sub-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="0a230-218">这主要用于事件处理程序，其中不能返回值。</span><span class="sxs-lookup"><span data-stu-id="0a230-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="0a230-219">无法等待 `Async` 的 `Sub` 过程，并且 `Async` `Sub` 过程的调用方无法捕获由 `Sub` 过程引发的异常。</span><span class="sxs-lookup"><span data-stu-id="0a230-219">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>

<span data-ttu-id="0a230-220">有关 `Async` 函数的详细信息，请参阅[采用 async 和 Await 的异步编程](../../../visual-basic/programming-guide/concepts/async/index.md)、[异步程序中的控制流](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)和[异步返回类型](../../../visual-basic/programming-guide/concepts/async/async-return-types.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="iterator-functions"></a><span data-ttu-id="0a230-221">迭代器函数</span><span class="sxs-lookup"><span data-stu-id="0a230-221">Iterator Functions</span></span>

<span data-ttu-id="0a230-222">*迭代器*函数在集合上执行自定义迭代，如列表或数组。</span><span class="sxs-lookup"><span data-stu-id="0a230-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="0a230-223">Iterator 函数使用[Yield](yield-statement.md)语句每次返回一个元素。</span><span class="sxs-lookup"><span data-stu-id="0a230-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="0a230-224">当到达[Yield](yield-statement.md)语句时，将记住代码中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="0a230-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="0a230-225">下次调用迭代器函数时，将从该位置重新开始执行。</span><span class="sxs-lookup"><span data-stu-id="0a230-225">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="0a230-226">使用 For Each ... 将从客户端代码调用迭代器[下一](for-each-next-statement.md)语句。</span><span class="sxs-lookup"><span data-stu-id="0a230-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>

<span data-ttu-id="0a230-227">迭代器函数的返回类型可以是 <xref:System.Collections.IEnumerable>、<xref:System.Collections.Generic.IEnumerable%601>、<xref:System.Collections.IEnumerator>或 <xref:System.Collections.Generic.IEnumerator%601>。</span><span class="sxs-lookup"><span data-stu-id="0a230-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="0a230-228">有关详细信息，请参阅[迭代器](../../programming-guide/concepts/iterators.md)。</span><span class="sxs-lookup"><span data-stu-id="0a230-228">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>

## <a name="example"></a><span data-ttu-id="0a230-229">示例</span><span class="sxs-lookup"><span data-stu-id="0a230-229">Example</span></span>

<span data-ttu-id="0a230-230">下面的示例使用 `Function` 语句来声明构成 `Function` 过程正文的名称、参数和代码。</span><span class="sxs-lookup"><span data-stu-id="0a230-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="0a230-231">`ParamArray` 修饰符使函数可以接受数量可变的参数。</span><span class="sxs-lookup"><span data-stu-id="0a230-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>

[!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]

## <a name="example"></a><span data-ttu-id="0a230-232">示例</span><span class="sxs-lookup"><span data-stu-id="0a230-232">Example</span></span>

<span data-ttu-id="0a230-233">下面的示例调用在前面的示例中声明的函数。</span><span class="sxs-lookup"><span data-stu-id="0a230-233">The following example invokes the function declared in the preceding example.</span></span>

[!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]

## <a name="example"></a><span data-ttu-id="0a230-234">示例</span><span class="sxs-lookup"><span data-stu-id="0a230-234">Example</span></span>

<span data-ttu-id="0a230-235">在下面的示例中，`DelayAsync` 是返回类型为 <xref:System.Threading.Tasks.Task%601>的 `Async` `Function`。</span><span class="sxs-lookup"><span data-stu-id="0a230-235">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="0a230-236">`DelayAsync` 具有返回整数的 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="0a230-236">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="0a230-237">因此，`DelayAsync` 的函数声明需要具有 `Task(Of Integer)`的返回类型。</span><span class="sxs-lookup"><span data-stu-id="0a230-237">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="0a230-238">由于返回类型为 `Task(Of Integer)`，因此 `DoSomethingAsync` 中 `Await` 表达式的计算将产生整数。</span><span class="sxs-lookup"><span data-stu-id="0a230-238">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="0a230-239">此语句演示了这一点： `Dim result As Integer = Await delayTask`。</span><span class="sxs-lookup"><span data-stu-id="0a230-239">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="0a230-240">`startButton_Click` 过程是 `Async Sub` 过程的示例。</span><span class="sxs-lookup"><span data-stu-id="0a230-240">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="0a230-241">由于 `DoSomethingAsync` 是 `Async` 函数，因此对 `DoSomethingAsync` 的调用的任务必须等待，如以下语句所示： `Await DoSomethingAsync()`。</span><span class="sxs-lookup"><span data-stu-id="0a230-241">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="0a230-242">必须使用 `Async` 修饰符定义 `startButton_Click` `Sub` 过程，因为它具有 `Await` 表达式。</span><span class="sxs-lookup"><span data-stu-id="0a230-242">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="0a230-243">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a230-243">See also</span></span>

- [<span data-ttu-id="0a230-244">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="0a230-244">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="0a230-245">Function 过程</span><span class="sxs-lookup"><span data-stu-id="0a230-245">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="0a230-246">参数列表</span><span class="sxs-lookup"><span data-stu-id="0a230-246">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="0a230-247">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="0a230-247">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="0a230-248">Call 语句</span><span class="sxs-lookup"><span data-stu-id="0a230-248">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="0a230-249">Of</span><span class="sxs-lookup"><span data-stu-id="0a230-249">Of</span></span>](of-clause.md)
- [<span data-ttu-id="0a230-250">参数数组</span><span class="sxs-lookup"><span data-stu-id="0a230-250">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="0a230-251">如何：使用泛型类</span><span class="sxs-lookup"><span data-stu-id="0a230-251">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="0a230-252">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="0a230-252">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="0a230-253">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="0a230-253">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="0a230-254">函数表达式</span><span class="sxs-lookup"><span data-stu-id="0a230-254">Function Expression</span></span>](../../../visual-basic/language-reference/operators/function-expression.md)

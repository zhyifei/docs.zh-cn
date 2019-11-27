---
title: Sub 语句
ms.date: 05/12/2018
f1_keywords:
- vb.Sub
helpviewer_keywords:
- Public keyword [Visual Basic], Sub statements
- procedures [Visual Basic], creating
- declaring procedures [Visual Basic], Sub statement
- arguments [Visual Basic], Sub procedures
- As keyword [Visual Basic], Sub statements
- Optional keyword [Visual Basic], Sub statements
- declarations [Visual Basic], procedures
- Sub keyword [Visual Basic]
- Handles keyword [Visual Basic], Sub statements
- Protected Friend keyword [Visual Basic]
- ParamArray keyword [Visual Basic], Sub statements
- Implements keyword [Visual Basic], Sub statements
- Sub statement [Visual Basic]
- subroutines
- ByRef keyword [Visual Basic], Sub statements
- Sub procedures [Visual Basic], Sub statement
- recursive procedures
- Private keyword [Visual Basic], Sub statements
- Friend keyword [Visual Basic], Sub statements
- Exit statement [Visual Basic], Sub statements
- procedures [Visual Basic], Sub
- End keyword [Visual Basic], Sub statements
- ByVal keyword [Visual Basic], Sub statements
- Visual Basic code, Sub procedures
ms.assetid: e347d700-d06c-405b-b302-e9b1edb57dfc
ms.openlocfilehash: da498a5e0a3633eb98882aaed145fcd21ab169fd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346444"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="638a4-102">Sub 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="638a4-102">Sub Statement (Visual Basic)</span></span>

<span data-ttu-id="638a4-103">声明定义 `Sub` 过程的名称、参数和代码。</span><span class="sxs-lookup"><span data-stu-id="638a4-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>

## <a name="syntax"></a><span data-ttu-id="638a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="638a4-104">Syntax</span></span>

```vb
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]
    [ statements ]
    [ Exit Sub ]
    [ statements ]
End Sub
```

## <a name="parts"></a><span data-ttu-id="638a4-105">部件</span><span class="sxs-lookup"><span data-stu-id="638a4-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="638a4-106">可选。</span><span class="sxs-lookup"><span data-stu-id="638a4-106">Optional.</span></span> <span data-ttu-id="638a4-107">请参阅[特性列表](attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-107">See [Attribute List](attribute-list.md).</span></span>

- `Partial`

  <span data-ttu-id="638a4-108">可选。</span><span class="sxs-lookup"><span data-stu-id="638a4-108">Optional.</span></span> <span data-ttu-id="638a4-109">指示分部方法的定义。</span><span class="sxs-lookup"><span data-stu-id="638a4-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="638a4-110">请参阅[分部方法](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="638a4-111">可选。</span><span class="sxs-lookup"><span data-stu-id="638a4-111">Optional.</span></span> <span data-ttu-id="638a4-112">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="638a4-112">Can be one of the following:</span></span>

  - [<span data-ttu-id="638a4-113">Public</span><span class="sxs-lookup"><span data-stu-id="638a4-113">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="638a4-114">Protected</span><span class="sxs-lookup"><span data-stu-id="638a4-114">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="638a4-115">Friend</span><span class="sxs-lookup"><span data-stu-id="638a4-115">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="638a4-116">Private</span><span class="sxs-lookup"><span data-stu-id="638a4-116">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="638a4-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="638a4-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="638a4-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="638a4-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="638a4-119">请参阅 [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `proceduremodifiers`

  <span data-ttu-id="638a4-120">可选。</span><span class="sxs-lookup"><span data-stu-id="638a4-120">Optional.</span></span> <span data-ttu-id="638a4-121">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="638a4-121">Can be one of the following:</span></span>

  - [<span data-ttu-id="638a4-122">Overloads</span><span class="sxs-lookup"><span data-stu-id="638a4-122">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="638a4-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="638a4-123">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="638a4-124">Overrides</span><span class="sxs-lookup"><span data-stu-id="638a4-124">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="638a4-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="638a4-125">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="638a4-126">MyBase</span><span class="sxs-lookup"><span data-stu-id="638a4-126">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="638a4-127">可选。</span><span class="sxs-lookup"><span data-stu-id="638a4-127">Optional.</span></span> <span data-ttu-id="638a4-128">请参阅[共享](../modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-128">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="638a4-129">可选。</span><span class="sxs-lookup"><span data-stu-id="638a4-129">Optional.</span></span> <span data-ttu-id="638a4-130">请参阅[阴影](../modifiers/shadows.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-130">See [Shadows](../modifiers/shadows.md).</span></span>

- `Async`

  <span data-ttu-id="638a4-131">可选。</span><span class="sxs-lookup"><span data-stu-id="638a4-131">Optional.</span></span> <span data-ttu-id="638a4-132">请参阅[Async](../modifiers/async.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-132">See [Async](../modifiers/async.md).</span></span>

- `name`

  <span data-ttu-id="638a4-133">必需。</span><span class="sxs-lookup"><span data-stu-id="638a4-133">Required.</span></span> <span data-ttu-id="638a4-134">过程的名称。</span><span class="sxs-lookup"><span data-stu-id="638a4-134">Name of the procedure.</span></span> <span data-ttu-id="638a4-135">请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-135">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="638a4-136">若要为类创建构造函数过程，请将 `Sub` 过程的名称设置为 `New` 关键字。</span><span class="sxs-lookup"><span data-stu-id="638a4-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="638a4-137">有关详细信息，请参阅[对象生存期：如何创建和销毁对象](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

- `typeparamlist`

  <span data-ttu-id="638a4-138">可选。</span><span class="sxs-lookup"><span data-stu-id="638a4-138">Optional.</span></span> <span data-ttu-id="638a4-139">泛型过程的类型参数的列表。</span><span class="sxs-lookup"><span data-stu-id="638a4-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="638a4-140">请参阅[类型列表](type-list.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-140">See [Type List](type-list.md).</span></span>

- `parameterlist`

  <span data-ttu-id="638a4-141">可选。</span><span class="sxs-lookup"><span data-stu-id="638a4-141">Optional.</span></span> <span data-ttu-id="638a4-142">表示此过程参数的本地变量名称列表。</span><span class="sxs-lookup"><span data-stu-id="638a4-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="638a4-143">请参阅[参数列表](parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-143">See [Parameter List](parameter-list.md).</span></span>

- `Implements`

  <span data-ttu-id="638a4-144">可选。</span><span class="sxs-lookup"><span data-stu-id="638a4-144">Optional.</span></span> <span data-ttu-id="638a4-145">指示此过程实现一个或多个 `Sub` 过程，每个过程都在此过程的包含类或结构实现的接口中定义。</span><span class="sxs-lookup"><span data-stu-id="638a4-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="638a4-146">请参阅[Implements 语句](implements-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-146">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="638a4-147">如果提供 `Implements`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="638a4-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="638a4-148">所实现的 `Sub` 过程的列表。</span><span class="sxs-lookup"><span data-stu-id="638a4-148">List of `Sub` procedures being implemented.</span></span>

  `implementedprocedure [ , implementedprocedure ... ]`

  <span data-ttu-id="638a4-149">每个 `implementedprocedure` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="638a4-149">Each `implementedprocedure` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="638a4-150">部件</span><span class="sxs-lookup"><span data-stu-id="638a4-150">Part</span></span>|<span data-ttu-id="638a4-151">说明</span><span class="sxs-lookup"><span data-stu-id="638a4-151">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="638a4-152">必需。</span><span class="sxs-lookup"><span data-stu-id="638a4-152">Required.</span></span> <span data-ttu-id="638a4-153">此过程的包含类或结构实现的接口的名称。</span><span class="sxs-lookup"><span data-stu-id="638a4-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="638a4-154">必需。</span><span class="sxs-lookup"><span data-stu-id="638a4-154">Required.</span></span> <span data-ttu-id="638a4-155">在 `interface` 中用于定义过程的名称。</span><span class="sxs-lookup"><span data-stu-id="638a4-155">Name by which the procedure is defined in `interface`.</span></span>|

- `Handles`

  <span data-ttu-id="638a4-156">可选。</span><span class="sxs-lookup"><span data-stu-id="638a4-156">Optional.</span></span> <span data-ttu-id="638a4-157">指示此过程可以处理一个或多个特定事件。</span><span class="sxs-lookup"><span data-stu-id="638a4-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="638a4-158">请参阅[句柄](handles-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-158">See [Handles](handles-clause.md).</span></span>

- `eventlist`

  <span data-ttu-id="638a4-159">如果提供 `Handles`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="638a4-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="638a4-160">此过程处理的事件列表。</span><span class="sxs-lookup"><span data-stu-id="638a4-160">List of events this procedure handles.</span></span>

  `eventspecifier [ , eventspecifier ... ]`

  <span data-ttu-id="638a4-161">每个 `eventspecifier` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="638a4-161">Each `eventspecifier` has the following syntax and parts:</span></span>

  `eventvariable.event`

  |<span data-ttu-id="638a4-162">部件</span><span class="sxs-lookup"><span data-stu-id="638a4-162">Part</span></span>|<span data-ttu-id="638a4-163">说明</span><span class="sxs-lookup"><span data-stu-id="638a4-163">Description</span></span>|
  |---|---|
  |`eventvariable`|<span data-ttu-id="638a4-164">必需。</span><span class="sxs-lookup"><span data-stu-id="638a4-164">Required.</span></span> <span data-ttu-id="638a4-165">用引发事件的类或结构的数据类型声明的对象变量。</span><span class="sxs-lookup"><span data-stu-id="638a4-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|
  |`event`|<span data-ttu-id="638a4-166">必需。</span><span class="sxs-lookup"><span data-stu-id="638a4-166">Required.</span></span> <span data-ttu-id="638a4-167">此过程处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="638a4-167">Name of the event this procedure handles.</span></span>|

- `statements`

  <span data-ttu-id="638a4-168">可选。</span><span class="sxs-lookup"><span data-stu-id="638a4-168">Optional.</span></span> <span data-ttu-id="638a4-169">要在此过程中运行的语句块。</span><span class="sxs-lookup"><span data-stu-id="638a4-169">Block of statements to run within this procedure.</span></span>

- `End Sub`

  <span data-ttu-id="638a4-170">终止此过程的定义。</span><span class="sxs-lookup"><span data-stu-id="638a4-170">Terminates the definition of this procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="638a4-171">备注</span><span class="sxs-lookup"><span data-stu-id="638a4-171">Remarks</span></span>

<span data-ttu-id="638a4-172">所有可执行代码都必须在过程内。</span><span class="sxs-lookup"><span data-stu-id="638a4-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="638a4-173">如果不想将值返回到调用代码，请使用 `Sub` 过程。</span><span class="sxs-lookup"><span data-stu-id="638a4-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="638a4-174">如果要返回值，请使用 `Function` 过程。</span><span class="sxs-lookup"><span data-stu-id="638a4-174">Use a `Function` procedure when you want to return a value.</span></span>

## <a name="defining-a-sub-procedure"></a><span data-ttu-id="638a4-175">定义 Sub 过程</span><span class="sxs-lookup"><span data-stu-id="638a4-175">Defining a Sub Procedure</span></span>

<span data-ttu-id="638a4-176">只能在模块级别定义 `Sub` 过程。</span><span class="sxs-lookup"><span data-stu-id="638a4-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="638a4-177">因此，sub 过程的声明上下文必须是类、结构、模块或接口，不能是源文件、命名空间、过程或块。</span><span class="sxs-lookup"><span data-stu-id="638a4-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="638a4-178">有关详细信息，请参阅[声明上下文和默认访问级别](declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="638a4-179">`Sub` 过程默认为公共访问。</span><span class="sxs-lookup"><span data-stu-id="638a4-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="638a4-180">您可以使用访问修饰符调整其访问级别。</span><span class="sxs-lookup"><span data-stu-id="638a4-180">You can adjust their access levels by using the access modifiers.</span></span>

<span data-ttu-id="638a4-181">如果过程使用 `Implements` 关键字，则包含类或结构必须具有紧跟其 `Class` 或 `Structure` 语句的 `Implements` 语句。</span><span class="sxs-lookup"><span data-stu-id="638a4-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="638a4-182">`Implements` 语句必须包括 `implementslist`中指定的每个接口。</span><span class="sxs-lookup"><span data-stu-id="638a4-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="638a4-183">但是，接口定义 `Sub` （在 `definedname`中）的名称不必与此过程的名称匹配（在 `name`中）。</span><span class="sxs-lookup"><span data-stu-id="638a4-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>

## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="638a4-184">从 Sub 过程返回</span><span class="sxs-lookup"><span data-stu-id="638a4-184">Returning from a Sub Procedure</span></span>

<span data-ttu-id="638a4-185">当 `Sub` 过程返回到调用代码时，执行将继续执行调用它的语句之后的语句。</span><span class="sxs-lookup"><span data-stu-id="638a4-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>

<span data-ttu-id="638a4-186">下面的示例演示如何从 `Sub` 过程返回。</span><span class="sxs-lookup"><span data-stu-id="638a4-186">The following example shows a return from a `Sub` procedure.</span></span>

```vb
Sub mySub(ByVal q As String)
    Return
End Sub
```

<span data-ttu-id="638a4-187">`Exit Sub` 和 `Return` 语句导致立即退出 `Sub` 过程。</span><span class="sxs-lookup"><span data-stu-id="638a4-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="638a4-188">任意数量的 `Exit Sub` 和 `Return` 语句可以出现在过程中的任何位置，并且可以混合 `Exit Sub` 和 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="638a4-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>

## <a name="calling-a-sub-procedure"></a><span data-ttu-id="638a4-189">调用 Sub 过程</span><span class="sxs-lookup"><span data-stu-id="638a4-189">Calling a Sub Procedure</span></span>

<span data-ttu-id="638a4-190">通过在语句中使用过程名称，然后将该名称跟在括号中的参数列表后面来调用 `Sub` 过程。</span><span class="sxs-lookup"><span data-stu-id="638a4-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="638a4-191">仅当未提供任何参数时，才可以省略括号。</span><span class="sxs-lookup"><span data-stu-id="638a4-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="638a4-192">但是，如果你始终包含括号，你的代码将更具可读性。</span><span class="sxs-lookup"><span data-stu-id="638a4-192">However, your code is more readable if you always include the parentheses.</span></span>

<span data-ttu-id="638a4-193">`Sub` 过程和 `Function` 过程可以具有参数并执行一系列语句。</span><span class="sxs-lookup"><span data-stu-id="638a4-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="638a4-194">但 `Function` 过程将返回一个值，而 `Sub` 过程不会。</span><span class="sxs-lookup"><span data-stu-id="638a4-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="638a4-195">因此，不能在表达式中使用 `Sub` 过程。</span><span class="sxs-lookup"><span data-stu-id="638a4-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>

<span data-ttu-id="638a4-196">调用 `Sub` 过程时，可以使用 `Call` 关键字，但对于大多数用途，不建议使用该关键字。</span><span class="sxs-lookup"><span data-stu-id="638a4-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="638a4-197">有关详细信息，请参阅[Call 语句](call-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-197">For more information, see [Call Statement](call-statement.md).</span></span>

<span data-ttu-id="638a4-198">Visual Basic 有时会重新排列算术表达式以提高内部效率。</span><span class="sxs-lookup"><span data-stu-id="638a4-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="638a4-199">出于此原因，如果参数列表包含调用其他过程的表达式，则不应假定将按特定顺序调用这些表达式。</span><span class="sxs-lookup"><span data-stu-id="638a4-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>

## <a name="async-sub-procedures"></a><span data-ttu-id="638a4-200">Async Sub 过程</span><span class="sxs-lookup"><span data-stu-id="638a4-200">Async Sub Procedures</span></span>

<span data-ttu-id="638a4-201">通过使用异步功能，你可以调用异步函数而无需使用显式回调或在多个函数或 lambda 表达式中手动拆分你的代码。</span><span class="sxs-lookup"><span data-stu-id="638a4-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>

<span data-ttu-id="638a4-202">如果使用[Async](../modifiers/async.md)修饰符标记过程，则可以在过程中使用[Await](../../../visual-basic/language-reference/operators/await-operator.md)运算符。</span><span class="sxs-lookup"><span data-stu-id="638a4-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="638a4-203">当控件在 `Async` 过程中到达 `Await` 表达式时，控件将返回到调用方，并且在等待的任务完成之前，将挂起过程中的进度。</span><span class="sxs-lookup"><span data-stu-id="638a4-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="638a4-204">任务完成后，可以在过程中继续执行。</span><span class="sxs-lookup"><span data-stu-id="638a4-204">When the task is complete, execution can resume in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="638a4-205">当遇到尚未完成的第一个等待对象或到达 `Async` 过程的结束时（以先发生者为准），`Async` 过程返回到调用方。</span><span class="sxs-lookup"><span data-stu-id="638a4-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>

<span data-ttu-id="638a4-206">还可以使用 `Async` 修饰符标记[函数语句](function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="638a4-207">`Async` 函数的返回类型可以是 <xref:System.Threading.Tasks.Task%601> 或 <xref:System.Threading.Tasks.Task>。</span><span class="sxs-lookup"><span data-stu-id="638a4-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="638a4-208">本主题后面的示例演示了一个返回类型为 <xref:System.Threading.Tasks.Task%601>的 `Async` 函数。</span><span class="sxs-lookup"><span data-stu-id="638a4-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>

<span data-ttu-id="638a4-209">`Async` `Sub` 过程主要用于事件处理程序，其中不能返回值。</span><span class="sxs-lookup"><span data-stu-id="638a4-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="638a4-210">无法等待 `Async` 的 `Sub` 过程，并且 `Async` `Sub` 过程的调用方无法捕获 `Sub` 过程引发的异常。</span><span class="sxs-lookup"><span data-stu-id="638a4-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>

<span data-ttu-id="638a4-211">`Async` 过程不能声明任何[ByRef](../modifiers/byref.md)参数。</span><span class="sxs-lookup"><span data-stu-id="638a4-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>

<span data-ttu-id="638a4-212">有关 `Async` 过程的详细信息，请参阅[采用 async 和 Await 的异步编程](../../../visual-basic/programming-guide/concepts/async/index.md)、[异步程序中的控制流](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)和[异步返回类型](../../../visual-basic/programming-guide/concepts/async/async-return-types.md)。</span><span class="sxs-lookup"><span data-stu-id="638a4-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="example"></a><span data-ttu-id="638a4-213">示例</span><span class="sxs-lookup"><span data-stu-id="638a4-213">Example</span></span>

<span data-ttu-id="638a4-214">下面的示例使用 `Sub` 语句来定义构成 `Sub` 过程正文的名称、参数和代码。</span><span class="sxs-lookup"><span data-stu-id="638a4-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>

[!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]

## <a name="example"></a><span data-ttu-id="638a4-215">示例</span><span class="sxs-lookup"><span data-stu-id="638a4-215">Example</span></span>

<span data-ttu-id="638a4-216">在下面的示例中，`DelayAsync` 是返回类型为 <xref:System.Threading.Tasks.Task%601>的 `Async` `Function`。</span><span class="sxs-lookup"><span data-stu-id="638a4-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="638a4-217">`DelayAsync` 具有返回整数的 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="638a4-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="638a4-218">因此，`DelayAsync` 的函数声明的返回类型必须为 `Task(Of Integer)`。</span><span class="sxs-lookup"><span data-stu-id="638a4-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="638a4-219">由于返回类型为 `Task(Of Integer)`，因此 `DoSomethingAsync` 中 `Await` 表达式的计算将生成一个整数，如以下语句所示： `Dim result As Integer = Await delayTask`。</span><span class="sxs-lookup"><span data-stu-id="638a4-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>

<span data-ttu-id="638a4-220">`startButton_Click` 过程是 `Async Sub` 过程的示例。</span><span class="sxs-lookup"><span data-stu-id="638a4-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="638a4-221">由于 `DoSomethingAsync` 是 `Async` 函数，因此对 `DoSomethingAsync` 的调用的任务必须等待，如以下语句所示： `Await DoSomethingAsync()`。</span><span class="sxs-lookup"><span data-stu-id="638a4-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="638a4-222">必须使用 `Async` 修饰符定义 `startButton_Click` `Sub` 过程，因为它具有 `Await` 表达式。</span><span class="sxs-lookup"><span data-stu-id="638a4-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>

[!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="638a4-223">另请参阅</span><span class="sxs-lookup"><span data-stu-id="638a4-223">See also</span></span>

- [<span data-ttu-id="638a4-224">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="638a4-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="638a4-225">Function 语句</span><span class="sxs-lookup"><span data-stu-id="638a4-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="638a4-226">参数列表</span><span class="sxs-lookup"><span data-stu-id="638a4-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="638a4-227">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="638a4-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="638a4-228">Call 语句</span><span class="sxs-lookup"><span data-stu-id="638a4-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="638a4-229">Of</span><span class="sxs-lookup"><span data-stu-id="638a4-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="638a4-230">参数数组</span><span class="sxs-lookup"><span data-stu-id="638a4-230">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="638a4-231">如何：使用泛型类</span><span class="sxs-lookup"><span data-stu-id="638a4-231">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="638a4-232">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="638a4-232">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="638a4-233">分部方法</span><span class="sxs-lookup"><span data-stu-id="638a4-233">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)

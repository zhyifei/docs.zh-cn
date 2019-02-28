---
title: Sub 语句 (Visual Basic)
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
ms.openlocfilehash: 6984e7e9f8695ff5bccdde01171733e740a5d6a7
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965951"
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="42896-102">Sub 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42896-102">Sub Statement (Visual Basic)</span></span>
<span data-ttu-id="42896-103">声明名称、 参数和定义的代码`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="42896-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42896-104">语法</span><span class="sxs-lookup"><span data-stu-id="42896-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="42896-105">部件</span><span class="sxs-lookup"><span data-stu-id="42896-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="42896-106">可选。</span><span class="sxs-lookup"><span data-stu-id="42896-106">Optional.</span></span> <span data-ttu-id="42896-107">请参阅[属性列表](attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="42896-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `Partial`  
  
     <span data-ttu-id="42896-108">可选。</span><span class="sxs-lookup"><span data-stu-id="42896-108">Optional.</span></span> <span data-ttu-id="42896-109">指示分部方法的定义。</span><span class="sxs-lookup"><span data-stu-id="42896-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="42896-110">请参阅[分部方法](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="42896-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="42896-111">可选。</span><span class="sxs-lookup"><span data-stu-id="42896-111">Optional.</span></span> <span data-ttu-id="42896-112">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="42896-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="42896-113">Public</span><span class="sxs-lookup"><span data-stu-id="42896-113">Public</span></span>](../modifiers/public.md)  
  
    -   [<span data-ttu-id="42896-114">Protected</span><span class="sxs-lookup"><span data-stu-id="42896-114">Protected</span></span>](../modifiers/protected.md)  
  
    -   [<span data-ttu-id="42896-115">Friend</span><span class="sxs-lookup"><span data-stu-id="42896-115">Friend</span></span>](../modifiers/friend.md)  
  
    -   [<span data-ttu-id="42896-116">Private</span><span class="sxs-lookup"><span data-stu-id="42896-116">Private</span></span>](../modifiers/private.md)  
  
    - [<span data-ttu-id="42896-117">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="42896-117">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

    - [<span data-ttu-id="42896-118">Private Protected</span><span class="sxs-lookup"><span data-stu-id="42896-118">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)
  
     <span data-ttu-id="42896-119">请参阅 [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="42896-119">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="42896-120">可选。</span><span class="sxs-lookup"><span data-stu-id="42896-120">Optional.</span></span> <span data-ttu-id="42896-121">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="42896-121">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="42896-122">重载</span><span class="sxs-lookup"><span data-stu-id="42896-122">Overloads</span></span>](../modifiers/overloads.md)  
  
    -   [<span data-ttu-id="42896-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="42896-123">Overrides</span></span>](../modifiers/overrides.md)  
  
    -   [<span data-ttu-id="42896-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="42896-124">Overridable</span></span>](../modifiers/overridable.md)  
  
    -   [<span data-ttu-id="42896-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="42896-125">NotOverridable</span></span>](../modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="42896-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="42896-126">MustOverride</span></span>](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="42896-127">可选。</span><span class="sxs-lookup"><span data-stu-id="42896-127">Optional.</span></span> <span data-ttu-id="42896-128">请参阅[共享](../modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="42896-128">See [Shared](../modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="42896-129">可选。</span><span class="sxs-lookup"><span data-stu-id="42896-129">Optional.</span></span> <span data-ttu-id="42896-130">请参阅[Shadows](../modifiers/shadows.md)。</span><span class="sxs-lookup"><span data-stu-id="42896-130">See [Shadows](../modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="42896-131">可选。</span><span class="sxs-lookup"><span data-stu-id="42896-131">Optional.</span></span> <span data-ttu-id="42896-132">请参阅[异步](../modifiers/async.md)。</span><span class="sxs-lookup"><span data-stu-id="42896-132">See [Async](../modifiers/async.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="42896-133">必需。</span><span class="sxs-lookup"><span data-stu-id="42896-133">Required.</span></span> <span data-ttu-id="42896-134">该过程的名称。</span><span class="sxs-lookup"><span data-stu-id="42896-134">Name of the procedure.</span></span> <span data-ttu-id="42896-135">请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="42896-135">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="42896-136">若要创建一个类的构造函数过程，请设置的名称`Sub`过程`New`关键字。</span><span class="sxs-lookup"><span data-stu-id="42896-136">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="42896-137">有关详细信息，请参阅[对象生存期：如何创建和销毁对象](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)。</span><span class="sxs-lookup"><span data-stu-id="42896-137">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="42896-138">可选。</span><span class="sxs-lookup"><span data-stu-id="42896-138">Optional.</span></span> <span data-ttu-id="42896-139">针对泛型过程的类型参数的列表。</span><span class="sxs-lookup"><span data-stu-id="42896-139">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="42896-140">请参阅[类型列表](type-list.md)。</span><span class="sxs-lookup"><span data-stu-id="42896-140">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="42896-141">可选。</span><span class="sxs-lookup"><span data-stu-id="42896-141">Optional.</span></span> <span data-ttu-id="42896-142">表示此过程的参数的本地变量名称的列表。</span><span class="sxs-lookup"><span data-stu-id="42896-142">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="42896-143">请参阅[参数列表](parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="42896-143">See [Parameter List](parameter-list.md).</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="42896-144">可选。</span><span class="sxs-lookup"><span data-stu-id="42896-144">Optional.</span></span> <span data-ttu-id="42896-145">指示此过程将实现一个或多个`Sub`过程，此过程包含类或结构实现接口中定义每个。</span><span class="sxs-lookup"><span data-stu-id="42896-145">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="42896-146">请参阅[实现语句](implements-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="42896-146">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="42896-147">如果提供 `Implements`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="42896-147">Required if `Implements` is supplied.</span></span> <span data-ttu-id="42896-148">所实现的 `Sub` 过程的列表。</span><span class="sxs-lookup"><span data-stu-id="42896-148">List of `Sub` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="42896-149">每个 `implementedprocedure` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="42896-149">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="42896-150">部件</span><span class="sxs-lookup"><span data-stu-id="42896-150">Part</span></span>|<span data-ttu-id="42896-151">描述</span><span class="sxs-lookup"><span data-stu-id="42896-151">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="42896-152">必需。</span><span class="sxs-lookup"><span data-stu-id="42896-152">Required.</span></span> <span data-ttu-id="42896-153">此过程实现的接口的名称的包含类或结构。</span><span class="sxs-lookup"><span data-stu-id="42896-153">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="42896-154">必需。</span><span class="sxs-lookup"><span data-stu-id="42896-154">Required.</span></span> <span data-ttu-id="42896-155">在 `interface` 中用于定义过程的名称。</span><span class="sxs-lookup"><span data-stu-id="42896-155">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="42896-156">可选。</span><span class="sxs-lookup"><span data-stu-id="42896-156">Optional.</span></span> <span data-ttu-id="42896-157">指示此过程可以处理一个或多个特定事件。</span><span class="sxs-lookup"><span data-stu-id="42896-157">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="42896-158">请参阅[处理](handles-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="42896-158">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="42896-159">如果提供 `Handles`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="42896-159">Required if `Handles` is supplied.</span></span> <span data-ttu-id="42896-160">此过程处理的事件的列表。</span><span class="sxs-lookup"><span data-stu-id="42896-160">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="42896-161">每个 `eventspecifier` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="42896-161">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="42896-162">部件</span><span class="sxs-lookup"><span data-stu-id="42896-162">Part</span></span>|<span data-ttu-id="42896-163">描述</span><span class="sxs-lookup"><span data-stu-id="42896-163">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="42896-164">必需。</span><span class="sxs-lookup"><span data-stu-id="42896-164">Required.</span></span> <span data-ttu-id="42896-165">声明的类或结构，它会引发事件的数据类型的对象变量。</span><span class="sxs-lookup"><span data-stu-id="42896-165">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="42896-166">必需。</span><span class="sxs-lookup"><span data-stu-id="42896-166">Required.</span></span> <span data-ttu-id="42896-167">此过程处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="42896-167">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="42896-168">可选。</span><span class="sxs-lookup"><span data-stu-id="42896-168">Optional.</span></span> <span data-ttu-id="42896-169">要在此过程中运行的语句块。</span><span class="sxs-lookup"><span data-stu-id="42896-169">Block of statements to run within this procedure.</span></span>  
  
-   `End Sub`  
  
     <span data-ttu-id="42896-170">终止此过程的定义。</span><span class="sxs-lookup"><span data-stu-id="42896-170">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42896-171">备注</span><span class="sxs-lookup"><span data-stu-id="42896-171">Remarks</span></span>  
 <span data-ttu-id="42896-172">在过程内必须是所有可执行代码。</span><span class="sxs-lookup"><span data-stu-id="42896-172">All executable code must be inside a procedure.</span></span> <span data-ttu-id="42896-173">使用`Sub`过程时不想要将值返回给调用代码。</span><span class="sxs-lookup"><span data-stu-id="42896-173">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="42896-174">使用`Function`过程时要返回的值。</span><span class="sxs-lookup"><span data-stu-id="42896-174">Use a `Function` procedure when you want to return a value.</span></span>  
  
## <a name="defining-a-sub-procedure"></a><span data-ttu-id="42896-175">定义 Sub 过程</span><span class="sxs-lookup"><span data-stu-id="42896-175">Defining a Sub Procedure</span></span>  
 <span data-ttu-id="42896-176">您可以定义`Sub`只能在模块级别的过程。</span><span class="sxs-lookup"><span data-stu-id="42896-176">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="42896-177">Sub 过程的声明上下文，因此，必须类、 结构、 模块或接口，且不能为源文件、 命名空间、 过程或块。</span><span class="sxs-lookup"><span data-stu-id="42896-177">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="42896-178">有关详细信息，请参阅[声明上下文和默认访问级别](declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="42896-178">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="42896-179">`Sub` 过程默认为公共访问。</span><span class="sxs-lookup"><span data-stu-id="42896-179">`Sub` procedures default to public access.</span></span> <span data-ttu-id="42896-180">可以使用访问修饰符来调整其访问级别。</span><span class="sxs-lookup"><span data-stu-id="42896-180">You can adjust their access levels by using the access modifiers.</span></span>  
  
 <span data-ttu-id="42896-181">如果过程使用`Implements`关键字、 包含类或结构必须具有`Implements`紧跟在后面的语句及其`Class`或`Structure`语句。</span><span class="sxs-lookup"><span data-stu-id="42896-181">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="42896-182">`Implements`语句必须包括在中指定每个接口`implementslist`。</span><span class="sxs-lookup"><span data-stu-id="42896-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="42896-183">但是，通过该接口定义的名称`Sub`(在`definedname`) 不需要此过程的名称匹配 (在`name`)。</span><span class="sxs-lookup"><span data-stu-id="42896-183">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>  
  
## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="42896-184">返回从 Sub 过程</span><span class="sxs-lookup"><span data-stu-id="42896-184">Returning from a Sub Procedure</span></span>  
 <span data-ttu-id="42896-185">当`Sub`过程返回到调用代码时，继续执行调用了它的语句之后的语句。</span><span class="sxs-lookup"><span data-stu-id="42896-185">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>  
  
 <span data-ttu-id="42896-186">下面的示例演示从返回`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="42896-186">The following example shows a return from a `Sub` procedure.</span></span>  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 <span data-ttu-id="42896-187">`Exit Sub`并`Return`语句会导致立即退出`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="42896-187">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="42896-188">任意数量的`Exit Sub`并`Return`语句可以在过程中，任何位置出现，并且可以混合`Exit Sub`和`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="42896-188">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>  
  
## <a name="calling-a-sub-procedure"></a><span data-ttu-id="42896-189">调用一个 Sub 过程</span><span class="sxs-lookup"><span data-stu-id="42896-189">Calling a Sub Procedure</span></span>  
 <span data-ttu-id="42896-190">在调用`Sub`过程的方法是在语句中使用的过程名称，然后按照该名称与在括号中其自变量列表。</span><span class="sxs-lookup"><span data-stu-id="42896-190">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="42896-191">仅当不提供任何参数，可以省略括号。</span><span class="sxs-lookup"><span data-stu-id="42896-191">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="42896-192">但是，你的代码是始终使用圆括号更具可读性。</span><span class="sxs-lookup"><span data-stu-id="42896-192">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="42896-193">一个`Sub`过程和一个`Function`过程可以具有参数，并且执行一系列语句。</span><span class="sxs-lookup"><span data-stu-id="42896-193">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="42896-194">但是，`Function`过程返回一个值，以及一个`Sub`过程不会。</span><span class="sxs-lookup"><span data-stu-id="42896-194">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="42896-195">因此，不能使用`Sub`在表达式中的过程。</span><span class="sxs-lookup"><span data-stu-id="42896-195">Therefore, you can't use a `Sub` procedure in an expression.</span></span>  
  
 <span data-ttu-id="42896-196">可以使用`Call`关键字调用时`Sub`大多数使用不推荐使用过程中，但是该关键字。</span><span class="sxs-lookup"><span data-stu-id="42896-196">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="42896-197">有关详细信息，请参阅[Call 语句](call-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="42896-197">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="42896-198">Visual Basic 有时会重新排列算术表达式来提高内部工作效率。</span><span class="sxs-lookup"><span data-stu-id="42896-198">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="42896-199">出于此原因，如果在参数列表包含表达式调用其他过程，您不应假定，将按特定顺序调用这些表达式。</span><span class="sxs-lookup"><span data-stu-id="42896-199">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>  
  
## <a name="async-sub-procedures"></a><span data-ttu-id="42896-200">Async Sub 过程</span><span class="sxs-lookup"><span data-stu-id="42896-200">Async Sub Procedures</span></span>  
 <span data-ttu-id="42896-201">通过使用异步功能，可以调用异步函数，而无需使用显式回调或手动拆分跨多个函数或 lambda 表达式的代码。</span><span class="sxs-lookup"><span data-stu-id="42896-201">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="42896-202">如果您将过程标记为与[异步](../modifiers/async.md)修饰符，可以使用[Await](../../../visual-basic/language-reference/operators/await-operator.md)过程中的运算符。</span><span class="sxs-lookup"><span data-stu-id="42896-202">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="42896-203">当控件到达`Await`中的表达式`Async`过程中，控件返回到调用方，并在该过程的进度被挂起，直到等待的任务完成。</span><span class="sxs-lookup"><span data-stu-id="42896-203">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="42896-204">任务完成后，可以在该过程中恢复执行。</span><span class="sxs-lookup"><span data-stu-id="42896-204">When the task is complete, execution can resume in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42896-205">`Async`过程返回到调用方时遇到任一的第一个等待的对象不是完全或末尾`Async`达到过程，以先发生者为准。</span><span class="sxs-lookup"><span data-stu-id="42896-205">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>  
  
 <span data-ttu-id="42896-206">此外可以将标记[Function 语句](function-statement.md)与`Async`修饰符。</span><span class="sxs-lookup"><span data-stu-id="42896-206">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="42896-207">`Async`函数可以具有的返回类型<xref:System.Threading.Tasks.Task%601>或<xref:System.Threading.Tasks.Task>。</span><span class="sxs-lookup"><span data-stu-id="42896-207">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="42896-208">示例更高版本在本主题演示`Async`函数的返回类型为<xref:System.Threading.Tasks.Task%601>。</span><span class="sxs-lookup"><span data-stu-id="42896-208">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="42896-209">`Async` `Sub` 过程主要用于事件处理程序的值不能返回。</span><span class="sxs-lookup"><span data-stu-id="42896-209">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="42896-210">`Async` `Sub`无法等待过程，和的调用方`Async``Sub`过程无法捕获的异常的`Sub`过程，则会引发。</span><span class="sxs-lookup"><span data-stu-id="42896-210">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>  
  
 <span data-ttu-id="42896-211">`Async`过程不能声明任何[ByRef](../modifiers/byref.md)参数。</span><span class="sxs-lookup"><span data-stu-id="42896-211">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="42896-212">有关详细信息`Async`过程，请参阅[使用 Async 和 Await 的异步编程](../../../visual-basic/programming-guide/concepts/async/index.md)，[异步程序中的控制流](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)，并[异步返回类型](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="42896-212">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="42896-213">示例</span><span class="sxs-lookup"><span data-stu-id="42896-213">Example</span></span>  
 <span data-ttu-id="42896-214">下面的示例使用`Sub`语句来定义名称、 参数和窗体的主体的代码`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="42896-214">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#58)]  
  
## <a name="example"></a><span data-ttu-id="42896-215">示例</span><span class="sxs-lookup"><span data-stu-id="42896-215">Example</span></span>  
 <span data-ttu-id="42896-216">在以下示例中，`DelayAsync`是`Async``Function`具有返回类型的<xref:System.Threading.Tasks.Task%601>。</span><span class="sxs-lookup"><span data-stu-id="42896-216">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="42896-217">`DelayAsync` 具有返回整数的 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="42896-217">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="42896-218">因此，函数声明`DelayAsync`必须具有返回类型为`Task(Of Integer)`。</span><span class="sxs-lookup"><span data-stu-id="42896-218">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="42896-219">因为返回类型是`Task(Of Integer)`的评估`Await`中的表达式`DoSomethingAsync`如下语句所示得出整数： `Dim result As Integer = Await delayTask`。</span><span class="sxs-lookup"><span data-stu-id="42896-219">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="42896-220">`startButton_Click`过程是一种`Async Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="42896-220">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="42896-221">因为`DoSomethingAsync`是`Async`函数，为调用任务`DoSomethingAsync`必须等待，如以下语句所示： `Await DoSomethingAsync()`。</span><span class="sxs-lookup"><span data-stu-id="42896-221">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="42896-222">`startButton_Click` `Sub`过程必须使用定义`Async`修饰符，因此`Await`表达式。</span><span class="sxs-lookup"><span data-stu-id="42896-222">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="42896-223">请参阅</span><span class="sxs-lookup"><span data-stu-id="42896-223">See also</span></span>
- [<span data-ttu-id="42896-224">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="42896-224">Implements Statement</span></span>](implements-statement.md)
- [<span data-ttu-id="42896-225">Function 语句</span><span class="sxs-lookup"><span data-stu-id="42896-225">Function Statement</span></span>](function-statement.md)
- [<span data-ttu-id="42896-226">参数列表</span><span class="sxs-lookup"><span data-stu-id="42896-226">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="42896-227">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="42896-227">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="42896-228">Call 语句</span><span class="sxs-lookup"><span data-stu-id="42896-228">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="42896-229">Of</span><span class="sxs-lookup"><span data-stu-id="42896-229">Of</span></span>](of-clause.md)
- [<span data-ttu-id="42896-230">参数数组</span><span class="sxs-lookup"><span data-stu-id="42896-230">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="42896-231">如何：使用泛型类</span><span class="sxs-lookup"><span data-stu-id="42896-231">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="42896-232">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="42896-232">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="42896-233">分部方法</span><span class="sxs-lookup"><span data-stu-id="42896-233">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)

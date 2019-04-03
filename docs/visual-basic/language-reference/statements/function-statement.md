---
title: Function 语句 (Visual Basic)
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
ms.openlocfilehash: dffe67d1c31b0fe7c037839ba0588793a461f276
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818457"
---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="d03df-102">Function 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d03df-102">Function Statement (Visual Basic)</span></span>
<span data-ttu-id="d03df-103">声明名称、 参数和定义的代码`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="d03df-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d03df-104">语法</span><span class="sxs-lookup"><span data-stu-id="d03df-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="d03df-105">部件</span><span class="sxs-lookup"><span data-stu-id="d03df-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="d03df-106">可选。</span><span class="sxs-lookup"><span data-stu-id="d03df-106">Optional.</span></span> <span data-ttu-id="d03df-107">请参阅[属性列表](attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="d03df-108">可选。</span><span class="sxs-lookup"><span data-stu-id="d03df-108">Optional.</span></span> <span data-ttu-id="d03df-109">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="d03df-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="d03df-110">Public</span><span class="sxs-lookup"><span data-stu-id="d03df-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="d03df-111">Protected</span><span class="sxs-lookup"><span data-stu-id="d03df-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="d03df-112">Friend</span><span class="sxs-lookup"><span data-stu-id="d03df-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="d03df-113">Private</span><span class="sxs-lookup"><span data-stu-id="d03df-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [<span data-ttu-id="d03df-114">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="d03df-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

    - [<span data-ttu-id="d03df-115">Private Protected</span><span class="sxs-lookup"><span data-stu-id="d03df-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)  
  
     <span data-ttu-id="d03df-116">请参阅 [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="d03df-117">可选。</span><span class="sxs-lookup"><span data-stu-id="d03df-117">Optional.</span></span> <span data-ttu-id="d03df-118">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="d03df-118">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="d03df-119">重载</span><span class="sxs-lookup"><span data-stu-id="d03df-119">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="d03df-120">Overrides</span><span class="sxs-lookup"><span data-stu-id="d03df-120">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="d03df-121">Overridable</span><span class="sxs-lookup"><span data-stu-id="d03df-121">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="d03df-122">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="d03df-122">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="d03df-123">MustOverride</span><span class="sxs-lookup"><span data-stu-id="d03df-123">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="d03df-124">可选。</span><span class="sxs-lookup"><span data-stu-id="d03df-124">Optional.</span></span> <span data-ttu-id="d03df-125">请参阅[共享](../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-125">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="d03df-126">可选。</span><span class="sxs-lookup"><span data-stu-id="d03df-126">Optional.</span></span> <span data-ttu-id="d03df-127">请参阅[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-127">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="d03df-128">可选。</span><span class="sxs-lookup"><span data-stu-id="d03df-128">Optional.</span></span> <span data-ttu-id="d03df-129">请参阅[异步](../../../visual-basic/language-reference/modifiers/async.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-129">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="d03df-130">可选。</span><span class="sxs-lookup"><span data-stu-id="d03df-130">Optional.</span></span> <span data-ttu-id="d03df-131">请参阅[迭代器](../../../visual-basic/language-reference/modifiers/iterator.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-131">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="d03df-132">必需。</span><span class="sxs-lookup"><span data-stu-id="d03df-132">Required.</span></span> <span data-ttu-id="d03df-133">该过程的名称。</span><span class="sxs-lookup"><span data-stu-id="d03df-133">Name of the procedure.</span></span> <span data-ttu-id="d03df-134">请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="d03df-135">可选。</span><span class="sxs-lookup"><span data-stu-id="d03df-135">Optional.</span></span> <span data-ttu-id="d03df-136">针对泛型过程的类型参数的列表。</span><span class="sxs-lookup"><span data-stu-id="d03df-136">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="d03df-137">请参阅[类型列表](type-list.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-137">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="d03df-138">可选。</span><span class="sxs-lookup"><span data-stu-id="d03df-138">Optional.</span></span> <span data-ttu-id="d03df-139">表示此过程的参数的本地变量名称的列表。</span><span class="sxs-lookup"><span data-stu-id="d03df-139">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="d03df-140">请参阅[参数列表](parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-140">See [Parameter List](parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="d03df-141">需要`Option Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="d03df-141">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="d03df-142">此过程返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="d03df-142">Data type of the value returned by this procedure.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="d03df-143">可选。</span><span class="sxs-lookup"><span data-stu-id="d03df-143">Optional.</span></span> <span data-ttu-id="d03df-144">指示此过程将实现一个或多个`Function`过程，此过程包含类或结构实现接口中定义每个。</span><span class="sxs-lookup"><span data-stu-id="d03df-144">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="d03df-145">请参阅[实现语句](implements-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-145">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="d03df-146">如果提供 `Implements`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="d03df-146">Required if `Implements` is supplied.</span></span> <span data-ttu-id="d03df-147">所实现的 `Function` 过程的列表。</span><span class="sxs-lookup"><span data-stu-id="d03df-147">List of `Function` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="d03df-148">每个 `implementedprocedure` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="d03df-148">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="d03df-149">部件</span><span class="sxs-lookup"><span data-stu-id="d03df-149">Part</span></span>|<span data-ttu-id="d03df-150">描述</span><span class="sxs-lookup"><span data-stu-id="d03df-150">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="d03df-151">必需。</span><span class="sxs-lookup"><span data-stu-id="d03df-151">Required.</span></span> <span data-ttu-id="d03df-152">此过程实现的接口的名称的包含类或结构。</span><span class="sxs-lookup"><span data-stu-id="d03df-152">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="d03df-153">必需。</span><span class="sxs-lookup"><span data-stu-id="d03df-153">Required.</span></span> <span data-ttu-id="d03df-154">在 `interface` 中用于定义过程的名称。</span><span class="sxs-lookup"><span data-stu-id="d03df-154">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="d03df-155">可选。</span><span class="sxs-lookup"><span data-stu-id="d03df-155">Optional.</span></span> <span data-ttu-id="d03df-156">指示此过程可以处理一个或多个特定事件。</span><span class="sxs-lookup"><span data-stu-id="d03df-156">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="d03df-157">请参阅[处理](handles-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-157">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="d03df-158">如果提供 `Handles`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="d03df-158">Required if `Handles` is supplied.</span></span> <span data-ttu-id="d03df-159">此过程处理的事件的列表。</span><span class="sxs-lookup"><span data-stu-id="d03df-159">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="d03df-160">每个 `eventspecifier` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="d03df-160">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="d03df-161">部件</span><span class="sxs-lookup"><span data-stu-id="d03df-161">Part</span></span>|<span data-ttu-id="d03df-162">描述</span><span class="sxs-lookup"><span data-stu-id="d03df-162">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="d03df-163">必需。</span><span class="sxs-lookup"><span data-stu-id="d03df-163">Required.</span></span> <span data-ttu-id="d03df-164">声明的类或结构，它会引发事件的数据类型的对象变量。</span><span class="sxs-lookup"><span data-stu-id="d03df-164">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="d03df-165">必需。</span><span class="sxs-lookup"><span data-stu-id="d03df-165">Required.</span></span> <span data-ttu-id="d03df-166">此过程处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="d03df-166">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="d03df-167">可选。</span><span class="sxs-lookup"><span data-stu-id="d03df-167">Optional.</span></span> <span data-ttu-id="d03df-168">若要在此过程中执行的语句块。</span><span class="sxs-lookup"><span data-stu-id="d03df-168">Block of statements to be executed within this procedure.</span></span>  
  
-   `End Function`  
  
     <span data-ttu-id="d03df-169">终止此过程的定义。</span><span class="sxs-lookup"><span data-stu-id="d03df-169">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d03df-170">备注</span><span class="sxs-lookup"><span data-stu-id="d03df-170">Remarks</span></span>  
 <span data-ttu-id="d03df-171">在过程内必须是所有可执行代码。</span><span class="sxs-lookup"><span data-stu-id="d03df-171">All executable code must be inside a procedure.</span></span> <span data-ttu-id="d03df-172">反过来，每个过程，一个类、 结构或被称为包含的类、 结构或模块的模块中声明。</span><span class="sxs-lookup"><span data-stu-id="d03df-172">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>  
  
 <span data-ttu-id="d03df-173">若要将值返回给调用代码，请使用`Function`过程; 否则，请使用`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="d03df-173">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>  
  
## <a name="defining-a-function"></a><span data-ttu-id="d03df-174">定义函数</span><span class="sxs-lookup"><span data-stu-id="d03df-174">Defining a Function</span></span>  
 <span data-ttu-id="d03df-175">您可以定义`Function`只能在模块级别的过程。</span><span class="sxs-lookup"><span data-stu-id="d03df-175">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="d03df-176">因此，对于函数的声明上下文必须是类、 结构、 模块或接口，且不能为源文件、 命名空间、 过程或块。</span><span class="sxs-lookup"><span data-stu-id="d03df-176">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="d03df-177">有关详细信息，请参阅[声明上下文和默认访问级别](declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-177">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="d03df-178">`Function` 过程默认为公共访问。</span><span class="sxs-lookup"><span data-stu-id="d03df-178">`Function` procedures default to public access.</span></span> <span data-ttu-id="d03df-179">您可以调整其访问级别和访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="d03df-179">You can adjust their access levels with the access modifiers.</span></span>  
  
 <span data-ttu-id="d03df-180">一个`Function`过程可以声明该过程返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="d03df-180">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="d03df-181">您可以指定任何数据类型或枚举、 结构、 类或接口的名称。</span><span class="sxs-lookup"><span data-stu-id="d03df-181">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="d03df-182">如果未指定`returntype`参数，该过程返回`Object`。</span><span class="sxs-lookup"><span data-stu-id="d03df-182">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>  
  
 <span data-ttu-id="d03df-183">如果使用此过程`Implements`关键字、 包含类或结构必须还具有`Implements`紧跟在后面的语句及其`Class`或`Structure`语句。</span><span class="sxs-lookup"><span data-stu-id="d03df-183">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="d03df-184">`Implements`语句必须包括在中指定每个接口`implementslist`。</span><span class="sxs-lookup"><span data-stu-id="d03df-184">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="d03df-185">但是，通过该接口定义的名称`Function`(在`definedname`) 不需要此过程的名称匹配 (在`name`)。</span><span class="sxs-lookup"><span data-stu-id="d03df-185">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d03df-186">可以使用 lambda 表达式来定义内联函数表达式。</span><span class="sxs-lookup"><span data-stu-id="d03df-186">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="d03df-187">有关详细信息，请参阅[函数表达式](../../../visual-basic/language-reference/operators/function-expression.md)并[Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-187">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="returning-from-a-function"></a><span data-ttu-id="d03df-188">从函数返回</span><span class="sxs-lookup"><span data-stu-id="d03df-188">Returning from a Function</span></span>  
 <span data-ttu-id="d03df-189">当`Function`过程返回到调用代码时，继续执行后面的语句调用该过程的语句。</span><span class="sxs-lookup"><span data-stu-id="d03df-189">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>  
  
 <span data-ttu-id="d03df-190">若要从函数返回一个值，可以将该值赋给函数名称，或将其包含在`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="d03df-190">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>  
  
 <span data-ttu-id="d03df-191">`Return`语句同时分配返回值，并退出函数，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="d03df-191">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>  
  
 [!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]  
  
 <span data-ttu-id="d03df-192">以下示例将返回值分配为函数名称`myFunction`，然后使用`Exit Function`语句返回。</span><span class="sxs-lookup"><span data-stu-id="d03df-192">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>  
  
 [!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]  
  
 <span data-ttu-id="d03df-193">`Exit Function`并`Return`语句会导致立即退出`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="d03df-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="d03df-194">任意数量的`Exit Function`并`Return`语句可以在过程中，任何位置出现，并且可以混合`Exit Function`和`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="d03df-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>  
  
 <span data-ttu-id="d03df-195">如果您使用`Exit Function`而不将分配到的值`name`，该过程返回在指定的数据类型的默认值`returntype`。</span><span class="sxs-lookup"><span data-stu-id="d03df-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="d03df-196">如果`returntype`未指定，该过程将返回`Nothing`，它是默认值， `Object`。</span><span class="sxs-lookup"><span data-stu-id="d03df-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>  
  
## <a name="calling-a-function"></a><span data-ttu-id="d03df-197">调用函数</span><span class="sxs-lookup"><span data-stu-id="d03df-197">Calling a Function</span></span>  
 <span data-ttu-id="d03df-198">在调用`Function`过程的方法是使用过程名称后, 跟在括号内，在表达式中的参数列表。</span><span class="sxs-lookup"><span data-stu-id="d03df-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="d03df-199">只有在不提供任何参数，可以省略括号。</span><span class="sxs-lookup"><span data-stu-id="d03df-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="d03df-200">但是，你的代码是始终使用圆括号更具可读性。</span><span class="sxs-lookup"><span data-stu-id="d03df-200">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="d03df-201">在调用`Function`相同的方式调用任何库函数如过程`Sqrt`， `Cos`，或`ChrW`。</span><span class="sxs-lookup"><span data-stu-id="d03df-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>  
  
 <span data-ttu-id="d03df-202">此外可以调用一个函数，通过使用`Call`关键字。</span><span class="sxs-lookup"><span data-stu-id="d03df-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="d03df-203">在这种情况下，将忽略返回值。</span><span class="sxs-lookup"><span data-stu-id="d03df-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="d03df-204">使用`Call`关键字不建议在大多数情况下。</span><span class="sxs-lookup"><span data-stu-id="d03df-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="d03df-205">有关详细信息，请参阅[Call 语句](call-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-205">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="d03df-206">Visual Basic 有时会重新排列算术表达式来提高内部工作效率。</span><span class="sxs-lookup"><span data-stu-id="d03df-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="d03df-207">因此，不应使用`Function`函数更改同一表达式中的变量的值时的算术表达式中的过程。</span><span class="sxs-lookup"><span data-stu-id="d03df-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>  
  
## <a name="async-functions"></a><span data-ttu-id="d03df-208">异步函数</span><span class="sxs-lookup"><span data-stu-id="d03df-208">Async Functions</span></span>  
 <span data-ttu-id="d03df-209">*异步*功能使您能够而无需使用显式回调或手动拆分跨多个函数或 lambda 表达式的代码调用异步函数。</span><span class="sxs-lookup"><span data-stu-id="d03df-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="d03df-210">如果标记的函数[异步](../../../visual-basic/language-reference/modifiers/async.md)修饰符，可以使用[Await](../../../visual-basic/language-reference/operators/await-operator.md)函数中的运算符。</span><span class="sxs-lookup"><span data-stu-id="d03df-210">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="d03df-211">当控件到达`Await`中的表达式`Async`函数，控制权返回给调用方，并在函数中的进度被挂起，直到等待的任务完成。</span><span class="sxs-lookup"><span data-stu-id="d03df-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="d03df-212">任务完成后，可以在函数中恢复执行。</span><span class="sxs-lookup"><span data-stu-id="d03df-212">When the task is complete, execution can resume in the function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d03df-213">`Async`过程返回给调用方时或者遇到过程尚未结束，第一个 awaited 的对象或到达末尾`Async`过程中，发生者为准第一次。</span><span class="sxs-lookup"><span data-stu-id="d03df-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>  
  
 <span data-ttu-id="d03df-214">`Async`函数可以具有的返回类型<xref:System.Threading.Tasks.Task%601>或<xref:System.Threading.Tasks.Task>。</span><span class="sxs-lookup"><span data-stu-id="d03df-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="d03df-215">举例`Async`函数的返回类型为<xref:System.Threading.Tasks.Task%601>如下所示。</span><span class="sxs-lookup"><span data-stu-id="d03df-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>  
  
 <span data-ttu-id="d03df-216">`Async`函数不能声明任何[ByRef](../../../visual-basic/language-reference/modifiers/byref.md)参数。</span><span class="sxs-lookup"><span data-stu-id="d03df-216">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="d03df-217">一个[Sub 语句](sub-statement.md)还可以使用标记`Async`修饰符。</span><span class="sxs-lookup"><span data-stu-id="d03df-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="d03df-218">这主要用于事件处理程序的值不能返回。</span><span class="sxs-lookup"><span data-stu-id="d03df-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="d03df-219">`Async` `Sub`无法等待过程，和的调用方`Async``Sub`过程不能捕获引发的异常`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="d03df-219">An `Async` `Sub` procedure can't be awaited, and the caller of an `Async` `Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>  
  
 <span data-ttu-id="d03df-220">有关详细信息`Async`函数，请参阅[使用 Async 和 Await 的异步编程](../../../visual-basic/programming-guide/concepts/async/index.md)，[异步程序中的控制流](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)，并[异步返回类型](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="d03df-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="iterator-functions"></a><span data-ttu-id="d03df-221">迭代器函数</span><span class="sxs-lookup"><span data-stu-id="d03df-221">Iterator Functions</span></span>  
 <span data-ttu-id="d03df-222">*迭代器*函数对集合，例如列表或数组执行自定义迭代。</span><span class="sxs-lookup"><span data-stu-id="d03df-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="d03df-223">迭代器函数使用[产生](yield-statement.md)语句返回每个元素，其中一个返回一次。</span><span class="sxs-lookup"><span data-stu-id="d03df-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="d03df-224">当[产生](yield-statement.md)语句到达时，将记住当前代码中的位置。</span><span class="sxs-lookup"><span data-stu-id="d03df-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="d03df-225">下次调用迭代器函数时，将从该位置重新开始执行。</span><span class="sxs-lookup"><span data-stu-id="d03df-225">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="d03df-226">通过使用从客户端代码调用迭代器[为每个...下一步](for-each-next-statement.md)语句。</span><span class="sxs-lookup"><span data-stu-id="d03df-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>  
  
 <span data-ttu-id="d03df-227">迭代器函数的返回类型可以是<xref:System.Collections.IEnumerable>， <xref:System.Collections.Generic.IEnumerable%601>， <xref:System.Collections.IEnumerator>，或<xref:System.Collections.Generic.IEnumerator%601>。</span><span class="sxs-lookup"><span data-stu-id="d03df-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="d03df-228">有关更多信息，请参见 [迭代器](../../programming-guide/concepts/iterators.md)。</span><span class="sxs-lookup"><span data-stu-id="d03df-228">For more information, see [Iterators](../../programming-guide/concepts/iterators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d03df-229">示例</span><span class="sxs-lookup"><span data-stu-id="d03df-229">Example</span></span>  
 <span data-ttu-id="d03df-230">下面的示例使用`Function`语句声明名称、 参数和窗体的主体的代码`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="d03df-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="d03df-231">`ParamArray`修饰符使函数能够接受数目可变的参数。</span><span class="sxs-lookup"><span data-stu-id="d03df-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#25)]  
  
## <a name="example"></a><span data-ttu-id="d03df-232">示例</span><span class="sxs-lookup"><span data-stu-id="d03df-232">Example</span></span>  
 <span data-ttu-id="d03df-233">下面的示例调用在前面的示例声明的函数。</span><span class="sxs-lookup"><span data-stu-id="d03df-233">The following example invokes the function declared in the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
## <a name="example"></a><span data-ttu-id="d03df-234">示例</span><span class="sxs-lookup"><span data-stu-id="d03df-234">Example</span></span>  
 <span data-ttu-id="d03df-235">在以下示例中，`DelayAsync`是`Async``Function`具有返回类型的<xref:System.Threading.Tasks.Task%601>。</span><span class="sxs-lookup"><span data-stu-id="d03df-235">In the following example, `DelayAsync` is an `Async` `Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="d03df-236">`DelayAsync` 具有返回整数的 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="d03df-236">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="d03df-237">因此的函数声明`DelayAsync`需要具有返回类型为`Task(Of Integer)`。</span><span class="sxs-lookup"><span data-stu-id="d03df-237">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="d03df-238">因为返回类型是`Task(Of Integer)`的评估`Await`中的表达式`DoSomethingAsync`得出整数。</span><span class="sxs-lookup"><span data-stu-id="d03df-238">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="d03df-239">此语句中对此进行了演示： `Dim result As Integer = Await delayTask`。</span><span class="sxs-lookup"><span data-stu-id="d03df-239">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="d03df-240">`startButton_Click`过程是一种`Async Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="d03df-240">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="d03df-241">因为`DoSomethingAsync`是`Async`函数，为调用任务`DoSomethingAsync`必须等待，如下面的语句中所示： `Await DoSomethingAsync()`。</span><span class="sxs-lookup"><span data-stu-id="d03df-241">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="d03df-242">`startButton_Click` `Sub`过程必须使用定义`Async`修饰符，因此`Await`表达式。</span><span class="sxs-lookup"><span data-stu-id="d03df-242">The `startButton_Click` `Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/csasyncmethod/vb/mainwindow.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d03df-243">请参阅</span><span class="sxs-lookup"><span data-stu-id="d03df-243">See also</span></span>

- [<span data-ttu-id="d03df-244">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="d03df-244">Sub Statement</span></span>](sub-statement.md)
- [<span data-ttu-id="d03df-245">Function 过程</span><span class="sxs-lookup"><span data-stu-id="d03df-245">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="d03df-246">参数列表</span><span class="sxs-lookup"><span data-stu-id="d03df-246">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="d03df-247">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="d03df-247">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="d03df-248">Call 语句</span><span class="sxs-lookup"><span data-stu-id="d03df-248">Call Statement</span></span>](call-statement.md)
- [<span data-ttu-id="d03df-249">Of</span><span class="sxs-lookup"><span data-stu-id="d03df-249">Of</span></span>](of-clause.md)
- [<span data-ttu-id="d03df-250">参数数组</span><span class="sxs-lookup"><span data-stu-id="d03df-250">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
- [<span data-ttu-id="d03df-251">如何：使用泛型类</span><span class="sxs-lookup"><span data-stu-id="d03df-251">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="d03df-252">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="d03df-252">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
- [<span data-ttu-id="d03df-253">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="d03df-253">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="d03df-254">函数表达式</span><span class="sxs-lookup"><span data-stu-id="d03df-254">Function Expression</span></span>](../../../visual-basic/language-reference/operators/function-expression.md)

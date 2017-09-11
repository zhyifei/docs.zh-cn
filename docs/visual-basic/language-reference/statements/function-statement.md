---
title: "函数语句 (Visual Basic) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Function
dev_langs:
- VB
helpviewer_keywords:
- procedures, creating
- Function procedures, Function statement syntax
- functions [Visual Basic], function procedures
- ParamArray keyword, Function statements
- Private keyword, Function statements
- declarations, procedures
- procedures, declaration
- Public keyword, in Function statement
- ByVal keyword, Function statements
- procedures, recursive
- Implements keyword, Function statements
- procedures, returning values
- Exit statement, in Function procedures
- recursive procedures
- As keyword, in Function statement
- Optional keyword, Function statements
- Function statement
- Visual Basic code, Function procedures
- procedures, function
- ByRef keyword, Function statements
- Friend keyword, Function statements
- End keyword, Function statements
- Handles keyword, Function statements
ms.assetid: a4497077-0f46-4ede-a27f-9e8670df52b9
caps.latest.revision: 62
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: dc1c456c71efb3cc6e60a8fdc77384e65975f110
ms.openlocfilehash: d875fe6df3ef7ac9390346588b1c2d48497d7116
ms.contentlocale: zh-cn
ms.lasthandoff: 05/15/2017

---
# <a name="function-statement-visual-basic"></a><span data-ttu-id="cb4d8-102">Function 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb4d8-102">Function Statement (Visual Basic)</span></span>
<span data-ttu-id="cb4d8-103">声明名称、 参数和定义的代码`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-103">Declares the name, parameters, and code that define a `Function` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb4d8-104">语法</span><span class="sxs-lookup"><span data-stu-id="cb4d8-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async | Iterator ]  
Function name [ (Of typeparamlist) ] [ (parameterlist) ] [ As returntype ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Function ]  
    [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="cb4d8-105">部件</span><span class="sxs-lookup"><span data-stu-id="cb4d8-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="cb4d8-106">可选。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-106">Optional.</span></span> <span data-ttu-id="cb4d8-107">请参阅[属性列表](attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="cb4d8-108">可选。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-108">Optional.</span></span> <span data-ttu-id="cb4d8-109">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="cb4d8-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="cb4d8-110">Public</span><span class="sxs-lookup"><span data-stu-id="cb4d8-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="cb4d8-111">Protected</span><span class="sxs-lookup"><span data-stu-id="cb4d8-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="cb4d8-112">Friend</span><span class="sxs-lookup"><span data-stu-id="cb4d8-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="cb4d8-113">Private</span><span class="sxs-lookup"><span data-stu-id="cb4d8-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="cb4d8-114">请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-114">See [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="cb4d8-115">可选。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-115">Optional.</span></span> <span data-ttu-id="cb4d8-116">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="cb4d8-116">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="cb4d8-117">重载</span><span class="sxs-lookup"><span data-stu-id="cb4d8-117">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="cb4d8-118">Overrides</span><span class="sxs-lookup"><span data-stu-id="cb4d8-118">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="cb4d8-119">Overridable</span><span class="sxs-lookup"><span data-stu-id="cb4d8-119">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="cb4d8-120">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="cb4d8-120">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="cb4d8-121">MustOverride</span><span class="sxs-lookup"><span data-stu-id="cb4d8-121">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="cb4d8-122">可选。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-122">Optional.</span></span> <span data-ttu-id="cb4d8-123">请参阅[共享](../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-123">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="cb4d8-124">可选。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-124">Optional.</span></span> <span data-ttu-id="cb4d8-125">请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-125">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="cb4d8-126">可选。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-126">Optional.</span></span> <span data-ttu-id="cb4d8-127">请参阅[异步](../../../visual-basic/language-reference/modifiers/async.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-127">See [Async](../../../visual-basic/language-reference/modifiers/async.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="cb4d8-128">可选。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-128">Optional.</span></span> <span data-ttu-id="cb4d8-129">请参阅[迭代器](../../../visual-basic/language-reference/modifiers/iterator.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-129">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="cb4d8-130">必需。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-130">Required.</span></span> <span data-ttu-id="cb4d8-131">该过程的名称。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-131">Name of the procedure.</span></span> <span data-ttu-id="cb4d8-132">请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-132">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="cb4d8-133">可选。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-133">Optional.</span></span> <span data-ttu-id="cb4d8-134">针对泛型过程的类型参数的列表。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-134">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="cb4d8-135">请参阅[键入列表](type-list.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-135">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="cb4d8-136">可选。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-136">Optional.</span></span> <span data-ttu-id="cb4d8-137">表示此过程的参数的本地变量名称的列表。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-137">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="cb4d8-138">请参阅[参数列表](parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-138">See [Parameter List](parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="cb4d8-139">如果使用`Option Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-139">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="cb4d8-140">此过程所返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-140">Data type of the value returned by this procedure.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="cb4d8-141">可选。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-141">Optional.</span></span> <span data-ttu-id="cb4d8-142">指示此过程实现一个或多个`Function`过程，此过程包含类或结构实现的接口中定义每个组。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-142">Indicates that this procedure implements one or more `Function` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="cb4d8-143">请参阅[实现语句](implements-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-143">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="cb4d8-144">如果提供 `Implements`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-144">Required if `Implements` is supplied.</span></span> <span data-ttu-id="cb4d8-145">所实现的 `Function` 过程的列表。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-145">List of `Function` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="cb4d8-146">每个 `implementedprocedure` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="cb4d8-146">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="cb4d8-147">部件</span><span class="sxs-lookup"><span data-stu-id="cb4d8-147">Part</span></span>|<span data-ttu-id="cb4d8-148">说明</span><span class="sxs-lookup"><span data-stu-id="cb4d8-148">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="cb4d8-149">必需。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-149">Required.</span></span> <span data-ttu-id="cb4d8-150">此过程所实现的接口名称的包含类或结构。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-150">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="cb4d8-151">必需。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-151">Required.</span></span> <span data-ttu-id="cb4d8-152">在 `interface` 中用于定义过程的名称。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-152">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="cb4d8-153">可选。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-153">Optional.</span></span> <span data-ttu-id="cb4d8-154">指示此过程可以处理一个或多个特定事件。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-154">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="cb4d8-155">请参阅[处理](handles-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-155">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="cb4d8-156">如果提供 `Handles`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-156">Required if `Handles` is supplied.</span></span> <span data-ttu-id="cb4d8-157">此过程处理的事件的列表。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-157">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="cb4d8-158">每个 `eventspecifier` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="cb4d8-158">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="cb4d8-159">部件</span><span class="sxs-lookup"><span data-stu-id="cb4d8-159">Part</span></span>|<span data-ttu-id="cb4d8-160">说明</span><span class="sxs-lookup"><span data-stu-id="cb4d8-160">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="cb4d8-161">必需。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-161">Required.</span></span> <span data-ttu-id="cb4d8-162">声明的类或结构，它将引发事件的数据类型的对象变量。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-162">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="cb4d8-163">必需。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-163">Required.</span></span> <span data-ttu-id="cb4d8-164">此过程处理的事件的名称。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-164">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="cb4d8-165">可选。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-165">Optional.</span></span> <span data-ttu-id="cb4d8-166">此过程中执行的语句块。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-166">Block of statements to be executed within this procedure.</span></span>  
  
-   `End Function`  
  
     <span data-ttu-id="cb4d8-167">终止此过程的定义。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-167">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb4d8-168">备注</span><span class="sxs-lookup"><span data-stu-id="cb4d8-168">Remarks</span></span>  
 <span data-ttu-id="cb4d8-169">在过程内必须是所有可执行代码。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-169">All executable code must be inside a procedure.</span></span> <span data-ttu-id="cb4d8-170">反过来，每个过程，一个类、 结构或包含的类、 结构或模块称为一个模块中声明。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-170">Each procedure, in turn, is declared within a class, a structure, or a module that is referred to as the containing class, structure, or module.</span></span>  
  
 <span data-ttu-id="cb4d8-171">若要将值返回给调用代码，使用`Function`过程; 否则，请使用`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-171">To return a value to the calling code, use a `Function` procedure; otherwise, use a `Sub` procedure.</span></span>  
  
## <a name="defining-a-function"></a><span data-ttu-id="cb4d8-172">定义函数</span><span class="sxs-lookup"><span data-stu-id="cb4d8-172">Defining a Function</span></span>  
 <span data-ttu-id="cb4d8-173">您可以定义`Function`仅在模块级别的过程。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-173">You can define a `Function` procedure only at the module level.</span></span> <span data-ttu-id="cb4d8-174">因此，对于函数的声明上下文必须是一个类、 结构、 模块或接口，且不能为源文件、 命名空间、 过程或块。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-174">Therefore, the declaration context for a function must be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="cb4d8-175">有关详细信息，请参阅[声明上下文和默认访问级别](declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-175">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="cb4d8-176">`Function`过程默认为公共访问。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-176">`Function` procedures default to public access.</span></span> <span data-ttu-id="cb4d8-177">您可以调整它们的访问级别使用的访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-177">You can adjust their access levels with the access modifiers.</span></span>  
  
 <span data-ttu-id="cb4d8-178">一个`Function`过程可以声明该过程返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-178">A `Function` procedure can declare the data type of the value that the procedure returns.</span></span> <span data-ttu-id="cb4d8-179">您可以指定任何数据类型或枚举、 结构、 类或接口的名称。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-179">You can specify any data type or the name of an enumeration, a structure, a class, or an interface.</span></span> <span data-ttu-id="cb4d8-180">如果没有指定`returntype`参数，则该过程返回`Object`。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-180">If you don't specify the `returntype` parameter, the procedure returns `Object`.</span></span>  
  
 <span data-ttu-id="cb4d8-181">如果此过程使用`Implements`关键字、 包含的类或结构还必须具有`Implements`紧跟在后面的语句及其`Class`或`Structure`语句。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-181">If this procedure uses the `Implements` keyword, the containing class or structure must also have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="cb4d8-182">`Implements`语句必须包含在指定的每个接口`implementslist`。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-182">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="cb4d8-183">但是，通过该接口定义的名称`Function`(在`definedname`) 不需要此过程的名称匹配 (在`name`)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-183">However, the name by which an interface defines the `Function` (in `definedname`) doesn't need to match the name of this procedure (in `name`).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb4d8-184">可以使用 lambda 表达式来定义内联函数的表达式。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-184">You can use lambda expressions to define function expressions inline.</span></span> <span data-ttu-id="cb4d8-185">有关详细信息，请参阅[函数表达式](../../../visual-basic/language-reference/operators/function-expression.md)和[Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-185">For more information, see [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md) and [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="returning-from-a-function"></a><span data-ttu-id="cb4d8-186">从函数返回</span><span class="sxs-lookup"><span data-stu-id="cb4d8-186">Returning from a Function</span></span>  
 <span data-ttu-id="cb4d8-187">当`Function`过程返回到调用代码时，继续执行调用该过程的语句后面的语句。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-187">When the `Function` procedure returns to the calling code, execution continues with the statement that follows the statement that called the procedure.</span></span>  
  
 <span data-ttu-id="cb4d8-188">若要从函数返回一个值，可以将该值赋给出函数名称，或将其包含在`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-188">To return a value from a function, you can either assign the value to the function name or include it in a `Return` statement.</span></span>  
  
 <span data-ttu-id="cb4d8-189">`Return`语句同时分配返回值，并退出函数，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-189">The `Return` statement simultaneously assigns the return value and exits the function, as the following example shows.</span></span>  
  
 <span data-ttu-id="cb4d8-190">[!code-vb[VbVbalrStatements #&24;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb4d8-190">[!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="cb4d8-191">下面的示例将返回值分配给函数名`myFunction`，然后使用`Exit Function`语句返回。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-191">The following example assigns the return value to the function name `myFunction` and then uses the `Exit Function` statement to return.</span></span>  
  
 <span data-ttu-id="cb4d8-192">[!code-vb[VbVbalrStatements 第&23;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb4d8-192">[!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_2.vb)]</span></span>  
  
 <span data-ttu-id="cb4d8-193">`Exit Function`和`Return`语句会导致立即退出`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-193">The `Exit Function` and `Return` statements cause an immediate exit from a `Function` procedure.</span></span> <span data-ttu-id="cb4d8-194">任意数量的`Exit Function`和`Return`语句可以在过程中，任何位置出现，并可混合`Exit Function`和`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-194">Any number of `Exit Function` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Function` and `Return` statements.</span></span>  
  
 <span data-ttu-id="cb4d8-195">如果您使用`Exit Function`而无需将值分配给`name`，该过程返回在指定的数据类型的默认值`returntype`。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-195">If you use `Exit Function` without assigning a value to `name`, the procedure returns the default value for the data type that's specified in `returntype`.</span></span> <span data-ttu-id="cb4d8-196">如果`returntype`未指定，则该过程返回`Nothing`，这是默认值为`Object`。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-196">If `returntype` isn't specified, the procedure returns `Nothing`, which is the default value for `Object`.</span></span>  
  
## <a name="calling-a-function"></a><span data-ttu-id="cb4d8-197">调用函数</span><span class="sxs-lookup"><span data-stu-id="cb4d8-197">Calling a Function</span></span>  
 <span data-ttu-id="cb4d8-198">您调用`Function`过程的方法是使用过程名，跟在括号内，在表达式中的参数列表。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-198">You call a `Function` procedure by using the procedure name, followed by the argument list in parentheses, in an expression.</span></span> <span data-ttu-id="cb4d8-199">只有在不提供任何参数，可以省略括号。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-199">You can omit the parentheses only if you aren't supplying any arguments.</span></span> <span data-ttu-id="cb4d8-200">但是，您的代码是始终包含括号更具可读性。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-200">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="cb4d8-201">您调用`Function`过程相同的方式调用的任何库函数如`Sqrt`， `Cos`，或`ChrW`。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-201">You call a `Function` procedure the same way that you call any library function such as `Sqrt`, `Cos`, or `ChrW`.</span></span>  
  
 <span data-ttu-id="cb4d8-202">您还可以通过调用一个函数`Call`关键字。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-202">You can also call a function by using the `Call` keyword.</span></span> <span data-ttu-id="cb4d8-203">在这种情况下，将忽略返回值。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-203">In that case, the return value is ignored.</span></span> <span data-ttu-id="cb4d8-204">利用`Call`关键字，则不建议在大多数情况下。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-204">Use of the `Call` keyword isn't recommended in most cases.</span></span> <span data-ttu-id="cb4d8-205">有关详细信息，请参阅[Call 语句](call-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-205">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="cb4d8-206">Visual Basic 有时可以重新排列算术表达式来提高内部工作效率。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-206">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="cb4d8-207">由于这个原因，不应使用`Function`算术表达式时该函数更改同一表达式中的变量的值中的过程。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-207">For that reason, you shouldn't use a `Function` procedure in an arithmetic expression when the function changes the value of variables in the same expression.</span></span>  
  
## <a name="async-functions"></a><span data-ttu-id="cb4d8-208">异步函数</span><span class="sxs-lookup"><span data-stu-id="cb4d8-208">Async Functions</span></span>  
 <span data-ttu-id="cb4d8-209">*异步*功能可用于调用异步函数而无需使用显式回调或手动将您的代码分拆跨多个函数或 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-209">The *Async* feature allows you to invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="cb4d8-210">如果将标记与函数[异步](../../../visual-basic/language-reference/modifiers/async.md)修饰符，您可以使用[Await](../../../visual-basic/language-reference/operators/await-operator.md)函数中的运算符。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-210">If you mark a function with the [Async](../../../visual-basic/language-reference/modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the function.</span></span> <span data-ttu-id="cb4d8-211">当控制达到`Await`中的表达式`Async`函数，控制权将返回给调用方，并且等待的任务完成之前一直于挂起在函数中的进度。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-211">When control reaches an `Await` expression in the `Async` function, control returns to the caller, and progress in the function is suspended until the awaited task completes.</span></span> <span data-ttu-id="cb4d8-212">当任务完成后时，可在函数中恢复执行。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-212">When the task is complete, execution can resume in the function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb4d8-213">`Async`过程将返回给调用方时也遇到尚未完成，第一个 awaited 的对象或到达末尾`Async`过程中，无论哪个操作发生第一次。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-213">An `Async` procedure returns to the caller when either it encounters the first awaited object that’s not yet complete, or it gets to the end of the `Async` procedure, whichever occurs first.</span></span>  
  
 <span data-ttu-id="cb4d8-214">`Async`函数可以具有返回类型为<xref:System.Threading.Tasks.Task%601>或<xref:System.Threading.Tasks.Task>.</xref:System.Threading.Tasks.Task> </xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="cb4d8-214">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="cb4d8-215">举例说明如何`Async`函数的返回类型为<xref:System.Threading.Tasks.Task%601>下面提供了。</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="cb4d8-215">An example of an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601> is provided below.</span></span>  
  
 <span data-ttu-id="cb4d8-216">`Async`函数不能声明任何[ByRef](../../../visual-basic/language-reference/modifiers/byref.md)参数。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-216">An `Async` function cannot declare any [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="cb4d8-217">一个[Sub 语句](sub-statement.md)还可以使用标记`Async`修饰符。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-217">A [Sub Statement](sub-statement.md) can also be marked with the `Async` modifier.</span></span> <span data-ttu-id="cb4d8-218">这主要用于事件处理程序，不能返回一个值的位置。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-218">This is primarily used for event handlers, where a value cannot be returned.</span></span> <span data-ttu-id="cb4d8-219">`Async``Sub`过程不能处于等待状态，并且调用方的`Async``Sub`过程不能捕获所引发异常的`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-219">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that are thrown by the `Sub` procedure.</span></span>  
  
 <span data-ttu-id="cb4d8-220">有关详细信息`Async`函数，请参见[使用 Async 和 Await 的异步编程](../../../visual-basic/programming-guide/concepts/async/index.md)，[异步程序中的控制流](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)，和[异步返回类型](../../../visual-basic/programming-guide/concepts/async/async-return-types.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-220">For more information about `Async` functions, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="iterator-functions"></a><span data-ttu-id="cb4d8-221">迭代器函数</span><span class="sxs-lookup"><span data-stu-id="cb4d8-221">Iterator Functions</span></span>  
 <span data-ttu-id="cb4d8-222">*迭代器*函数执行自定义迭代访问集合，如列表或数组。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-222">An *iterator* function performs a custom iteration over a collection, such as a list or array.</span></span> <span data-ttu-id="cb4d8-223">迭代器函数使用[生成](yield-statement.md)语句可一次返回每个元素。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-223">An iterator function uses the [Yield](yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="cb4d8-224">当[产生](yield-statement.md)到达语句，记住代码中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-224">When a [Yield](yield-statement.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="cb4d8-225">在下次调用迭代器函数将从该位置重新开始执行。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-225">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="cb4d8-226">通过使用从客户端代码调用迭代器[为每个...下一步](for-each-next-statement.md)语句。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-226">You call an iterator from client code by using a [For Each…Next](for-each-next-statement.md) statement.</span></span>  
  
 <span data-ttu-id="cb4d8-227">迭代器函数的返回类型可以是<xref:System.Collections.IEnumerable>， <xref:System.Collections.Generic.IEnumerable%601>， <xref:System.Collections.IEnumerator>，或<xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="cb4d8-227">The return type of an iterator function can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="cb4d8-228">有关详细信息，请参阅[迭代器](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-228">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb4d8-229">示例</span><span class="sxs-lookup"><span data-stu-id="cb4d8-229">Example</span></span>  
 <span data-ttu-id="cb4d8-230">下面的示例使用`Function`语句来声明名称、 参数和窗体的主体的代码`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-230">The following example uses the `Function` statement to declare the name, parameters, and code that form the body of a `Function` procedure.</span></span> <span data-ttu-id="cb4d8-231">`ParamArray`修饰符将启用用于接受可变数量的参数的函数。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-231">The `ParamArray` modifier enables the function to accept a variable number of arguments.</span></span>  
  
 <span data-ttu-id="cb4d8-232">[!code-vb[VbVbalrStatements #&25;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb4d8-232">[!code-vb[VbVbalrStatements#25](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb4d8-233">示例</span><span class="sxs-lookup"><span data-stu-id="cb4d8-233">Example</span></span>  
 <span data-ttu-id="cb4d8-234">下面的示例调用在前面的示例声明的函数。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-234">The following example invokes the function declared in the preceding example.</span></span>  
  
 <span data-ttu-id="cb4d8-235">[!code-vb[VbVbalrStatements #&26;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb4d8-235">[!code-vb[VbVbalrStatements#26](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/function-statement_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb4d8-236">示例</span><span class="sxs-lookup"><span data-stu-id="cb4d8-236">Example</span></span>  
 <span data-ttu-id="cb4d8-237">在下面的示例中，`DelayAsync`是`Async``Function`，其返回类型为<xref:System.Threading.Tasks.Task%601>。</xref:System.Threading.Tasks.Task%601></span><span class="sxs-lookup"><span data-stu-id="cb4d8-237">In the following example, `DelayAsync` is an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="cb4d8-238">`DelayAsync` 具有返回整数的 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-238">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="cb4d8-239">因此的函数声明`DelayAsync`需要具有返回类型的`Task(Of Integer)`。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-239">Therefore the function declaration of `DelayAsync` needs to have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="cb4d8-240">因为返回类型为`Task(Of Integer)`，计算`Await`中的表达式`DoSomethingAsync`产生一个整数。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-240">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer.</span></span> <span data-ttu-id="cb4d8-241">在此语句中对此进行了演示︰ `Dim result As Integer = Await delayTask`。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-241">This is demonstrated in this statement: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="cb4d8-242">`startButton_Click`过程是一种`Async Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-242">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="cb4d8-243">因为`DoSomethingAsync`是`Async`函数，以调用任务`DoSomethingAsync`必须等待，如下面的语句所示︰ `Await DoSomethingAsync()`。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-243">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement demonstrates: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="cb4d8-244">`startButton_Click``Sub`过程必须定义与`Async`修饰符，因此`Await`表达式。</span><span class="sxs-lookup"><span data-stu-id="cb4d8-244">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 <span data-ttu-id="cb4d8-245">[!code-vb[csAsyncMethod&#1;](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="cb4d8-245">[!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/function-statement_5.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb4d8-246">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb4d8-246">See Also</span></span>  
 <span data-ttu-id="cb4d8-247">[Sub 语句](sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="cb4d8-247">[Sub Statement](sub-statement.md) </span></span>  
<span data-ttu-id="cb4d8-248"> [Function 过程](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="cb4d8-248"> [Function Procedures](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span></span>  
<span data-ttu-id="cb4d8-249"> [参数列表](parameter-list.md) </span><span class="sxs-lookup"><span data-stu-id="cb4d8-249"> [Parameter List](parameter-list.md) </span></span>  
<span data-ttu-id="cb4d8-250"> [Dim 语句](dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="cb4d8-250"> [Dim Statement](dim-statement.md) </span></span>  
<span data-ttu-id="cb4d8-251"> [Call 语句](call-statement.md) </span><span class="sxs-lookup"><span data-stu-id="cb4d8-251"> [Call Statement](call-statement.md) </span></span>  
<span data-ttu-id="cb4d8-252"> [Of](of-clause.md) </span><span class="sxs-lookup"><span data-stu-id="cb4d8-252"> [Of](of-clause.md) </span></span>  
<span data-ttu-id="cb4d8-253"> [参数数组](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="cb4d8-253"> [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md) </span></span>  
<span data-ttu-id="cb4d8-254"> [如何︰ 使用泛型类](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span><span class="sxs-lookup"><span data-stu-id="cb4d8-254"> [How to: Use a Generic Class](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span></span>  
<span data-ttu-id="cb4d8-255"> [故障排除过程](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="cb4d8-255"> [Troubleshooting Procedures](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="cb4d8-256"> [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="cb4d8-256"> [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span></span>  
<span data-ttu-id="cb4d8-257"> [函数表达式](../../../visual-basic/language-reference/operators/function-expression.md)</span><span class="sxs-lookup"><span data-stu-id="cb4d8-257"> [Function Expression](../../../visual-basic/language-reference/operators/function-expression.md)</span></span>


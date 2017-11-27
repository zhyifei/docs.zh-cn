---
title: "Sub 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Sub
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
caps.latest.revision: "52"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 02ba9a999db20abce2106269522c9a3221a00cef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="sub-statement-visual-basic"></a><span data-ttu-id="d6d0f-102">Sub 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6d0f-102">Sub Statement (Visual Basic)</span></span>
<span data-ttu-id="d6d0f-103">声明名称、 参数和定义的代码`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-103">Declares the name, parameters, and code that define a `Sub` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6d0f-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6d0f-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Partial ] [ accessmodifier ] [ proceduremodifiers ] [ Shared ] [ Shadows ] [ Async ]  
Sub name [ (Of typeparamlist) ] [ (parameterlist) ] [ Implements implementslist | Handles eventlist ]  
    [ statements ]  
    [ Exit Sub ]  
    [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="d6d0f-105">部件</span><span class="sxs-lookup"><span data-stu-id="d6d0f-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="d6d0f-106">可选。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-106">Optional.</span></span> <span data-ttu-id="d6d0f-107">请参阅[属性列表](attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-107">See [Attribute List](attribute-list.md).</span></span>  
  
-   `Partial`  
  
     <span data-ttu-id="d6d0f-108">可选。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-108">Optional.</span></span> <span data-ttu-id="d6d0f-109">指示分部方法的定义。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-109">Indicates definition of a partial method.</span></span> <span data-ttu-id="d6d0f-110">请参阅[分部方法](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-110">See [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="d6d0f-111">可选。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-111">Optional.</span></span> <span data-ttu-id="d6d0f-112">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="d6d0f-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="d6d0f-113">Public</span><span class="sxs-lookup"><span data-stu-id="d6d0f-113">Public</span></span>](../modifiers/public.md)  
  
    -   [<span data-ttu-id="d6d0f-114">Protected</span><span class="sxs-lookup"><span data-stu-id="d6d0f-114">Protected</span></span>](../modifiers/protected.md)  
  
    -   [<span data-ttu-id="d6d0f-115">Friend</span><span class="sxs-lookup"><span data-stu-id="d6d0f-115">Friend</span></span>](../modifiers/friend.md)  
  
    -   [<span data-ttu-id="d6d0f-116">Private</span><span class="sxs-lookup"><span data-stu-id="d6d0f-116">Private</span></span>](../modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="d6d0f-117">请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-117">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `proceduremodifiers`  
  
     <span data-ttu-id="d6d0f-118">可选。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-118">Optional.</span></span> <span data-ttu-id="d6d0f-119">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="d6d0f-119">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="d6d0f-120">重载</span><span class="sxs-lookup"><span data-stu-id="d6d0f-120">Overloads</span></span>](../modifiers/overloads.md)  
  
    -   [<span data-ttu-id="d6d0f-121">Overrides</span><span class="sxs-lookup"><span data-stu-id="d6d0f-121">Overrides</span></span>](../modifiers/overrides.md)  
  
    -   [<span data-ttu-id="d6d0f-122">Overridable</span><span class="sxs-lookup"><span data-stu-id="d6d0f-122">Overridable</span></span>](../modifiers/overridable.md)  
  
    -   [<span data-ttu-id="d6d0f-123">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="d6d0f-123">NotOverridable</span></span>](../modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="d6d0f-124">MustOverride</span><span class="sxs-lookup"><span data-stu-id="d6d0f-124">MustOverride</span></span>](../modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="d6d0f-125">可选。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-125">Optional.</span></span> <span data-ttu-id="d6d0f-126">请参阅[共享](../modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-126">See [Shared](../modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="d6d0f-127">可选。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-127">Optional.</span></span> <span data-ttu-id="d6d0f-128">请参阅[阴影](../modifiers/shadows.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-128">See [Shadows](../modifiers/shadows.md).</span></span>  
  
-   `Async`  
  
     <span data-ttu-id="d6d0f-129">可选。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-129">Optional.</span></span> <span data-ttu-id="d6d0f-130">请参阅[异步](../modifiers/async.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-130">See [Async](../modifiers/async.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="d6d0f-131">必需。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-131">Required.</span></span> <span data-ttu-id="d6d0f-132">过程的名称。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-132">Name of the procedure.</span></span> <span data-ttu-id="d6d0f-133">请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-133">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span> <span data-ttu-id="d6d0f-134">若要创建一个类的构造函数过程，设置的名称`Sub`过程`New`关键字。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-134">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="d6d0f-135">有关详细信息，请参阅[对象生存期： 对象的创建和破坏的方式](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-135">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
-   `typeparamlist`  
  
     <span data-ttu-id="d6d0f-136">可选。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-136">Optional.</span></span> <span data-ttu-id="d6d0f-137">类型参数的泛型过程的列表。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-137">List of type parameters for a generic procedure.</span></span> <span data-ttu-id="d6d0f-138">请参阅[键入列表](type-list.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-138">See [Type List](type-list.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="d6d0f-139">可选。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-139">Optional.</span></span> <span data-ttu-id="d6d0f-140">表示此过程的参数的本地变量名称的列表。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-140">List of local variable names representing the parameters of this procedure.</span></span> <span data-ttu-id="d6d0f-141">请参阅[参数列表](parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-141">See [Parameter List](parameter-list.md).</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="d6d0f-142">可选。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-142">Optional.</span></span> <span data-ttu-id="d6d0f-143">指示，此过程可实现一个或多个`Sub`过程，此过程的包含类或结构实现接口中定义的每个组。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-143">Indicates that this procedure implements one or more `Sub` procedures, each one defined in an interface implemented by this procedure's containing class or structure.</span></span> <span data-ttu-id="d6d0f-144">请参阅[实现语句](implements-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-144">See [Implements Statement](implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="d6d0f-145">如果提供 `Implements`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-145">Required if `Implements` is supplied.</span></span> <span data-ttu-id="d6d0f-146">所实现的 `Sub` 过程的列表。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-146">List of `Sub` procedures being implemented.</span></span>  
  
     `implementedprocedure [ , implementedprocedure ... ]`  
  
     <span data-ttu-id="d6d0f-147">每个 `implementedprocedure` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="d6d0f-147">Each `implementedprocedure` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="d6d0f-148">部件</span><span class="sxs-lookup"><span data-stu-id="d6d0f-148">Part</span></span>|<span data-ttu-id="d6d0f-149">描述</span><span class="sxs-lookup"><span data-stu-id="d6d0f-149">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="d6d0f-150">必需。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-150">Required.</span></span> <span data-ttu-id="d6d0f-151">此过程所实现的接口的名称包含的类或结构。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-151">Name of an interface implemented by this procedure's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="d6d0f-152">必需。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-152">Required.</span></span> <span data-ttu-id="d6d0f-153">在 `interface` 中用于定义过程的名称。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-153">Name by which the procedure is defined in `interface`.</span></span>|  
  
-   `Handles`  
  
     <span data-ttu-id="d6d0f-154">可选。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-154">Optional.</span></span> <span data-ttu-id="d6d0f-155">指示此过程可以处理一个或多个特定事件。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-155">Indicates that this procedure can handle one or more specific events.</span></span> <span data-ttu-id="d6d0f-156">请参阅[处理](handles-clause.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-156">See [Handles](handles-clause.md).</span></span>  
  
-   `eventlist`  
  
     <span data-ttu-id="d6d0f-157">如果提供 `Handles`，则是必需的。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-157">Required if `Handles` is supplied.</span></span> <span data-ttu-id="d6d0f-158">此过程可处理的事件的列表。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-158">List of events this procedure handles.</span></span>  
  
     `eventspecifier [ , eventspecifier ... ]`  
  
     <span data-ttu-id="d6d0f-159">每个 `eventspecifier` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="d6d0f-159">Each `eventspecifier` has the following syntax and parts:</span></span>  
  
     `eventvariable.event`  
  
    |<span data-ttu-id="d6d0f-160">部件</span><span class="sxs-lookup"><span data-stu-id="d6d0f-160">Part</span></span>|<span data-ttu-id="d6d0f-161">描述</span><span class="sxs-lookup"><span data-stu-id="d6d0f-161">Description</span></span>|  
    |---|---|  
    |`eventvariable`|<span data-ttu-id="d6d0f-162">必需。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-162">Required.</span></span> <span data-ttu-id="d6d0f-163">声明的类或结构，它引发事件的数据类型的对象变量。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-163">Object variable declared with the data type of the class or structure that raises the event.</span></span>|  
    |`event`|<span data-ttu-id="d6d0f-164">必需。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-164">Required.</span></span> <span data-ttu-id="d6d0f-165">此过程可处理的事件名称。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-165">Name of the event this procedure handles.</span></span>|  
  
-   `statements`  
  
     <span data-ttu-id="d6d0f-166">可选。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-166">Optional.</span></span> <span data-ttu-id="d6d0f-167">要在此过程中运行的语句块。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-167">Block of statements to run within this procedure.</span></span>  
  
-   `End Sub`  
  
     <span data-ttu-id="d6d0f-168">终止此过程的定义。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-168">Terminates the definition of this procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6d0f-169">备注</span><span class="sxs-lookup"><span data-stu-id="d6d0f-169">Remarks</span></span>  
 <span data-ttu-id="d6d0f-170">过程内必须是所有可执行代码。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-170">All executable code must be inside a procedure.</span></span> <span data-ttu-id="d6d0f-171">使用`Sub`时你不想要将值返回给调用代码的过程。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-171">Use a `Sub` procedure when you don't want to return a value to the calling code.</span></span> <span data-ttu-id="d6d0f-172">使用`Function`过程在你想要返回一个值。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-172">Use a `Function` procedure when you want to return a value.</span></span>  
  
## <a name="defining-a-sub-procedure"></a><span data-ttu-id="d6d0f-173">定义 Sub 过程</span><span class="sxs-lookup"><span data-stu-id="d6d0f-173">Defining a Sub Procedure</span></span>  
 <span data-ttu-id="d6d0f-174">你可以定义`Sub`只能在模块级别的过程。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-174">You can define a `Sub` procedure only at the module level.</span></span> <span data-ttu-id="d6d0f-175">Sub 过程的声明上下文，因此，必须类、 结构、 模块或接口，并且不能为源文件、 命名空间、 过程或块。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-175">The declaration context for a sub procedure must, therefore, be a class, a structure, a module, or an interface and can't be a source file, a namespace, a procedure, or a block.</span></span> <span data-ttu-id="d6d0f-176">有关详细信息，请参阅[声明上下文和默认访问级别](declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-176">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="d6d0f-177">`Sub`过程默认为公共访问。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-177">`Sub` procedures default to public access.</span></span> <span data-ttu-id="d6d0f-178">你可以使用访问修饰符来调整其访问级别。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-178">You can adjust their access levels by using the access modifiers.</span></span>  
  
 <span data-ttu-id="d6d0f-179">如果该过程使用`Implements`关键字、 包含的类或结构必须具有`Implements`紧随的语句其`Class`或`Structure`语句。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-179">If the procedure uses the `Implements` keyword, the containing class or structure must have an `Implements` statement that immediately follows its `Class` or `Structure` statement.</span></span> <span data-ttu-id="d6d0f-180">`Implements`语句必须包含在指定的每个接口`implementslist`。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-180">The `Implements` statement must include each interface that's specified in `implementslist`.</span></span> <span data-ttu-id="d6d0f-181">但是，通过该接口定义的名称`Sub`(在`definedname`) 不一定要与此过程的名称 (在`name`)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-181">However, the name by which an interface defines the `Sub` (in `definedname`) doesn't have to match the name of this procedure (in `name`).</span></span>  
  
## <a name="returning-from-a-sub-procedure"></a><span data-ttu-id="d6d0f-182">返回从 Sub 过程</span><span class="sxs-lookup"><span data-stu-id="d6d0f-182">Returning from a Sub Procedure</span></span>  
 <span data-ttu-id="d6d0f-183">当`Sub`过程返回到调用代码时，继续执行调用它的语句之后的语句。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-183">When a `Sub` procedure returns to the calling code, execution continues with the statement after the statement that called it.</span></span>  
  
 <span data-ttu-id="d6d0f-184">下面的示例演示从返回`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-184">The following example shows a return from a `Sub` procedure.</span></span>  
  
```vb  
Sub mySub(ByVal q As String)  
    Return  
End Sub   
```  
  
 <span data-ttu-id="d6d0f-185">`Exit Sub`和`Return`语句会导致立即退出`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-185">The `Exit Sub` and `Return` statements cause an immediate exit from a `Sub` procedure.</span></span> <span data-ttu-id="d6d0f-186">任意数量的`Exit Sub`和`Return`语句可以出现的任何位置在过程中，并可混合`Exit Sub`和`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-186">Any number of `Exit Sub` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Sub` and `Return` statements.</span></span>  
  
## <a name="calling-a-sub-procedure"></a><span data-ttu-id="d6d0f-187">调用 Sub 过程</span><span class="sxs-lookup"><span data-stu-id="d6d0f-187">Calling a Sub Procedure</span></span>  
 <span data-ttu-id="d6d0f-188">你调用`Sub`过程的方法是在语句中使用的过程名称，然后遵照该名称与在括号中其自变量列表。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-188">You call a `Sub` procedure by using the procedure name in a statement and then following that name with its argument list in parentheses.</span></span> <span data-ttu-id="d6d0f-189">仅当你不提供任何参数，可以省略括号。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-189">You can omit the parentheses only if you don't supply any arguments.</span></span> <span data-ttu-id="d6d0f-190">但是，你的代码是始终包含括号更具可读性。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-190">However, your code is more readable if you always include the parentheses.</span></span>  
  
 <span data-ttu-id="d6d0f-191">A`Sub`过程和`Function`过程可以具有参数和执行一系列语句。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-191">A `Sub` procedure and a `Function` procedure  can have parameters and perform a series of statements.</span></span> <span data-ttu-id="d6d0f-192">但是，`Function`过程返回一个值，以及一`Sub`过程不会。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-192">However, a `Function` procedure returns a value, and a `Sub` procedure doesn't.</span></span> <span data-ttu-id="d6d0f-193">因此，不能使用`Sub`在表达式中的过程。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-193">Therefore, you can't use a `Sub` procedure in an expression.</span></span>  
  
 <span data-ttu-id="d6d0f-194">你可以使用`Call`关键字在调用时`Sub`过程中，但是该关键字，则不建议的大部分使用。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-194">You can use the `Call` keyword when you call a `Sub` procedure, but that keyword isn't recommended for most uses.</span></span> <span data-ttu-id="d6d0f-195">有关详细信息，请参阅[Call 语句](call-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-195">For more information, see [Call Statement](call-statement.md).</span></span>  
  
 <span data-ttu-id="d6d0f-196">Visual Basic 有时重新排列算术表达式来提高内部的工作效率。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-196">Visual Basic sometimes rearranges arithmetic expressions to increase internal efficiency.</span></span> <span data-ttu-id="d6d0f-197">因此，如果自变量列表包括调用其他过程的表达式，您不应假定，将按特定顺序调用这些表达式。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-197">For that reason, if your argument list includes expressions that call other procedures, you shouldn't assume that those expressions will be called in a particular order.</span></span>  
  
## <a name="async-sub-procedures"></a><span data-ttu-id="d6d0f-198">异步 Sub 过程</span><span class="sxs-lookup"><span data-stu-id="d6d0f-198">Async Sub Procedures</span></span>  
 <span data-ttu-id="d6d0f-199">通过使用异步功能，可以调用的异步函数，而无需使用显式回调，也跨多个函数或 lambda 表达式中手动拆分代码。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-199">By using the Async feature, you can invoke asynchronous functions without using explicit callbacks or manually splitting your code across multiple functions or lambda expressions.</span></span>  
  
 <span data-ttu-id="d6d0f-200">如果将标记与过程[异步](../modifiers/async.md)修饰符，你可以使用[Await](../../../visual-basic/language-reference/operators/await-operator.md)过程中的运算符。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-200">If you mark a procedure with the [Async](../modifiers/async.md) modifier, you can use the [Await](../../../visual-basic/language-reference/operators/await-operator.md) operator in the procedure.</span></span> <span data-ttu-id="d6d0f-201">当控件到达`Await`中的表达式`Async`过程中，控件将返回给调用方，并在过程中的进度将挂起，直到所等待的任务完成。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-201">When control reaches an `Await` expression in the `Async` procedure, control returns to the caller, and progress in the procedure is suspended until the awaited task completes.</span></span> <span data-ttu-id="d6d0f-202">在任务完成后，可以在该过程中恢复执行。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-202">When the task is complete, execution can resume in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6d0f-203">`Async`过程返回到调用方时遇到任一的第一个等待的对象尚未完成或末尾`Async`达到过程，以先发生者为准。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-203">An `Async` procedure returns to the caller when either the first awaited object that’s not yet complete is encountered or the end of the `Async` procedure is reached, whichever occurs first.</span></span>  
  
 <span data-ttu-id="d6d0f-204">你还可以将标记[Function 语句](function-statement.md)与`Async`修饰符。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-204">You can also mark a [Function Statement](function-statement.md) with the `Async` modifier.</span></span> <span data-ttu-id="d6d0f-205">`Async`函数可以具有返回类型的<xref:System.Threading.Tasks.Task%601>或<xref:System.Threading.Tasks.Task>。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-205">An `Async` function can have a return type of <xref:System.Threading.Tasks.Task%601> or <xref:System.Threading.Tasks.Task>.</span></span> <span data-ttu-id="d6d0f-206">示例更高版本在本主题演示`Async`具有的返回类型的函数<xref:System.Threading.Tasks.Task%601>。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-206">An example later in this topic shows an `Async` function that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
 <span data-ttu-id="d6d0f-207">`Async``Sub`过程主要使用，用于为事件处理程序，不能返回一个值的位置。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-207">`Async` `Sub` procedures are primarily used for event handlers, where a value can't be returned.</span></span> <span data-ttu-id="d6d0f-208">`Async``Sub`无法等待过程，和的调用方`Async``Sub`过程不能捕获异常，`Sub`过程引发。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-208">An `Async``Sub` procedure can't be awaited, and the caller of an `Async``Sub` procedure can't catch exceptions that the `Sub` procedure throws.</span></span>  
  
 <span data-ttu-id="d6d0f-209">`Async`过程不能声明任何[ByRef](../modifiers/byref.md)参数。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-209">An `Async` procedure can't declare any [ByRef](../modifiers/byref.md) parameters.</span></span>  
  
 <span data-ttu-id="d6d0f-210">有关详细信息`Async`过程，请参阅[使用 Async 和 Await 进行异步编程](../../../visual-basic/programming-guide/concepts/async/index.md)，[异步程序中的控制流](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)，和[异步返回类型](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="d6d0f-210">For more information about `Async` procedures, see [Asynchronous Programming with Async and Await](../../../visual-basic/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6d0f-211">示例</span><span class="sxs-lookup"><span data-stu-id="d6d0f-211">Example</span></span>  
 <span data-ttu-id="d6d0f-212">下面的示例使用`Sub`语句以定义名称、 参数和窗体的主体的代码`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-212">The following example uses the `Sub` statement to define the name, parameters, and code that form the body of a `Sub` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#58](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/sub-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="d6d0f-213">示例</span><span class="sxs-lookup"><span data-stu-id="d6d0f-213">Example</span></span>  
 <span data-ttu-id="d6d0f-214">在下面的示例中，`DelayAsync`是`Async``Function`，其返回类型为<xref:System.Threading.Tasks.Task%601>。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-214">In the following example, `DelayAsync` is an an `Async``Function` that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="d6d0f-215">`DelayAsync` 具有返回整数的 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-215">`DelayAsync` has a `Return` statement that returns an integer.</span></span> <span data-ttu-id="d6d0f-216">因此，函数声明的`DelayAsync`必须具有返回类型的`Task(Of Integer)`。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-216">Therefore, the function declaration of `DelayAsync` must have a return type of `Task(Of Integer)`.</span></span> <span data-ttu-id="d6d0f-217">因为返回类型为`Task(Of Integer)`，计算`Await`中的表达式`DoSomethingAsync`得出整数，如以下语句所示： `Dim result As Integer = Await delayTask`。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-217">Because the return type is `Task(Of Integer)`, the evaluation of the `Await` expression in `DoSomethingAsync` produces an integer, as the following statement shows: `Dim result As Integer = Await delayTask`.</span></span>  
  
 <span data-ttu-id="d6d0f-218">`startButton_Click`过程是一种`Async Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-218">The `startButton_Click` procedure is an example of an `Async Sub` procedure.</span></span> <span data-ttu-id="d6d0f-219">因为`DoSomethingAsync`是`Async`函数，以调用任务`DoSomethingAsync`必须等待，如以下语句所示： `Await DoSomethingAsync()`。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-219">Because `DoSomethingAsync` is an `Async` function, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `Await DoSomethingAsync()`.</span></span> <span data-ttu-id="d6d0f-220">`startButton_Click``Sub`过程必须使用定义`Async`修饰符因为它具有`Await`表达式。</span><span class="sxs-lookup"><span data-stu-id="d6d0f-220">The `startButton_Click``Sub` procedure must be defined with the `Async` modifier because it has an `Await` expression.</span></span>  
  
 [!code-vb[csAsyncMethod#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/VisualBasic/sub-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d6d0f-221">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6d0f-221">See Also</span></span>  
 [<span data-ttu-id="d6d0f-222">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="d6d0f-222">Implements Statement</span></span>](implements-statement.md)  
 [<span data-ttu-id="d6d0f-223">Function 语句</span><span class="sxs-lookup"><span data-stu-id="d6d0f-223">Function Statement</span></span>](function-statement.md)  
 [<span data-ttu-id="d6d0f-224">参数列表</span><span class="sxs-lookup"><span data-stu-id="d6d0f-224">Parameter List</span></span>](parameter-list.md)  
 [<span data-ttu-id="d6d0f-225">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="d6d0f-225">Dim Statement</span></span>](dim-statement.md)  
 [<span data-ttu-id="d6d0f-226">Call 语句</span><span class="sxs-lookup"><span data-stu-id="d6d0f-226">Call Statement</span></span>](call-statement.md)  
 [<span data-ttu-id="d6d0f-227">Of</span><span class="sxs-lookup"><span data-stu-id="d6d0f-227">Of</span></span>](of-clause.md)  
 [<span data-ttu-id="d6d0f-228">参数数组</span><span class="sxs-lookup"><span data-stu-id="d6d0f-228">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)  
 [<span data-ttu-id="d6d0f-229">如何：使用泛型类</span><span class="sxs-lookup"><span data-stu-id="d6d0f-229">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="d6d0f-230">过程疑难解答</span><span class="sxs-lookup"><span data-stu-id="d6d0f-230">Troubleshooting Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)  
 [<span data-ttu-id="d6d0f-231">分部方法</span><span class="sxs-lookup"><span data-stu-id="d6d0f-231">Partial Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)

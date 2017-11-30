---
title: "过程疑难解答 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b838644baa5ad10f1deb917cff5751a0f625fca6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-procedures-visual-basic"></a><span data-ttu-id="44a1b-102">过程疑难解答 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44a1b-102">Troubleshooting Procedures (Visual Basic)</span></span>
<span data-ttu-id="44a1b-103">此页列出在使用过程时可能发生的一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="44a1b-103">This page lists some common problems that can occur when working with procedures.</span></span>  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a><span data-ttu-id="44a1b-104">从一个函数的过程中返回数组类型</span><span class="sxs-lookup"><span data-stu-id="44a1b-104">Returning an Array Type from a Function Procedure</span></span>  
 <span data-ttu-id="44a1b-105">如果`Function`过程返回数组数据类型，则无法使用`Function`将值存储在数组的元素的名称。</span><span class="sxs-lookup"><span data-stu-id="44a1b-105">If a `Function` procedure returns an array data type, you cannot use the `Function` name to store values in the elements of the array.</span></span> <span data-ttu-id="44a1b-106">如果你尝试执行此操作，编译器会将它解释为对的调用`Function`。</span><span class="sxs-lookup"><span data-stu-id="44a1b-106">If you attempt to do this, the compiler interprets it as a call to the `Function`.</span></span> <span data-ttu-id="44a1b-107">下面的示例生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="44a1b-107">The following example generates compiler errors.</span></span>  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 <span data-ttu-id="44a1b-108">`' The following statement generates a`   `COMPILER ERROR`  `.`</span><span class="sxs-lookup"><span data-stu-id="44a1b-108">`' The following statement generates a`   `COMPILER ERROR`  `.`</span></span>  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 <span data-ttu-id="44a1b-109">`' The following statement generates a`   `COMPILER ERROR`  `.`</span><span class="sxs-lookup"><span data-stu-id="44a1b-109">`' The following statement generates a`   `COMPILER ERROR`  `.`</span></span>  
  
 `Return allOnes()`  
  
 `End Function`  
  
 <span data-ttu-id="44a1b-110">语句`allOnes(i) = 1`生成一个编译器错误，因为它似乎是调用`allOnes`用错误数据类型参数 (singleton`Integer`而不是`Integer`数组)。</span><span class="sxs-lookup"><span data-stu-id="44a1b-110">The statement `allOnes(i) = 1` generates a compiler error because it appears to call `allOnes` with an argument of the wrong data type (a singleton `Integer` instead of an `Integer` array).</span></span> <span data-ttu-id="44a1b-111">语句`Return allOnes()`生成一个编译器错误，因为它似乎是调用`allOnes`不带参数。</span><span class="sxs-lookup"><span data-stu-id="44a1b-111">The statement `Return allOnes()` generates a compiler error because it appears to call `allOnes` with no argument.</span></span>  
  
 <span data-ttu-id="44a1b-112">**正确的方法：**能够修改要返回的数组的元素，定义一个内部数组为本地变量。</span><span class="sxs-lookup"><span data-stu-id="44a1b-112">**Correct Approach:** To be able to modify the elements of an array that is to be returned, define an internal array as a local variable.</span></span> <span data-ttu-id="44a1b-113">下面的示例编译而不出错。</span><span class="sxs-lookup"><span data-stu-id="44a1b-113">The following example compiles without error.</span></span>  
  
 [!code-vb[VbVbcnProcedures#66](./codesnippet/VisualBasic/troubleshooting-procedures_1.vb)]  
  
## <a name="argument-not-being-modified-by-procedure-call"></a><span data-ttu-id="44a1b-114">未修改的自变量由过程调用</span><span class="sxs-lookup"><span data-stu-id="44a1b-114">Argument Not Being Modified by Procedure Call</span></span>  
 <span data-ttu-id="44a1b-115">如果你想要允许更改基础中调用代码的自变量的编程元素的过程，必须通过引用传递。</span><span class="sxs-lookup"><span data-stu-id="44a1b-115">If you intend to allow a procedure to change a programming element underlying an argument in the calling code, you must pass it by reference.</span></span> <span data-ttu-id="44a1b-116">但即使按值传递过程仍可访问的元素的引用类型参数。</span><span class="sxs-lookup"><span data-stu-id="44a1b-116">But a procedure can access the elements of a reference type argument even if you pass it by value.</span></span>  
  
-   <span data-ttu-id="44a1b-117">**基础变量**。</span><span class="sxs-lookup"><span data-stu-id="44a1b-117">**Underlying Variable**.</span></span> <span data-ttu-id="44a1b-118">若要允许替换基础变量元素本身的值的过程，该过程必须声明参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)。</span><span class="sxs-lookup"><span data-stu-id="44a1b-118">To allow the procedure to replace the value of the underlying variable element itself, the procedure must declare the parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="44a1b-119">此外，调用代码必须不将自变量在括号中，因为这样将重写`ByRef`传递机制。</span><span class="sxs-lookup"><span data-stu-id="44a1b-119">Also, the calling code must not enclose the argument in parentheses, because that would override the `ByRef` passing mechanism.</span></span>  
  
-   <span data-ttu-id="44a1b-120">**引用类型元素**。</span><span class="sxs-lookup"><span data-stu-id="44a1b-120">**Reference Type Elements**.</span></span> <span data-ttu-id="44a1b-121">如果声明的参数[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)，过程不能修改基础变量元素本身。</span><span class="sxs-lookup"><span data-stu-id="44a1b-121">If you declare a parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md), the procedure cannot modify the underlying variable element itself.</span></span> <span data-ttu-id="44a1b-122">但是，如果参数为引用类型，该过程可以修改它指向的该对象的成员，即使它不能替换变量的值一样。</span><span class="sxs-lookup"><span data-stu-id="44a1b-122">However, if the argument is a reference type, the procedure can modify the members of the object to which it points, even though it cannot replace the variable's value.</span></span> <span data-ttu-id="44a1b-123">例如，如果参数是一个数组变量，该过程不能将新数组赋给它，但它可以更改一个或多个它的元素。</span><span class="sxs-lookup"><span data-stu-id="44a1b-123">For example, if the argument is an array variable, the procedure cannot assign a new array to it, but it can change one or more of its elements.</span></span> <span data-ttu-id="44a1b-124">更改的元素会反映在调用代码中的基础数组变量。</span><span class="sxs-lookup"><span data-stu-id="44a1b-124">The changed elements are reflected in the underlying array variable in the calling code.</span></span>  
  
 <span data-ttu-id="44a1b-125">下面的示例定义两个过程可通过值采用一个数组变量并运行对其元素。</span><span class="sxs-lookup"><span data-stu-id="44a1b-125">The following example defines two procedures that take an array variable by value and operate on its elements.</span></span> <span data-ttu-id="44a1b-126">过程`increase`只需添加一个对每个元素。</span><span class="sxs-lookup"><span data-stu-id="44a1b-126">Procedure `increase` simply adds one to each element.</span></span> <span data-ttu-id="44a1b-127">过程`replace`将一个新数组分配给参数`a()`，然后添加一个用于每个元素。</span><span class="sxs-lookup"><span data-stu-id="44a1b-127">Procedure `replace` assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="44a1b-128">但是，重新分配不会影响调用代码中的基础数组变量因为`a()`声明`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="44a1b-128">However, the reassignment does not affect the underlying array variable in the calling code because `a()` is declared `ByVal`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/troubleshooting-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/troubleshooting-procedures_3.vb)]  
  
 <span data-ttu-id="44a1b-129">下面的示例调用`increase`和`replace`。</span><span class="sxs-lookup"><span data-stu-id="44a1b-129">The following example makes calls to `increase` and `replace`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/troubleshooting-procedures_4.vb)]  
  
 <span data-ttu-id="44a1b-130">第一个`MsgBox`调用显示"后 increase(n): 11、 21、 31、 41"。</span><span class="sxs-lookup"><span data-stu-id="44a1b-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="44a1b-131">因为`n`是引用类型，`increase`可以更改的成员，即使它传递`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="44a1b-131">Because `n` is a reference type, `increase` can change its members, even though it is passed `ByVal`.</span></span>  
  
 <span data-ttu-id="44a1b-132">第二个`MsgBox`调用显示"后 replace(n): 11、 21、 31、 41"。</span><span class="sxs-lookup"><span data-stu-id="44a1b-132">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="44a1b-133">因为`n`传递`ByVal`，`replace`不能修改变量`n`通过向它分配一个新数组。</span><span class="sxs-lookup"><span data-stu-id="44a1b-133">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` by assigning a new array to it.</span></span> <span data-ttu-id="44a1b-134">当`replace`创建新的数组实例`k`并将其分配到本地变量`a`，它将失去对引用`n`传递中调用代码。</span><span class="sxs-lookup"><span data-stu-id="44a1b-134">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="44a1b-135">当它递增的成员`a`，只有本地数组`k`受到影响。</span><span class="sxs-lookup"><span data-stu-id="44a1b-135">When it increments the members of `a`, only the local array `k` is affected.</span></span>  
  
 <span data-ttu-id="44a1b-136">**正确的方法：**能够修改本身的基础变量元素，它通过引用传递。</span><span class="sxs-lookup"><span data-stu-id="44a1b-136">**Correct Approach:** To be able to modify an underlying variable element itself, pass it by reference.</span></span> <span data-ttu-id="44a1b-137">下面的示例演示的声明中的更改`replace`允许它将替换中调用代码的另一个数组。</span><span class="sxs-lookup"><span data-stu-id="44a1b-137">The following example shows the change in the declaration of `replace` that allows it to replace one array with another in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#64](./codesnippet/VisualBasic/troubleshooting-procedures_5.vb)]  
  
## <a name="unable-to-define-an-overload"></a><span data-ttu-id="44a1b-138">无法定义重载</span><span class="sxs-lookup"><span data-stu-id="44a1b-138">Unable to Define an Overload</span></span>  
 <span data-ttu-id="44a1b-139">如果你想要定义一个过程的重载的版本，则必须使用相同的名称，但不同的签名。</span><span class="sxs-lookup"><span data-stu-id="44a1b-139">If you want to define an overloaded version of a procedure, you must use the same name but a different signature.</span></span> <span data-ttu-id="44a1b-140">如果编译器无法区分具有相同签名的重载将声明，它会生成错误。</span><span class="sxs-lookup"><span data-stu-id="44a1b-140">If the compiler cannot differentiate your declaration from an overload with the same signature, it generates an error.</span></span>  
  
 <span data-ttu-id="44a1b-141">*签名*的过程由过程名称和参数列表。</span><span class="sxs-lookup"><span data-stu-id="44a1b-141">The *signature* of a procedure is determined by the procedure name and the parameter list.</span></span> <span data-ttu-id="44a1b-142">每个重载必须有与所有其他重载相同的名称，但必须从中至少一个签名的其他组件的所有不同。</span><span class="sxs-lookup"><span data-stu-id="44a1b-142">Each overload must have the same name as all the other overloads but must differ from all of them in at least one of the other components of the signature.</span></span> <span data-ttu-id="44a1b-143">有关详细信息，请参阅[过程重载](./procedure-overloading.md)。</span><span class="sxs-lookup"><span data-stu-id="44a1b-143">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="44a1b-144">以下各项，即使它们涉及到参数列表中，不是签名的过程的组件：</span><span class="sxs-lookup"><span data-stu-id="44a1b-144">The following items, even though they pertain to the parameter list, are not components of a procedure's signature:</span></span>  
  
-   <span data-ttu-id="44a1b-145">过程修饰符关键字，如`Public`， `Shared`，和`Static`</span><span class="sxs-lookup"><span data-stu-id="44a1b-145">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>  
  
-   <span data-ttu-id="44a1b-146">参数名称</span><span class="sxs-lookup"><span data-stu-id="44a1b-146">Parameter names</span></span>  
  
-   <span data-ttu-id="44a1b-147">参数修饰符关键字，如`ByRef`和`Optional`</span><span class="sxs-lookup"><span data-stu-id="44a1b-147">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>  
  
-   <span data-ttu-id="44a1b-148">数据类型 （除转换运算符） 的返回值</span><span class="sxs-lookup"><span data-stu-id="44a1b-148">The data type of the return value (except for a conversion operator)</span></span>  
  
 <span data-ttu-id="44a1b-149">不能通过一个或多个前述各项仅改变重载过程。</span><span class="sxs-lookup"><span data-stu-id="44a1b-149">You cannot overload a procedure by varying only one or more of the preceding items.</span></span>  
  
 <span data-ttu-id="44a1b-150">**正确的方法：**能够定义的过程重载，您必须改变签名。</span><span class="sxs-lookup"><span data-stu-id="44a1b-150">**Correct Approach:** To be able to define a procedure overload, you must vary the signature.</span></span> <span data-ttu-id="44a1b-151">因为你必须使用相同的名称，您必须改变数量、 顺序或参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="44a1b-151">Because you must use the same name, you must vary the number, order, or data types of the parameters.</span></span> <span data-ttu-id="44a1b-152">在泛型过程中，可以使用不同类型参数的数目。</span><span class="sxs-lookup"><span data-stu-id="44a1b-152">In a generic procedure, you can vary the number of type parameters.</span></span> <span data-ttu-id="44a1b-153">在转换运算符 ([CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md))，您可以改变的返回类型。</span><span class="sxs-lookup"><span data-stu-id="44a1b-153">In a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)), you can vary the return type.</span></span>  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="44a1b-154">重载决策可选和 ParamArray 自变量</span><span class="sxs-lookup"><span data-stu-id="44a1b-154">Overload Resolution with Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="44a1b-155">如果重载具有一个或多个过程[可选](../../../../visual-basic/language-reference/modifiers/optional.md)参数或[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数，则必须避免复制任何*隐式重载*。</span><span class="sxs-lookup"><span data-stu-id="44a1b-155">If you are overloading a procedure with one or more [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameters or a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you must avoid duplicating any of the *implicit overloads*.</span></span> <span data-ttu-id="44a1b-156">有关信息，请参阅[中重载过程注意事项](./considerations-in-overloading-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="44a1b-156">For information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="calling-a-wrong-version-of-an-overloaded-procedure"></a><span data-ttu-id="44a1b-157">调用重载过程的错误版本</span><span class="sxs-lookup"><span data-stu-id="44a1b-157">Calling a Wrong Version of an Overloaded Procedure</span></span>  
 <span data-ttu-id="44a1b-158">如果过程有多个重载的版本，你应熟悉所有其参数列表，并了解如何[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]之间重载解析调用。</span><span class="sxs-lookup"><span data-stu-id="44a1b-158">If a procedure has several overloaded versions, you should be familiar with all their parameter lists and understand how [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] resolves calls among the overloads.</span></span> <span data-ttu-id="44a1b-159">否则，你可以调用预期以外的重载。</span><span class="sxs-lookup"><span data-stu-id="44a1b-159">Otherwise you could call an overload other than the intended one.</span></span>  
  
 <span data-ttu-id="44a1b-160">就能确定你想要调用的重载，请务必遵守以下规则：</span><span class="sxs-lookup"><span data-stu-id="44a1b-160">When you have determined which overload you want to call, be careful to observe the following rules:</span></span>  
  
-   <span data-ttu-id="44a1b-161">提供正确数量的自变量，并按正确的顺序。</span><span class="sxs-lookup"><span data-stu-id="44a1b-161">Supply the correct number of arguments, and in the correct order.</span></span>  
  
-   <span data-ttu-id="44a1b-162">理想情况下，你的自变量应具有作为相应的参数完全相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="44a1b-162">Ideally, your arguments should have the exact same data types as the corresponding parameters.</span></span> <span data-ttu-id="44a1b-163">在任何情况下，每个自变量的数据类型必须扩大到其对应的参数。</span><span class="sxs-lookup"><span data-stu-id="44a1b-163">In any case, the data type of each argument must widen to that of its corresponding parameter.</span></span> <span data-ttu-id="44a1b-164">这是如此[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)设置为`Off`。</span><span class="sxs-lookup"><span data-stu-id="44a1b-164">This is true even with the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) set to `Off`.</span></span> <span data-ttu-id="44a1b-165">如果某个重载需要从你的自变量列表中，重载任何收缩转换不能调用。</span><span class="sxs-lookup"><span data-stu-id="44a1b-165">If an overload requires any narrowing conversion from your argument list, that overload is not eligible to be called.</span></span>  
  
-   <span data-ttu-id="44a1b-166">如果你提供需要扩大转换的自变量，请为相应的参数数据类型尽可能接近，其数据类型。</span><span class="sxs-lookup"><span data-stu-id="44a1b-166">If you supply arguments that require widening, make their data types as close as possible to the corresponding parameter data types.</span></span> <span data-ttu-id="44a1b-167">如果两个或多个重载接受您的自变量数据类型，编译器将解析对调用进行最少量的扩大转换的重载的调用。</span><span class="sxs-lookup"><span data-stu-id="44a1b-167">If two or more overloads accept your argument data types, the compiler resolves your call to the overload that calls for the least amount of widening.</span></span>  
  
 <span data-ttu-id="44a1b-168">你可以通过使用降低的数据类型不匹配的机率[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)转换关键字做准备你的自变量时。</span><span class="sxs-lookup"><span data-stu-id="44a1b-168">You can reduce the chance of data type mismatches by using the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) conversion keyword when preparing your arguments.</span></span>  
  
### <a name="overload-resolution-failure"></a><span data-ttu-id="44a1b-169">重载决策失败</span><span class="sxs-lookup"><span data-stu-id="44a1b-169">Overload Resolution Failure</span></span>  
 <span data-ttu-id="44a1b-170">当调用重载的过程时，编译器将尝试消除所有但的重载之一。</span><span class="sxs-lookup"><span data-stu-id="44a1b-170">When you call an overloaded procedure, the compiler attempts to eliminate all but one of the overloads.</span></span> <span data-ttu-id="44a1b-171">如果成功，它会解析到该重载的调用。</span><span class="sxs-lookup"><span data-stu-id="44a1b-171">If it succeeds, it resolves the call to that overload.</span></span> <span data-ttu-id="44a1b-172">如果它消除了所有重载，或者如果它不能减少为单个候选符合条件的重载，它会生成错误。</span><span class="sxs-lookup"><span data-stu-id="44a1b-172">If it eliminates all the overloads, or if it cannot reduce the eligible overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="44a1b-173">下面的示例阐释了重载决策过程。</span><span class="sxs-lookup"><span data-stu-id="44a1b-173">The following example illustrates the overload resolution process.</span></span>  
  
 [!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/troubleshooting-procedures_6.vb)]  
  
 [!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/troubleshooting-procedures_7.vb)]  
  
 <span data-ttu-id="44a1b-174">在第一个调用中，编译器消除第一个重载，因为第一个参数的类型 (`Short`) 收缩到相应的参数的类型 (`Byte`)。</span><span class="sxs-lookup"><span data-stu-id="44a1b-174">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="44a1b-175">因为每个自变量类型中的第二个重载，它会然后消除第三个重载 (`Short`和`Single`) 扩大到第三个重载中的对应类型 (`Integer`和`Single`)。</span><span class="sxs-lookup"><span data-stu-id="44a1b-175">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="44a1b-176">第二个重载都需要较少扩大转换，因此编译器将使用它的调用。</span><span class="sxs-lookup"><span data-stu-id="44a1b-176">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="44a1b-177">在第二个调用中，编译器不能消除任何基于收缩的重载。</span><span class="sxs-lookup"><span data-stu-id="44a1b-177">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="44a1b-178">因为它可以调用使用最少扩大量自变量类型的第二个重载，它会出于同一原因如下所示的第一个调用，消除第三个重载。</span><span class="sxs-lookup"><span data-stu-id="44a1b-178">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="44a1b-179">但是，编译器无法解析的第一个和第二个重载之间。</span><span class="sxs-lookup"><span data-stu-id="44a1b-179">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="44a1b-180">每个具有一个已定义的参数类型扩大到另一部分中的相应类型 (`Byte`到`Short`，但`Single`到`Double`)。</span><span class="sxs-lookup"><span data-stu-id="44a1b-180">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="44a1b-181">因此，编译器将生成重载解析错误。</span><span class="sxs-lookup"><span data-stu-id="44a1b-181">The compiler therefore generates an overload resolution error.</span></span>  
  
 <span data-ttu-id="44a1b-182">**正确的方法：**能够调用清楚无误地重载的过程，使用[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)以匹配的参数类型的参数数据类型。</span><span class="sxs-lookup"><span data-stu-id="44a1b-182">**Correct Approach:** To be able to call an overloaded procedure without ambiguity, use [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to match the argument data types to the parameter types.</span></span> <span data-ttu-id="44a1b-183">下面的示例演示调用`z`对第二个重载强制解析。</span><span class="sxs-lookup"><span data-stu-id="44a1b-183">The following example shows a call to `z` that forces resolution to the second overload.</span></span>  
  
 [!code-vb[VbVbcnProcedures#65](./codesnippet/VisualBasic/troubleshooting-procedures_8.vb)]  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="44a1b-184">重载决策可选和 ParamArray 自变量</span><span class="sxs-lookup"><span data-stu-id="44a1b-184">Overload Resolution with Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="44a1b-185">如果过程的两个重载具有完全相同的签名，只不过声明的最后一个参数[可选](../../../../visual-basic/language-reference/modifiers/optional.md)之一中和[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)中另一个，则编译器将解析对该过程的调用根据最接近的匹配。</span><span class="sxs-lookup"><span data-stu-id="44a1b-185">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure according to the closest match.</span></span> <span data-ttu-id="44a1b-186">有关详细信息，请参阅[重载解析](./overload-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="44a1b-186">For more information, see [Overload Resolution](./overload-resolution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44a1b-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44a1b-187">See Also</span></span>  
 [<span data-ttu-id="44a1b-188">过程</span><span class="sxs-lookup"><span data-stu-id="44a1b-188">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="44a1b-189">Sub 过程</span><span class="sxs-lookup"><span data-stu-id="44a1b-189">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="44a1b-190">Function 过程</span><span class="sxs-lookup"><span data-stu-id="44a1b-190">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="44a1b-191">属性过程</span><span class="sxs-lookup"><span data-stu-id="44a1b-191">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="44a1b-192">运算符过程</span><span class="sxs-lookup"><span data-stu-id="44a1b-192">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="44a1b-193">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="44a1b-193">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="44a1b-194">过程重载</span><span class="sxs-lookup"><span data-stu-id="44a1b-194">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="44a1b-195">重载过程注意事项</span><span class="sxs-lookup"><span data-stu-id="44a1b-195">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="44a1b-196">重载决策</span><span class="sxs-lookup"><span data-stu-id="44a1b-196">Overload Resolution</span></span>](./overload-resolution.md)

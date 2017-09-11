---
title: "故障排除过程 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures, troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures, about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
caps.latest.revision: 17
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
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a16a03aa8c12e6696f80eeddb96f4f90c3bb7c68
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="troubleshooting-procedures-visual-basic"></a><span data-ttu-id="ff918-102">过程疑难解答 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff918-102">Troubleshooting Procedures (Visual Basic)</span></span>
<span data-ttu-id="ff918-103">此页列出在使用过程时可能发生的一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="ff918-103">This page lists some common problems that can occur when working with procedures.</span></span>  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a><span data-ttu-id="ff918-104">从函数过程返回的数组类型</span><span class="sxs-lookup"><span data-stu-id="ff918-104">Returning an Array Type from a Function Procedure</span></span>  
 <span data-ttu-id="ff918-105">如果`Function`过程返回数组数据类型，则无法使用`Function`要将值存储在数组的元素名称。</span><span class="sxs-lookup"><span data-stu-id="ff918-105">If a `Function` procedure returns an array data type, you cannot use the `Function` name to store values in the elements of the array.</span></span> <span data-ttu-id="ff918-106">如果尝试这样做，编译器会将其解释为对的调用`Function`。</span><span class="sxs-lookup"><span data-stu-id="ff918-106">If you attempt to do this, the compiler interprets it as a call to the `Function`.</span></span> <span data-ttu-id="ff918-107">下面的示例将生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="ff918-107">The following example generates compiler errors.</span></span>  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 <span data-ttu-id="ff918-108">`' The following statement generates a`   `COMPILER ERROR`  `.`</span><span class="sxs-lookup"><span data-stu-id="ff918-108">`' The following statement generates a`   `COMPILER ERROR`  `.`</span></span>  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 <span data-ttu-id="ff918-109">`' The following statement generates a`   `COMPILER ERROR`  `.`</span><span class="sxs-lookup"><span data-stu-id="ff918-109">`' The following statement generates a`   `COMPILER ERROR`  `.`</span></span>  
  
 `Return allOnes()`  
  
 `End Function`  
  
 <span data-ttu-id="ff918-110">该语句`allOnes(i) = 1`生成编译器错误，因为它看起来在调用`allOnes`用错误的数据类型的参数 (单一实例`Integer`而不是`Integer`数组)。</span><span class="sxs-lookup"><span data-stu-id="ff918-110">The statement `allOnes(i) = 1` generates a compiler error because it appears to call `allOnes` with an argument of the wrong data type (a singleton `Integer` instead of an `Integer` array).</span></span> <span data-ttu-id="ff918-111">该语句`Return allOnes()`生成编译器错误，因为它看起来在调用`allOnes`不带参数。</span><span class="sxs-lookup"><span data-stu-id="ff918-111">The statement `Return allOnes()` generates a compiler error because it appears to call `allOnes` with no argument.</span></span>  
  
 <span data-ttu-id="ff918-112">**正确的方法︰**能够修改将返回一个数组的元素，定义一个内部数组中，为本地变量。</span><span class="sxs-lookup"><span data-stu-id="ff918-112">**Correct Approach:** To be able to modify the elements of an array that is to be returned, define an internal array as a local variable.</span></span> <span data-ttu-id="ff918-113">下面的示例编译而不出错。</span><span class="sxs-lookup"><span data-stu-id="ff918-113">The following example compiles without error.</span></span>  
  
 <span data-ttu-id="ff918-114">[!code-vb[VbVbcnProcedures #&66;](./codesnippet/VisualBasic/troubleshooting-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ff918-114">[!code-vb[VbVbcnProcedures#66](./codesnippet/VisualBasic/troubleshooting-procedures_1.vb)]</span></span>  
  
## <a name="argument-not-being-modified-by-procedure-call"></a><span data-ttu-id="ff918-115">未修改的参数由过程调用</span><span class="sxs-lookup"><span data-stu-id="ff918-115">Argument Not Being Modified by Procedure Call</span></span>  
 <span data-ttu-id="ff918-116">如果您想要允许更改基础调用代码中的参数的编程元素的过程，必须通过引用传递。</span><span class="sxs-lookup"><span data-stu-id="ff918-116">If you intend to allow a procedure to change a programming element underlying an argument in the calling code, you must pass it by reference.</span></span> <span data-ttu-id="ff918-117">但是，即使按值传递过程仍可访问的元素的引用类型参数。</span><span class="sxs-lookup"><span data-stu-id="ff918-117">But a procedure can access the elements of a reference type argument even if you pass it by value.</span></span>  
  
-   <span data-ttu-id="ff918-118">**基础变量**。</span><span class="sxs-lookup"><span data-stu-id="ff918-118">**Underlying Variable**.</span></span> <span data-ttu-id="ff918-119">若要允许替换基础的变量元素本身的值的过程，该过程必须声明该参数[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)。</span><span class="sxs-lookup"><span data-stu-id="ff918-119">To allow the procedure to replace the value of the underlying variable element itself, the procedure must declare the parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="ff918-120">此外，调用代码必须不在括号内，则实参，因为这样将重写`ByRef`传递机制。</span><span class="sxs-lookup"><span data-stu-id="ff918-120">Also, the calling code must not enclose the argument in parentheses, because that would override the `ByRef` passing mechanism.</span></span>  
  
-   <span data-ttu-id="ff918-121">**引用类型的元素**。</span><span class="sxs-lookup"><span data-stu-id="ff918-121">**Reference Type Elements**.</span></span> <span data-ttu-id="ff918-122">如果将参数声明[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)，该过程不能修改基础的变量元素本身。</span><span class="sxs-lookup"><span data-stu-id="ff918-122">If you declare a parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md), the procedure cannot modify the underlying variable element itself.</span></span> <span data-ttu-id="ff918-123">但是，如果参数为引用类型，该过程可以修改它指向的该对象的成员，即使它不能替换变量的值一样。</span><span class="sxs-lookup"><span data-stu-id="ff918-123">However, if the argument is a reference type, the procedure can modify the members of the object to which it points, even though it cannot replace the variable's value.</span></span> <span data-ttu-id="ff918-124">例如，如果参数是一个数组变量，该过程不能将一个新数组分配给它，但它可以更改一个或多个元素。</span><span class="sxs-lookup"><span data-stu-id="ff918-124">For example, if the argument is an array variable, the procedure cannot assign a new array to it, but it can change one or more of its elements.</span></span> <span data-ttu-id="ff918-125">更改的元素将反映在调用代码中的基础数组变量。</span><span class="sxs-lookup"><span data-stu-id="ff918-125">The changed elements are reflected in the underlying array variable in the calling code.</span></span>  
  
 <span data-ttu-id="ff918-126">下面的示例定义两个过程，获得数组变量通过值和操作对其元素。</span><span class="sxs-lookup"><span data-stu-id="ff918-126">The following example defines two procedures that take an array variable by value and operate on its elements.</span></span> <span data-ttu-id="ff918-127">过程`increase`只需添加一个对每个元素。</span><span class="sxs-lookup"><span data-stu-id="ff918-127">Procedure `increase` simply adds one to each element.</span></span> <span data-ttu-id="ff918-128">过程`replace`将一个新数组分配给该参数`a()`，然后添加一个对每个元素。</span><span class="sxs-lookup"><span data-stu-id="ff918-128">Procedure `replace` assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="ff918-129">但是，重新分配不影响调用代码中的基础数组变量因为`a()`声明`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="ff918-129">However, the reassignment does not affect the underlying array variable in the calling code because `a()` is declared `ByVal`.</span></span>  
  
 <span data-ttu-id="ff918-130">[!code-vb[VbVbcnProcedures #&35;](./codesnippet/VisualBasic/troubleshooting-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ff918-130">[!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/troubleshooting-procedures_2.vb)]</span></span>  
  
 <span data-ttu-id="ff918-131">[!code-vb[VbVbcnProcedures #&38;](./codesnippet/VisualBasic/troubleshooting-procedures_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="ff918-131">[!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/troubleshooting-procedures_3.vb)]</span></span>  
  
 <span data-ttu-id="ff918-132">以下示例将对调用`increase`和`replace`。</span><span class="sxs-lookup"><span data-stu-id="ff918-132">The following example makes calls to `increase` and `replace`.</span></span>  
  
 <span data-ttu-id="ff918-133">[!code-vb[VbVbcnProcedures #&37;](./codesnippet/VisualBasic/troubleshooting-procedures_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="ff918-133">[!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/troubleshooting-procedures_4.vb)]</span></span>  
  
 <span data-ttu-id="ff918-134">第一个`MsgBox`调用显示"之后 increase(n): 11、 21、 31、 41"。</span><span class="sxs-lookup"><span data-stu-id="ff918-134">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="ff918-135">因为`n`是引用类型，`increase`可以更改其中一个成员，即使它传递`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="ff918-135">Because `n` is a reference type, `increase` can change its members, even though it is passed `ByVal`.</span></span>  
  
 <span data-ttu-id="ff918-136">第二个`MsgBox`调用显示"之后 replace(n): 11、 21、 31、 41"。</span><span class="sxs-lookup"><span data-stu-id="ff918-136">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="ff918-137">因为`n`传递`ByVal`，`replace`不能修改该变量`n`通过向它分配一个新数组。</span><span class="sxs-lookup"><span data-stu-id="ff918-137">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` by assigning a new array to it.</span></span> <span data-ttu-id="ff918-138">当`replace`创建新的数组实例`k`并将其分配给本地变量`a`，它将失去对引用`n`由调用代码传入的。</span><span class="sxs-lookup"><span data-stu-id="ff918-138">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="ff918-139">当它递增的成员`a`，只有本地数组`k`受到影响。</span><span class="sxs-lookup"><span data-stu-id="ff918-139">When it increments the members of `a`, only the local array `k` is affected.</span></span>  
  
 <span data-ttu-id="ff918-140">**正确的方法︰**能够修改基础的变量元素本身，通过引用传递。</span><span class="sxs-lookup"><span data-stu-id="ff918-140">**Correct Approach:** To be able to modify an underlying variable element itself, pass it by reference.</span></span> <span data-ttu-id="ff918-141">下面的示例的声明中显示的更改`replace`允许它将替换为调用的代码中的另一个数组。</span><span class="sxs-lookup"><span data-stu-id="ff918-141">The following example shows the change in the declaration of `replace` that allows it to replace one array with another in the calling code.</span></span>  
  
 <span data-ttu-id="ff918-142">[!code-vb[VbVbcnProcedures #&64;](./codesnippet/VisualBasic/troubleshooting-procedures_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="ff918-142">[!code-vb[VbVbcnProcedures#64](./codesnippet/VisualBasic/troubleshooting-procedures_5.vb)]</span></span>  
  
## <a name="unable-to-define-an-overload"></a><span data-ttu-id="ff918-143">无法定义重载方法</span><span class="sxs-lookup"><span data-stu-id="ff918-143">Unable to Define an Overload</span></span>  
 <span data-ttu-id="ff918-144">如果你想要定义一个过程的重载的版本，则必须使用相同的名称但不同的签名。</span><span class="sxs-lookup"><span data-stu-id="ff918-144">If you want to define an overloaded version of a procedure, you must use the same name but a different signature.</span></span> <span data-ttu-id="ff918-145">如果编译器无法区分具有相同签名的重载将声明，它会生成错误。</span><span class="sxs-lookup"><span data-stu-id="ff918-145">If the compiler cannot differentiate your declaration from an overload with the same signature, it generates an error.</span></span>  
  
 <span data-ttu-id="ff918-146">*签名*的过程由过程名称和参数列表。</span><span class="sxs-lookup"><span data-stu-id="ff918-146">The *signature* of a procedure is determined by the procedure name and the parameter list.</span></span> <span data-ttu-id="ff918-147">每个重载必须具有与所有其他重载相同的名称，但必须不同于所有人中至少一个签名的其他组件。</span><span class="sxs-lookup"><span data-stu-id="ff918-147">Each overload must have the same name as all the other overloads but must differ from all of them in at least one of the other components of the signature.</span></span> <span data-ttu-id="ff918-148">有关详细信息，请参阅[过程重载](./procedure-overloading.md)。</span><span class="sxs-lookup"><span data-stu-id="ff918-148">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="ff918-149">以下各项，即使它们与参数列表中，不是过程签名的组件︰</span><span class="sxs-lookup"><span data-stu-id="ff918-149">The following items, even though they pertain to the parameter list, are not components of a procedure's signature:</span></span>  
  
-   <span data-ttu-id="ff918-150">过程修饰符关键字，如`Public`， `Shared`，和`Static`</span><span class="sxs-lookup"><span data-stu-id="ff918-150">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>  
  
-   <span data-ttu-id="ff918-151">参数名称</span><span class="sxs-lookup"><span data-stu-id="ff918-151">Parameter names</span></span>  
  
-   <span data-ttu-id="ff918-152">参数修饰符关键字，如`ByRef`和`Optional`</span><span class="sxs-lookup"><span data-stu-id="ff918-152">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>  
  
-   <span data-ttu-id="ff918-153">返回值 （转换运算符除外） 的数据类型</span><span class="sxs-lookup"><span data-stu-id="ff918-153">The data type of the return value (except for a conversion operator)</span></span>  
  
 <span data-ttu-id="ff918-154">不能通过一个或多个上述各项只改变重载的过程。</span><span class="sxs-lookup"><span data-stu-id="ff918-154">You cannot overload a procedure by varying only one or more of the preceding items.</span></span>  
  
 <span data-ttu-id="ff918-155">**正确的方法︰**能够定义过程重载，您必须改变签名。</span><span class="sxs-lookup"><span data-stu-id="ff918-155">**Correct Approach:** To be able to define a procedure overload, you must vary the signature.</span></span> <span data-ttu-id="ff918-156">因为您必须使用相同的名称，您必须改变数量、 顺序或参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ff918-156">Because you must use the same name, you must vary the number, order, or data types of the parameters.</span></span> <span data-ttu-id="ff918-157">在一般的过程中，您可以更改类型参数的数目。</span><span class="sxs-lookup"><span data-stu-id="ff918-157">In a generic procedure, you can vary the number of type parameters.</span></span> <span data-ttu-id="ff918-158">在转换运算符 ([CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md))，可以指定不同的返回类型。</span><span class="sxs-lookup"><span data-stu-id="ff918-158">In a conversion operator ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)), you can vary the return type.</span></span>  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="ff918-159">重载带有可选的分辨率和 ParamArray 参数</span><span class="sxs-lookup"><span data-stu-id="ff918-159">Overload Resolution with Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="ff918-160">如果重载具有一个或多个过程[可选](../../../../visual-basic/language-reference/modifiers/optional.md)参数或[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)参数，则必须避免复制任何*隐式重载*。</span><span class="sxs-lookup"><span data-stu-id="ff918-160">If you are overloading a procedure with one or more [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameters or a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you must avoid duplicating any of the *implicit overloads*.</span></span> <span data-ttu-id="ff918-161">有关信息，请参阅[中重载过程注意事项](./considerations-in-overloading-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="ff918-161">For information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="calling-a-wrong-version-of-an-overloaded-procedure"></a><span data-ttu-id="ff918-162">调用重载过程的不正确版本</span><span class="sxs-lookup"><span data-stu-id="ff918-162">Calling a Wrong Version of an Overloaded Procedure</span></span>  
 <span data-ttu-id="ff918-163">如果过程具有多个重载的版本，你应该熟悉它们的参数列表并了解如何[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]之间重载解析调用。</span><span class="sxs-lookup"><span data-stu-id="ff918-163">If a procedure has several overloaded versions, you should be familiar with all their parameter lists and understand how [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] resolves calls among the overloads.</span></span> <span data-ttu-id="ff918-164">否则，您可以调用非预期的重载。</span><span class="sxs-lookup"><span data-stu-id="ff918-164">Otherwise you could call an overload other than the intended one.</span></span>  
  
 <span data-ttu-id="ff918-165">当你已确定你想要调用的重载时，小心地将其遵守以下规则︰</span><span class="sxs-lookup"><span data-stu-id="ff918-165">When you have determined which overload you want to call, be careful to observe the following rules:</span></span>  
  
-   <span data-ttu-id="ff918-166">提供正确数量的参数，并以正确的顺序。</span><span class="sxs-lookup"><span data-stu-id="ff918-166">Supply the correct number of arguments, and in the correct order.</span></span>  
  
-   <span data-ttu-id="ff918-167">理想情况下，您的参数应具有与对应的参数完全相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ff918-167">Ideally, your arguments should have the exact same data types as the corresponding parameters.</span></span> <span data-ttu-id="ff918-168">在任何情况下，每个参数的数据类型必须扩大到其对应的参数。</span><span class="sxs-lookup"><span data-stu-id="ff918-168">In any case, the data type of each argument must widen to that of its corresponding parameter.</span></span> <span data-ttu-id="ff918-169">这甚至对于一点[Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)设置为`Off`。</span><span class="sxs-lookup"><span data-stu-id="ff918-169">This is true even with the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) set to `Off`.</span></span> <span data-ttu-id="ff918-170">如果某个重载需要从参数列表中，该重载的任何收缩转换是不能调用。</span><span class="sxs-lookup"><span data-stu-id="ff918-170">If an overload requires any narrowing conversion from your argument list, that overload is not eligible to be called.</span></span>  
  
-   <span data-ttu-id="ff918-171">如果您提供需要扩大的参数，使它们尽可能接近，到对应的参数数据类型的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ff918-171">If you supply arguments that require widening, make their data types as close as possible to the corresponding parameter data types.</span></span> <span data-ttu-id="ff918-172">如果两个或多个重载接受您的参数数据类型，则编译器将解析对最少量的扩大转换为调用的重载的调用。</span><span class="sxs-lookup"><span data-stu-id="ff918-172">If two or more overloads accept your argument data types, the compiler resolves your call to the overload that calls for the least amount of widening.</span></span>  
  
 <span data-ttu-id="ff918-173">可以通过使用降低的数据类型不匹配的机率[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)转换关键字准备参数时。</span><span class="sxs-lookup"><span data-stu-id="ff918-173">You can reduce the chance of data type mismatches by using the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) conversion keyword when preparing your arguments.</span></span>  
  
### <a name="overload-resolution-failure"></a><span data-ttu-id="ff918-174">重载解析失败</span><span class="sxs-lookup"><span data-stu-id="ff918-174">Overload Resolution Failure</span></span>  
 <span data-ttu-id="ff918-175">当调用重载的过程时，编译器会尝试消除所有但的重载之一。</span><span class="sxs-lookup"><span data-stu-id="ff918-175">When you call an overloaded procedure, the compiler attempts to eliminate all but one of the overloads.</span></span> <span data-ttu-id="ff918-176">如果成功，它可消除对该重载的调用。</span><span class="sxs-lookup"><span data-stu-id="ff918-176">If it succeeds, it resolves the call to that overload.</span></span> <span data-ttu-id="ff918-177">如果它消除了所有重载，或者如果它不能减少为单个候选资格的重载，它将产生错误。</span><span class="sxs-lookup"><span data-stu-id="ff918-177">If it eliminates all the overloads, or if it cannot reduce the eligible overloads to a single candidate, it generates an error.</span></span>  
  
 <span data-ttu-id="ff918-178">下面的示例阐释了重载决策过程。</span><span class="sxs-lookup"><span data-stu-id="ff918-178">The following example illustrates the overload resolution process.</span></span>  
  
 <span data-ttu-id="ff918-179">[!code-vb[VbVbcnProcedures #&62;](./codesnippet/VisualBasic/troubleshooting-procedures_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="ff918-179">[!code-vb[VbVbcnProcedures#62](./codesnippet/VisualBasic/troubleshooting-procedures_6.vb)]</span></span>  
  
 <span data-ttu-id="ff918-180">[!code-vb[VbVbcnProcedures #&63;](./codesnippet/VisualBasic/troubleshooting-procedures_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="ff918-180">[!code-vb[VbVbcnProcedures#63](./codesnippet/VisualBasic/troubleshooting-procedures_7.vb)]</span></span>  
  
 <span data-ttu-id="ff918-181">在第一个调用中，编译器消除第一个重载，因为第一个参数的类型 (`Short`) 缩小到相应的参数的类型 (`Byte`)。</span><span class="sxs-lookup"><span data-stu-id="ff918-181">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="ff918-182">它然后能消除第三个重载，因为每个参数类型中的第二个重载 (`Short`和`Single`) 加宽到第三个重载中的相应类型 (`Integer`和`Single`)。</span><span class="sxs-lookup"><span data-stu-id="ff918-182">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="ff918-183">第二个重载需要扩大量较少，因此编译器将用它的调用。</span><span class="sxs-lookup"><span data-stu-id="ff918-183">The second overload requires less widening, so the compiler uses it for the call.</span></span>  
  
 <span data-ttu-id="ff918-184">在第二个调用中，编译器不能消除任何根据收缩重载。</span><span class="sxs-lookup"><span data-stu-id="ff918-184">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="ff918-185">因为它可以调用带参数类型的最少扩大的第二个重载，它会出于同样的原因如下所示的第一个调用，消除第三个重载。</span><span class="sxs-lookup"><span data-stu-id="ff918-185">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="ff918-186">但是，编译器无法解析的第一个和第二个重载之间。</span><span class="sxs-lookup"><span data-stu-id="ff918-186">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="ff918-187">每个已扩大为中其他的相应类型的一种已定义的参数类型 (`Byte`到`Short`，但`Single`到`Double`)。</span><span class="sxs-lookup"><span data-stu-id="ff918-187">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="ff918-188">因此，编译器会生成重载解析错误。</span><span class="sxs-lookup"><span data-stu-id="ff918-188">The compiler therefore generates an overload resolution error.</span></span>  
  
 <span data-ttu-id="ff918-189">**正确的方法︰**若要能够调用重载的过程不二义性的情况下，使用[CType 函数](../../../../visual-basic/language-reference/functions/ctype-function.md)以匹配为形参类型的参数数据类型。</span><span class="sxs-lookup"><span data-stu-id="ff918-189">**Correct Approach:** To be able to call an overloaded procedure without ambiguity, use [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to match the argument data types to the parameter types.</span></span> <span data-ttu-id="ff918-190">下面的示例演示如何调用`z`强制解析到的第二个重载。</span><span class="sxs-lookup"><span data-stu-id="ff918-190">The following example shows a call to `z` that forces resolution to the second overload.</span></span>  
  
 <span data-ttu-id="ff918-191">[!code-vb[VbVbcnProcedures #&65;](./codesnippet/VisualBasic/troubleshooting-procedures_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="ff918-191">[!code-vb[VbVbcnProcedures#65](./codesnippet/VisualBasic/troubleshooting-procedures_8.vb)]</span></span>  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="ff918-192">重载带有可选的分辨率和 ParamArray 参数</span><span class="sxs-lookup"><span data-stu-id="ff918-192">Overload Resolution with Optional and ParamArray Arguments</span></span>  
 <span data-ttu-id="ff918-193">如果某个过程的两个重载具有相同的签名只是声明的最后一个参数[可选](../../../../visual-basic/language-reference/modifiers/optional.md)合一和[ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)中另一个，则编译器将解析对根据最接近的匹配该过程的调用。</span><span class="sxs-lookup"><span data-stu-id="ff918-193">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) in one and [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure according to the closest match.</span></span> <span data-ttu-id="ff918-194">有关详细信息，请参阅[重载解析](./overload-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="ff918-194">For more information, see [Overload Resolution](./overload-resolution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff918-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff918-195">See Also</span></span>  
 <span data-ttu-id="ff918-196">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="ff918-196">[Procedures](./index.md) </span></span>  
<span data-ttu-id="ff918-197"> [Sub 过程](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="ff918-197"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="ff918-198"> [Function 过程](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="ff918-198"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="ff918-199"> [属性过程](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="ff918-199"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="ff918-200"> [运算符过程](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="ff918-200"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="ff918-201"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="ff918-201"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="ff918-202"> [过程重载](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="ff918-202"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="ff918-203"> [重载过程注意事项](./considerations-in-overloading-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="ff918-203"> [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md) </span></span>  
<span data-ttu-id="ff918-204"> [重载决策](./overload-resolution.md)</span><span class="sxs-lookup"><span data-stu-id="ff918-204"> [Overload Resolution](./overload-resolution.md)</span></span>

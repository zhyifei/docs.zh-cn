---
title: "Option Strict 语句 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Strict
- vb.OptionStrict
dev_langs:
- VB
helpviewer_keywords:
- Strict keyword
- Option Strict statement
- conversions, implicit
- late binding
- implicit conversions
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
caps.latest.revision: 49
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
ms.openlocfilehash: 055565082757318334e89410d12ed7067e5814cb
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="option-strict-statement"></a><span data-ttu-id="f3421-102">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="f3421-102">Option Strict Statement</span></span>
<span data-ttu-id="f3421-103">隐式数据类型将转换限制为只能扩大转换，不允许后期绑定，并禁止隐式类型化会导致`Object`类型。</span><span class="sxs-lookup"><span data-stu-id="f3421-103">Restricts implicit data type conversions to only widening conversions, disallows late binding, and disallows implicit typing that results in an `Object` type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3421-104">语法</span><span class="sxs-lookup"><span data-stu-id="f3421-104">Syntax</span></span>  
  
```  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="f3421-105">部件</span><span class="sxs-lookup"><span data-stu-id="f3421-105">Parts</span></span>  
  
|<span data-ttu-id="f3421-106">术语</span><span class="sxs-lookup"><span data-stu-id="f3421-106">Term</span></span>|<span data-ttu-id="f3421-107">定义</span><span class="sxs-lookup"><span data-stu-id="f3421-107">Definition</span></span>|  
|---|---|  
|`On`|<span data-ttu-id="f3421-108">可选。</span><span class="sxs-lookup"><span data-stu-id="f3421-108">Optional.</span></span> <span data-ttu-id="f3421-109">使`Option Strict`检查。</span><span class="sxs-lookup"><span data-stu-id="f3421-109">Enables `Option Strict` checking.</span></span>|  
|`Off`|<span data-ttu-id="f3421-110">可选。</span><span class="sxs-lookup"><span data-stu-id="f3421-110">Optional.</span></span> <span data-ttu-id="f3421-111">禁用`Option Strict`检查。</span><span class="sxs-lookup"><span data-stu-id="f3421-111">Disables `Option Strict` checking.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3421-112">备注</span><span class="sxs-lookup"><span data-stu-id="f3421-112">Remarks</span></span>  
 <span data-ttu-id="f3421-113">当`Option Strict On`或`Option Strict`出现在文件中，以下情况会导致编译时错误︰</span><span class="sxs-lookup"><span data-stu-id="f3421-113">When `Option Strict On` or `Option Strict` appears in a file, the following conditions cause a compile-time error:</span></span>  
  
-   <span data-ttu-id="f3421-114">隐式收缩转换</span><span class="sxs-lookup"><span data-stu-id="f3421-114">Implicit narrowing conversions</span></span>  
  
-   <span data-ttu-id="f3421-115">后期绑定</span><span class="sxs-lookup"><span data-stu-id="f3421-115">Late binding</span></span>  
  
-   <span data-ttu-id="f3421-116">隐式类型化会导致`Object`类型</span><span class="sxs-lookup"><span data-stu-id="f3421-116">Implicit typing that results in an `Object` type</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3421-117">您可以对设置的警告配置[编译页，项目设计器 (Visual Basic 中)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)，有三个设置对应的三个条件会导致编译时错误。</span><span class="sxs-lookup"><span data-stu-id="f3421-117">In the warning configurations that you can set on the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic), there are three settings that correspond to the three conditions that cause a compile-time error.</span></span> <span data-ttu-id="f3421-118">有关如何使用这些设置的信息，请参阅[在 IDE 中设置警告配置](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions)本主题中更高版本。</span><span class="sxs-lookup"><span data-stu-id="f3421-118">For information about how to use these settings, see [To set warning configurations in the IDE](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) later in this topic.</span></span>  
  
 <span data-ttu-id="f3421-119">`Option Strict Off`语句关闭错误和警告检查对于所有三个条件，即使相关联的 IDE 设置指定要打开这些错误或警告。</span><span class="sxs-lookup"><span data-stu-id="f3421-119">The `Option Strict Off` statement turns off error and warning checking for all three conditions, even if the associated IDE settings specify to turn on these errors or warnings.</span></span> <span data-ttu-id="f3421-120">`Option Strict On`语句启用错误和警告检查对于所有三个条件，即使相关联的 IDE 设置指定将关闭这些错误或警告。</span><span class="sxs-lookup"><span data-stu-id="f3421-120">The `Option Strict On` statement turns on error and warning checking for all three conditions, even if the associated IDE settings specify to turn off these errors or warnings.</span></span>  
  
 <span data-ttu-id="f3421-121">如果使用，`Option Strict`语句必须出现在文件中的任何其他源代码语句之前。</span><span class="sxs-lookup"><span data-stu-id="f3421-121">If used, the `Option Strict` statement must appear before any other code statements in a file.</span></span>  
  
 <span data-ttu-id="f3421-122">当您将设置`Option Strict`到`On`，Visual Basic 检查，指定所有编程元素的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f3421-122">When you set `Option Strict` to `On`, Visual Basic checks that data types are specified for all programming elements.</span></span> <span data-ttu-id="f3421-123">可以显式指定，或通过使用局部类型推理指定数据类型。</span><span class="sxs-lookup"><span data-stu-id="f3421-123">Data types can be specified explicitly, or specified by using local type inference.</span></span> <span data-ttu-id="f3421-124">建议为所有编程元素指定数据类型，原因如下︰</span><span class="sxs-lookup"><span data-stu-id="f3421-124">Specifying data types for all your programming elements is recommended, for the following reasons:</span></span>  
  
-   <span data-ttu-id="f3421-125">它使您的变量和参数的 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="f3421-125">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="f3421-126">这使您以您键入代码时查看其属性和其他成员。</span><span class="sxs-lookup"><span data-stu-id="f3421-126">This enables you to see their properties and other members as you type code.</span></span>  
  
-   <span data-ttu-id="f3421-127">它使编译器能够执行类型检查。</span><span class="sxs-lookup"><span data-stu-id="f3421-127">It enables the compiler to perform type checking.</span></span> <span data-ttu-id="f3421-128">类型检查可以帮助您找到在运行时由于类型转换错误而失败的语句。</span><span class="sxs-lookup"><span data-stu-id="f3421-128">Type checking helps you find statements that can fail at run time because of type conversion errors.</span></span> <span data-ttu-id="f3421-129">它还标识对不支持这些方法的对象上的方法的调用。</span><span class="sxs-lookup"><span data-stu-id="f3421-129">It also identifies calls to methods on objects that do not support those methods.</span></span>  
  
-   <span data-ttu-id="f3421-130">它可以提高代码的执行。</span><span class="sxs-lookup"><span data-stu-id="f3421-130">It speeds up the execution of code.</span></span> <span data-ttu-id="f3421-131">一个原因是，如果未指定的编程元素的数据类型，Visual Basic 编译器将其分配`Object`类型。</span><span class="sxs-lookup"><span data-stu-id="f3421-131">One reason for this is that if you do not specify a data type for a programming element, the Visual Basic compiler assigns it the `Object` type.</span></span> <span data-ttu-id="f3421-132">已编译的代码可能需要将之间来回转换`Object`和其他数据类型，这会降低性能。</span><span class="sxs-lookup"><span data-stu-id="f3421-132">Compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="implicit-narrowing-conversion-errors"></a><span data-ttu-id="f3421-133">隐式收缩转换错误</span><span class="sxs-lookup"><span data-stu-id="f3421-133">Implicit Narrowing Conversion Errors</span></span>  
 <span data-ttu-id="f3421-134">是收缩转换的隐式数据类型转换时，将发生隐式收缩转换错误。</span><span class="sxs-lookup"><span data-stu-id="f3421-134">Implicit narrowing conversion errors occur when there is an implicit data type conversion that is a narrowing conversion.</span></span>  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="f3421-135">可以将许多数据类型转换为其他数据类型。</span><span class="sxs-lookup"><span data-stu-id="f3421-135"> can convert many data types to other data types.</span></span> <span data-ttu-id="f3421-136">一种数据类型的值转换为精度较低或容量较小的数据类型时，会发生数据丢失。</span><span class="sxs-lookup"><span data-stu-id="f3421-136">Data loss can occur when the value of one data type is converted to a data type that has less precision or a smaller capacity.</span></span> <span data-ttu-id="f3421-137">如果这种收缩转换失败，则会发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="f3421-137">A run-time error occurs if such a narrowing conversion fails.</span></span> <span data-ttu-id="f3421-138">`Option Strict`这样可以避免它们，请确保这些收缩转换提供编译时通知。</span><span class="sxs-lookup"><span data-stu-id="f3421-138">`Option Strict` ensures compile-time notification of these narrowing conversions so that you can avoid them.</span></span> <span data-ttu-id="f3421-139">有关详细信息，请参阅[隐式和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)和[扩大和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="f3421-139">For more information, see [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) and [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
 <span data-ttu-id="f3421-140">可能会导致错误的转换包括在表达式中发生的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="f3421-140">Conversions that can cause errors include implicit conversions that occur in expressions.</span></span> <span data-ttu-id="f3421-141">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="f3421-141">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="f3421-142">+ 运算符</span><span class="sxs-lookup"><span data-stu-id="f3421-142">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [<span data-ttu-id="f3421-143">+= 运算符</span><span class="sxs-lookup"><span data-stu-id="f3421-143">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [<span data-ttu-id="f3421-144">\ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3421-144">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [<span data-ttu-id="f3421-145">/ = 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3421-145">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [<span data-ttu-id="f3421-146">Char 数据类型</span><span class="sxs-lookup"><span data-stu-id="f3421-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 <span data-ttu-id="f3421-147">通过使用连接字符串时[& 运算符](../../../visual-basic/language-reference/operators/concatenation-operator.md)，为字符串的所有转换被都认为是会扩大。</span><span class="sxs-lookup"><span data-stu-id="f3421-147">When you concatenate strings by using the [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md), all conversions to the strings are considered to be widening.</span></span> <span data-ttu-id="f3421-148">因此这些转换不会生成隐式收缩转换错误，即使`Option Strict`上。</span><span class="sxs-lookup"><span data-stu-id="f3421-148">So these conversions do not generate an implicit narrowing conversion error, even if `Option Strict` is on.</span></span>  
  
 <span data-ttu-id="f3421-149">当调用一个方法包含具有不同于相应的参数的数据类型的实际参数时，收缩转换会导致编译时错误如果`Option Strict`上。</span><span class="sxs-lookup"><span data-stu-id="f3421-149">When you call a method that has an argument that has a data type different from the corresponding parameter, a narrowing conversion causes a compile-time error if `Option Strict` is on.</span></span> <span data-ttu-id="f3421-150">若要避免编译时错误，可使用扩大转换或显式转换。</span><span class="sxs-lookup"><span data-stu-id="f3421-150">You can avoid the compile-time error by using a widening conversion or an explicit conversion.</span></span>  
  
 <span data-ttu-id="f3421-151">在转换中的元素的编译时，将隐式收缩转换错误会抑制`For Each…Next`循环控制变量的集合。</span><span class="sxs-lookup"><span data-stu-id="f3421-151">Implicit narrowing conversion errors are suppressed at compile-time for conversions from the elements in a `For Each…Next` collection to the loop control variable.</span></span> <span data-ttu-id="f3421-152">发生这种情况即使`Option Strict`上。</span><span class="sxs-lookup"><span data-stu-id="f3421-152">This occurs even if `Option Strict` is on.</span></span> <span data-ttu-id="f3421-153">有关详细信息，请参阅中的"收缩转换"一节[为每个...下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="f3421-153">For more information, see the "Narrowing Conversions" section in [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="late-binding-errors"></a><span data-ttu-id="f3421-154">后期绑定错误</span><span class="sxs-lookup"><span data-stu-id="f3421-154">Late Binding Errors</span></span>  
 <span data-ttu-id="f3421-155">一个对象后期绑定到属性或方法声明为类型的变量的分配`Object`。</span><span class="sxs-lookup"><span data-stu-id="f3421-155">An object is late bound when it is assigned to a property or method of a variable that is declared to be of type `Object`.</span></span> <span data-ttu-id="f3421-156">有关详细信息，请参阅[早期绑定和后期绑定](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)。</span><span class="sxs-lookup"><span data-stu-id="f3421-156">For more information, see [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).</span></span>  
  
## <a name="implicit-object-type-errors"></a><span data-ttu-id="f3421-157">隐式对象类型错误</span><span class="sxs-lookup"><span data-stu-id="f3421-157">Implicit Object Type Errors</span></span>  
 <span data-ttu-id="f3421-158">隐式对象类型错误发生时相应类型不能是为推断出声明的变量，因此一种类型的`Object`这方面的推断。</span><span class="sxs-lookup"><span data-stu-id="f3421-158">Implicit object type errors occur when an appropriate type cannot be inferred for a declared variable, so a type of `Object` is inferred.</span></span> <span data-ttu-id="f3421-159">这主要发生在您使用`Dim`语句声明一个变量，但不使用`As`子句中，和`Option Infer`处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="f3421-159">This primarily occurs when you use a `Dim` statement to declare a variable without using an `As` clause, and `Option Infer` is off.</span></span> <span data-ttu-id="f3421-160">有关详细信息，请参阅[Option Infer 语句](../../../visual-basic/language-reference/statements/option-infer-statement.md)和[Visual Basic 语言规范](../../../visual-basic/reference/language-specification.md)。</span><span class="sxs-lookup"><span data-stu-id="f3421-160">For more information, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).</span></span>  
  
 <span data-ttu-id="f3421-161">方法参数`As`子句是可选的如果`Option Strict`处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="f3421-161">For method parameters, the `As` clause is optional if `Option Strict` is off.</span></span> <span data-ttu-id="f3421-162">但是，如果任何一个参数使用`As`子句，它们都必须使用它。</span><span class="sxs-lookup"><span data-stu-id="f3421-162">However, if any one parameter uses an `As` clause, they all must use it.</span></span> <span data-ttu-id="f3421-163">如果`Option Strict`处于打开状态，`As`子句是必需的每个参数定义。</span><span class="sxs-lookup"><span data-stu-id="f3421-163">If `Option Strict` is on, the `As` clause is required for every parameter definition.</span></span>  
  
 <span data-ttu-id="f3421-164">如果您声明一个变量而无需使用`As`子句并将其设置为`Nothing`，变量有一种类型的`Object`。</span><span class="sxs-lookup"><span data-stu-id="f3421-164">If you declare a variable without using an `As` clause and set it to `Nothing`, the variable has a type of `Object`.</span></span> <span data-ttu-id="f3421-165">在这种情况下出现任何编译时错误时`Option Strict`位于和`Option Infer`上。</span><span class="sxs-lookup"><span data-stu-id="f3421-165">No compile-time error occurs in this case when `Option Strict` is on and `Option Infer` is on.</span></span> <span data-ttu-id="f3421-166">此示例是`Dim something = Nothing`。</span><span class="sxs-lookup"><span data-stu-id="f3421-166">An example of this is `Dim something = Nothing`.</span></span>  
  
### <a name="default-data-types-and-values"></a><span data-ttu-id="f3421-167">默认数据类型和值</span><span class="sxs-lookup"><span data-stu-id="f3421-167">Default Data Types and Values</span></span>  
 <span data-ttu-id="f3421-168">下表描述了指定的数据类型和初始值设定项中的各种组合的结果[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="f3421-168">The following table describes the results of various combinations of specifying the data type and initializer in a [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
|<span data-ttu-id="f3421-169">是否指定数据类型？</span><span class="sxs-lookup"><span data-stu-id="f3421-169">Data type specified?</span></span>|<span data-ttu-id="f3421-170">是否指定初始值设定项？</span><span class="sxs-lookup"><span data-stu-id="f3421-170">Initializer specified?</span></span>|<span data-ttu-id="f3421-171">示例</span><span class="sxs-lookup"><span data-stu-id="f3421-171">Example</span></span>|<span data-ttu-id="f3421-172">结果</span><span class="sxs-lookup"><span data-stu-id="f3421-172">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="f3421-173">否</span><span class="sxs-lookup"><span data-stu-id="f3421-173">No</span></span>|<span data-ttu-id="f3421-174">否</span><span class="sxs-lookup"><span data-stu-id="f3421-174">No</span></span>|`Dim qty`|<span data-ttu-id="f3421-175">如果 `Option Strict` 处于关闭状态（默认），则将变量设置为 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="f3421-175">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="f3421-176">如果 `Option Strict` 处于打开状态，则发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="f3421-176">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="f3421-177">否</span><span class="sxs-lookup"><span data-stu-id="f3421-177">No</span></span>|<span data-ttu-id="f3421-178">是</span><span class="sxs-lookup"><span data-stu-id="f3421-178">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="f3421-179">如果 `Option Infer` 处于打开状态（默认），则变量采用初始值设定项的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f3421-179">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="f3421-180">请参阅[局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="f3421-180">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="f3421-181">如果 `Option Infer` 和 `Option Strict` 均处于关闭状态，则变量采用 `Object` 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f3421-181">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="f3421-182">如果 `Option Infer` 处于关闭状态但 `Option Strict` 处于打开状态，则发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="f3421-182">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="f3421-183">是</span><span class="sxs-lookup"><span data-stu-id="f3421-183">Yes</span></span>|<span data-ttu-id="f3421-184">否</span><span class="sxs-lookup"><span data-stu-id="f3421-184">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="f3421-185">将变量初始化为数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="f3421-185">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="f3421-186">有关详细信息，请参阅[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="f3421-186">For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>|  
|<span data-ttu-id="f3421-187">是</span><span class="sxs-lookup"><span data-stu-id="f3421-187">Yes</span></span>|<span data-ttu-id="f3421-188">是</span><span class="sxs-lookup"><span data-stu-id="f3421-188">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="f3421-189">如果初始值设定项的数据类型不可转换为指定数据类型，则会发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="f3421-189">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a><span data-ttu-id="f3421-190">当 Option Strict 语句不存在时</span><span class="sxs-lookup"><span data-stu-id="f3421-190">When an Option Strict Statement Is Not Present</span></span>  
 <span data-ttu-id="f3421-191">如果源代码不包含`Option Strict`语句， **Option strict**上设置[编译页，项目设计器 (Visual Basic 中)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)使用。</span><span class="sxs-lookup"><span data-stu-id="f3421-191">If the source code does not contain an `Option Strict` statement, the **Option strict** setting on the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="f3421-192">**编译页**具有提供更多控制权生成错误的条件的设置。</span><span class="sxs-lookup"><span data-stu-id="f3421-192">The **Compile Page** has settings that provide additional control over the conditions that generate an error.</span></span>  
  
 <span data-ttu-id="f3421-193">如果你正在使用命令行编译器，则可以使用[/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)编译器选项指定的设置`Option Strict`。</span><span class="sxs-lookup"><span data-stu-id="f3421-193">If you are using the command-line compiler, you can use the [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option to specify a setting for `Option Strict`.</span></span>  
  
### <a name="to-set-option-strict-in-the-ide"></a><span data-ttu-id="f3421-194">若要在 IDE 中设置 Option Strict</span><span class="sxs-lookup"><span data-stu-id="f3421-194">To set Option Strict in the IDE</span></span>  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
1.  <span data-ttu-id="f3421-195">在**解决方案资源管理器**，选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="f3421-195">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="f3421-196">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f3421-196">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="f3421-197">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="f3421-197">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="f3421-198">在**编译**选项卡上，在设置的值**Option Strict**框。</span><span class="sxs-lookup"><span data-stu-id="f3421-198">On the **Compile** tab, set the value in the **Option Strict** box.</span></span>  
  
###  <span data-ttu-id="f3421-199"><a name="conditions"></a>若要在 IDE 中设置警告配置</span><span class="sxs-lookup"><span data-stu-id="f3421-199"><a name="conditions"></a> To set warning configurations in the IDE</span></span>  
 <span data-ttu-id="f3421-200">当您使用[编译页，项目设计器 (Visual Basic 中)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)而不是`Option Strict`语句中，您有更多控制权会生成错误的条件。</span><span class="sxs-lookup"><span data-stu-id="f3421-200">When you use the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) instead of an `Option Strict` statement, you have additional control over the conditions that generate errors.</span></span> <span data-ttu-id="f3421-201">**警告配置**部分**编译页**具有对应的三个条件会导致编译时错误的设置时`Option Strict`上。</span><span class="sxs-lookup"><span data-stu-id="f3421-201">The **Warning configurations** section of the **Compile Page** has settings that correspond to the three conditions that cause a compile-time error when `Option Strict` is on.</span></span> <span data-ttu-id="f3421-202">这些设置如下︰</span><span class="sxs-lookup"><span data-stu-id="f3421-202">Following are these settings:</span></span>  
  
-   <span data-ttu-id="f3421-203">**隐式转换**</span><span class="sxs-lookup"><span data-stu-id="f3421-203">**Implicit conversion**</span></span>  
  
-   <span data-ttu-id="f3421-204">**后期绑定;调用可能在运行时失败**</span><span class="sxs-lookup"><span data-stu-id="f3421-204">**Late binding; call could fail at run time**</span></span>  
  
-   <span data-ttu-id="f3421-205">**隐式类型;假定为对象**</span><span class="sxs-lookup"><span data-stu-id="f3421-205">**Implicit type; object assumed**</span></span>  
  
 <span data-ttu-id="f3421-206">当您将设置**Option Strict**到**上**，所有这三个警告配置设置设置为**错误**。</span><span class="sxs-lookup"><span data-stu-id="f3421-206">When you set **Option Strict** to **On**, all three of these warning configuration settings are set to **Error**.</span></span> <span data-ttu-id="f3421-207">当您将设置**Option Strict**到**关闭**，所有三个设置设置为**无**。</span><span class="sxs-lookup"><span data-stu-id="f3421-207">When you set **Option Strict** to **Off**, all three settings are set to **None**.</span></span>  
  
 <span data-ttu-id="f3421-208">你可以单独更改将设置为每个警告配置**无**，**警告**，或**错误**。</span><span class="sxs-lookup"><span data-stu-id="f3421-208">You can individually change each warning configuration setting to **None**, **Warning**, or **Error**.</span></span> <span data-ttu-id="f3421-209">如果所有三个警告的配置设置都设置为**错误**，`On`将出现在`Option strict`框。</span><span class="sxs-lookup"><span data-stu-id="f3421-209">If all three warning configuration settings are set to **Error**, `On` appears in the `Option strict` box.</span></span> <span data-ttu-id="f3421-210">如果所有三个设置为**无**，`Off`出现在此框中。</span><span class="sxs-lookup"><span data-stu-id="f3421-210">If all three are set to **None**, `Off` appears in this box.</span></span> <span data-ttu-id="f3421-211">有关这些设置的任何其他组合**（自定义）**出现。</span><span class="sxs-lookup"><span data-stu-id="f3421-211">For any other combination of these settings, **(custom)** appears.</span></span>  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a><span data-ttu-id="f3421-212">若要设置 Option Strict 的默认设置为新项目</span><span class="sxs-lookup"><span data-stu-id="f3421-212">To set the Option Strict default setting for new projects</span></span>  
 <span data-ttu-id="f3421-213">当您创建项目时， **Option Strict**上设置**编译**选项卡上设置为**Option Strict**中设置**选项**对话框。</span><span class="sxs-lookup"><span data-stu-id="f3421-213">When you create a project, the **Option Strict** setting on the **Compile** tab is set to the **Option Strict** setting in the **Options** dialog box.</span></span>  
  
 <span data-ttu-id="f3421-214">若要设置`Option Strict`在此对话框中，在**工具**菜单上，单击**选项**。</span><span class="sxs-lookup"><span data-stu-id="f3421-214">To set `Option Strict` in this dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="f3421-215">在**选项**对话框框中，展开**项目和解决方案**，然后单击**VB 默认值**。</span><span class="sxs-lookup"><span data-stu-id="f3421-215">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="f3421-216">中的初始默认设置**VB 默认值**是`Off`。</span><span class="sxs-lookup"><span data-stu-id="f3421-216">The initial default setting in **VB Defaults** is `Off`.</span></span>  
  
### <a name="to-set-option-strict-on-the-command-line"></a><span data-ttu-id="f3421-217">若要在命令行上设置 Option Strict</span><span class="sxs-lookup"><span data-stu-id="f3421-217">To set Option Strict on the command line</span></span>  
 <span data-ttu-id="f3421-218">包括[/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)中的编译器选项**vbc**命令。</span><span class="sxs-lookup"><span data-stu-id="f3421-218">Include the [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3421-219">示例</span><span class="sxs-lookup"><span data-stu-id="f3421-219">Example</span></span>  
 <span data-ttu-id="f3421-220">下面的示例演示了编译时错误引起的缩窄转换的隐式类型转换。</span><span class="sxs-lookup"><span data-stu-id="f3421-220">The following examples demonstrate compile-time errors caused by implicit type conversions that are narrowing conversions.</span></span> <span data-ttu-id="f3421-221">这类错误对应于**隐式转换**条件**编译页**。</span><span class="sxs-lookup"><span data-stu-id="f3421-221">This category of errors corresponds to the **Implicit conversion** condition on the **Compile Page**.</span></span>  
  
 <span data-ttu-id="f3421-222">[!code-vb[VbVbalrStatements #&161;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3421-222">[!code-vb[VbVbalrStatements#161](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3421-223">示例</span><span class="sxs-lookup"><span data-stu-id="f3421-223">Example</span></span>  
 <span data-ttu-id="f3421-224">下面的示例演示了编译时错误引起的后期绑定。</span><span class="sxs-lookup"><span data-stu-id="f3421-224">The following example demonstrates a compile-time error caused by late binding.</span></span> <span data-ttu-id="f3421-225">这类错误对应于**Late 绑定; 调用可能在运行时失败**条件**编译页**。</span><span class="sxs-lookup"><span data-stu-id="f3421-225">This category of errors corresponds to the **Late binding; call could fail at run time** condition on the **Compile Page**.</span></span>  
  
 <span data-ttu-id="f3421-226">[!code-vb[VbVbalrStatements #&162;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3421-226">[!code-vb[VbVbalrStatements#162](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3421-227">示例</span><span class="sxs-lookup"><span data-stu-id="f3421-227">Example</span></span>  
 <span data-ttu-id="f3421-228">下面的示例演示使用隐式类型的声明的变量引起的错误`Object`。</span><span class="sxs-lookup"><span data-stu-id="f3421-228">The following examples demonstrate errors caused by variables that are declared with an implicit type of `Object`.</span></span> <span data-ttu-id="f3421-229">这类错误对应于**隐式类型; 假定为对象**条件**编译页**。</span><span class="sxs-lookup"><span data-stu-id="f3421-229">This category of errors corresponds to the **Implicit type; object assumed** condition on the **Compile Page**.</span></span>  
  
 <span data-ttu-id="f3421-230">[!code-vb[VbVbalrStatements #&163;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3421-230">[!code-vb[VbVbalrStatements#163](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]</span></span>  
  
 <span data-ttu-id="f3421-231">[!code-vb[VbVbalrStatements #&164;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3421-231">[!code-vb[VbVbalrStatements#164](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3421-232">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3421-232">See Also</span></span>  
 <span data-ttu-id="f3421-233">[扩大转换和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="f3421-233">[Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span></span>  
<span data-ttu-id="f3421-234"> [隐式和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="f3421-234"> [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="f3421-235"> [“项目设计器”->“编译”页 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="f3421-235"> [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="f3421-236"> [Option Explicit 语句](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f3421-236"> [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="f3421-237"> [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="f3421-237"> [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="f3421-238"> [如何︰ 访问对象的成员](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md) </span><span class="sxs-lookup"><span data-stu-id="f3421-238"> [How to: Access Members of an Object](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md) </span></span>  
<span data-ttu-id="f3421-239"> [XML 中的嵌入式的表达式](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span><span class="sxs-lookup"><span data-stu-id="f3421-239"> [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span></span>  
<span data-ttu-id="f3421-240"> [宽松的委托转换](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md) </span><span class="sxs-lookup"><span data-stu-id="f3421-240"> [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md) </span></span>  
<span data-ttu-id="f3421-241"> [Office 解决方案中的后期绑定](https://msdn.microsoft.com/library/3xxe951d) </span><span class="sxs-lookup"><span data-stu-id="f3421-241"> [Late Binding in Office Solutions](https://msdn.microsoft.com/library/3xxe951d) </span></span>  
<span data-ttu-id="f3421-242"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="f3421-242"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="f3421-243"> [“选项”对话框 ->“项目”->“Visual Basic 默认值”](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="f3421-243"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>

---
title: Option Strict Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Strict
- vb.OptionStrict
helpviewer_keywords:
- Strict keyword [Visual Basic]
- Option Strict statement [Visual Basic]
- conversions [Visual Basic], implicit
- late binding [Visual Basic]
- implicit conversions [Visual Basic]
ms.assetid: 5883e0c1-a920-4274-8e46-b0ff047eaee5
caps.latest.revision: "49"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1a01edd918ea49c08defddb45bf23c33307e814f
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="option-strict-statement"></a><span data-ttu-id="5e4b0-102">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="5e4b0-102">Option Strict Statement</span></span>
<span data-ttu-id="5e4b0-103">隐式数据类型将转换限制为仅扩大转换，不允许后期绑定，而不接受隐式类型化导致`Object`类型。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-103">Restricts implicit data type conversions to only widening conversions, disallows late binding, and disallows implicit typing that results in an `Object` type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e4b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="5e4b0-104">Syntax</span></span>  
  
```  
Option Strict { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="5e4b0-105">部件</span><span class="sxs-lookup"><span data-stu-id="5e4b0-105">Parts</span></span>  
  
|<span data-ttu-id="5e4b0-106">术语</span><span class="sxs-lookup"><span data-stu-id="5e4b0-106">Term</span></span>|<span data-ttu-id="5e4b0-107">定义</span><span class="sxs-lookup"><span data-stu-id="5e4b0-107">Definition</span></span>|  
|---|---|  
|`On`|<span data-ttu-id="5e4b0-108">可选。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-108">Optional.</span></span> <span data-ttu-id="5e4b0-109">使`Option Strict`检查。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-109">Enables `Option Strict` checking.</span></span>|  
|`Off`|<span data-ttu-id="5e4b0-110">可选。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-110">Optional.</span></span> <span data-ttu-id="5e4b0-111">禁用`Option Strict`检查。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-111">Disables `Option Strict` checking.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e4b0-112">备注</span><span class="sxs-lookup"><span data-stu-id="5e4b0-112">Remarks</span></span>  
 <span data-ttu-id="5e4b0-113">当`Option Strict On`或`Option Strict`出现在文件中，以下情况会导致编译时错误：</span><span class="sxs-lookup"><span data-stu-id="5e4b0-113">When `Option Strict On` or `Option Strict` appears in a file, the following conditions cause a compile-time error:</span></span>  
  
-   <span data-ttu-id="5e4b0-114">隐式收缩转换</span><span class="sxs-lookup"><span data-stu-id="5e4b0-114">Implicit narrowing conversions</span></span>  
  
-   <span data-ttu-id="5e4b0-115">后期绑定</span><span class="sxs-lookup"><span data-stu-id="5e4b0-115">Late binding</span></span>  
  
-   <span data-ttu-id="5e4b0-116">隐式键入会导致 `Object` 类型</span><span class="sxs-lookup"><span data-stu-id="5e4b0-116">Implicit typing that results in an `Object` type</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e4b0-117">在可以对设置的警告配置[编译页，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)，有三个对应于导致编译时错误的三个条件的设置。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-117">In the warning configurations that you can set on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), there are three settings that correspond to the three conditions that cause a compile-time error.</span></span> <span data-ttu-id="5e4b0-118">有关如何使用这些设置的信息，请参阅[在 IDE 中设置警告配置](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions)本主题中更高版本。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-118">For information about how to use these settings, see [To set warning configurations in the IDE](../../../visual-basic/language-reference/statements/option-strict-statement.md#conditions) later in this topic.</span></span>  
  
 <span data-ttu-id="5e4b0-119">`Option Strict Off`语句关闭错误和警告正在检查所有三个条件，即使关联的 IDE 设置指定要打开这些错误或警告。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-119">The `Option Strict Off` statement turns off error and warning checking for all three conditions, even if the associated IDE settings specify to turn on these errors or warnings.</span></span> <span data-ttu-id="5e4b0-120">`Option Strict On`语句启用错误和警告正在检查所有三个条件，即使关联的 IDE 设置指定将关闭这些错误或警告。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-120">The `Option Strict On` statement turns on error and warning checking for all three conditions, even if the associated IDE settings specify to turn off these errors or warnings.</span></span>  
  
 <span data-ttu-id="5e4b0-121">如果使用，`Option Strict`语句必须出现在文件中的任何其他源代码语句之前。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-121">If used, the `Option Strict` statement must appear before any other code statements in a file.</span></span>  
  
 <span data-ttu-id="5e4b0-122">当你将设置`Option Strict`到`On`，Visual Basic 检查，指定所有编程元素的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-122">When you set `Option Strict` to `On`, Visual Basic checks that data types are specified for all programming elements.</span></span> <span data-ttu-id="5e4b0-123">可以显式指定，或通过使用局部类型推理指定数据类型。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-123">Data types can be specified explicitly, or specified by using local type inference.</span></span> <span data-ttu-id="5e4b0-124">建议指定所有编程元素的数据类型，原因如下：</span><span class="sxs-lookup"><span data-stu-id="5e4b0-124">Specifying data types for all your programming elements is recommended, for the following reasons:</span></span>  
  
-   <span data-ttu-id="5e4b0-125">它使对变量和参数的 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-125">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="5e4b0-126">这使你可以查看其属性和其他成员如键入代码。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-126">This enables you to see their properties and other members as you type code.</span></span>  
  
-   <span data-ttu-id="5e4b0-127">它使得编译器执行类型检查。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-127">It enables the compiler to perform type checking.</span></span> <span data-ttu-id="5e4b0-128">类型检查可帮助你找到可以在运行时由于类型转换错误而失败的语句。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-128">Type checking helps you find statements that can fail at run time because of type conversion errors.</span></span> <span data-ttu-id="5e4b0-129">它还标识到不支持这些方法的对象的方法的调用。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-129">It also identifies calls to methods on objects that do not support those methods.</span></span>  
  
-   <span data-ttu-id="5e4b0-130">它可加快执行的代码。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-130">It speeds up the execution of code.</span></span> <span data-ttu-id="5e4b0-131">一个原因是，如果不指定编程元素中的数据类型，Visual Basic 编译器将其分配`Object`类型。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-131">One reason for this is that if you do not specify a data type for a programming element, the Visual Basic compiler assigns it the `Object` type.</span></span> <span data-ttu-id="5e4b0-132">编译的代码可能需要将之间来回转换`Object`和其他数据类型，这会降低性能。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-132">Compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="implicit-narrowing-conversion-errors"></a><span data-ttu-id="5e4b0-133">隐式收缩转换错误</span><span class="sxs-lookup"><span data-stu-id="5e4b0-133">Implicit Narrowing Conversion Errors</span></span>  
 <span data-ttu-id="5e4b0-134">隐式数据类型转换为收缩转换时，将发生隐式收缩转换错误。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-134">Implicit narrowing conversion errors occur when there is an implicit data type conversion that is a narrowing conversion.</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="5e4b0-135">可以将多种数据类型转换为其他数据类型。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-135"> can convert many data types to other data types.</span></span> <span data-ttu-id="5e4b0-136">一种数据类型的值转换为精度较低或容量较小的数据类型时，可能发生数据丢失。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-136">Data loss can occur when the value of one data type is converted to a data type that has less precision or a smaller capacity.</span></span> <span data-ttu-id="5e4b0-137">如果这种收缩转换失败，则会发生运行时错误。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-137">A run-time error occurs if such a narrowing conversion fails.</span></span> <span data-ttu-id="5e4b0-138">`Option Strict`可确保在编译时通知这些收缩转换，以便你可以避免它们。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-138">`Option Strict` ensures compile-time notification of these narrowing conversions so that you can avoid them.</span></span> <span data-ttu-id="5e4b0-139">有关详细信息，请参阅[隐式和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)和[扩大和收缩转换](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-139">For more information, see [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) and [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
 <span data-ttu-id="5e4b0-140">可能会导致错误的转换包括在表达式中发生的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-140">Conversions that can cause errors include implicit conversions that occur in expressions.</span></span> <span data-ttu-id="5e4b0-141">有关详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="5e4b0-141">For more information, see the following topics:</span></span>  
  
-   [<span data-ttu-id="5e4b0-142">+ 运算符</span><span class="sxs-lookup"><span data-stu-id="5e4b0-142">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)  
  
-   [<span data-ttu-id="5e4b0-143">+= 运算符</span><span class="sxs-lookup"><span data-stu-id="5e4b0-143">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
  
-   [<span data-ttu-id="5e4b0-144">\ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e4b0-144">\ Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/integer-division-operator.md)  
  
-   [<span data-ttu-id="5e4b0-145">/ = 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e4b0-145">/= Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)  
  
-   [<span data-ttu-id="5e4b0-146">Char 数据类型</span><span class="sxs-lookup"><span data-stu-id="5e4b0-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)  
  
 <span data-ttu-id="5e4b0-147">通过使用连接字符串时[& 运算符](../../../visual-basic/language-reference/operators/concatenation-operator.md)，考虑到字符串的所有转换会扩大。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-147">When you concatenate strings by using the [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md), all conversions to the strings are considered to be widening.</span></span> <span data-ttu-id="5e4b0-148">因此，隐式收缩转换错误，即使这些转换不会生成`Option Strict`上。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-148">So these conversions do not generate an implicit narrowing conversion error, even if `Option Strict` is on.</span></span>  
  
 <span data-ttu-id="5e4b0-149">在调用时有一个具有不同于对应的参数的数据类型的参数的方法，收缩转换会导致编译时错误如果`Option Strict`上。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-149">When you call a method that has an argument that has a data type different from the corresponding parameter, a narrowing conversion causes a compile-time error if `Option Strict` is on.</span></span> <span data-ttu-id="5e4b0-150">可以使用一个的扩大转换或显式转换来避免编译时错误。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-150">You can avoid the compile-time error by using a widening conversion or an explicit conversion.</span></span>  
  
 <span data-ttu-id="5e4b0-151">在从中的元素的转换的编译时将隐式收缩转换错误被抑制`For Each…Next`向循环控制变量的集合。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-151">Implicit narrowing conversion errors are suppressed at compile-time for conversions from the elements in a `For Each…Next` collection to the loop control variable.</span></span> <span data-ttu-id="5e4b0-152">发生这种情况即使`Option Strict`上。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-152">This occurs even if `Option Strict` is on.</span></span> <span data-ttu-id="5e4b0-153">有关详细信息，请参阅中的"收缩转换"一节[每个...下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-153">For more information, see the "Narrowing Conversions" section in [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="late-binding-errors"></a><span data-ttu-id="5e4b0-154">后期绑定错误</span><span class="sxs-lookup"><span data-stu-id="5e4b0-154">Late Binding Errors</span></span>  
 <span data-ttu-id="5e4b0-155">如果将对象分配给声明为 `Object` 类型的变量，则该对象为晚期绑定。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-155">An object is late bound when it is assigned to a property or method of a variable that is declared to be of type `Object`.</span></span> <span data-ttu-id="5e4b0-156">有关详细信息，请参阅[早期绑定和后期绑定](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-156">For more information, see [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).</span></span>  
  
## <a name="implicit-object-type-errors"></a><span data-ttu-id="5e4b0-157">隐式对象类型错误</span><span class="sxs-lookup"><span data-stu-id="5e4b0-157">Implicit Object Type Errors</span></span>  
 <span data-ttu-id="5e4b0-158">如果无法为已声明的变量推断出合适的类型，则会发生隐式对象类型错误，因此 `Object` 类型是推断出来的。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-158">Implicit object type errors occur when an appropriate type cannot be inferred for a declared variable, so a type of `Object` is inferred.</span></span> <span data-ttu-id="5e4b0-159">这主要是在未使用 `As` 子句的情况下使用 `Dim` 语句声明变量，且 `Option Infer` 为关闭时发生的。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-159">This primarily occurs when you use a `Dim` statement to declare a variable without using an `As` clause, and `Option Infer` is off.</span></span> <span data-ttu-id="5e4b0-160">有关详细信息，请参阅[Option Infer 语句](../../../visual-basic/language-reference/statements/option-infer-statement.md)和[Visual Basic 语言规范](../../../visual-basic/reference/language-specification/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-160">For more information, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification/index.md).</span></span>  
  
 <span data-ttu-id="5e4b0-161">为方法参数`As`子句是可选的如果`Option Strict`处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-161">For method parameters, the `As` clause is optional if `Option Strict` is off.</span></span> <span data-ttu-id="5e4b0-162">但是，如果任何一个参数使用`As`子句，它们都必须使用它。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-162">However, if any one parameter uses an `As` clause, they all must use it.</span></span> <span data-ttu-id="5e4b0-163">如果`Option Strict`处于打开状态，`As`子句是必需的每个参数定义。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-163">If `Option Strict` is on, the `As` clause is required for every parameter definition.</span></span>  
  
 <span data-ttu-id="5e4b0-164">如果您声明一个变量而无需使用`As`子句将其设置为`Nothing`，该变量具有一种`Object`。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-164">If you declare a variable without using an `As` clause and set it to `Nothing`, the variable has a type of `Object`.</span></span> <span data-ttu-id="5e4b0-165">没有编译时错误发生在这种情况下时`Option Strict`位于和`Option Infer`上。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-165">No compile-time error occurs in this case when `Option Strict` is on and `Option Infer` is on.</span></span> <span data-ttu-id="5e4b0-166">此示例是`Dim something = Nothing`。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-166">An example of this is `Dim something = Nothing`.</span></span>  
  
### <a name="default-data-types-and-values"></a><span data-ttu-id="5e4b0-167">默认数据类型和值</span><span class="sxs-lookup"><span data-stu-id="5e4b0-167">Default Data Types and Values</span></span>  
 <span data-ttu-id="5e4b0-168">下表描述指定的数据类型和初始值设定项中的各种组合的结果[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-168">The following table describes the results of various combinations of specifying the data type and initializer in a [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
|<span data-ttu-id="5e4b0-169">是否指定数据类型？</span><span class="sxs-lookup"><span data-stu-id="5e4b0-169">Data type specified?</span></span>|<span data-ttu-id="5e4b0-170">是否指定初始值设定项？</span><span class="sxs-lookup"><span data-stu-id="5e4b0-170">Initializer specified?</span></span>|<span data-ttu-id="5e4b0-171">示例</span><span class="sxs-lookup"><span data-stu-id="5e4b0-171">Example</span></span>|<span data-ttu-id="5e4b0-172">结果</span><span class="sxs-lookup"><span data-stu-id="5e4b0-172">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="5e4b0-173">否</span><span class="sxs-lookup"><span data-stu-id="5e4b0-173">No</span></span>|<span data-ttu-id="5e4b0-174">否</span><span class="sxs-lookup"><span data-stu-id="5e4b0-174">No</span></span>|`Dim qty`|<span data-ttu-id="5e4b0-175">如果 `Option Strict` 处于关闭状态（默认），则将变量设置为 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-175">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="5e4b0-176">如果 `Option Strict` 处于打开状态，则发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-176">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="5e4b0-177">否</span><span class="sxs-lookup"><span data-stu-id="5e4b0-177">No</span></span>|<span data-ttu-id="5e4b0-178">是</span><span class="sxs-lookup"><span data-stu-id="5e4b0-178">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="5e4b0-179">如果 `Option Infer` 处于打开状态（默认），则变量采用初始值设定项的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-179">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="5e4b0-180">请参阅[局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-180">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="5e4b0-181">如果 `Option Infer` 和 `Option Strict` 均处于关闭状态，则变量采用 `Object` 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-181">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="5e4b0-182">如果 `Option Infer` 处于关闭状态但 `Option Strict` 处于打开状态，则发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-182">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="5e4b0-183">是</span><span class="sxs-lookup"><span data-stu-id="5e4b0-183">Yes</span></span>|<span data-ttu-id="5e4b0-184">否</span><span class="sxs-lookup"><span data-stu-id="5e4b0-184">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="5e4b0-185">将变量初始化为数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-185">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="5e4b0-186">有关详细信息，请参阅[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-186">For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>|  
|<span data-ttu-id="5e4b0-187">是</span><span class="sxs-lookup"><span data-stu-id="5e4b0-187">Yes</span></span>|<span data-ttu-id="5e4b0-188">是</span><span class="sxs-lookup"><span data-stu-id="5e4b0-188">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="5e4b0-189">如果初始值设定项的数据类型不可转换为指定数据类型，则会发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-189">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
## <a name="when-an-option-strict-statement-is-not-present"></a><span data-ttu-id="5e4b0-190">Option Strict 语句不存在</span><span class="sxs-lookup"><span data-stu-id="5e4b0-190">When an Option Strict Statement Is Not Present</span></span>  
 <span data-ttu-id="5e4b0-191">如果源代码不包含`Option Strict`语句，**选项严格**上设置[编译页，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)使用。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-191">If the source code does not contain an `Option Strict` statement, the **Option strict** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="5e4b0-192">**编译页**具有提供对生成错误的条件的其他控制的设置。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-192">The **Compile Page** has settings that provide additional control over the conditions that generate an error.</span></span>  
  
 <span data-ttu-id="5e4b0-193">如果你正在使用命令行编译器，则可以使用[/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)编译器选项指定的设置`Option Strict`。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-193">If you are using the command-line compiler, you can use the [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option to specify a setting for `Option Strict`.</span></span>  
  
### <a name="to-set-option-strict-in-the-ide"></a><span data-ttu-id="5e4b0-194">在 IDE 中设置 Option Strict</span><span class="sxs-lookup"><span data-stu-id="5e4b0-194">To set Option Strict in the IDE</span></span>  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
1.  <span data-ttu-id="5e4b0-195">在“解决方案资源管理器”中，选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-195">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="5e4b0-196">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-196">On the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="5e4b0-197">上**编译**选项卡上，设置中的值**Option Strict**框。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-197">On the **Compile** tab, set the value in the **Option Strict** box.</span></span>  
  
###  <a name="conditions"></a><span data-ttu-id="5e4b0-198">在 IDE 中设置警告配置</span><span class="sxs-lookup"><span data-stu-id="5e4b0-198">To set warning configurations in the IDE</span></span>  
 <span data-ttu-id="5e4b0-199">当你使用[编译页，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)而不是`Option Strict`语句中，你可以生成错误的条件的其他控制。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-199">When you use the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) instead of an `Option Strict` statement, you have additional control over the conditions that generate errors.</span></span> <span data-ttu-id="5e4b0-200">**警告配置**部分**编译页**已设置，对应于导致编译时错误的三个条件时`Option Strict`上。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-200">The **Warning configurations** section of the **Compile Page** has settings that correspond to the three conditions that cause a compile-time error when `Option Strict` is on.</span></span> <span data-ttu-id="5e4b0-201">这些设置如下：</span><span class="sxs-lookup"><span data-stu-id="5e4b0-201">Following are these settings:</span></span>  
  
-   <span data-ttu-id="5e4b0-202">隐式转换</span><span class="sxs-lookup"><span data-stu-id="5e4b0-202">**Implicit conversion**</span></span>  
  
-   <span data-ttu-id="5e4b0-203">晚期绑定；调用可能在运行时失败</span><span class="sxs-lookup"><span data-stu-id="5e4b0-203">**Late binding; call could fail at run time**</span></span>  
  
-   <span data-ttu-id="5e4b0-204">隐式类型；假定为对象</span><span class="sxs-lookup"><span data-stu-id="5e4b0-204">**Implicit type; object assumed**</span></span>  
  
 <span data-ttu-id="5e4b0-205">“Option Strict”设置为“开启”时，所有这三个警告配置设置都将被设置为“错误”。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-205">When you set **Option Strict** to **On**, all three of these warning configuration settings are set to **Error**.</span></span> <span data-ttu-id="5e4b0-206">“Option Strict”设置为“关闭”时，所有这三个设置都将被设置为“无”。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-206">When you set **Option Strict** to **Off**, all three settings are set to **None**.</span></span>  
  
 <span data-ttu-id="5e4b0-207">可单独将各个警告配置设置更改为“无”、“警告”或“错误”。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-207">You can individually change each warning configuration setting to **None**, **Warning**, or **Error**.</span></span> <span data-ttu-id="5e4b0-208">如果三个警告配置都设置为“错误”，则 `On` 会出现在 `Option strict` 框中。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-208">If all three warning configuration settings are set to **Error**, `On` appears in the `Option strict` box.</span></span> <span data-ttu-id="5e4b0-209">如果三个都设置为“无”，则 `Off` 会出现在此框中。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-209">If all three are set to **None**, `Off` appears in this box.</span></span> <span data-ttu-id="5e4b0-210">对于这些配置的任何其他组合，显示“(自定义)”。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-210">For any other combination of these settings, **(custom)** appears.</span></span>  
  
### <a name="to-set-the-option-strict-default-setting-for-new-projects"></a><span data-ttu-id="5e4b0-211">设置选项严格的默认设置为新项目</span><span class="sxs-lookup"><span data-stu-id="5e4b0-211">To set the Option Strict default setting for new projects</span></span>  
 <span data-ttu-id="5e4b0-212">当你创建项目， **Option Strict**上设置**编译**选项卡设置为**Option Strict**中设置**选项**对话框。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-212">When you create a project, the **Option Strict** setting on the **Compile** tab is set to the **Option Strict** setting in the **Options** dialog box.</span></span>  
  
 <span data-ttu-id="5e4b0-213">若要设置`Option Strict`在此对话框中，在**工具**菜单上，单击**选项**。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-213">To set `Option Strict` in this dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="5e4b0-214">在“选项”对话框中，展开“项目和解决方案”，然后单击“VB 默认值”。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-214">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="5e4b0-215">中的初始默认设置**VB 默认值**是`Off`。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-215">The initial default setting in **VB Defaults** is `Off`.</span></span>  
  
### <a name="to-set-option-strict-on-the-command-line"></a><span data-ttu-id="5e4b0-216">若要设置命令行上的 Option Strict</span><span class="sxs-lookup"><span data-stu-id="5e4b0-216">To set Option Strict on the command line</span></span>  
 <span data-ttu-id="5e4b0-217">包括[/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)中的编译器选项**vbc**命令。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-217">Include the [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e4b0-218">示例</span><span class="sxs-lookup"><span data-stu-id="5e4b0-218">Example</span></span>  
 <span data-ttu-id="5e4b0-219">下面的示例演示通过隐式类型转换收缩转换导致的编译时错误。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-219">The following examples demonstrate compile-time errors caused by implicit type conversions that are narrowing conversions.</span></span> <span data-ttu-id="5e4b0-220">这类错误对应于**隐式转换**条件上**编译页**。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-220">This category of errors corresponds to the **Implicit conversion** condition on the **Compile Page**.</span></span>  
  
 [!code-vb[VbVbalrStatements#161](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="5e4b0-221">示例</span><span class="sxs-lookup"><span data-stu-id="5e4b0-221">Example</span></span>  
 <span data-ttu-id="5e4b0-222">下面的示例演示了后期绑定引起的编译时错误。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-222">The following example demonstrates a compile-time error caused by late binding.</span></span> <span data-ttu-id="5e4b0-223">这类错误对应于**延迟绑定; 调用可能在运行时失败**条件上**编译页**。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-223">This category of errors corresponds to the **Late binding; call could fail at run time** condition on the **Compile Page**.</span></span>  
  
 [!code-vb[VbVbalrStatements#162](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="5e4b0-224">示例</span><span class="sxs-lookup"><span data-stu-id="5e4b0-224">Example</span></span>  
 <span data-ttu-id="5e4b0-225">下面的示例演示通过隐式类型的声明的变量引起的错误`Object`。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-225">The following examples demonstrate errors caused by variables that are declared with an implicit type of `Object`.</span></span> <span data-ttu-id="5e4b0-226">这类错误对应于**隐式类型; 对象假设**条件上**编译页**。</span><span class="sxs-lookup"><span data-stu-id="5e4b0-226">This category of errors corresponds to the **Implicit type; object assumed** condition on the **Compile Page**.</span></span>  
  
 [!code-vb[VbVbalrStatements#163](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#164](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-strict-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5e4b0-227">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e4b0-227">See Also</span></span>  
 [<span data-ttu-id="5e4b0-228">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="5e4b0-228">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="5e4b0-229">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="5e4b0-229">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="5e4b0-230">“项目设计器”->“编译”页 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e4b0-230">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [<span data-ttu-id="5e4b0-231">Option Explicit 语句</span><span class="sxs-lookup"><span data-stu-id="5e4b0-231">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="5e4b0-232">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="5e4b0-232">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="5e4b0-233">如何：访问对象的成员</span><span class="sxs-lookup"><span data-stu-id="5e4b0-233">How to: Access Members of an Object</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)  
 [<span data-ttu-id="5e4b0-234">XML 中的嵌入式表达式</span><span class="sxs-lookup"><span data-stu-id="5e4b0-234">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [<span data-ttu-id="5e4b0-235">宽松委托转换</span><span class="sxs-lookup"><span data-stu-id="5e4b0-235">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [<span data-ttu-id="5e4b0-236">Office 解决方案中的晚期绑定</span><span class="sxs-lookup"><span data-stu-id="5e4b0-236">Late Binding in Office Solutions</span></span>](https://msdn.microsoft.com/library/3xxe951d)  
 [<span data-ttu-id="5e4b0-237">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="5e4b0-237">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="5e4b0-238">“选项”对话框 ->“项目”->“Visual Basic 默认值”</span><span class="sxs-lookup"><span data-stu-id="5e4b0-238">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)

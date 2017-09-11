---
title: "局部类型推理 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- local type inference
- vb.TypeInfer
dev_langs:
- VB
helpviewer_keywords:
- Option Infer statement
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
caps.latest.revision: 43
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
ms.openlocfilehash: af8de63eb00db917771600f0fca8f200ec451afe
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="474b7-102">局部类型推理 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="474b7-102">Local Type Inference (Visual Basic)</span></span>
<span data-ttu-id="474b7-103">Visual Basic 编译器使用*类型推理*来确定未声明的局部变量的数据类型`As`子句。</span><span class="sxs-lookup"><span data-stu-id="474b7-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="474b7-104">编译器推断出类型的变量的初始化表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="474b7-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="474b7-105">这使您无需显式声明一个类型声明变量，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="474b7-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="474b7-106">由于声明，而同时`num1`和`num2`强类型化为整数。</span><span class="sxs-lookup"><span data-stu-id="474b7-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 <span data-ttu-id="474b7-107">[!code-vb[VbVbalrTypeInference #&1;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="474b7-107">[!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="474b7-108">如果不希望`num2`在前面的示例，若要将类型化为`Integer`，您可以使用声明，例如指定另一种类型`Dim num3 As Object = 3`或`Dim num4 As Double = 3`。</span><span class="sxs-lookup"><span data-stu-id="474b7-108">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>  
  
 <span data-ttu-id="474b7-109">局部类型推理适用于过程级。</span><span class="sxs-lookup"><span data-stu-id="474b7-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="474b7-110">它不能用于声明在模块级别 （在类、 结构、 模块或接口中但不是能在过程或块） 的变量。</span><span class="sxs-lookup"><span data-stu-id="474b7-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="474b7-111">如果`num2`在前面的示例而不是一个过程中的本地变量类的字段，该声明会导致出现错误与`Option Strict`，并将对其分类`num2`作为`Object`与`Option Strict`关闭。</span><span class="sxs-lookup"><span data-stu-id="474b7-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="474b7-112">同样，局部类型推理不会应用于过程级变量声明为`Static`。</span><span class="sxs-lookup"><span data-stu-id="474b7-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>  
  
## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="474b7-113">类型推理与。后期绑定</span><span class="sxs-lookup"><span data-stu-id="474b7-113">Type Inference vs. Late Binding</span></span>  
 <span data-ttu-id="474b7-114">使用类型推理的代码类似于依赖后期绑定的代码。</span><span class="sxs-lookup"><span data-stu-id="474b7-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="474b7-115">但是，类型推断为强类型而不是将其保留为变量`Object`。</span><span class="sxs-lookup"><span data-stu-id="474b7-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="474b7-116">编译器使用变量的初始值设定项来确定在编译时，若要生成早期绑定的代码的变量的类型。</span><span class="sxs-lookup"><span data-stu-id="474b7-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="474b7-117">在上一示例中， `num2`、 like `num1`，类型化为`Integer`。</span><span class="sxs-lookup"><span data-stu-id="474b7-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>  
  
 <span data-ttu-id="474b7-118">早期绑定的变量的行为不同于，后期绑定的变量，仅在运行时为其已知类型。</span><span class="sxs-lookup"><span data-stu-id="474b7-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="474b7-119">尽早知道的类型使编译器能够识别问题，然后执行、 准确地说，分配内存并执行其他优化。</span><span class="sxs-lookup"><span data-stu-id="474b7-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="474b7-120">早期绑定还可使 Visual Basic 的集成的开发环境 (IDE)，以提供有关对象的成员的 IntelliSense 将帮助。</span><span class="sxs-lookup"><span data-stu-id="474b7-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="474b7-121">早期绑定也是性能的首选分发点。</span><span class="sxs-lookup"><span data-stu-id="474b7-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="474b7-122">这是因为后期绑定变量中存储的所有数据都必须作为类型都包装`Object`，并在运行时访问该类型的成员使程序运行较慢。</span><span class="sxs-lookup"><span data-stu-id="474b7-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="474b7-123">示例</span><span class="sxs-lookup"><span data-stu-id="474b7-123">Examples</span></span>  
 <span data-ttu-id="474b7-124">而无需声明本地变量时，会发生类型推理`As`子句和初始化。</span><span class="sxs-lookup"><span data-stu-id="474b7-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="474b7-125">编译器将使用的初始已赋值的类型作为该变量的类型。</span><span class="sxs-lookup"><span data-stu-id="474b7-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="474b7-126">例如，下面的代码行的每个声明类型的变量`String`。</span><span class="sxs-lookup"><span data-stu-id="474b7-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>  
  
 <span data-ttu-id="474b7-127">[!code-vb[VbVbalrTypeInference #&2;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="474b7-127">[!code-vb[VbVbalrTypeInference#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]</span></span>  
  
 <span data-ttu-id="474b7-128">下面的代码演示两个等效的方法来创建整数的数组。</span><span class="sxs-lookup"><span data-stu-id="474b7-128">The following code demonstrates two equivalent ways to create an array of integers.</span></span>  
  
 <span data-ttu-id="474b7-129">[!code-vb[VbVbalrTypeInference #&3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="474b7-129">[!code-vb[VbVbalrTypeInference#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]</span></span>  
  
 <span data-ttu-id="474b7-130">它很方便地使用类型推断功能来确定的循环控制变量的类型。</span><span class="sxs-lookup"><span data-stu-id="474b7-130">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="474b7-131">在下面的代码中，编译器推断`number`是`Integer`因为`someNumbers2`从上一个示例是一个整数数组。</span><span class="sxs-lookup"><span data-stu-id="474b7-131">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>  
  
 <span data-ttu-id="474b7-132">[!code-vb[VbVbalrTypeInference #&4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="474b7-132">[!code-vb[VbVbalrTypeInference#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]</span></span>  
  
 <span data-ttu-id="474b7-133">可以在使用局部类型推理`Using`语句，以建立资源名称的类型，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="474b7-133">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>  
  
 <span data-ttu-id="474b7-134">[!code-vb[VbVbalrTypeInference #&7;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="474b7-134">[!code-vb[VbVbalrTypeInference#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]</span></span>  
  
 <span data-ttu-id="474b7-135">如以下示例所示，还可以从函数的返回值推断变量类型。</span><span class="sxs-lookup"><span data-stu-id="474b7-135">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="474b7-136">同时`pList1`和`pList2`都是进程数组，因为`Process.GetProcesses`返回的进程的数组。</span><span class="sxs-lookup"><span data-stu-id="474b7-136">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>  
  
 <span data-ttu-id="474b7-137">[!code-vb[VbVbalrTypeInference #&5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="474b7-137">[!code-vb[VbVbalrTypeInference#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]</span></span>  
  
## <a name="option-infer"></a><span data-ttu-id="474b7-138">Option Infer</span><span class="sxs-lookup"><span data-stu-id="474b7-138">Option Infer</span></span>  
 <span data-ttu-id="474b7-139">`Option Infer`允许您指定在特定的文件中是否允许局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="474b7-139">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="474b7-140">若要启用或阻止该选项，请在该文件的开头键入以下语句之一。</span><span class="sxs-lookup"><span data-stu-id="474b7-140">To enable or to block the option, type one of the following statements at the start of the file.</span></span>  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 <span data-ttu-id="474b7-141">如果未指定的值`Option Infer`在代码中，默认的编译器是`Option Infer On`。</span><span class="sxs-lookup"><span data-stu-id="474b7-141">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span> <span data-ttu-id="474b7-142">从项目升级为[!INCLUDE[vb_orcas_long](../../../../visual-basic/misc/includes/vb_orcas_long_md.md)]或更早版本，默认的编译器是`Option Infer Off`。</span><span class="sxs-lookup"><span data-stu-id="474b7-142">For projects upgraded from [!INCLUDE[vb_orcas_long](../../../../visual-basic/misc/includes/vb_orcas_long_md.md)] or earlier, the compiler default is `Option Infer Off`.</span></span>  
  
 <span data-ttu-id="474b7-143">如果为文件中 `Option Infer` 设置的值与在 IDE 中或在命令行上设置的值冲突，则文件中的值优先。</span><span class="sxs-lookup"><span data-stu-id="474b7-143">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="474b7-144">有关详细信息，请参阅[Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)和[编译页，项目设计器 (Visual Basic 中)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="474b7-144">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="474b7-145">限制</span><span class="sxs-lookup"><span data-stu-id="474b7-145">Restrictions</span></span>  
 <span data-ttu-id="474b7-146">类型推理可以仅用于非静态局部变量;它不能用于确定类字段、 属性或函数的类型。</span><span class="sxs-lookup"><span data-stu-id="474b7-146">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="474b7-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="474b7-147">See Also</span></span>  
 <span data-ttu-id="474b7-148">[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="474b7-148">[Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span></span>  
<span data-ttu-id="474b7-149"> [早期绑定和后期绑定](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md) </span><span class="sxs-lookup"><span data-stu-id="474b7-149"> [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md) </span></span>  
<span data-ttu-id="474b7-150"> [每个...下一条语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="474b7-150"> [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="474b7-151"> [有关...下一条语句](../../../../visual-basic/language-reference/statements/for-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="474b7-151"> [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md) </span></span>  
<span data-ttu-id="474b7-152"> [Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="474b7-152"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="474b7-153"> [/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="474b7-153"> [/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="474b7-154"> [在 Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="474b7-154"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>

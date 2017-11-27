---
title: "局部类型推理 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
caps.latest.revision: "43"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d753d1fbdc60f70dcf0513d809f28a112243c111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="81c8d-102">局部类型推理 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81c8d-102">Local Type Inference (Visual Basic)</span></span>
<span data-ttu-id="81c8d-103">Visual Basic 编译器使用*类型推理*来确定未声明的本地变量的数据类型`As`子句。</span><span class="sxs-lookup"><span data-stu-id="81c8d-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="81c8d-104">编译器推断出从初始化表达式的类型变量的类型。</span><span class="sxs-lookup"><span data-stu-id="81c8d-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="81c8d-105">这使您可以无需显式声明类型，声明变量，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="81c8d-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="81c8d-106">由于声明，同时`num1`和`num2`强类型为整数。</span><span class="sxs-lookup"><span data-stu-id="81c8d-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]  
 
> [!NOTE]
>  <span data-ttu-id="81c8d-107">如果不希望`num2`在前面的示例类型化为`Integer`，你可以通过使用声明，例如指定另一种类型`Dim num3 As Object = 3`或`Dim num4 As Double = 3`。</span><span class="sxs-lookup"><span data-stu-id="81c8d-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>  

> [!NOTE]
>  <span data-ttu-id="81c8d-108">类型推理可以仅用于非静态局部变量;它不用于确定类字段、 属性或函数的类型。</span><span class="sxs-lookup"><span data-stu-id="81c8d-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>
 
 <span data-ttu-id="81c8d-109">局部类型推理在过程级别适用。</span><span class="sxs-lookup"><span data-stu-id="81c8d-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="81c8d-110">它不能用于声明在模块级别 （在类、 结构、 模块或接口，但不是在过程或块） 的变量。</span><span class="sxs-lookup"><span data-stu-id="81c8d-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="81c8d-111">如果`num2`在前面的示例而不是一个过程中的本地变量类的字段，声明将导致错误`Option Strict`，并将对其分类`num2`作为`Object`与`Option Strict`关闭。</span><span class="sxs-lookup"><span data-stu-id="81c8d-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="81c8d-112">同样，局部类型推理不应用于过程级变量声明为`Static`。</span><span class="sxs-lookup"><span data-stu-id="81c8d-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>  
  
## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="81c8d-113">类型推理与。后期绑定</span><span class="sxs-lookup"><span data-stu-id="81c8d-113">Type Inference vs. Late Binding</span></span>  
 <span data-ttu-id="81c8d-114">依赖于后期绑定的代码与使用类型推理的代码类似。</span><span class="sxs-lookup"><span data-stu-id="81c8d-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="81c8d-115">但是，类型推理为强类型而不是将其保留为变量`Object`。</span><span class="sxs-lookup"><span data-stu-id="81c8d-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="81c8d-116">编译器使用变量的初始值设定项来确定在编译时生成早期绑定代码的变量的类型。</span><span class="sxs-lookup"><span data-stu-id="81c8d-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="81c8d-117">在前面的示例中， `num2`、 like `num1`，被类型化为`Integer`。</span><span class="sxs-lookup"><span data-stu-id="81c8d-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>  
  
 <span data-ttu-id="81c8d-118">早期绑定的变量的行为不同于后期绑定变量，并仅在运行时知道它的类型。</span><span class="sxs-lookup"><span data-stu-id="81c8d-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="81c8d-119">尽早知道的类型使编译器能够识别问题，然后执行、 准确地说，分配内存和执行其他优化。</span><span class="sxs-lookup"><span data-stu-id="81c8d-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="81c8d-120">早期绑定还可使 Visual Basic 集成的开发环境 (IDE) IntelliSense 帮助提供有关对象的成员。</span><span class="sxs-lookup"><span data-stu-id="81c8d-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="81c8d-121">早期绑定也是性能的首选分发点。</span><span class="sxs-lookup"><span data-stu-id="81c8d-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="81c8d-122">这是因为后期绑定变量中存储的所有数据都必须作为类型都包装`Object`，并在运行时访问该类型的成员使程序运行较慢。</span><span class="sxs-lookup"><span data-stu-id="81c8d-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="81c8d-123">示例</span><span class="sxs-lookup"><span data-stu-id="81c8d-123">Examples</span></span>  
 <span data-ttu-id="81c8d-124">本地变量声明而无需时，会发生类型推理`As`子句和初始化。</span><span class="sxs-lookup"><span data-stu-id="81c8d-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="81c8d-125">编译器将使用分配的初始值的类型作为变量的类型。</span><span class="sxs-lookup"><span data-stu-id="81c8d-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="81c8d-126">例如，以下代码行的每个声明类型的变量的`String`。</span><span class="sxs-lookup"><span data-stu-id="81c8d-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]  
  
 <span data-ttu-id="81c8d-127">下面的代码演示了两个等效方法创建整数的数组。</span><span class="sxs-lookup"><span data-stu-id="81c8d-127">The following code demonstrates two equivalent ways to create an array of integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]  
  
 <span data-ttu-id="81c8d-128">它很方便地使用类型推断功能来确定的循环控制变量的类型。</span><span class="sxs-lookup"><span data-stu-id="81c8d-128">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="81c8d-129">在下面的代码中，编译器推断出的`number`是`Integer`因为`someNumbers2`从前面的示例是一个整数数组。</span><span class="sxs-lookup"><span data-stu-id="81c8d-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]  
  
 <span data-ttu-id="81c8d-130">可以在使用局部类型推理`Using`语句来确定资源名称的类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="81c8d-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]  
  
 <span data-ttu-id="81c8d-131">如以下示例所示，还可以从函数的返回值推断变量的类型。</span><span class="sxs-lookup"><span data-stu-id="81c8d-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="81c8d-132">同时`pList1`和`pList2`是进程的数组，因为`Process.GetProcesses`返回进程的数组。</span><span class="sxs-lookup"><span data-stu-id="81c8d-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]  
  
## <a name="option-infer"></a><span data-ttu-id="81c8d-133">Option Infer</span><span class="sxs-lookup"><span data-stu-id="81c8d-133">Option Infer</span></span>  
 <span data-ttu-id="81c8d-134">`Option Infer`允许你指定特定文件中是否允许局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="81c8d-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="81c8d-135">若要启用或阻止该选项，请在文件的开头键入以下语句之一。</span><span class="sxs-lookup"><span data-stu-id="81c8d-135">To enable or to block the option, type one of the following statements at the start of the file.</span></span>  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 <span data-ttu-id="81c8d-136">如果未指定的值`Option Infer`编译器默认值是在代码中， `Option Infer On`。</span><span class="sxs-lookup"><span data-stu-id="81c8d-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span> <span data-ttu-id="81c8d-137">从项目升级为[!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)]或更早版本，编译器默认`Option Infer Off`。</span><span class="sxs-lookup"><span data-stu-id="81c8d-137">For projects upgraded from [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] or earlier, the compiler default is `Option Infer Off`.</span></span>  
  
 <span data-ttu-id="81c8d-138">如果为文件中 `Option Infer` 设置的值与在 IDE 中或在命令行上设置的值冲突，则文件中的值优先。</span><span class="sxs-lookup"><span data-stu-id="81c8d-138">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="81c8d-139">有关详细信息，请参阅[Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)和[编译页，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="81c8d-139">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c8d-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81c8d-140">See Also</span></span>  
 [<span data-ttu-id="81c8d-141">匿名类型</span><span class="sxs-lookup"><span data-stu-id="81c8d-141">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="81c8d-142">早期绑定和后期绑定</span><span class="sxs-lookup"><span data-stu-id="81c8d-142">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [<span data-ttu-id="81c8d-143">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="81c8d-143">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="81c8d-144">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="81c8d-144">For...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="81c8d-145">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="81c8d-145">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="81c8d-146">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="81c8d-146">/optioninfer</span></span>](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="81c8d-147">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="81c8d-147">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)

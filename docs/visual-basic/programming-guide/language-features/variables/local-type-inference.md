---
title: 局部类型推理 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: e6214938262b987a1bae4a9ca1d5c945f8b7fe6e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826816"
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="94b69-102">局部类型推理 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94b69-102">Local Type Inference (Visual Basic)</span></span>
<span data-ttu-id="94b69-103">使用 Visual Basic 编译器*类型推理*以确定未声明的局部变量的数据类型`As`子句。</span><span class="sxs-lookup"><span data-stu-id="94b69-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="94b69-104">编译器将推断变量的初始化表达式的类型的类型。</span><span class="sxs-lookup"><span data-stu-id="94b69-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="94b69-105">这使您无需显式声明一个类型，声明变量，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="94b69-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="94b69-106">由于声明，而两者`num1`和`num2`强类型为整数。</span><span class="sxs-lookup"><span data-stu-id="94b69-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
 
> [!NOTE]
>  <span data-ttu-id="94b69-107">如果不希望`num2`在前面的示例以类型化为`Integer`，可以通过使用声明，例如指定另一种类型`Dim num3 As Object = 3`或`Dim num4 As Double = 3`。</span><span class="sxs-lookup"><span data-stu-id="94b69-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>  

> [!NOTE]
>  <span data-ttu-id="94b69-108">类型推断可仅用于非静态局部变量;它不能用于确定类字段、 属性或函数的类型。</span><span class="sxs-lookup"><span data-stu-id="94b69-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>
 
 <span data-ttu-id="94b69-109">局部类型推理在过程级别进行应用。</span><span class="sxs-lookup"><span data-stu-id="94b69-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="94b69-110">它不能用于声明在模块级别 （在类、 结构、 模块或接口，但不是在过程或块） 的变量。</span><span class="sxs-lookup"><span data-stu-id="94b69-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="94b69-111">如果`num2`上一示例中而不是一个过程中的本地变量类的字段，声明会导致出错`Option Strict`，并将对其分类`num2`作为`Object`与`Option Strict`关闭。</span><span class="sxs-lookup"><span data-stu-id="94b69-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="94b69-112">同样，局部类型推理不适用于过程级变量声明为`Static`。</span><span class="sxs-lookup"><span data-stu-id="94b69-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>  
  
## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="94b69-113">类型推理与。后期绑定</span><span class="sxs-lookup"><span data-stu-id="94b69-113">Type Inference vs. Late Binding</span></span>  
 <span data-ttu-id="94b69-114">使用类型推理的代码类似于依赖后期绑定代码。</span><span class="sxs-lookup"><span data-stu-id="94b69-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="94b69-115">但是，类型推断为强类型的变量而不是将其保留为`Object`。</span><span class="sxs-lookup"><span data-stu-id="94b69-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="94b69-116">编译器使用变量的初始值设定项来确定在编译时生成早期绑定代码变量的类型。</span><span class="sxs-lookup"><span data-stu-id="94b69-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="94b69-117">在上一示例中， `num2`，例如`num1`，类型化为`Integer`。</span><span class="sxs-lookup"><span data-stu-id="94b69-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>  
  
 <span data-ttu-id="94b69-118">早期绑定的变量的行为不同于后期绑定变量，并仅在运行时知道它的类型。</span><span class="sxs-lookup"><span data-stu-id="94b69-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="94b69-119">尽早知道类型使编译器能够识别问题，然后执行、 准确地说，分配的内存和执行其他优化。</span><span class="sxs-lookup"><span data-stu-id="94b69-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="94b69-120">早期绑定还使 Visual Basic 的集成的开发环境 (IDE)，IntelliSense 将帮助提供有关对象的成员。</span><span class="sxs-lookup"><span data-stu-id="94b69-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="94b69-121">早期绑定也是首选的性能。</span><span class="sxs-lookup"><span data-stu-id="94b69-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="94b69-122">这是因为后期绑定变量中存储的所有数据都必须为类型都包装`Object`，并在运行时访问该类型的成员使程序运行较慢。</span><span class="sxs-lookup"><span data-stu-id="94b69-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="94b69-123">示例</span><span class="sxs-lookup"><span data-stu-id="94b69-123">Examples</span></span>  
 <span data-ttu-id="94b69-124">未声明本地变量时，会发生类型推理`As`子句和初始化。</span><span class="sxs-lookup"><span data-stu-id="94b69-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="94b69-125">编译器使用已分配的初始值的类型作为变量的类型。</span><span class="sxs-lookup"><span data-stu-id="94b69-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="94b69-126">例如，以下代码行的每个声明类型的变量的`String`。</span><span class="sxs-lookup"><span data-stu-id="94b69-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]  
  
 <span data-ttu-id="94b69-127">下面的代码演示两个等效方法来创建整数数组。</span><span class="sxs-lookup"><span data-stu-id="94b69-127">The following code demonstrates two equivalent ways to create an array of integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]  
  
 <span data-ttu-id="94b69-128">它可以方便地使用类型推理来确定循环控制变量的类型。</span><span class="sxs-lookup"><span data-stu-id="94b69-128">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="94b69-129">在下面的代码中，编译器推断`number`是`Integer`因为`someNumbers2`上一示例中是一个整数数组。</span><span class="sxs-lookup"><span data-stu-id="94b69-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]  
  
 <span data-ttu-id="94b69-130">可以在使用局部类型推理`Using`语句，以建立资源名称的类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="94b69-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]  
  
 <span data-ttu-id="94b69-131">如以下示例所示，还可以从函数的返回值推断变量类型。</span><span class="sxs-lookup"><span data-stu-id="94b69-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="94b69-132">这两`pList1`并`pList2`是数组的进程，因为`Process.GetProcesses`返回进程的数组。</span><span class="sxs-lookup"><span data-stu-id="94b69-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]  
  
## <a name="option-infer"></a><span data-ttu-id="94b69-133">Option Infer</span><span class="sxs-lookup"><span data-stu-id="94b69-133">Option Infer</span></span>  
 <span data-ttu-id="94b69-134">`Option Infer` 允许指定特定文件中是否允许在局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="94b69-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="94b69-135">若要启用或阻止该选项，请在文件的开头键入以下语句之一。</span><span class="sxs-lookup"><span data-stu-id="94b69-135">To enable or to block the option, type one of the following statements at the start of the file.</span></span>  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 <span data-ttu-id="94b69-136">如果未指定的值`Option Infer`在代码中，编译器默认设置是`Option Infer On`。</span><span class="sxs-lookup"><span data-stu-id="94b69-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span> <span data-ttu-id="94b69-137">有关从升级项目[!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)]或更早版本，编译器默认`Option Infer Off`。</span><span class="sxs-lookup"><span data-stu-id="94b69-137">For projects upgraded from [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] or earlier, the compiler default is `Option Infer Off`.</span></span>  
  
 <span data-ttu-id="94b69-138">如果为文件中 `Option Infer` 设置的值与在 IDE 中或在命令行上设置的值冲突，则文件中的值优先。</span><span class="sxs-lookup"><span data-stu-id="94b69-138">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="94b69-139">有关详细信息，请参阅[Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)并[编译页，项目设计器 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="94b69-139">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b69-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="94b69-140">See also</span></span>

- [<span data-ttu-id="94b69-141">匿名类型</span><span class="sxs-lookup"><span data-stu-id="94b69-141">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="94b69-142">早期绑定和后期绑定</span><span class="sxs-lookup"><span data-stu-id="94b69-142">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="94b69-143">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="94b69-143">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="94b69-144">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="94b69-144">For...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="94b69-145">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="94b69-145">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="94b69-146">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="94b69-146">/optioninfer</span></span>](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="94b69-147">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="94b69-147">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)

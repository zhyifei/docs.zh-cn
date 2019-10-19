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
ms.openlocfilehash: 26df91229f7c640f53fcc018d881f7d24baf7e42
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582455"
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="9b8a7-102">局部类型推理 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b8a7-102">Local Type Inference (Visual Basic)</span></span>

<span data-ttu-id="9b8a7-103">Visual Basic 编译器使用*类型推理*来确定不使用 `As` 子句声明的局部变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="9b8a7-104">编译器从初始化表达式的类型推断出变量的类型。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="9b8a7-105">这样，便可以在不显式声明类型的情况下声明变量，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="9b8a7-106">作为声明的结果，`num1` 和 `num2` 都作为整数强类型化。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>

[!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="9b8a7-107">如果您不希望在前一示例中将 `num2` 类型化为 `Integer`，则可以使用 `Dim num3 As Object = 3` 或 `Dim num4 As Double = 3` 之类的声明来指定另一种类型。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>

> [!NOTE]
> <span data-ttu-id="9b8a7-108">类型推理只能用于非静态局部变量;它不能用于确定类字段、属性或函数的类型。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>

<span data-ttu-id="9b8a7-109">局部类型推理适用于过程级别。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="9b8a7-110">它不能用于在模块级别（在类、结构、模块或接口中，而不是在过程或块中）声明变量。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="9b8a7-111">如果上一个示例中 `num2` 是某个类的一个字段，而不是过程中的局部变量，则该声明将导致与 `Option Strict` 出现错误，并将 `num2` 分类为 `Object` `Option Strict` off。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="9b8a7-112">同样，局部类型推理不适用于声明为 `Static` 的过程级变量。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>

## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="9b8a7-113">类型推理与后期绑定</span><span class="sxs-lookup"><span data-stu-id="9b8a7-113">Type Inference vs. Late Binding</span></span>

<span data-ttu-id="9b8a7-114">使用类型推理的代码与依赖后期绑定的代码类似。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="9b8a7-115">但是，类型推理强类型变量，而不是将其保留为 `Object`。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="9b8a7-116">编译器在编译时使用变量的初始值设定项来确定变量的类型以生成早期绑定的代码。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="9b8a7-117">在前面的示例中，`num2` （如 `num1`）被类型化为 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>

<span data-ttu-id="9b8a7-118">早期绑定变量的行为与后期绑定变量的行为不同，后者的类型仅在运行时已知。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="9b8a7-119">事先知道类型使编译器能够在执行之前识别问题，精确分配内存并执行其他优化。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="9b8a7-120">早期绑定还允许 Visual Basic 集成开发环境（IDE）为对象的成员提供 IntelliSense 帮助。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="9b8a7-121">早期绑定也是性能的首选。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="9b8a7-122">这是因为，后期绑定变量中存储的所有数据都必须包装为类型 `Object`，并且在运行时访问该类型的成员会使程序速度变慢。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>

## <a name="examples"></a><span data-ttu-id="9b8a7-123">示例</span><span class="sxs-lookup"><span data-stu-id="9b8a7-123">Examples</span></span>

<span data-ttu-id="9b8a7-124">如果在不使用 `As` 子句的情况下声明了本地变量并进行了初始化，则会发生类型推理。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="9b8a7-125">编译器使用所赋的初始值的类型作为变量的类型。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="9b8a7-126">例如，以下每行代码都声明一个 `String` 类型的变量。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>

[!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]

<span data-ttu-id="9b8a7-127">下面的代码演示了两种创建整数数组的等效方法。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-127">The following code demonstrates two equivalent ways to create an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]

<span data-ttu-id="9b8a7-128">使用类型推理来确定循环控制变量的类型是一种很方便的方法。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-128">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="9b8a7-129">在下面的代码中，编译器将推断 `number` 是 `Integer`，因为上一示例中的 `someNumbers2` 是整数数组。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]

<span data-ttu-id="9b8a7-130">可以在 `Using` 语句中使用局部类型推理来建立资源名称的类型，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>

[!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]

<span data-ttu-id="9b8a7-131">还可以从函数的返回值推断变量的类型，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="9b8a7-132">@No__t_0 和 `pList2` 都是进程的数组，因为 `Process.GetProcesses` 返回进程的数组。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>

[!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]

## <a name="option-infer"></a><span data-ttu-id="9b8a7-133">选项推断</span><span class="sxs-lookup"><span data-stu-id="9b8a7-133">Option Infer</span></span>

<span data-ttu-id="9b8a7-134">`Option Infer` 使你可以指定是否允许在特定文件中执行局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="9b8a7-135">若要启用或阻止该选项，请在文件开头键入以下语句之一。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-135">To enable or to block the option, type one of the following statements at the start of the file.</span></span>

`Option Infer On`

`Option Infer Off`

<span data-ttu-id="9b8a7-136">如果在代码中未指定 `Option Infer` 的值，则将 `Option Infer On` 编译器默认值。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span>

<span data-ttu-id="9b8a7-137">如果为文件中 `Option Infer` 设置的值与在 IDE 中或在命令行上设置的值冲突，则文件中的值优先。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-137">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>

<span data-ttu-id="9b8a7-138">有关详细信息，请参阅[选项推断语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)和[编译页，项目设计器（Visual Basic）](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="9b8a7-138">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>

## <a name="see-also"></a><span data-ttu-id="9b8a7-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b8a7-139">See also</span></span>

- [<span data-ttu-id="9b8a7-140">匿名类型</span><span class="sxs-lookup"><span data-stu-id="9b8a7-140">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="9b8a7-141">早期绑定和后期绑定</span><span class="sxs-lookup"><span data-stu-id="9b8a7-141">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="9b8a7-142">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="9b8a7-142">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="9b8a7-143">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="9b8a7-143">For...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="9b8a7-144">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="9b8a7-144">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="9b8a7-145">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="9b8a7-145">/optioninfer</span></span>](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="9b8a7-146">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="9b8a7-146">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)

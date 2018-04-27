---
title: Option Infer 语句
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.OptionInfer
- vb.Infer
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement [Visual Basic]
- Infer keyword [Visual Basic]
- declaring variables [Visual Basic], inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
caps.latest.revision: 72
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb6aea2b1e8faf9afd7d252d8828358130fb5374
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="option-infer-statement"></a><span data-ttu-id="5def3-102">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="5def3-102">Option Infer Statement</span></span>
<span data-ttu-id="5def3-103">允许声明变量时使用局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="5def3-103">Enables the use of local type inference in declaring variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5def3-104">语法</span><span class="sxs-lookup"><span data-stu-id="5def3-104">Syntax</span></span>  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="5def3-105">部件</span><span class="sxs-lookup"><span data-stu-id="5def3-105">Parts</span></span>  
  
|<span data-ttu-id="5def3-106">术语</span><span class="sxs-lookup"><span data-stu-id="5def3-106">Term</span></span>|<span data-ttu-id="5def3-107">定义</span><span class="sxs-lookup"><span data-stu-id="5def3-107">Definition</span></span>|  
|---|---|  
|`On`|<span data-ttu-id="5def3-108">可选。</span><span class="sxs-lookup"><span data-stu-id="5def3-108">Optional.</span></span> <span data-ttu-id="5def3-109">启用局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="5def3-109">Enables local type inference.</span></span>|  
|`Off`|<span data-ttu-id="5def3-110">可选。</span><span class="sxs-lookup"><span data-stu-id="5def3-110">Optional.</span></span> <span data-ttu-id="5def3-111">禁用局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="5def3-111">Disables local type inference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5def3-112">备注</span><span class="sxs-lookup"><span data-stu-id="5def3-112">Remarks</span></span>  
 <span data-ttu-id="5def3-113">若要在文件中设置 `Option Infer`，请在任何其他源代码之前、文件顶部键入 `Option Infer On` 或 `Option Infer Off`。</span><span class="sxs-lookup"><span data-stu-id="5def3-113">To set `Option Infer` in a file, type `Option Infer On` or `Option Infer Off` at the top of the file, before any other source code.</span></span> <span data-ttu-id="5def3-114">如果为文件中 `Option Infer` 设置的值与在 IDE 中或在命令行上设置的值冲突，则文件中的值优先。</span><span class="sxs-lookup"><span data-stu-id="5def3-114">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="5def3-115">将 `Option Infer` 设置为 `On`时，你可以无需显式声明数据类型就声明本地变量。</span><span class="sxs-lookup"><span data-stu-id="5def3-115">When you set `Option Infer` to `On`, you can declare local variables without explicitly stating a data type.</span></span> <span data-ttu-id="5def3-116">编译器会从其初始化表达式的类型推断出变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5def3-116">The compiler infers the data type of a variable from the type of its initialization expression.</span></span>  
  
 <span data-ttu-id="5def3-117">在下图中，`Option Infer` 处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="5def3-117">In the following illustration, `Option Infer` is turned on.</span></span> <span data-ttu-id="5def3-118">声明 `Dim someVar = 2` 中的变量由类型推理声明为整数。</span><span class="sxs-lookup"><span data-stu-id="5def3-118">The variable in the declaration `Dim someVar = 2` is declared as an integer by type inference.</span></span>  
  
 <span data-ttu-id="5def3-119">![声明的 IntelliSense 视图。] (../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span><span class="sxs-lookup"><span data-stu-id="5def3-119">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span></span>  
<span data-ttu-id="5def3-120">Option Infer 处于打开状态时的 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="5def3-120">IntelliSense when Option Infer is on</span></span>  
  
 <span data-ttu-id="5def3-121">在下图中，`Option Infer` 处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="5def3-121">In the following illustration, `Option Infer` is turned off.</span></span> <span data-ttu-id="5def3-122">声明 `Dim someVar = 2` 中的变量由类型推理声明为 `Object`。</span><span class="sxs-lookup"><span data-stu-id="5def3-122">The variable in the declaration `Dim someVar = 2` is declared as an `Object` by type inference.</span></span> <span data-ttu-id="5def3-123">在此示例中， **Option Strict**设置设为**关闭**上[编译页，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="5def3-123">In this example, the **Option Strict** setting is set to **Off** on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="5def3-124">![声明的 IntelliSense 视图。] (../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span><span class="sxs-lookup"><span data-stu-id="5def3-124">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span></span>  
<span data-ttu-id="5def3-125">Option Infer 处于关闭状态时的 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="5def3-125">IntelliSense when Option Infer is off</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5def3-126">变量声明为 `Object` 时，可在程序运行时更改运行时类型。</span><span class="sxs-lookup"><span data-stu-id="5def3-126">When a variable is declared as an `Object`, the run-time type can change while the program is running.</span></span> <span data-ttu-id="5def3-127">Visual Basic 执行调用的操作*装箱*和*取消装箱*之间进行转换`Object`和值类型，这会使执行速度较慢。</span><span class="sxs-lookup"><span data-stu-id="5def3-127">Visual Basic performs operations called *boxing* and *unboxing* to convert between an `Object` and a value type, which makes execution slower.</span></span> <span data-ttu-id="5def3-128">有关装箱和取消装箱的信息，请参阅[Visual Basic 语言规范](../../../visual-basic/reference/language-specification/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5def3-128">For information about boxing and unboxing, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification/index.md).</span></span>
  
 <span data-ttu-id="5def3-129">类型推理适用于过程级，且在类、结构、模块或接口中的过程之外不适用。</span><span class="sxs-lookup"><span data-stu-id="5def3-129">Type inference applies at the procedure level, and does not apply outside a procedure in a class, structure, module, or interface.</span></span>  
  
 <span data-ttu-id="5def3-130">有关其他信息，请参阅[本地类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="5def3-130">For additional information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="when-an-option-infer-statement-is-not-present"></a><span data-ttu-id="5def3-131">当 Option Infer 语句不存在时</span><span class="sxs-lookup"><span data-stu-id="5def3-131">When an Option Infer Statement Is Not Present</span></span>  
 <span data-ttu-id="5def3-132">如果源代码不包含`Option Infer`语句， **Option Infer**上设置[编译页，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)使用。</span><span class="sxs-lookup"><span data-stu-id="5def3-132">If the source code does not contain an `Option Infer` statement, the **Option Infer** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="5def3-133">如果使用命令行编译器， [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)使用编译器选项。</span><span class="sxs-lookup"><span data-stu-id="5def3-133">If the command-line compiler is used, the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-infer-in-the-ide"></a><span data-ttu-id="5def3-134">若要在 IDE 中设置 Option Infer</span><span class="sxs-lookup"><span data-stu-id="5def3-134">To set Option Infer in the IDE</span></span>  
  
1.  <span data-ttu-id="5def3-135">在“解决方案资源管理器”中，选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="5def3-135">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="5def3-136">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="5def3-136">On the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="5def3-137">单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="5def3-137">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="5def3-138">设置中的值**Option infer**框。</span><span class="sxs-lookup"><span data-stu-id="5def3-138">Set the value in the **Option infer** box.</span></span>  
  
 <span data-ttu-id="5def3-139">当创建新项目， **Option Infer**上设置**编译**选项卡设置为**Option Infer**中设置**VB 默认值**对话框。</span><span class="sxs-lookup"><span data-stu-id="5def3-139">When you create a new project, the **Option Infer** setting on the **Compile** tab is set to the **Option Infer** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="5def3-140">访问**VB 默认值**对话框中，在**工具**菜单上，单击**选项**。</span><span class="sxs-lookup"><span data-stu-id="5def3-140">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="5def3-141">在“选项”对话框中，展开“项目和解决方案”，然后单击“VB 默认值”。</span><span class="sxs-lookup"><span data-stu-id="5def3-141">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="5def3-142">中的初始默认设置**VB 默认值**是`On`。</span><span class="sxs-lookup"><span data-stu-id="5def3-142">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-infer-on-the-command-line"></a><span data-ttu-id="5def3-143">若要设置命令行上的 Option Infer</span><span class="sxs-lookup"><span data-stu-id="5def3-143">To set Option Infer on the command line</span></span>  
  
-   <span data-ttu-id="5def3-144">包括[/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)中的编译器选项**vbc**命令。</span><span class="sxs-lookup"><span data-stu-id="5def3-144">Include the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="default-data-types-and-values"></a><span data-ttu-id="5def3-145">默认数据类型和值</span><span class="sxs-lookup"><span data-stu-id="5def3-145">Default Data Types and Values</span></span>  
 <span data-ttu-id="5def3-146">下表描述了指定 `Dim` 语句中数据类型和初始值设定项的各种组合的结果。</span><span class="sxs-lookup"><span data-stu-id="5def3-146">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="5def3-147">是否指定数据类型？</span><span class="sxs-lookup"><span data-stu-id="5def3-147">Data type specified?</span></span>|<span data-ttu-id="5def3-148">是否指定初始值设定项？</span><span class="sxs-lookup"><span data-stu-id="5def3-148">Initializer specified?</span></span>|<span data-ttu-id="5def3-149">示例</span><span class="sxs-lookup"><span data-stu-id="5def3-149">Example</span></span>|<span data-ttu-id="5def3-150">结果</span><span class="sxs-lookup"><span data-stu-id="5def3-150">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="5def3-151">否</span><span class="sxs-lookup"><span data-stu-id="5def3-151">No</span></span>|<span data-ttu-id="5def3-152">否</span><span class="sxs-lookup"><span data-stu-id="5def3-152">No</span></span>|`Dim qty`|<span data-ttu-id="5def3-153">如果 `Option Strict` 处于关闭状态（默认），则将变量设置为 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="5def3-153">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="5def3-154">如果 `Option Strict` 处于打开状态，则发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="5def3-154">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="5def3-155">否</span><span class="sxs-lookup"><span data-stu-id="5def3-155">No</span></span>|<span data-ttu-id="5def3-156">是</span><span class="sxs-lookup"><span data-stu-id="5def3-156">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="5def3-157">如果 `Option Infer` 处于打开状态（默认），则变量采用初始值设定项的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5def3-157">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="5def3-158">请参阅[局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="5def3-158">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="5def3-159">如果 `Option Infer` 和 `Option Strict` 均处于关闭状态，则变量采用 `Object` 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5def3-159">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="5def3-160">如果 `Option Infer` 处于关闭状态但 `Option Strict` 处于打开状态，则发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="5def3-160">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="5def3-161">是</span><span class="sxs-lookup"><span data-stu-id="5def3-161">Yes</span></span>|<span data-ttu-id="5def3-162">否</span><span class="sxs-lookup"><span data-stu-id="5def3-162">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="5def3-163">将变量初始化为数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="5def3-163">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="5def3-164">有关详细信息，请参阅[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="5def3-164">For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>|  
|<span data-ttu-id="5def3-165">是</span><span class="sxs-lookup"><span data-stu-id="5def3-165">Yes</span></span>|<span data-ttu-id="5def3-166">是</span><span class="sxs-lookup"><span data-stu-id="5def3-166">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="5def3-167">如果初始值设定项的数据类型不可转换为指定数据类型，则会发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="5def3-167">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5def3-168">示例</span><span class="sxs-lookup"><span data-stu-id="5def3-168">Example</span></span>  
 <span data-ttu-id="5def3-169">下例演示了 `Option Infer` 语句启用局部类型推理的方式。</span><span class="sxs-lookup"><span data-stu-id="5def3-169">The following examples demonstrate how the `Option Infer` statement enables local type inference.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="5def3-170">示例</span><span class="sxs-lookup"><span data-stu-id="5def3-170">Example</span></span>  
 <span data-ttu-id="5def3-171">下例演示了变量被标识为 `Object` 时运行时类型可以改变的情况。</span><span class="sxs-lookup"><span data-stu-id="5def3-171">The following example demonstrates that the run-time type can differ when a variable is identified as an `Object`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#11](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5def3-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="5def3-172">See Also</span></span>  
 [<span data-ttu-id="5def3-173">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="5def3-173">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="5def3-174">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="5def3-174">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="5def3-175">Option Compare 语句</span><span class="sxs-lookup"><span data-stu-id="5def3-175">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="5def3-176">Option Explicit 语句</span><span class="sxs-lookup"><span data-stu-id="5def3-176">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="5def3-177">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="5def3-177">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="5def3-178">“选项”对话框 ->“项目”->“Visual Basic 默认值”</span><span class="sxs-lookup"><span data-stu-id="5def3-178">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)  
 [<span data-ttu-id="5def3-179">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="5def3-179">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="5def3-180">装箱和取消装箱</span><span class="sxs-lookup"><span data-stu-id="5def3-180">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)

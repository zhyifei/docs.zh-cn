---
title: "Option Infer 语句"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
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
caps.latest.revision: "72"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4634c198b5fc41a4834cbd3cd96f9d3f1863d09b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="option-infer-statement"></a><span data-ttu-id="982f5-102">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="982f5-102">Option Infer Statement</span></span>
<span data-ttu-id="982f5-103">允许声明变量时使用局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="982f5-103">Enables the use of local type inference in declaring variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="982f5-104">语法</span><span class="sxs-lookup"><span data-stu-id="982f5-104">Syntax</span></span>  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="982f5-105">部件</span><span class="sxs-lookup"><span data-stu-id="982f5-105">Parts</span></span>  
  
|<span data-ttu-id="982f5-106">术语</span><span class="sxs-lookup"><span data-stu-id="982f5-106">Term</span></span>|<span data-ttu-id="982f5-107">定义</span><span class="sxs-lookup"><span data-stu-id="982f5-107">Definition</span></span>|  
|---|---|  
|`On`|<span data-ttu-id="982f5-108">可选。</span><span class="sxs-lookup"><span data-stu-id="982f5-108">Optional.</span></span> <span data-ttu-id="982f5-109">启用局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="982f5-109">Enables local type inference.</span></span>|  
|`Off`|<span data-ttu-id="982f5-110">可选。</span><span class="sxs-lookup"><span data-stu-id="982f5-110">Optional.</span></span> <span data-ttu-id="982f5-111">禁用局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="982f5-111">Disables local type inference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="982f5-112">备注</span><span class="sxs-lookup"><span data-stu-id="982f5-112">Remarks</span></span>  
 <span data-ttu-id="982f5-113">若要在文件中设置 `Option Infer`，请在任何其他源代码之前、文件顶部键入 `Option Infer On` 或 `Option Infer Off`。</span><span class="sxs-lookup"><span data-stu-id="982f5-113">To set `Option Infer` in a file, type `Option Infer On` or `Option Infer Off` at the top of the file, before any other source code.</span></span> <span data-ttu-id="982f5-114">如果为文件中 `Option Infer` 设置的值与在 IDE 中或在命令行上设置的值冲突，则文件中的值优先。</span><span class="sxs-lookup"><span data-stu-id="982f5-114">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="982f5-115">将 `Option Infer` 设置为 `On`时，你可以无需显式声明数据类型就声明本地变量。</span><span class="sxs-lookup"><span data-stu-id="982f5-115">When you set `Option Infer` to `On`, you can declare local variables without explicitly stating a data type.</span></span> <span data-ttu-id="982f5-116">编译器会从其初始化表达式的类型推断出变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="982f5-116">The compiler infers the data type of a variable from the type of its initialization expression.</span></span>  
  
 <span data-ttu-id="982f5-117">在下图中，`Option Infer` 处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="982f5-117">In the following illustration, `Option Infer` is turned on.</span></span> <span data-ttu-id="982f5-118">声明 `Dim someVar = 2` 中的变量由类型推理声明为整数。</span><span class="sxs-lookup"><span data-stu-id="982f5-118">The variable in the declaration `Dim someVar = 2` is declared as an integer by type inference.</span></span>  
  
 <span data-ttu-id="982f5-119">![声明的 IntelliSense 视图。] (../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span><span class="sxs-lookup"><span data-stu-id="982f5-119">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span></span>  
<span data-ttu-id="982f5-120">Option Infer 处于打开状态时的 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="982f5-120">IntelliSense when Option Infer is on</span></span>  
  
 <span data-ttu-id="982f5-121">在下图中，`Option Infer` 处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="982f5-121">In the following illustration, `Option Infer` is turned off.</span></span> <span data-ttu-id="982f5-122">声明 `Dim someVar = 2` 中的变量由类型推理声明为 `Object`。</span><span class="sxs-lookup"><span data-stu-id="982f5-122">The variable in the declaration `Dim someVar = 2` is declared as an `Object` by type inference.</span></span> <span data-ttu-id="982f5-123">在此示例中， **Option Strict**设置设为**关闭**上[编译页，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="982f5-123">In this example, the **Option Strict** setting is set to **Off** on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="982f5-124">![声明的 IntelliSense 视图。] (../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span><span class="sxs-lookup"><span data-stu-id="982f5-124">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span></span>  
<span data-ttu-id="982f5-125">Option Infer 处于关闭状态时的 IntelliSense</span><span class="sxs-lookup"><span data-stu-id="982f5-125">IntelliSense when Option Infer is off</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="982f5-126">变量声明为 `Object` 时，可在程序运行时更改运行时类型。</span><span class="sxs-lookup"><span data-stu-id="982f5-126">When a variable is declared as an `Object`, the run-time type can change while the program is running.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="982f5-127">执行操作调用*装箱*和*取消装箱*之间进行转换`Object`和值类型，这会使执行速度较慢。</span><span class="sxs-lookup"><span data-stu-id="982f5-127"> performs operations called *boxing* and *unboxing* to convert between an `Object` and a value type, which makes execution slower.</span></span> <span data-ttu-id="982f5-128">有关装箱和取消装箱的信息，请参阅[Visual Basic 语言规范](../../../visual-basic/reference/language-specification/index.md)。</span><span class="sxs-lookup"><span data-stu-id="982f5-128">For information about boxing and unboxing, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification/index.md).</span></span>
  
 <span data-ttu-id="982f5-129">类型推理适用于过程级，且在类、结构、模块或接口中的过程之外不适用。</span><span class="sxs-lookup"><span data-stu-id="982f5-129">Type inference applies at the procedure level, and does not apply outside a procedure in a class, structure, module, or interface.</span></span>  
  
 <span data-ttu-id="982f5-130">有关其他信息，请参阅[本地类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="982f5-130">For additional information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="when-an-option-infer-statement-is-not-present"></a><span data-ttu-id="982f5-131">当 Option Infer 语句不存在时</span><span class="sxs-lookup"><span data-stu-id="982f5-131">When an Option Infer Statement Is Not Present</span></span>  
 <span data-ttu-id="982f5-132">如果源代码不包含`Option Infer`语句， **Option Infer**上设置[编译页，项目设计器 (Visual Basic 中)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)使用。</span><span class="sxs-lookup"><span data-stu-id="982f5-132">If the source code does not contain an `Option Infer` statement, the **Option Infer** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="982f5-133">如果使用命令行编译器， [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)使用编译器选项。</span><span class="sxs-lookup"><span data-stu-id="982f5-133">If the command-line compiler is used, the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-infer-in-the-ide"></a><span data-ttu-id="982f5-134">若要在 IDE 中设置 Option Infer</span><span class="sxs-lookup"><span data-stu-id="982f5-134">To set Option Infer in the IDE</span></span>  
  
1.  <span data-ttu-id="982f5-135">在“解决方案资源管理器”中，选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="982f5-135">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="982f5-136">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="982f5-136">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="982f5-137">有关详细信息，请参阅[NIB： 项目设计器用管理项目属性](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e)。</span><span class="sxs-lookup"><span data-stu-id="982f5-137">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="982f5-138">单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="982f5-138">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="982f5-139">设置中的值**Option infer**框。</span><span class="sxs-lookup"><span data-stu-id="982f5-139">Set the value in the **Option infer** box.</span></span>  
  
 <span data-ttu-id="982f5-140">当创建新项目， **Option Infer**上设置**编译**选项卡设置为**Option Infer**中设置**VB 默认值**对话框。</span><span class="sxs-lookup"><span data-stu-id="982f5-140">When you create a new project, the **Option Infer** setting on the **Compile** tab is set to the **Option Infer** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="982f5-141">访问**VB 默认值**对话框中，在**工具**菜单上，单击**选项**。</span><span class="sxs-lookup"><span data-stu-id="982f5-141">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="982f5-142">在**选项**对话框框中，展开**项目和解决方案**，然后单击**VB 默认值**。</span><span class="sxs-lookup"><span data-stu-id="982f5-142">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="982f5-143">中的初始默认设置**VB 默认值**是`On`。</span><span class="sxs-lookup"><span data-stu-id="982f5-143">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-infer-on-the-command-line"></a><span data-ttu-id="982f5-144">若要设置命令行上的 Option Infer</span><span class="sxs-lookup"><span data-stu-id="982f5-144">To set Option Infer on the command line</span></span>  
  
-   <span data-ttu-id="982f5-145">包括[/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)中的编译器选项**vbc**命令。</span><span class="sxs-lookup"><span data-stu-id="982f5-145">Include the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="default-data-types-and-values"></a><span data-ttu-id="982f5-146">默认数据类型和值</span><span class="sxs-lookup"><span data-stu-id="982f5-146">Default Data Types and Values</span></span>  
 <span data-ttu-id="982f5-147">下表描述了指定 `Dim` 语句中数据类型和初始值设定项的各种组合的结果。</span><span class="sxs-lookup"><span data-stu-id="982f5-147">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="982f5-148">是否指定数据类型？</span><span class="sxs-lookup"><span data-stu-id="982f5-148">Data type specified?</span></span>|<span data-ttu-id="982f5-149">是否指定初始值设定项？</span><span class="sxs-lookup"><span data-stu-id="982f5-149">Initializer specified?</span></span>|<span data-ttu-id="982f5-150">示例</span><span class="sxs-lookup"><span data-stu-id="982f5-150">Example</span></span>|<span data-ttu-id="982f5-151">结果</span><span class="sxs-lookup"><span data-stu-id="982f5-151">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="982f5-152">否</span><span class="sxs-lookup"><span data-stu-id="982f5-152">No</span></span>|<span data-ttu-id="982f5-153">否</span><span class="sxs-lookup"><span data-stu-id="982f5-153">No</span></span>|`Dim qty`|<span data-ttu-id="982f5-154">如果 `Option Strict` 处于关闭状态（默认），则将变量设置为 `Nothing`。</span><span class="sxs-lookup"><span data-stu-id="982f5-154">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="982f5-155">如果 `Option Strict` 处于打开状态，则发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="982f5-155">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="982f5-156">否</span><span class="sxs-lookup"><span data-stu-id="982f5-156">No</span></span>|<span data-ttu-id="982f5-157">是</span><span class="sxs-lookup"><span data-stu-id="982f5-157">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="982f5-158">如果 `Option Infer` 处于打开状态（默认），则变量采用初始值设定项的数据类型。</span><span class="sxs-lookup"><span data-stu-id="982f5-158">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="982f5-159">请参阅[局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="982f5-159">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="982f5-160">如果 `Option Infer` 和 `Option Strict` 均处于关闭状态，则变量采用 `Object` 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="982f5-160">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="982f5-161">如果 `Option Infer` 处于关闭状态但 `Option Strict` 处于打开状态，则发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="982f5-161">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="982f5-162">是</span><span class="sxs-lookup"><span data-stu-id="982f5-162">Yes</span></span>|<span data-ttu-id="982f5-163">否</span><span class="sxs-lookup"><span data-stu-id="982f5-163">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="982f5-164">将变量初始化为数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="982f5-164">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="982f5-165">有关详细信息，请参阅[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="982f5-165">For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>|  
|<span data-ttu-id="982f5-166">是</span><span class="sxs-lookup"><span data-stu-id="982f5-166">Yes</span></span>|<span data-ttu-id="982f5-167">是</span><span class="sxs-lookup"><span data-stu-id="982f5-167">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="982f5-168">如果初始值设定项的数据类型不可转换为指定数据类型，则会发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="982f5-168">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="982f5-169">示例</span><span class="sxs-lookup"><span data-stu-id="982f5-169">Example</span></span>  
 <span data-ttu-id="982f5-170">下例演示了 `Option Infer` 语句启用局部类型推理的方式。</span><span class="sxs-lookup"><span data-stu-id="982f5-170">The following examples demonstrate how the `Option Infer` statement enables local type inference.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="982f5-171">示例</span><span class="sxs-lookup"><span data-stu-id="982f5-171">Example</span></span>  
 <span data-ttu-id="982f5-172">下例演示了变量被标识为 `Object` 时运行时类型可以改变的情况。</span><span class="sxs-lookup"><span data-stu-id="982f5-172">The following example demonstrates that the run-time type can differ when a variable is identified as an `Object`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#11](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="982f5-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="982f5-173">See Also</span></span>  
 [<span data-ttu-id="982f5-174">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="982f5-174">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="982f5-175">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="982f5-175">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="982f5-176">Option Compare 语句</span><span class="sxs-lookup"><span data-stu-id="982f5-176">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="982f5-177">Option Explicit 语句</span><span class="sxs-lookup"><span data-stu-id="982f5-177">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="982f5-178">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="982f5-178">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="982f5-179">“选项”对话框 ->“项目”->“Visual Basic 默认值”</span><span class="sxs-lookup"><span data-stu-id="982f5-179">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)  
 [<span data-ttu-id="982f5-180">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="982f5-180">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="982f5-181">装箱和取消装箱</span><span class="sxs-lookup"><span data-stu-id="982f5-181">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)

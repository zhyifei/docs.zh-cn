---
title: Visual Basic 中的条件编译
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 828edf2e5491394f5ac802b5c9babfb3df359e59
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967841"
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="91236-102">Visual Basic 中的条件编译</span><span class="sxs-lookup"><span data-stu-id="91236-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="91236-103">在中*条件编译*，而其他人将被忽略，将有选择地编译特定程序中的代码块。</span><span class="sxs-lookup"><span data-stu-id="91236-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="91236-104">例如，你可能想要编写调试语句来比较不同的方法的速度到相同的编程任务，也可能想要本地化为多种语言的应用程序。</span><span class="sxs-lookup"><span data-stu-id="91236-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="91236-105">条件编译语句被设计为在编译时，不是在运行时期间运行。</span><span class="sxs-lookup"><span data-stu-id="91236-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="91236-106">表示用于使用有条件地编译的代码块`#If...Then...#Else`指令。</span><span class="sxs-lookup"><span data-stu-id="91236-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="91236-107">例如，若要创建法语和德语版本的相同应用程序的同一源代码，嵌入中特定于平台的代码段`#If...Then`使用的预定义的常量的语句`FrenchVersion`和`GermanVersion`。</span><span class="sxs-lookup"><span data-stu-id="91236-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="91236-108">下面的示例演示如何：</span><span class="sxs-lookup"><span data-stu-id="91236-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 <span data-ttu-id="91236-109">如果设置的值`FrenchVersion`条件编译常量为`True`在编译时，法语版的条件代码进行编译。</span><span class="sxs-lookup"><span data-stu-id="91236-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="91236-110">如果设置的值`GermanVersion`常量到`True`，编译器将使用德语版本。</span><span class="sxs-lookup"><span data-stu-id="91236-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="91236-111">如果未设置`True`，在最后一个代码`Else`块将运行。</span><span class="sxs-lookup"><span data-stu-id="91236-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91236-112">自动完成功能将不函数时编辑代码，并使用条件编译指令，如果代码不是当前分支的一部分。</span><span class="sxs-lookup"><span data-stu-id="91236-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="91236-113">声明条件编译常量</span><span class="sxs-lookup"><span data-stu-id="91236-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="91236-114">可以通过三种方式之一来设置条件编译常量：</span><span class="sxs-lookup"><span data-stu-id="91236-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
-   <span data-ttu-id="91236-115">在**项目设计器**</span><span class="sxs-lookup"><span data-stu-id="91236-115">In the **Project Designer**</span></span>  
  
-   <span data-ttu-id="91236-116">在命令行使用命令行编译器时</span><span class="sxs-lookup"><span data-stu-id="91236-116">At the command line when using the command-line compiler</span></span>  
  
-   <span data-ttu-id="91236-117">在代码中</span><span class="sxs-lookup"><span data-stu-id="91236-117">In your code</span></span>  
  
 <span data-ttu-id="91236-118">条件编译常量具有特殊的作用域，并且不能从标准的代码访问。</span><span class="sxs-lookup"><span data-stu-id="91236-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="91236-119">条件编译常数的范围是依赖于它的设置的方式。</span><span class="sxs-lookup"><span data-stu-id="91236-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="91236-120">下表列出了使用上面提到的三种方法的每个声明的常量的作用域。</span><span class="sxs-lookup"><span data-stu-id="91236-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="91236-121">如何设置常量</span><span class="sxs-lookup"><span data-stu-id="91236-121">How constant is set</span></span>|<span data-ttu-id="91236-122">常量的作用域</span><span class="sxs-lookup"><span data-stu-id="91236-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="91236-123">**项目设计器**</span><span class="sxs-lookup"><span data-stu-id="91236-123">**Project Designer**</span></span>|<span data-ttu-id="91236-124">在项目中的所有文件是公共的</span><span class="sxs-lookup"><span data-stu-id="91236-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="91236-125">命令行</span><span class="sxs-lookup"><span data-stu-id="91236-125">Command line</span></span>|<span data-ttu-id="91236-126">传递到命令行编译器的所有文件是公共的</span><span class="sxs-lookup"><span data-stu-id="91236-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="91236-127">`#Const` 在代码中的语句</span><span class="sxs-lookup"><span data-stu-id="91236-127">`#Const` statement in code</span></span>|<span data-ttu-id="91236-128">专用于在其中声明的文件</span><span class="sxs-lookup"><span data-stu-id="91236-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="91236-129">若要在项目设计器中设置常量</span><span class="sxs-lookup"><span data-stu-id="91236-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="91236-130">-之前创建可执行文件，在中设置常量**项目设计器**中提供的步骤[管理项目和解决方案属性](/visualstudio/ide/managing-project-and-solution-properties)。</span><span class="sxs-lookup"><span data-stu-id="91236-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="91236-131">在命令行上设置常量</span><span class="sxs-lookup"><span data-stu-id="91236-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="91236-132">-使用 **/d**开关输入条件编译常量，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="91236-132">-   Use the **/d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="91236-133">不所需之间的任何空间 **/d**开关与第一个常数。</span><span class="sxs-lookup"><span data-stu-id="91236-133">No space is required between the **/d** switch and the first constant.</span></span> <span data-ttu-id="91236-134">有关详细信息，请参阅[/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)。</span><span class="sxs-lookup"><span data-stu-id="91236-134">For more information, see [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="91236-135">命令行声明会覆盖输入声明**项目设计器**，但不是清除它们。</span><span class="sxs-lookup"><span data-stu-id="91236-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="91236-136">参数中设置**项目设计器**始终有效，对于后续编译。</span><span class="sxs-lookup"><span data-stu-id="91236-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="91236-137">时编写代码本身中的常量，没有严格的规则对其位置，因为它们的作用域是整个模块声明它们。</span><span class="sxs-lookup"><span data-stu-id="91236-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="91236-138">若要在代码中设置常量</span><span class="sxs-lookup"><span data-stu-id="91236-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="91236-139">-将常量放在声明块中使用它们的模块。</span><span class="sxs-lookup"><span data-stu-id="91236-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="91236-140">这有助于保持代码组织有序且易于阅读。</span><span class="sxs-lookup"><span data-stu-id="91236-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="91236-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="91236-141">Related Topics</span></span>  
  
|<span data-ttu-id="91236-142">标题</span><span class="sxs-lookup"><span data-stu-id="91236-142">Title</span></span>|<span data-ttu-id="91236-143">描述</span><span class="sxs-lookup"><span data-stu-id="91236-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="91236-144">程序结构和代码约定</span><span class="sxs-lookup"><span data-stu-id="91236-144">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|<span data-ttu-id="91236-145">提供有关使代码易于阅读和维护建议。</span><span class="sxs-lookup"><span data-stu-id="91236-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="91236-146">参考</span><span class="sxs-lookup"><span data-stu-id="91236-146">Reference</span></span>  
 [<span data-ttu-id="91236-147">#Const 指令</span><span class="sxs-lookup"><span data-stu-id="91236-147">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="91236-148">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="91236-148">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="91236-149">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91236-149">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)

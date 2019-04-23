---
title: Visual Basic 程序的结构
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
ms.openlocfilehash: 42e366a844f9c5e80a8f617bf73dfd869608540d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295765"
---
# <a name="structure-of-a-visual-basic-program"></a><span data-ttu-id="9e546-102">Visual Basic 程序的结构</span><span class="sxs-lookup"><span data-stu-id="9e546-102">Structure of a Visual Basic Program</span></span>
<span data-ttu-id="9e546-103">从标准构建基块是构建 Visual Basic 程序。</span><span class="sxs-lookup"><span data-stu-id="9e546-103">A Visual Basic program is built up from standard building blocks.</span></span> <span data-ttu-id="9e546-104">一个*解决方案*由一个或多个项目组成。</span><span class="sxs-lookup"><span data-stu-id="9e546-104">A *solution* comprises one or more projects.</span></span> <span data-ttu-id="9e546-105">一个*项目*又可以包含一个或多个程序集。</span><span class="sxs-lookup"><span data-stu-id="9e546-105">A *project* in turn can contain one or more assemblies.</span></span> <span data-ttu-id="9e546-106">每个*程序集*从一个或多个源代码文件编译。</span><span class="sxs-lookup"><span data-stu-id="9e546-106">Each *assembly* is compiled from one or more source files.</span></span> <span data-ttu-id="9e546-107">一个*源文件*提供定义和实现的类、 结构、 模块和接口，它们最终包含了所有代码。</span><span class="sxs-lookup"><span data-stu-id="9e546-107">A *source file* provides the definition and implementation of classes, structures, modules, and interfaces, which ultimately contain all your code.</span></span>  
  
 <span data-ttu-id="9e546-108">有关这些构建基块的 Visual Basic 程序的详细信息，请参阅[解决方案和项目](/visualstudio/ide/solutions-and-projects-in-visual-studio)并[.NET 中的程序集](../../../standard/assembly/index.md)。</span><span class="sxs-lookup"><span data-stu-id="9e546-108">For more information about these building blocks of a Visual Basic program, see [Solutions and Projects](/visualstudio/ide/solutions-and-projects-in-visual-studio) and [Assemblies in .NET](../../../standard/assembly/index.md).</span></span>  
  
## <a name="file-level-programming-elements"></a><span data-ttu-id="9e546-109">文件级别的编程元素</span><span class="sxs-lookup"><span data-stu-id="9e546-109">File-Level Programming Elements</span></span>  
 <span data-ttu-id="9e546-110">当您启动项目或文件，并打开代码编辑器中时，您将看到一些代码已存在并按正确的顺序。</span><span class="sxs-lookup"><span data-stu-id="9e546-110">When you start a project or file and open the code editor, you see some code already in place and in the correct order.</span></span> <span data-ttu-id="9e546-111">您编写任何代码都应遵循以下顺序：</span><span class="sxs-lookup"><span data-stu-id="9e546-111">Any code that you write should follow the following sequence:</span></span>  
  
1. <span data-ttu-id="9e546-112">`Option` 语句</span><span class="sxs-lookup"><span data-stu-id="9e546-112">`Option` statements</span></span>  
  
2. <span data-ttu-id="9e546-113">`Imports` 语句</span><span class="sxs-lookup"><span data-stu-id="9e546-113">`Imports` statements</span></span>  
  
3. <span data-ttu-id="9e546-114">`Namespace` 语句和命名空间级别的元素</span><span class="sxs-lookup"><span data-stu-id="9e546-114">`Namespace` statements and namespace-level elements</span></span>  
  
 <span data-ttu-id="9e546-115">如果按不同顺序输入语句，可以产生编译错误。</span><span class="sxs-lookup"><span data-stu-id="9e546-115">If you enter statements in a different order, compilation errors can result.</span></span>  
  
 <span data-ttu-id="9e546-116">程序还可以包含条件编译语句。</span><span class="sxs-lookup"><span data-stu-id="9e546-116">A program can also contain conditional compilation statements.</span></span> <span data-ttu-id="9e546-117">您可以单引号分隔文件中的上述顺序语句之间的源文件。</span><span class="sxs-lookup"><span data-stu-id="9e546-117">You can intersperse these in the source file among the statements of the preceding sequence.</span></span>  
  
### <a name="option-statements"></a><span data-ttu-id="9e546-118">选项语句</span><span class="sxs-lookup"><span data-stu-id="9e546-118">Option Statements</span></span>  
 <span data-ttu-id="9e546-119">`Option` 语句建立基本为后续的代码，以防止语法和逻辑错误的规则。</span><span class="sxs-lookup"><span data-stu-id="9e546-119">`Option` statements establish ground rules for subsequent code, helping prevent syntax and logic errors.</span></span> <span data-ttu-id="9e546-120">[Option Explicit 语句](../../../visual-basic/language-reference/statements/option-explicit-statement.md)可确保所有变量声明和拼写正确，这可以减少调试时间。</span><span class="sxs-lookup"><span data-stu-id="9e546-120">The [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) ensures that all variables are declared and spelled correctly, which reduces debugging time.</span></span> <span data-ttu-id="9e546-121">[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)帮助不同的数据类型的变量之间工作时可能发生的逻辑错误和数据丢失降到最低。</span><span class="sxs-lookup"><span data-stu-id="9e546-121">The [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) helps to minimize logic errors and data loss that can occur when you work between variables of different data types.</span></span> <span data-ttu-id="9e546-122">[Option 比较语句](../../../visual-basic/language-reference/statements/option-compare-statement.md)指定字符串的方式相互进行比较，基于其`Binary`或`Text`值。</span><span class="sxs-lookup"><span data-stu-id="9e546-122">The [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) specifies the way strings are compared to each other, based on either their `Binary` or `Text` values.</span></span>  
  
### <a name="imports-statements"></a><span data-ttu-id="9e546-123">Imports 语句</span><span class="sxs-lookup"><span data-stu-id="9e546-123">Imports Statements</span></span>  
 <span data-ttu-id="9e546-124">可以包括[Imports 语句 （.NET Namespace 和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)导入在项目外部定义的名称。</span><span class="sxs-lookup"><span data-stu-id="9e546-124">You can include an [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to import names defined outside your project.</span></span> <span data-ttu-id="9e546-125">`Imports`语句允许您的代码来指代类和其他类型定义中导入命名空间，而无需限定它们。</span><span class="sxs-lookup"><span data-stu-id="9e546-125">An `Imports` statement allows your code to refer to classes and other types defined within the imported namespace, without having to qualify them.</span></span> <span data-ttu-id="9e546-126">可以使用任意多个`Imports`根据语句。</span><span class="sxs-lookup"><span data-stu-id="9e546-126">You can use as many `Imports` statements as appropriate.</span></span> <span data-ttu-id="9e546-127">有关详细信息，请参阅[引用和 Imports 语句](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="9e546-127">For more information, see [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).</span></span>  
  
### <a name="namespace-statements"></a><span data-ttu-id="9e546-128">Namespace 语句</span><span class="sxs-lookup"><span data-stu-id="9e546-128">Namespace Statements</span></span>  
 <span data-ttu-id="9e546-129">命名空间可帮助组织和分类以便于分组和访问编程元素。</span><span class="sxs-lookup"><span data-stu-id="9e546-129">Namespaces help you organize and classify your programming elements for ease of grouping and accessing.</span></span> <span data-ttu-id="9e546-130">您使用[Namespace 语句](../../../visual-basic/language-reference/statements/namespace-statement.md)进行分类在特定的命名空间中的以下语句。</span><span class="sxs-lookup"><span data-stu-id="9e546-130">You use the [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) to classify the following statements within a particular namespace.</span></span> <span data-ttu-id="9e546-131">有关详细信息，请参阅 [Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="9e546-131">For more information, see [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
### <a name="conditional-compilation-statements"></a><span data-ttu-id="9e546-132">条件编译语句</span><span class="sxs-lookup"><span data-stu-id="9e546-132">Conditional Compilation Statements</span></span>  
 <span data-ttu-id="9e546-133">条件编译语句可以出现在源文件中的几乎任何位置。</span><span class="sxs-lookup"><span data-stu-id="9e546-133">Conditional compilation statements can appear almost anywhere in your source file.</span></span> <span data-ttu-id="9e546-134">它们会导致您的代码以包括或排除在编译时根据特定条件的部分。</span><span class="sxs-lookup"><span data-stu-id="9e546-134">They cause parts of your code to be included or excluded at compile time depending on certain conditions.</span></span> <span data-ttu-id="9e546-135">您可以将它们用于调试应用程序中，因为在调试模式下仅在运行的条件代码。</span><span class="sxs-lookup"><span data-stu-id="9e546-135">You can also use them for debugging your application, because conditional code runs in debugging mode only.</span></span> <span data-ttu-id="9e546-136">有关详细信息，请参阅[条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)。</span><span class="sxs-lookup"><span data-stu-id="9e546-136">For more information, see [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).</span></span>  
  
## <a name="namespace-level-programming-elements"></a><span data-ttu-id="9e546-137">Namespace 级别的编程元素</span><span class="sxs-lookup"><span data-stu-id="9e546-137">Namespace-Level Programming Elements</span></span>  
 <span data-ttu-id="9e546-138">类、 结构和模块包含在源文件中的所有代码。</span><span class="sxs-lookup"><span data-stu-id="9e546-138">Classes, structures, and modules contain all the code in your source file.</span></span> <span data-ttu-id="9e546-139">它们是*命名空间级别*元素可出现在命名空间或文件级别的源的文件。</span><span class="sxs-lookup"><span data-stu-id="9e546-139">They are *namespace-level* elements, which can appear within a namespace or at the source file level.</span></span> <span data-ttu-id="9e546-140">它们具有所有其他编程元素的声明。</span><span class="sxs-lookup"><span data-stu-id="9e546-140">They hold the declarations of all other programming elements.</span></span> <span data-ttu-id="9e546-141">接口，它们定义元素签名，但不提供实现，也出现在模块级别。</span><span class="sxs-lookup"><span data-stu-id="9e546-141">Interfaces, which define element signatures but provide no implementation, also appear at module level.</span></span> <span data-ttu-id="9e546-142">模块级别元素的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="9e546-142">For more information on the module-level elements, see the following:</span></span>  
  
-   [<span data-ttu-id="9e546-143">Class 语句</span><span class="sxs-lookup"><span data-stu-id="9e546-143">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [<span data-ttu-id="9e546-144">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="9e546-144">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [<span data-ttu-id="9e546-145">Module 语句</span><span class="sxs-lookup"><span data-stu-id="9e546-145">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [<span data-ttu-id="9e546-146">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="9e546-146">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 <span data-ttu-id="9e546-147">在命名空间级别的数据元素是枚举和委托。</span><span class="sxs-lookup"><span data-stu-id="9e546-147">Data elements at namespace level are enumerations and delegates.</span></span>  
  
## <a name="module-level-programming-elements"></a><span data-ttu-id="9e546-148">模块级的编程元素</span><span class="sxs-lookup"><span data-stu-id="9e546-148">Module-Level Programming Elements</span></span>  
 <span data-ttu-id="9e546-149">过程、 运算符、 属性和事件是可以保存可执行代码 （在运行时执行操作的语句） 的唯一编程元素。</span><span class="sxs-lookup"><span data-stu-id="9e546-149">Procedures, operators, properties, and events are the only programming elements that can hold executable code (statements that perform actions at run time).</span></span> <span data-ttu-id="9e546-150">它们是*模块级*的程序元素。</span><span class="sxs-lookup"><span data-stu-id="9e546-150">They are the *module-level* elements of your program.</span></span> <span data-ttu-id="9e546-151">过程级别元素的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="9e546-151">For more information on the procedure-level elements, see the following:</span></span>  
  
-   [<span data-ttu-id="9e546-152">Function 语句</span><span class="sxs-lookup"><span data-stu-id="9e546-152">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="9e546-153">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="9e546-153">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [<span data-ttu-id="9e546-154">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="9e546-154">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="9e546-155">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="9e546-155">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [<span data-ttu-id="9e546-156">Property 语句</span><span class="sxs-lookup"><span data-stu-id="9e546-156">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="9e546-157">Event 语句</span><span class="sxs-lookup"><span data-stu-id="9e546-157">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 <span data-ttu-id="9e546-158">在模块级别的数据元素是变量、 常量、 枚举和委托。</span><span class="sxs-lookup"><span data-stu-id="9e546-158">Data elements at module level are variables, constants, enumerations, and delegates.</span></span>  
  
## <a name="procedure-level-programming-elements"></a><span data-ttu-id="9e546-159">过程级别的编程元素</span><span class="sxs-lookup"><span data-stu-id="9e546-159">Procedure-Level Programming Elements</span></span>  
 <span data-ttu-id="9e546-160">大多数的内容*过程级别*元素都是可执行语句，它们构成您的程序的运行时代码。</span><span class="sxs-lookup"><span data-stu-id="9e546-160">Most of the contents of *procedure-level* elements are executable statements, which constitute the run-time code of your program.</span></span> <span data-ttu-id="9e546-161">所有可执行代码必须是在一些过程 (`Function`， `Sub`， `Operator`， `Get`， `Set`， `AddHandler`， `RemoveHandler`， `RaiseEvent`)。</span><span class="sxs-lookup"><span data-stu-id="9e546-161">All executable code must be in some procedure (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span></span> <span data-ttu-id="9e546-162">有关详细信息，请参阅[语句](../../../visual-basic/programming-guide/language-features/statements.md)。</span><span class="sxs-lookup"><span data-stu-id="9e546-162">For more information, see [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
 <span data-ttu-id="9e546-163">在过程级别的数据元素仅限于本地变量和常量。</span><span class="sxs-lookup"><span data-stu-id="9e546-163">Data elements at procedure level are limited to local variables and constants.</span></span>  
  
## <a name="the-main-procedure"></a><span data-ttu-id="9e546-164">主要过程</span><span class="sxs-lookup"><span data-stu-id="9e546-164">The Main Procedure</span></span>  
 <span data-ttu-id="9e546-165">`Main`过程是用于运行时应用程序已加载的第一个代码。</span><span class="sxs-lookup"><span data-stu-id="9e546-165">The `Main` procedure is the first code to run when your application has been loaded.</span></span> <span data-ttu-id="9e546-166">`Main` 可作为起始点和应用程序的总体控制。</span><span class="sxs-lookup"><span data-stu-id="9e546-166">`Main` serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="9e546-167">有四种`Main`:</span><span class="sxs-lookup"><span data-stu-id="9e546-167">There are four varieties of `Main`:</span></span>  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 <span data-ttu-id="9e546-168">此过程的最常见类型是`Sub Main()`。</span><span class="sxs-lookup"><span data-stu-id="9e546-168">The most common variety of this procedure is `Sub Main()`.</span></span> <span data-ttu-id="9e546-169">有关详细信息，请参阅[在 Visual Basic 中的 Main 过程](../../../visual-basic/programming-guide/program-structure/main-procedure.md)。</span><span class="sxs-lookup"><span data-stu-id="9e546-169">For more information, see [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e546-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e546-170">See also</span></span>

- [<span data-ttu-id="9e546-171">在 Visual Basic 中的主要过程</span><span class="sxs-lookup"><span data-stu-id="9e546-171">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)
- [<span data-ttu-id="9e546-172">Visual Basic 命名约定</span><span class="sxs-lookup"><span data-stu-id="9e546-172">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="9e546-173">Visual Basic 限制</span><span class="sxs-lookup"><span data-stu-id="9e546-173">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)

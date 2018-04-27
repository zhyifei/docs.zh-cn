---
title: 引用和 Imports 语句 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 051351c2fa0648de54bbfd36b1630ec1cd49d6f0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="ed4a5-102">引用和 Imports 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed4a5-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="ed4a5-103">你可以向外部对象提供你的项目通过选择**添加引用**命令**项目**菜单。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="ed4a5-104">在 Visual Basic 中的引用可以指向程序集，它们是与类似类型库但包含的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="ed4a5-105">Imports 语句</span><span class="sxs-lookup"><span data-stu-id="ed4a5-105">The Imports Statement</span></span>  
 <span data-ttu-id="ed4a5-106">程序集包含一个或多个命名空间。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="ed4a5-107">当你将添加对程序集的引用时，你还可以添加`Imports`控制该程序集的模块中的命名空间的可见性的模块的语句。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="ed4a5-108">`Imports`语句提供了的作用域的上下文中，你可以使用仅提供唯一的引用所需的命名空间的一部分。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="ed4a5-109">`Imports`语句具有以下语法：</span><span class="sxs-lookup"><span data-stu-id="ed4a5-109">The `Imports` statement has the following syntax:</span></span>  
  
 <span data-ttu-id="ed4a5-110">`Imports` [`|``Aliasname` =] `Namespace`</span><span class="sxs-lookup"><span data-stu-id="ed4a5-110">`Imports` [`|``Aliasname` =] `Namespace`</span></span>  
  
 <span data-ttu-id="ed4a5-111">`Aliasname` 引用为短名称，你可以使用代码中引用的导入的命名空间。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-111">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="ed4a5-112">`Namespace` 是通过在项目中，定义或通过以前的项目引用的命名空间通过可用`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-112">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="ed4a5-113">模块可能包含任意数量的`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-113">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="ed4a5-114">它们必须出现在任何之后`Option`语句，如果存在，但在任何其他代码之前。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-114">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed4a5-115">不要混淆项目引用与`Imports`语句或`Declare`语句。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-115">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="ed4a5-116">项目引用使得外部对象，例如在程序集中中的对象可用于 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-116">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="ed4a5-117">`Imports`语句用于简化对项目引用的访问，但不提供对这些对象的访问。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-117">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="ed4a5-118">`Declare`语句用于声明对外部过程中动态链接库 (DLL) 的引用。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-118">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="ed4a5-119">使用导入语句中使用别名</span><span class="sxs-lookup"><span data-stu-id="ed4a5-119">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="ed4a5-120">`Imports`语句，从而更便于访问的类的方法，无需显式类型引用的完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-120">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="ed4a5-121">别名，可以将更友好的名称分配给一个属于命名空间。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-121">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="ed4a5-122">例如，回车符/换行符导致一段单独的文本显示在多个行上的序列是的一部分<xref:Microsoft.VisualBasic.ControlChars>中的模块<xref:Microsoft.VisualBasic?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-122">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="ed4a5-123">若要在不带别名程序中使用此常量，你需要键入以下代码：</span><span class="sxs-lookup"><span data-stu-id="ed4a5-123">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]  
  
 <span data-ttu-id="ed4a5-124">`Imports` 语句必须始终为紧接着的第一个行`Option`模块中的语句。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-124">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="ed4a5-125">下面的代码段演示如何导入和分配的别名<xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType>模块：</span><span class="sxs-lookup"><span data-stu-id="ed4a5-125">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]  
  
 <span data-ttu-id="ed4a5-126">将来对此命名空间的引用可以是简短得多：</span><span class="sxs-lookup"><span data-stu-id="ed4a5-126">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]  
  
 <span data-ttu-id="ed4a5-127">如果`Imports`语句不包括别名名称，而无需限定的模块可用于在导入的命名空间中定义的元素。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-127">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="ed4a5-128">如果指定的别名名称，则它必须用作限定符包含在该命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="ed4a5-128">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed4a5-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed4a5-129">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ControlChars>  
 <xref:Microsoft.VisualBasic>  
   
 [<span data-ttu-id="ed4a5-130">在 Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="ed4a5-130">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="ed4a5-131">程序集和全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="ed4a5-131">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="ed4a5-132">如何：使用命令行创建和使用程序集</span><span class="sxs-lookup"><span data-stu-id="ed4a5-132">How to: Create and Use Assemblies Using the Command Line</span></span>](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)  
 [<span data-ttu-id="ed4a5-133">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="ed4a5-133">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)

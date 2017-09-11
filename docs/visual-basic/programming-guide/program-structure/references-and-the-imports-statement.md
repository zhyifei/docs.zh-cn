---
title: "引用和 Imports 语句 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references, assembly
- namespaces, assemblies
- referencing assemblies
- Imports statement, referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
caps.latest.revision: 12
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
ms.openlocfilehash: 4c6ce65005f84317c96a1124d609c46734d3cc66
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="c908f-102">引用和 Imports 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c908f-102">References and the Imports Statement (Visual Basic)</span></span>
<span data-ttu-id="c908f-103">您可以通过使外部对象提供到您的项目选择**添加引用**命令**项目**菜单。</span><span class="sxs-lookup"><span data-stu-id="c908f-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="c908f-104">中的引用都[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]可以指向与类似的类型库但包含的详细信息的程序集。</span><span class="sxs-lookup"><span data-stu-id="c908f-104">References in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="c908f-105">Imports 语句</span><span class="sxs-lookup"><span data-stu-id="c908f-105">The Imports Statement</span></span>  
 <span data-ttu-id="c908f-106">程序集包含一个或多个命名空间。</span><span class="sxs-lookup"><span data-stu-id="c908f-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="c908f-107">在添加对程序集引用时，您还可以添加`Imports`控制的可见性的模块内的该程序集的命名空间的模块的语句。</span><span class="sxs-lookup"><span data-stu-id="c908f-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="c908f-108">`Imports`语句提供了使您可以使用仅需提供的唯一引用的命名空间部分的作用域上下文。</span><span class="sxs-lookup"><span data-stu-id="c908f-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="c908f-109">`Imports`语句具有以下语法︰</span><span class="sxs-lookup"><span data-stu-id="c908f-109">The `Imports` statement has the following syntax:</span></span>  
  
 <span data-ttu-id="c908f-110">`Imports` [`|``Aliasname` =] `Namespace`</span><span class="sxs-lookup"><span data-stu-id="c908f-110">`Imports` [`|``Aliasname` =] `Namespace`</span></span>  
  
 <span data-ttu-id="c908f-111">`Aliasname`是指可用于在代码内导入的命名空间是指一个短名称。</span><span class="sxs-lookup"><span data-stu-id="c908f-111">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="c908f-112">`Namespace`是通过在项目中，定义或通过以前的项目引用的命名空间可通过任何一个`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="c908f-112">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="c908f-113">模块可以包含任意数量的`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="c908f-113">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="c908f-114">它们必须出现在任何之后`Option`语句，如果存在，但在任何其他代码之前。</span><span class="sxs-lookup"><span data-stu-id="c908f-114">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c908f-115">不要混淆项目引用与`Imports`语句或`Declare`语句。</span><span class="sxs-lookup"><span data-stu-id="c908f-115">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="c908f-116">项目引用使得外部对象，例如在程序集中，对象可用于[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="c908f-116">Project references make external objects, such as objects in assemblies, available to [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] projects.</span></span> <span data-ttu-id="c908f-117">`Imports`语句用于简化对项目引用的访问，但不提供对这些对象的访问。</span><span class="sxs-lookup"><span data-stu-id="c908f-117">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="c908f-118">`Declare`语句用于声明对外部过程动态链接库 (DLL) 中的引用。</span><span class="sxs-lookup"><span data-stu-id="c908f-118">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="c908f-119">Imports 语句中使用别名</span><span class="sxs-lookup"><span data-stu-id="c908f-119">Using Aliases with the Imports Statement</span></span>  
 <span data-ttu-id="c908f-120">`Imports`语句，从而更便于访问类方法通过消除需要显式键入引用的完全限定的名。</span><span class="sxs-lookup"><span data-stu-id="c908f-120">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="c908f-121">别名允许您将更友好的名称分配给只是一个命名空间的一部分。</span><span class="sxs-lookup"><span data-stu-id="c908f-121">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="c908f-122">例如，回车符/换行符将导致在多行上显示的文本单个块的序列是属于<xref:Microsoft.VisualBasic.ControlChars>中的模块<xref:Microsoft.VisualBasic?displayProperty=fullName>命名空间。</xref:Microsoft.VisualBasic?displayProperty=fullName> </xref:Microsoft.VisualBasic.ControlChars></span><span class="sxs-lookup"><span data-stu-id="c908f-122">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="c908f-123">若要在不带别名程序中使用此常量，您需要键入以下代码︰</span><span class="sxs-lookup"><span data-stu-id="c908f-123">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 <span data-ttu-id="c908f-124">[!code-vb[VbVbalrApplication #&3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c908f-124">[!code-vb[VbVbalrApplication#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="c908f-125">`Imports`语句必须始终为紧接着的前几行`Option`模块中的语句。</span><span class="sxs-lookup"><span data-stu-id="c908f-125">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="c908f-126">下面的代码段演示如何导入并分配给别名<xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName>模块︰</xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c908f-126">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=fullName> module:</span></span>  
  
 <span data-ttu-id="c908f-127">[!code-vb[VbVbalrApplication #&4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c908f-127">[!code-vb[VbVbalrApplication#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_2.vb)]</span></span>  
  
 <span data-ttu-id="c908f-128">将来对此命名空间的引用可以简短得多︰</span><span class="sxs-lookup"><span data-stu-id="c908f-128">Future references to this namespace can be considerably shorter:</span></span>  
  
 <span data-ttu-id="c908f-129">[!code-vb[VbVbalrApplication #&5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="c908f-129">[!code-vb[VbVbalrApplication#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/references-and-the-imports-statement_3.vb)]</span></span>  
  
 <span data-ttu-id="c908f-130">如果`Imports`语句不包括别名，可以在无需限定即可模块中使用的导入的命名空间中定义的元素。</span><span class="sxs-lookup"><span data-stu-id="c908f-130">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="c908f-131">如果指定的别名的名称，它必须用作限定符的名称包含在该命名空间内。</span><span class="sxs-lookup"><span data-stu-id="c908f-131">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c908f-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c908f-132">See Also</span></span>  
 <span data-ttu-id="c908f-133"><xref:Microsoft.VisualBasic.ControlChars></xref:Microsoft.VisualBasic.ControlChars></span><span class="sxs-lookup"><span data-stu-id="c908f-133"><xref:Microsoft.VisualBasic.ControlChars></span></span>   
 <span data-ttu-id="c908f-134"><xref:Microsoft.VisualBasic></xref:Microsoft.VisualBasic></span><span class="sxs-lookup"><span data-stu-id="c908f-134"><xref:Microsoft.VisualBasic></span></span>   
<span data-ttu-id="c908f-135"> [NIB 如何：使用“添加引用”对话框添加或删除引用](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span><span class="sxs-lookup"><span data-stu-id="c908f-135"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span></span>  
<span data-ttu-id="c908f-136"> [在 Visual Basic 中的命名空间](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="c908f-136"> [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="c908f-137"> [程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="c908f-137"> [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="c908f-138"> [如何︰ 创建和使用程序集使用命令行](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) </span><span class="sxs-lookup"><span data-stu-id="c908f-138"> [How to: Create and Use Assemblies Using the Command Line](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) </span></span>  
<span data-ttu-id="c908f-139"> [Imports 语句（.NET 命名空间和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span><span class="sxs-lookup"><span data-stu-id="c908f-139"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)</span></span>

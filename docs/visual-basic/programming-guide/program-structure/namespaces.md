---
title: "在 Visual Basic 中的命名空间 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.global
dev_langs:
- VB
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- name collisions
- Global keyword [Visual Basic]
- namespace pollution
- names, avoiding conflicts
- naming conflicts, namespaces
- namespaces, assemblies
- Visual Basic code, namespaces
- fully qualified names
- naming conventions, naming conflicts
- namespaces
ms.assetid: cffac744-ab8c-4f1f-ba50-732c22ab4b88
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: bfc9f8f71b5ce5e05b6509ad490354663f894651
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="namespaces-in-visual-basic"></a><span data-ttu-id="76af2-102">Visual Basic 中的命名空间</span><span class="sxs-lookup"><span data-stu-id="76af2-102">Namespaces in Visual Basic</span></span>
<span data-ttu-id="76af2-103">命名空间组织程序集中定义的对象。</span><span class="sxs-lookup"><span data-stu-id="76af2-103">Namespaces organize the objects defined in an assembly.</span></span> <span data-ttu-id="76af2-104">程序集可以包含多个命名空间，命名空间又可以包含其他命名空间。</span><span class="sxs-lookup"><span data-stu-id="76af2-104">Assemblies can contain multiple namespaces, which can in turn contain other namespaces.</span></span> <span data-ttu-id="76af2-105">使用大组对象（比如类库）时，命名空间可以避免多义性和简化引用。</span><span class="sxs-lookup"><span data-stu-id="76af2-105">Namespaces prevent ambiguity and simplify references when using large groups of objects such as class libraries.</span></span>  
  
 <span data-ttu-id="76af2-106">例如，[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]定义<xref:System.Windows.Forms.ListBox>类<xref:System.Windows.Forms?displayProperty=fullName>命名空间。</xref:System.Windows.Forms?displayProperty=fullName> </xref:System.Windows.Forms.ListBox></span><span class="sxs-lookup"><span data-stu-id="76af2-106">For example, the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] defines the <xref:System.Windows.Forms.ListBox> class in the <xref:System.Windows.Forms?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="76af2-107">以下代码段演示如何使用此类的完全限定名称声明变量：</span><span class="sxs-lookup"><span data-stu-id="76af2-107">The following code fragment shows how to declare a variable using the fully qualified name for this class:</span></span>  
  
 <span data-ttu-id="76af2-108">[!code-vb[VbVbalrApplication #&6;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="76af2-108">[!code-vb[VbVbalrApplication#6](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_1.vb)]</span></span>  
  
## <a name="avoiding-name-collisions"></a><span data-ttu-id="76af2-109">避免名称冲突</span><span class="sxs-lookup"><span data-stu-id="76af2-109">Avoiding Name Collisions</span></span>  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]<span data-ttu-id="76af2-110">命名空间解决问题有时称为*命名空间污染*，在其中一个类库，开发人员，会影响使用的另一个库中的类似名称。</span><span class="sxs-lookup"><span data-stu-id="76af2-110"> namespaces address a problem sometimes called *namespace pollution*, in which the developer of a class library is hampered by the use of similar names in another library.</span></span> <span data-ttu-id="76af2-111">这些冲突及其现有组件有时被称为 *名称冲突*。</span><span class="sxs-lookup"><span data-stu-id="76af2-111">These conflicts with existing components are sometimes called *name collisions*.</span></span>  
  
 <span data-ttu-id="76af2-112">例如，如果创建一个名为 `ListBox`的新类，你可以在项目中不加限定地使用它。</span><span class="sxs-lookup"><span data-stu-id="76af2-112">For example, if you create a new class named `ListBox`, you can use it inside your project without qualification.</span></span> <span data-ttu-id="76af2-113">但是，如果您想要使用[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]<xref:System.Windows.Forms.ListBox>类在同一项目中，您必须使用完全限定的引用以使引用唯一。</xref:System.Windows.Forms.ListBox></span><span class="sxs-lookup"><span data-stu-id="76af2-113">However, if you want to use the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.Windows.Forms.ListBox> class in the same project, you must use a fully qualified reference to make the reference unique.</span></span> <span data-ttu-id="76af2-114">如果引用不唯一，[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 会产生一个错误，指出名称不明确。</span><span class="sxs-lookup"><span data-stu-id="76af2-114">If the reference is not unique, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] produces an error stating that the name is ambiguous.</span></span> <span data-ttu-id="76af2-115">下面的代码示例演示如何声明这些对象：</span><span class="sxs-lookup"><span data-stu-id="76af2-115">The following code example demonstrates how to declare these objects:</span></span>  
  
 <span data-ttu-id="76af2-116">[!code-vb[VbVbalrApplication #&7;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="76af2-116">[!code-vb[VbVbalrApplication#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_2.vb)]</span></span>  
  
 <span data-ttu-id="76af2-117">下图显示两个命名空间层次结构，它们都包含一个名为 `ListBox`的对象。</span><span class="sxs-lookup"><span data-stu-id="76af2-117">The following illustration shows two namespace hierarchies, both containing an object named `ListBox`.</span></span>  
  
 <span data-ttu-id="76af2-118">![Namespace 层次结构](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.gif "vaNamespaceHierarchy")</span><span class="sxs-lookup"><span data-stu-id="76af2-118">![Namespace Hierarchy](../../../visual-basic/programming-guide/program-structure/media/vanamespacehierarchy.gif "vaNamespaceHierarchy")</span></span>  
  
 <span data-ttu-id="76af2-119">默认情况下，使用 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 创建的所有可执行文件都包含与项目具有相同名称的命名空间。</span><span class="sxs-lookup"><span data-stu-id="76af2-119">By default, every executable file you create with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] contains a namespace with the same name as your project.</span></span> <span data-ttu-id="76af2-120">例如，如果在一个名为 `ListBoxProject`的项目中定义对象，则可执行文件 ListBoxProject.exe 包含一个名为 `ListBoxProject`的命名空间。</span><span class="sxs-lookup"><span data-stu-id="76af2-120">For example, if you define an object within a project named `ListBoxProject`, the executable file ListBoxProject.exe contains a namespace called `ListBoxProject`.</span></span>  
  
 <span data-ttu-id="76af2-121">多个程序集可以使用相同的命名空间。</span><span class="sxs-lookup"><span data-stu-id="76af2-121">Multiple assemblies can use the same namespace.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="76af2-122"> 会将它们视为多个名称的单个组。</span><span class="sxs-lookup"><span data-stu-id="76af2-122"> treats them as a single set of names.</span></span> <span data-ttu-id="76af2-123">例如，你可以为名为 `Assemb1` 的程序集中名为 `SomeNameSpace` 的命名空间定义多个类，并为名为 `Assemb2` 的程序集中相同的命名空间定义其他类。</span><span class="sxs-lookup"><span data-stu-id="76af2-123">For example, you can define classes for a namespace called `SomeNameSpace` in an assembly named `Assemb1`, and define additional classes for the same namespace from an assembly named `Assemb2`.</span></span>  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="76af2-124">完全限定名</span><span class="sxs-lookup"><span data-stu-id="76af2-124">Fully Qualified Names</span></span>  
 <span data-ttu-id="76af2-125">完全限定名是以在其中定义对象的命名空间的名称为前缀的对象引用。</span><span class="sxs-lookup"><span data-stu-id="76af2-125">Fully qualified names are object references that are prefixed with the name of the namespace in which the object is defined.</span></span> <span data-ttu-id="76af2-126">如果创建对类的引用（通过选择“项目” **** 菜单中的“添加引用” **** ），然后为代码中的对象使用完全限定名，则可以使用在其他项目中定义的对象。</span><span class="sxs-lookup"><span data-stu-id="76af2-126">You can use objects defined in other projects if you create a reference to the class (by choosing **Add Reference** from the **Project** menu) and then use the fully qualified name for the object in your code.</span></span> <span data-ttu-id="76af2-127">以下代码段演示如何为来自另一个项目命名空间的对象使用完全限定名：</span><span class="sxs-lookup"><span data-stu-id="76af2-127">The following code fragment shows how to use the fully qualified name for an object from another project's namespace:</span></span>  
  
 <span data-ttu-id="76af2-128">[!code-vb[VbVbalrApplication #&8;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="76af2-128">[!code-vb[VbVbalrApplication#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_3.vb)]</span></span>  
  
 <span data-ttu-id="76af2-129">完全限定名避免命名冲突，因为它们可以使编译器确定哪些对象正在被使用。</span><span class="sxs-lookup"><span data-stu-id="76af2-129">Fully qualified names prevent naming conflicts because they make it possible for the compiler to determine which object is being used.</span></span> <span data-ttu-id="76af2-130">但是，名称本身可能会变得冗长繁杂。</span><span class="sxs-lookup"><span data-stu-id="76af2-130">However, the names themselves can get long and cumbersome.</span></span> <span data-ttu-id="76af2-131">为避免这一问题，可以使用 `Imports` 语句来定义 *别名*- 可用于代替完全限定名的缩略名。</span><span class="sxs-lookup"><span data-stu-id="76af2-131">To get around this, you can use the `Imports` statement to define an *alias*—an abbreviated name you can use in place of a fully qualified name.</span></span> <span data-ttu-id="76af2-132">例如，以下代码示例为两个完全限定名创建别名，并使用这些别名来定义两个对象。</span><span class="sxs-lookup"><span data-stu-id="76af2-132">For example, the following code example creates aliases for two fully qualified names, and uses these aliases to define two objects.</span></span>  
  
 <span data-ttu-id="76af2-133">[!code-vb[VbVbalrApplication #&9;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="76af2-133">[!code-vb[VbVbalrApplication#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_4.vb)]</span></span>  
  
 <span data-ttu-id="76af2-134">[!code-vb[VbVbalrApplication #&10;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="76af2-134">[!code-vb[VbVbalrApplication#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_5.vb)]</span></span>  
  
 <span data-ttu-id="76af2-135">如果不带别名使用 `Imports` 语句，可以使用命名空间中的所有名称而无需限定，只要这些名称唯一。</span><span class="sxs-lookup"><span data-stu-id="76af2-135">If you use the `Imports` statement without an alias, you can use all the names in that namespace without qualification, provided they are unique to the project.</span></span> <span data-ttu-id="76af2-136">如果项目包含同名的项的命名空间使用的 `Imports` 语句，则使用时必须完全限定该名称。</span><span class="sxs-lookup"><span data-stu-id="76af2-136">If your project contains `Imports` statements for namespaces that contain items with the same name, you must fully qualify that name when you use it.</span></span> <span data-ttu-id="76af2-137">例如，假设项目包含以下两个 `Imports` 语句：</span><span class="sxs-lookup"><span data-stu-id="76af2-137">Suppose, for example, your project contained the following two `Imports` statements:</span></span>  
  
 <span data-ttu-id="76af2-138">[!code-vb[VbVbalrApplication #&11;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="76af2-138">[!code-vb[VbVbalrApplication#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_6.vb)]</span></span>  
  
 <span data-ttu-id="76af2-139">如果尝试使用 `Class1` 而不对其完全限定，则 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 会产生错误消息，指出名称 `Class1` 不明确。</span><span class="sxs-lookup"><span data-stu-id="76af2-139">If you attempt to use `Class1` without fully qualifying it, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] produces an error stating that the name `Class1` is ambiguous.</span></span>  
  
## <a name="namespace-level-statements"></a><span data-ttu-id="76af2-140">命名空间级别语句</span><span class="sxs-lookup"><span data-stu-id="76af2-140">Namespace Level Statements</span></span>  
 <span data-ttu-id="76af2-141">在命名空间中，可以定义项，如模块、接口、类、委托、枚举、结构和其他命名空间。</span><span class="sxs-lookup"><span data-stu-id="76af2-141">Within a namespace, you can define items such as modules, interfaces, classes, delegates, enumerations, structures, and other namespaces.</span></span> <span data-ttu-id="76af2-142">无法在命名空间级别定义属性、过程、变量和事件等项。</span><span class="sxs-lookup"><span data-stu-id="76af2-142">You cannot define items such as properties, procedures, variables and events at the namespace level.</span></span> <span data-ttu-id="76af2-143">这些项必须在模块、结构或类等容器内部进行声明。</span><span class="sxs-lookup"><span data-stu-id="76af2-143">These items must be declared within containers such as modules, structures, or classes.</span></span>  
  
## <a name="global-keyword-in-fully-qualified-names"></a><span data-ttu-id="76af2-144">完全限定名中的全局关键字</span><span class="sxs-lookup"><span data-stu-id="76af2-144">Global Keyword in Fully Qualified Names</span></span>  
 <span data-ttu-id="76af2-145">如果已定义的命名空间的嵌套层次结构，该层次结构内的代码可能会被阻止访问<xref:System?displayProperty=fullName>.NET Framework 命名空间。</xref:System?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="76af2-145">If you have defined a nested hierarchy of namespaces, code inside that hierarchy might be blocked from accessing the <xref:System?displayProperty=fullName> namespace of the .NET Framework.</span></span> <span data-ttu-id="76af2-146">下面的示例阐释了在其中的层次结构`SpecialSpace.System`命名空间块访问到<xref:System?displayProperty=fullName>。</xref:System?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="76af2-146">The following example illustrates a hierarchy in which the `SpecialSpace.System` namespace blocks access to <xref:System?displayProperty=fullName>.</span></span>  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As System.Int32  
                Dim n As System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 <span data-ttu-id="76af2-147">结果是，Visual Basic 编译器不能成功地解析对引用<xref:System.Int32?displayProperty=fullName>，这是因为`SpecialSpace.System`未定义`Int32`。</xref:System.Int32?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="76af2-147">As a result, the Visual Basic compiler cannot successfully resolve the reference to <xref:System.Int32?displayProperty=fullName>, because `SpecialSpace.System` does not define `Int32`.</span></span> <span data-ttu-id="76af2-148">可以使用 `Global` 关键字在.NET Framework 类库的最外层级别上启动限定链。</span><span class="sxs-lookup"><span data-stu-id="76af2-148">You can use the `Global` keyword to start the qualification chain at the outermost level of the .NET Framework class library.</span></span> <span data-ttu-id="76af2-149">这允许您指定<xref:System?displayProperty=fullName>命名空间或类库中的任何其他命名空间。</xref:System?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="76af2-149">This allows you to specify the <xref:System?displayProperty=fullName> namespace or any other namespace in the class library.</span></span> <span data-ttu-id="76af2-150">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="76af2-150">The following example illustrates this.</span></span>  
  
```vb  
Namespace SpecialSpace  
    Namespace System  
        Class abc  
            Function getValue() As Global.System.Int32  
                Dim n As Global.System.Int32  
                Return n  
            End Function  
        End Class  
    End Namespace  
End Namespace  
```  
  
 <span data-ttu-id="76af2-151">您可以使用`Global`访问其他根级别的命名空间，如<xref:Microsoft.VisualBasic?displayProperty=fullName>，并与您的项目相关联的任何命名空间。</xref:Microsoft.VisualBasic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="76af2-151">You can use `Global` to access other root-level namespaces, such as <xref:Microsoft.VisualBasic?displayProperty=fullName>, and any namespace associated with your project.</span></span>  
  
## <a name="global-keyword-in-namespace-statements"></a><span data-ttu-id="76af2-152">命名空间语句中的全局关键字</span><span class="sxs-lookup"><span data-stu-id="76af2-152">Global Keyword in Namespace Statements</span></span>  
 <span data-ttu-id="76af2-153">您还可以使用`Global`中的关键字[Namespace 语句](../../../visual-basic/language-reference/statements/namespace-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="76af2-153">You can also use the `Global` keyword in a [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md).</span></span> <span data-ttu-id="76af2-154">这将允许你定义项目根命名空间之外的命名空间。</span><span class="sxs-lookup"><span data-stu-id="76af2-154">This lets you define a namespace out of the root namespace of your project.</span></span>  
  
 <span data-ttu-id="76af2-155">项目中的所有命名空间均基于项目的根命名空间。</span><span class="sxs-lookup"><span data-stu-id="76af2-155">All namespaces in your project are based on the root namespace for the project.</span></span>  <span data-ttu-id="76af2-156">Visual Studio 针对项目中的所有代码，将项目名称指定为默认根命名空间。</span><span class="sxs-lookup"><span data-stu-id="76af2-156">Visual Studio assigns your project name as the default root namespace for all code in your project.</span></span> <span data-ttu-id="76af2-157">例如，如果项目命名为 `ConsoleApplication1`，则其编程元素属于命名空间 `ConsoleApplication1`。</span><span class="sxs-lookup"><span data-stu-id="76af2-157">For example, if your project is named `ConsoleApplication1`, its programming elements belong to namespace `ConsoleApplication1`.</span></span> <span data-ttu-id="76af2-158">如果声明 `Namespace Magnetosphere`，项目中对 `Magnetosphere` 的引用将访问 `ConsoleApplication1.Magnetosphere`。</span><span class="sxs-lookup"><span data-stu-id="76af2-158">If you declare `Namespace Magnetosphere`, references to `Magnetosphere` in the project will access `ConsoleApplication1.Magnetosphere`.</span></span>  
  
 <span data-ttu-id="76af2-159">以下示例使用 `Global` 关键字来为项目声明根命名空间之外的命名空间。</span><span class="sxs-lookup"><span data-stu-id="76af2-159">The following examples use the `Global` keyword to declare a namespace out of the root namespace for the project.</span></span>  
  
 <span data-ttu-id="76af2-160">[!code-vb[VbVbalrApplication #&22;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="76af2-160">[!code-vb[VbVbalrApplication#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_7.vb)]</span></span>  
  
 <span data-ttu-id="76af2-161">在命名空间声明中， `Global` 不能嵌套于另一个命名空间中。</span><span class="sxs-lookup"><span data-stu-id="76af2-161">In a namespace declaration, `Global` cannot be nested in another namespace.</span></span>  
  
 <span data-ttu-id="76af2-162">您可以使用[应用程序页，项目设计器 (Visual Basic 中)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)查看和修改**根 Namespace**的项目。</span><span class="sxs-lookup"><span data-stu-id="76af2-162">You can use the [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic) to view and modify the **Root Namespace** of the project.</span></span>  <span data-ttu-id="76af2-163">对于新项目，“根命名空间” **** 默认为该项目的名称。</span><span class="sxs-lookup"><span data-stu-id="76af2-163">For new projects, the **Root Namespace** defaults to the project name.</span></span> <span data-ttu-id="76af2-164">若要使 `Global` 成为顶级命名空间，可以清除“根命名空间” **** 条目，以便此框为空。</span><span class="sxs-lookup"><span data-stu-id="76af2-164">To cause `Global` to be the top-level namespace, you can clear the **Root Namespace** entry so that the box is empty.</span></span> <span data-ttu-id="76af2-165">清除“根命名空间” **** 移除了命名空间声明中需要的 `Global` 关键字。</span><span class="sxs-lookup"><span data-stu-id="76af2-165">Clearing **Root Namespace** removes the need for the `Global` keyword in namespace declarations.</span></span>  
  
 <span data-ttu-id="76af2-166">如果 `Namespace` 语句声明一个名称，而该名称也是.NET Framework 中的命名空间，则如果 `Global` 关键字未在完全限定名中使用，.NET Framework 命名空间会变得不可用。</span><span class="sxs-lookup"><span data-stu-id="76af2-166">If a `Namespace` statement declares a name that is also a namespace in the .NET Framework, the .NET Framework namespace becomes unavailable if the `Global` keyword is not used in a fully qualified name.</span></span> <span data-ttu-id="76af2-167">在不使用 `Global` 关键字的情况下，若要启用对该 .NET Framework 命名空间的访问，可以将 `Global` 关键字包括到 `Namespace` 语句中。</span><span class="sxs-lookup"><span data-stu-id="76af2-167">To enable access to that .NET Framework namespace without using the `Global` keyword, you can include the `Global` keyword in the `Namespace` statement.</span></span>  
  
 <span data-ttu-id="76af2-168">以下示例在 `Global` 命名空间声明中具有 `System.Text` 关键字。</span><span class="sxs-lookup"><span data-stu-id="76af2-168">The following example has the `Global` keyword in the `System.Text` namespace declaration.</span></span>  
  
 <span data-ttu-id="76af2-169">如果`Global`关键字时不存在，请在命名空间声明<xref:System.Text.StringBuilder>无法访问而无需指定`Global.System.Text.StringBuilder`。</xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="76af2-169">If the `Global` keyword was not present in the namespace declaration, <xref:System.Text.StringBuilder> could not be accessed without specifying `Global.System.Text.StringBuilder`.</span></span> <span data-ttu-id="76af2-170">对于名为 `ConsoleApplication1`的项目，如果未使用 `System.Text` 关键字，对 `ConsoleApplication1.System.Text` 的引用会访问 `Global` 。</span><span class="sxs-lookup"><span data-stu-id="76af2-170">For a project named `ConsoleApplication1`, references to `System.Text` would access `ConsoleApplication1.System.Text` if the `Global` keyword was not used.</span></span>  
  
 <span data-ttu-id="76af2-171">[!code-vb[VbVbalrApplication #&21;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="76af2-171">[!code-vb[VbVbalrApplication#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/namespaces_8.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76af2-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76af2-172">See Also</span></span>  
 <span data-ttu-id="76af2-173"><xref:System.Windows.Forms.ListBox></xref:System.Windows.Forms.ListBox></span><span class="sxs-lookup"><span data-stu-id="76af2-173"><xref:System.Windows.Forms.ListBox></span></span>   
 <span data-ttu-id="76af2-174"><xref:System.Windows.Forms?displayProperty=fullName></xref:System.Windows.Forms?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="76af2-174"><xref:System.Windows.Forms?displayProperty=fullName></span></span>   
<span data-ttu-id="76af2-175"> [程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="76af2-175"> [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="76af2-176"> [如何︰ 创建和使用程序集使用命令行](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) </span><span class="sxs-lookup"><span data-stu-id="76af2-176"> [How to: Create and Use Assemblies Using the Command Line](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4) </span></span>  
<span data-ttu-id="76af2-177"> [引用和 Imports 语句](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="76af2-177"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="76af2-178"> [Imports 语句（.NET 命名空间和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="76af2-178"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="76af2-179"> [在 Office 解决方案中编写代码](https://msdn.microsoft.com/library/bb608596)</span><span class="sxs-lookup"><span data-stu-id="76af2-179"> [Writing Code in Office Solutions](https://msdn.microsoft.com/library/bb608596)</span></span>

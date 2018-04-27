---
title: 对已声明元素的引用 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 86d25d42688cffbf4076c4fb42eccc3b917d1dc1
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="cea76-102">对已声明元素的引用 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cea76-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="cea76-103">如果你的代码引用声明的元素，Visual Basic 编译器匹配该名称的相应声明你引用中的名称。</span><span class="sxs-lookup"><span data-stu-id="cea76-103">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="cea76-104">如果多个元素具有相同名称声明，则可以控制这些元素哪一项将引用的*合格*其名称。</span><span class="sxs-lookup"><span data-stu-id="cea76-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="cea76-105">编译器将尝试匹配对具有的名称声明的名称引用*范围最小*。</span><span class="sxs-lookup"><span data-stu-id="cea76-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="cea76-106">这意味着它开头进行引用的代码，并向外扩展到包含元素的连续级别。</span><span class="sxs-lookup"><span data-stu-id="cea76-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="cea76-107">下面的示例演示对具有相同名称的两个变量的引用。</span><span class="sxs-lookup"><span data-stu-id="cea76-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="cea76-108">此示例声明两个变量，每个名为`totalCount`，不同的模块中的作用域级别`container`。</span><span class="sxs-lookup"><span data-stu-id="cea76-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="cea76-109">当过程`showCount`显示`totalCount`而无需限定，Visual Basic 编译器将解析对范围最小的作用域，即内的局部声明的声明的引用`showCount`。</span><span class="sxs-lookup"><span data-stu-id="cea76-109">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="cea76-110">当它鉴定`totalCount`与包含模块`container`，编译器将解析对具有更广泛的作用域声明的引用。</span><span class="sxs-lookup"><span data-stu-id="cea76-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="cea76-111">限定元素名称</span><span class="sxs-lookup"><span data-stu-id="cea76-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="cea76-112">如果你想要覆盖此搜索过程，并指定将名称声明在更广泛的范围内，你必须*限定*用更大范围的包含元素的名称。</span><span class="sxs-lookup"><span data-stu-id="cea76-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="cea76-113">在某些情况下，你可能还需要限定包含的元素。</span><span class="sxs-lookup"><span data-stu-id="cea76-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="cea76-114">限定名称意味着要在与标识定义目标元素的位置的信息源语句中将其前面。</span><span class="sxs-lookup"><span data-stu-id="cea76-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="cea76-115">此信息称为*限定字符串*。</span><span class="sxs-lookup"><span data-stu-id="cea76-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="cea76-116">它可以包含一个或多个命名空间和模块，类或结构。</span><span class="sxs-lookup"><span data-stu-id="cea76-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="cea76-117">模块、 类或结构，它包含的目标元素，应明确地指定限定字符串。</span><span class="sxs-lookup"><span data-stu-id="cea76-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="cea76-118">容器又可能位于另一个包含元素，通常是命名空间。</span><span class="sxs-lookup"><span data-stu-id="cea76-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="cea76-119">你可能需要限定字符串中包括几个包含的元素。</span><span class="sxs-lookup"><span data-stu-id="cea76-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="cea76-120">若要访问声明的元素限定其名称</span><span class="sxs-lookup"><span data-stu-id="cea76-120">To access a declared element by qualifying its name</span></span>  
  
1.  <span data-ttu-id="cea76-121">确定在其中定义元素的位置。</span><span class="sxs-lookup"><span data-stu-id="cea76-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="cea76-122">这可能包括命名空间或甚至层次结构的命名空间。</span><span class="sxs-lookup"><span data-stu-id="cea76-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="cea76-123">在最低级别命名空间，该元素必须包含在模块、 类或结构。</span><span class="sxs-lookup"><span data-stu-id="cea76-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2.  <span data-ttu-id="cea76-124">确定目标元素的位置上基于一个限定路径。</span><span class="sxs-lookup"><span data-stu-id="cea76-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="cea76-125">具有最高级别的命名空间、 进入最低级别的命名空间，以开头和结尾模块、 类或结构，它包含的目标元素。</span><span class="sxs-lookup"><span data-stu-id="cea76-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="cea76-126">在路径中的每个元素必须包含它后面的元素。</span><span class="sxs-lookup"><span data-stu-id="cea76-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="cea76-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="cea76-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3.  <span data-ttu-id="cea76-128">准备目标元素限定字符串。</span><span class="sxs-lookup"><span data-stu-id="cea76-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="cea76-129">放置一个句点 (`.`) 后的路径中的每个元素。</span><span class="sxs-lookup"><span data-stu-id="cea76-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="cea76-130">你限定字符串中，你的应用程序必须有对每个元素的访问。</span><span class="sxs-lookup"><span data-stu-id="cea76-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  <span data-ttu-id="cea76-131">编写表达式或赋值语句以常规方式引用的目标元素。</span><span class="sxs-lookup"><span data-stu-id="cea76-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  <span data-ttu-id="cea76-132">目标元素限定字符串名前面放置。</span><span class="sxs-lookup"><span data-stu-id="cea76-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="cea76-133">名称应紧跟在该期间 (`.`) 后面模块、 类或结构，它包含的元素。</span><span class="sxs-lookup"><span data-stu-id="cea76-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="cea76-134">编译器使用限定字符串查找可与目标元素引用匹配的明确、 明确声明。</span><span class="sxs-lookup"><span data-stu-id="cea76-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="cea76-135">你可能需要限定名称引用，如果你的应用程序可以访问多个具有相同名称的编程元素。</span><span class="sxs-lookup"><span data-stu-id="cea76-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="cea76-136">例如，<xref:System.Windows.Forms>和<xref:System.Web.UI.WebControls>这两个命名空间包含`Label`类 (<xref:System.Windows.Forms.Label?displayProperty=nameWithType>和<xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>)。</span><span class="sxs-lookup"><span data-stu-id="cea76-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="cea76-137">如果你的应用程序使用这两个，或者如果定义了其自己`Label`类，则必须区分不同`Label`对象。</span><span class="sxs-lookup"><span data-stu-id="cea76-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="cea76-138">在变量声明中包括的命名空间或导入别名。</span><span class="sxs-lookup"><span data-stu-id="cea76-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="cea76-139">下面的示例使用导入别名。</span><span class="sxs-lookup"><span data-stu-id="cea76-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="cea76-140">其他包含的元素的成员</span><span class="sxs-lookup"><span data-stu-id="cea76-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="cea76-141">当你使用的另一个类或结构的非共享的成员时，你必须首先使用限定的变量或表达式来指向类或结构的实例的成员名称。</span><span class="sxs-lookup"><span data-stu-id="cea76-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="cea76-142">在下面的示例中，`demoClass`是名为的类的实例`class1`。</span><span class="sxs-lookup"><span data-stu-id="cea76-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="cea76-143">无法使用类名本身来限定不是成员[共享](../../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="cea76-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="cea76-144">你必须首先创建中的对象变量的实例 (在这种情况下`demoClass`)，然后通过变量名称引用它。</span><span class="sxs-lookup"><span data-stu-id="cea76-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="cea76-145">如果类或结构具有`Shared`成员，您可以限定该成员通过类或结构名称或变量或表达式指向一个实例。</span><span class="sxs-lookup"><span data-stu-id="cea76-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="cea76-146">模块不包含任何单独的实例，并且所有成员都是`Shared`默认情况下。</span><span class="sxs-lookup"><span data-stu-id="cea76-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="cea76-147">因此，你限定使用模块名称的模块成员。</span><span class="sxs-lookup"><span data-stu-id="cea76-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="cea76-148">下面的示例显示了对模块成员过程的限定的引用。</span><span class="sxs-lookup"><span data-stu-id="cea76-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="cea76-149">此示例声明两个`Sub`过程，其名称`perform`，在项目中的不同模块中。</span><span class="sxs-lookup"><span data-stu-id="cea76-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="cea76-150">每个可以指定而无需限定在其自己的模块内，但是必须为限定，如果从其他位置引用。</span><span class="sxs-lookup"><span data-stu-id="cea76-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="cea76-151">因为最后一个引用中`module3`不合格`perform`，编译器无法解析该引用。</span><span class="sxs-lookup"><span data-stu-id="cea76-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a><span data-ttu-id="cea76-152">对项目的引用</span><span class="sxs-lookup"><span data-stu-id="cea76-152">References to Projects</span></span>  
 <span data-ttu-id="cea76-153">若要使用[公共](../../../../visual-basic/language-reference/modifiers/public.md)另一个项目中定义的元素，必须首先设置*引用*对该项目的程序集或类型库。</span><span class="sxs-lookup"><span data-stu-id="cea76-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="cea76-154">若要设置的引用，请单击**添加引用**上**项目**菜单上或使用[/reference (Visual Basic 中)](../../../../visual-basic/reference/command-line-compiler/reference.md)命令行编译器选项。</span><span class="sxs-lookup"><span data-stu-id="cea76-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="cea76-155">例如，可以使用的 XML 对象模型[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cea76-155">For example, you can use the XML object model of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="cea76-156">如果引用设置为<xref:System.Xml>命名空间，你可以声明并使用的任何类，例如<xref:System.Xml.XmlDocument>。</span><span class="sxs-lookup"><span data-stu-id="cea76-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="cea76-157">下面的示例使用<xref:System.Xml.XmlDocument>。</span><span class="sxs-lookup"><span data-stu-id="cea76-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="cea76-158">导入包含元素</span><span class="sxs-lookup"><span data-stu-id="cea76-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="cea76-159">你可以使用[Imports 语句 （.NET Namespace 和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)到*导入*包含模块或你想要使用的类的命名空间。</span><span class="sxs-lookup"><span data-stu-id="cea76-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="cea76-160">这使您可以引用在导入的命名空间中定义没有完全限定它们的名称的元素。</span><span class="sxs-lookup"><span data-stu-id="cea76-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="cea76-161">下面的示例重写前面的示例导入<xref:System.Xml>命名空间。</span><span class="sxs-lookup"><span data-stu-id="cea76-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="cea76-162">此外，`Imports`语句还可以定义*导入别名*每个导入的命名空间。</span><span class="sxs-lookup"><span data-stu-id="cea76-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="cea76-163">这会使更短且更易读的源代码。</span><span class="sxs-lookup"><span data-stu-id="cea76-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="cea76-164">下面的示例重写前面的示例使用`xD`的别名作为<xref:System.Xml>命名空间。</span><span class="sxs-lookup"><span data-stu-id="cea76-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="cea76-165">`Imports`语句不会将与其他项目的元素提供给你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="cea76-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="cea76-166">也就是说，它不会替代设置的引用。</span><span class="sxs-lookup"><span data-stu-id="cea76-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="cea76-167">只需导入命名空间不需要限定该命名空间中定义的名称。</span><span class="sxs-lookup"><span data-stu-id="cea76-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="cea76-168">你还可以使用`Imports`语句导入模块、 类、 结构和枚举。</span><span class="sxs-lookup"><span data-stu-id="cea76-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="cea76-169">然后可以使用此类导入而无需限定元素的成员。</span><span class="sxs-lookup"><span data-stu-id="cea76-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="cea76-170">但是，你必须始终名称限定类和结构的变量或表达式计算结果为类或结构的实例的非共享的的成员。</span><span class="sxs-lookup"><span data-stu-id="cea76-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="cea76-171">命名准则</span><span class="sxs-lookup"><span data-stu-id="cea76-171">Naming Guidelines</span></span>  
 <span data-ttu-id="cea76-172">如果定义了两个或多个具有相同的名称的编程元素*名称多义性*时编译器将尝试解析该名称的引用将会导致。</span><span class="sxs-lookup"><span data-stu-id="cea76-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="cea76-173">如果有多个定义位于范围内，或者如果没有定义在作用域中，该引用不无法解析。</span><span class="sxs-lookup"><span data-stu-id="cea76-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="cea76-174">有关示例，请参阅此帮助页上的"限定引用示例"。</span><span class="sxs-lookup"><span data-stu-id="cea76-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="cea76-175">可以通过为你的所有元素分别都指定唯一名称来避免名称多义性。</span><span class="sxs-lookup"><span data-stu-id="cea76-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="cea76-176">然后你可以对任何元素引用而无需限定其名称前的使用命名空间、 模块或类。</span><span class="sxs-lookup"><span data-stu-id="cea76-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="cea76-177">你还可以减少意外错误的元素中引用的可能性。</span><span class="sxs-lookup"><span data-stu-id="cea76-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="cea76-178">隐藏</span><span class="sxs-lookup"><span data-stu-id="cea76-178">Shadowing</span></span>  
 <span data-ttu-id="cea76-179">当两个编程元素共享相同的名称时，可以隐藏其中一个，或*卷影*，另一个。</span><span class="sxs-lookup"><span data-stu-id="cea76-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="cea76-180">隐藏的元素不可用于参考;相反，当你的代码使用隐藏的元素名称时，Visual Basic 编译器将其解析为隐藏的元素。</span><span class="sxs-lookup"><span data-stu-id="cea76-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="cea76-181">包含示例的更多详细说明，请参阅[Visual Basic 中的隐藏](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。</span><span class="sxs-lookup"><span data-stu-id="cea76-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cea76-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="cea76-182">See Also</span></span>  
 [<span data-ttu-id="cea76-183">已声明的元素名称</span><span class="sxs-lookup"><span data-stu-id="cea76-183">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="cea76-184">已声明元素的特性</span><span class="sxs-lookup"><span data-stu-id="cea76-184">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="cea76-185">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="cea76-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="cea76-186">变量</span><span class="sxs-lookup"><span data-stu-id="cea76-186">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="cea76-187">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="cea76-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="cea76-188">New 运算符</span><span class="sxs-lookup"><span data-stu-id="cea76-188">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="cea76-189">Public</span><span class="sxs-lookup"><span data-stu-id="cea76-189">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)

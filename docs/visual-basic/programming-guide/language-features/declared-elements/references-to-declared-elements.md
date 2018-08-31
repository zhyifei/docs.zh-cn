---
title: 对已声明元素的引用 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
ms.openlocfilehash: 18f9920891e35517efe7adcfd4c03e03ac771478
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "43254736"
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="04dbb-102">对已声明元素的引用 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04dbb-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="04dbb-103">当你的代码引用已声明的元素时，Visual Basic 编译器匹配中该名称的相应声明您引用的名称。</span><span class="sxs-lookup"><span data-stu-id="04dbb-103">When your code refers to a declared element, the Visual Basic compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="04dbb-104">如果多个元素具有相同名称声明，则可以控制哪些元素是由引用*合格*其名称。</span><span class="sxs-lookup"><span data-stu-id="04dbb-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="04dbb-105">编译器将尝试匹配对具有的名称声明的名称引用*最小范围*。</span><span class="sxs-lookup"><span data-stu-id="04dbb-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="04dbb-106">这意味着它启动，从而将该引用代码，并向外扩展到连续的元素的级别。</span><span class="sxs-lookup"><span data-stu-id="04dbb-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="04dbb-107">下面的示例演示对两个变量具有相同名称的引用。</span><span class="sxs-lookup"><span data-stu-id="04dbb-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="04dbb-108">此示例声明两个变量，每个命名`totalCount`，在模块中的作用域的不同级别`container`。</span><span class="sxs-lookup"><span data-stu-id="04dbb-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="04dbb-109">当该过程`showCount`将显示`totalCount`而无需限定，Visual Basic 编译器解析对具有最小范围，即内部的本地声明的声明引用`showCount`。</span><span class="sxs-lookup"><span data-stu-id="04dbb-109">When the procedure `showCount` displays `totalCount` without qualification, the Visual Basic compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="04dbb-110">当有资格`totalCount`与包含模块`container`，则编译器将解析对范围更广的声明的引用。</span><span class="sxs-lookup"><span data-stu-id="04dbb-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
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
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="04dbb-111">符合条件的元素名称</span><span class="sxs-lookup"><span data-stu-id="04dbb-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="04dbb-112">如果你想要覆盖此搜索过程并指定一个名称，必须在范围更广中, 声明*限定*用范围更广的包含元素的名称。</span><span class="sxs-lookup"><span data-stu-id="04dbb-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="04dbb-113">在某些情况下，您可能还需要限定包含元素。</span><span class="sxs-lookup"><span data-stu-id="04dbb-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="04dbb-114">限定名称意味着要标识定义目标元素的位置的信息与在源语句中前面。</span><span class="sxs-lookup"><span data-stu-id="04dbb-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="04dbb-115">此信息称为*限定字符串*。</span><span class="sxs-lookup"><span data-stu-id="04dbb-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="04dbb-116">它可以包含一个或多个命名空间和模块，是类或结构。</span><span class="sxs-lookup"><span data-stu-id="04dbb-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="04dbb-117">模块、 类或结构，它包含目标元素，应明确指定的限定字符串。</span><span class="sxs-lookup"><span data-stu-id="04dbb-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="04dbb-118">容器又可能位于另一个包含元素，通常是命名空间中。</span><span class="sxs-lookup"><span data-stu-id="04dbb-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="04dbb-119">您可能需要限定字符串中包含多个包含元素。</span><span class="sxs-lookup"><span data-stu-id="04dbb-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="04dbb-120">若要通过限定其名称来访问已声明的元素</span><span class="sxs-lookup"><span data-stu-id="04dbb-120">To access a declared element by qualifying its name</span></span>  
  
1.  <span data-ttu-id="04dbb-121">确定在其中定义元素的位置。</span><span class="sxs-lookup"><span data-stu-id="04dbb-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="04dbb-122">这可能包括一个命名空间或甚至命名空间的层次结构。</span><span class="sxs-lookup"><span data-stu-id="04dbb-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="04dbb-123">在最低级别命名空间，该元素必须包含在模块、 类或结构。</span><span class="sxs-lookup"><span data-stu-id="04dbb-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
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
  
2.  <span data-ttu-id="04dbb-124">确定基于目标元素的位置的限定路径。</span><span class="sxs-lookup"><span data-stu-id="04dbb-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="04dbb-125">具有最高级别的命名空间中，转到最低级别的命名空间，开头和结尾模块、 类或结构，它包含目标元素。</span><span class="sxs-lookup"><span data-stu-id="04dbb-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="04dbb-126">在路径中的每个元素必须包含它后面的元素。</span><span class="sxs-lookup"><span data-stu-id="04dbb-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="04dbb-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="04dbb-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3.  <span data-ttu-id="04dbb-128">准备目标元素的限定字符串。</span><span class="sxs-lookup"><span data-stu-id="04dbb-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="04dbb-129">放置一个句点 (`.`) 的路径中每个元素之后。</span><span class="sxs-lookup"><span data-stu-id="04dbb-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="04dbb-130">你的应用程序必须具有对每个元素的访问限定字符串中。</span><span class="sxs-lookup"><span data-stu-id="04dbb-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  <span data-ttu-id="04dbb-131">编写表达式或赋值语句以正常方式引用目标元素。</span><span class="sxs-lookup"><span data-stu-id="04dbb-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  <span data-ttu-id="04dbb-132">在之前使用限定字符串的目标元素名称。</span><span class="sxs-lookup"><span data-stu-id="04dbb-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="04dbb-133">该名称应立即采用段 (`.`) 后面模块、 类或结构，它包含的元素。</span><span class="sxs-lookup"><span data-stu-id="04dbb-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="04dbb-134">编译器使用限定字符串来查找可与目标元素引用匹配的清晰、 明确声明。</span><span class="sxs-lookup"><span data-stu-id="04dbb-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="04dbb-135">您可能还需要限定名称引用，如果你的应用程序有权访问多个具有相同名称的编程元素。</span><span class="sxs-lookup"><span data-stu-id="04dbb-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="04dbb-136">例如，<xref:System.Windows.Forms>并<xref:System.Web.UI.WebControls>这两个命名空间包含具有`Label`类 (<xref:System.Windows.Forms.Label?displayProperty=nameWithType>和<xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>)。</span><span class="sxs-lookup"><span data-stu-id="04dbb-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="04dbb-137">如果你的应用程序使用这两个，或如果定义了自己`Label`类，则必须区分不同`Label`对象。</span><span class="sxs-lookup"><span data-stu-id="04dbb-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="04dbb-138">在变量声明中包括命名空间或导入别名。</span><span class="sxs-lookup"><span data-stu-id="04dbb-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="04dbb-139">下面的示例使用导入别名。</span><span class="sxs-lookup"><span data-stu-id="04dbb-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="04dbb-140">包含的其他元素的成员</span><span class="sxs-lookup"><span data-stu-id="04dbb-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="04dbb-141">当你使用另一个类或结构的非共享的成员时，必须首先限定成员名称的变量或表达式来指向类或结构的实例。</span><span class="sxs-lookup"><span data-stu-id="04dbb-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="04dbb-142">在以下示例中，`demoClass`是一个名为类的实例`class1`。</span><span class="sxs-lookup"><span data-stu-id="04dbb-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="04dbb-143">不能使用自身的类名来限定成员不是[共享](../../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="04dbb-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="04dbb-144">中的对象变量必须先创建一个实例 (在这种情况下`demoClass`)，然后通过变量名称引用它。</span><span class="sxs-lookup"><span data-stu-id="04dbb-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="04dbb-145">如果类或结构具有`Shared`成员，可以限定该成员使用的类或结构的名称或变量或指向实例的表达式。</span><span class="sxs-lookup"><span data-stu-id="04dbb-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="04dbb-146">模块不具有任何单独的实例，且所有其成员`Shared`默认情况下。</span><span class="sxs-lookup"><span data-stu-id="04dbb-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="04dbb-147">因此，您有资格模块名称的模块成员。</span><span class="sxs-lookup"><span data-stu-id="04dbb-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="04dbb-148">下面的示例演示对模块成员过程的限定的引用。</span><span class="sxs-lookup"><span data-stu-id="04dbb-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="04dbb-149">此示例声明两个`Sub`过程，其名称`perform`，在项目中的不同模块中。</span><span class="sxs-lookup"><span data-stu-id="04dbb-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="04dbb-150">每个可以指定而无需限定在其自己的模块，但如果从其他位置引用必须是限定。</span><span class="sxs-lookup"><span data-stu-id="04dbb-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="04dbb-151">因为最后一个引用在`module3`不符合的条件`perform`，编译器无法解析该引用。</span><span class="sxs-lookup"><span data-stu-id="04dbb-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
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
  
## <a name="references-to-projects"></a><span data-ttu-id="04dbb-152">对项目的引用</span><span class="sxs-lookup"><span data-stu-id="04dbb-152">References to Projects</span></span>  
 <span data-ttu-id="04dbb-153">若要使用[公共](../../../../visual-basic/language-reference/modifiers/public.md)另一个项目中定义的元素，则必须首先设置*引用*对该项目的程序集或类型库。</span><span class="sxs-lookup"><span data-stu-id="04dbb-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="04dbb-154">若要设置的引用，请单击**添加引用**上**项目**菜单中或使用[/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md)命令行编译器选项。</span><span class="sxs-lookup"><span data-stu-id="04dbb-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="04dbb-155">例如，可以使用的 XML 对象模型[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="04dbb-155">For example, you can use the XML object model of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="04dbb-156">如果引用设置为<xref:System.Xml>命名空间中，您可以声明和使用的任何类，如<xref:System.Xml.XmlDocument>。</span><span class="sxs-lookup"><span data-stu-id="04dbb-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="04dbb-157">下面的示例使用<xref:System.Xml.XmlDocument>。</span><span class="sxs-lookup"><span data-stu-id="04dbb-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="04dbb-158">导入包含元素</span><span class="sxs-lookup"><span data-stu-id="04dbb-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="04dbb-159">可以使用[Imports 语句 （.NET Namespace 和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)到*导入*包含的模块或你想要使用的类的命名空间。</span><span class="sxs-lookup"><span data-stu-id="04dbb-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="04dbb-160">这使您可以引用而没有完全限定其名称在导入的命名空间中定义的元素。</span><span class="sxs-lookup"><span data-stu-id="04dbb-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="04dbb-161">下面的示例将重写前面的示例，若要导入<xref:System.Xml>命名空间。</span><span class="sxs-lookup"><span data-stu-id="04dbb-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="04dbb-162">此外，`Imports`语句可以定义*导入别名*为每个导入的命名空间。</span><span class="sxs-lookup"><span data-stu-id="04dbb-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="04dbb-163">这可以使较短且更易于读取的源代码。</span><span class="sxs-lookup"><span data-stu-id="04dbb-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="04dbb-164">下面的示例将重写前面的示例使用`xD`的别名作为<xref:System.Xml>命名空间。</span><span class="sxs-lookup"><span data-stu-id="04dbb-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="04dbb-165">`Imports`语句不会将其他项目中的元素提供给你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="04dbb-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="04dbb-166">也就是说，它才会对引用的设置的位置。</span><span class="sxs-lookup"><span data-stu-id="04dbb-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="04dbb-167">只需导入命名空间不要求限定该命名空间中定义的名称。</span><span class="sxs-lookup"><span data-stu-id="04dbb-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="04dbb-168">此外可以使用`Imports`语句导入模块、 类、 结构和枚举。</span><span class="sxs-lookup"><span data-stu-id="04dbb-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="04dbb-169">然后可以使用此类导入的元素，而无需限定的成员。</span><span class="sxs-lookup"><span data-stu-id="04dbb-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="04dbb-170">但是，始终必须限定非共享的成员的类和结构的变量或表达式的计算结果为类或结构的实例。</span><span class="sxs-lookup"><span data-stu-id="04dbb-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="04dbb-171">命名准则</span><span class="sxs-lookup"><span data-stu-id="04dbb-171">Naming Guidelines</span></span>  
 <span data-ttu-id="04dbb-172">如果定义了两个或多个具有相同名称的编程元素*名称多义性*时编译器将尝试解析对该名称的引用。</span><span class="sxs-lookup"><span data-stu-id="04dbb-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="04dbb-173">如果有多个一个定义位于范围内，或如果没有定义是在作用域中，则无法解析引用。</span><span class="sxs-lookup"><span data-stu-id="04dbb-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="04dbb-174">有关示例，请参阅此帮助页上的"限定引用示例"。</span><span class="sxs-lookup"><span data-stu-id="04dbb-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="04dbb-175">通过提供唯一的名称的所有元素，可以避免名称多义性。</span><span class="sxs-lookup"><span data-stu-id="04dbb-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="04dbb-176">然后您可以对进行引用的任何元素而无需限定其名称与命名空间、 模块或类。</span><span class="sxs-lookup"><span data-stu-id="04dbb-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="04dbb-177">您还可以减少意外引用错误的元素的可能性。</span><span class="sxs-lookup"><span data-stu-id="04dbb-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="04dbb-178">隐藏</span><span class="sxs-lookup"><span data-stu-id="04dbb-178">Shadowing</span></span>  
 <span data-ttu-id="04dbb-179">当两个编程元素共享相同的名称时，可以隐藏其中一个，或*卷影*，另一个。</span><span class="sxs-lookup"><span data-stu-id="04dbb-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="04dbb-180">隐藏的元素不是可用于引用;相反，当你的代码使用隐藏的元素名称时，Visual Basic 编译器将其解析为隐藏的元素。</span><span class="sxs-lookup"><span data-stu-id="04dbb-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the Visual Basic compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="04dbb-181">有关示例的更多详细说明，请参阅[Visual Basic 中的隐藏](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。</span><span class="sxs-lookup"><span data-stu-id="04dbb-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04dbb-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="04dbb-182">See Also</span></span>  
 [<span data-ttu-id="04dbb-183">已声明的元素名称</span><span class="sxs-lookup"><span data-stu-id="04dbb-183">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="04dbb-184">已声明元素的特性</span><span class="sxs-lookup"><span data-stu-id="04dbb-184">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="04dbb-185">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="04dbb-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="04dbb-186">变量</span><span class="sxs-lookup"><span data-stu-id="04dbb-186">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="04dbb-187">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="04dbb-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="04dbb-188">New 运算符</span><span class="sxs-lookup"><span data-stu-id="04dbb-188">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="04dbb-189">Public</span><span class="sxs-lookup"><span data-stu-id="04dbb-189">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)

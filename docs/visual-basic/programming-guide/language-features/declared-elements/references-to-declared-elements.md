---
title: "对已声明元素的引用 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9b3847164b4e577a9265a746b9329218b4af928b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="references-to-declared-elements-visual-basic"></a>对已声明元素的引用 (Visual Basic)
如果你的代码引用已声明的元素，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器匹配该名称的相应声明你引用中的名称。 如果多个元素具有相同名称声明，则可以控制这些元素哪一项将引用的*合格*其名称。  
  
 编译器将尝试匹配对具有的名称声明的名称引用*范围最小*。 这意味着它开头进行引用的代码，并向外扩展到包含元素的连续级别。  
  
 下面的示例演示对具有相同名称的两个变量的引用。 此示例声明两个变量，每个名为`totalCount`，不同的模块中的作用域级别`container`。 当过程`showCount`显示`totalCount`而无需限定，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器将解析对范围最小的作用域，即内的局部声明的声明的引用`showCount`。 当它鉴定`totalCount`与包含模块`container`，编译器将解析对具有更广泛的作用域声明的引用。  
  
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
  
## <a name="qualifying-an-element-name"></a>限定元素名称  
 如果你想要覆盖此搜索过程，并指定将名称声明在更广泛的范围内，你必须*限定*用更大范围的包含元素的名称。 在某些情况下，你可能还需要限定包含的元素。  
  
 限定名称意味着要在与标识定义目标元素的位置的信息源语句中将其前面。 此信息称为*限定字符串*。 它可以包含一个或多个命名空间和模块，类或结构。  
  
 模块、 类或结构，它包含的目标元素，应明确地指定限定字符串。 容器又可能位于另一个包含元素，通常是命名空间。 你可能需要限定字符串中包括几个包含的元素。  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a>若要访问声明的元素限定其名称  
  
1.  确定在其中定义元素的位置。 这可能包括命名空间或甚至层次结构的命名空间。 在最低级别命名空间，该元素必须包含在模块、 类或结构。  
  
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
  
2.  确定目标元素的位置上基于一个限定路径。 具有最高级别的命名空间、 进入最低级别的命名空间，以开头和结尾模块、 类或结构，它包含的目标元素。 在路径中的每个元素必须包含它后面的元素。  
  
     `outerSpace` → `innerSpace` → `holdsTotals` → `totals`  
  
3.  准备目标元素限定字符串。 放置一个句点 (`.`) 后的路径中的每个元素。 你限定字符串中，你的应用程序必须有对每个元素的访问。  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  编写表达式或赋值语句以常规方式引用的目标元素。  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  目标元素限定字符串名前面放置。 名称应紧跟在该期间 (`.`) 后面模块、 类或结构，它包含的元素。  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  编译器使用限定字符串查找可与目标元素引用匹配的明确、 明确声明。  
  
 你可能需要限定名称引用，如果你的应用程序可以访问多个具有相同名称的编程元素。 例如，<xref:System.Windows.Forms>和<xref:System.Web.UI.WebControls>这两个命名空间包含`Label`类 (<xref:System.Windows.Forms.Label?displayProperty=nameWithType>和<xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>)。 如果你的应用程序使用这两个，或者如果定义了其自己`Label`类，则必须区分不同`Label`对象。 在变量声明中包括的命名空间或导入别名。 下面的示例使用导入别名。  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a>其他包含的元素的成员  
 当你使用的另一个类或结构的非共享的成员时，你必须首先使用限定的变量或表达式来指向类或结构的实例的成员名称。 在下面的示例中，`demoClass`是名为的类的实例`class1`。  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 无法使用类名本身来限定不是成员[共享](../../../../visual-basic/language-reference/modifiers/shared.md)。 你必须首先创建中的对象变量的实例 (在这种情况下`demoClass`)，然后通过变量名称引用它。  
  
 如果类或结构具有`Shared`成员，您可以限定该成员通过类或结构名称或变量或表达式指向一个实例。  
  
 模块不包含任何单独的实例，并且所有成员都是`Shared`默认情况下。 因此，你限定使用模块名称的模块成员。  
  
 下面的示例显示了对模块成员过程的限定的引用。 此示例声明两个`Sub`过程，其名称`perform`，在项目中的不同模块中。 每个可以指定而无需限定在其自己的模块内，但是必须为限定，如果从其他位置引用。 因为最后一个引用中`module3`不合格`perform`，编译器无法解析该引用。  
  
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
  
## <a name="references-to-projects"></a>对项目的引用  
 若要使用[公共](../../../../visual-basic/language-reference/modifiers/public.md)另一个项目中定义的元素，必须首先设置*引用*对该项目的程序集或类型库。 若要设置的引用，请单击**添加引用**上**项目**菜单上或使用[/reference (Visual Basic 中)](../../../../visual-basic/reference/command-line-compiler/reference.md)命令行编译器选项。  
  
 例如，可以使用的 XML 对象模型[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]。 如果引用设置为<xref:System.Xml>命名空间，你可以声明并使用的任何类，例如<xref:System.Xml.XmlDocument>。 下面的示例使用<xref:System.Xml.XmlDocument>。  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a>导入包含元素  
 你可以使用[Imports 语句 （.NET Namespace 和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)到*导入*包含模块或你想要使用的类的命名空间。 这使您可以引用在导入的命名空间中定义没有完全限定它们的名称的元素。 下面的示例重写前面的示例导入<xref:System.Xml>命名空间。  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 此外，`Imports`语句还可以定义*导入别名*每个导入的命名空间。 这会使更短且更易读的源代码。 下面的示例重写前面的示例使用`xD`的别名作为<xref:System.Xml>命名空间。  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 `Imports`语句不会将与其他项目的元素提供给你的应用程序。 也就是说，它不会替代设置的引用。 只需导入命名空间不需要限定该命名空间中定义的名称。  
  
 你还可以使用`Imports`语句导入模块、 类、 结构和枚举。 然后可以使用此类导入而无需限定元素的成员。 但是，你必须始终名称限定类和结构的变量或表达式计算结果为类或结构的实例的非共享的的成员。  
  
## <a name="naming-guidelines"></a>命名准则  
 如果定义了两个或多个具有相同的名称的编程元素*名称多义性*时编译器将尝试解析该名称的引用将会导致。 如果有多个定义位于范围内，或者如果没有定义在作用域中，该引用不无法解析。 有关示例，请参阅此帮助页上的"限定引用示例"。  
  
 可以通过为你的所有元素分别都指定唯一名称来避免名称多义性。 然后你可以对任何元素引用而无需限定其名称前的使用命名空间、 模块或类。 你还可以减少意外错误的元素中引用的可能性。  
  
## <a name="shadowing"></a>隐藏  
 当两个编程元素共享相同的名称时，可以隐藏其中一个，或*卷影*，另一个。 隐藏的元素不可用于参考;相反，当你的代码使用隐藏的元素名称，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器将其解析为隐藏的元素。 包含示例的更多详细说明，请参阅[Visual Basic 中的隐藏](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)。  
  
## <a name="see-also"></a>另请参阅  
 [已声明的元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [已声明元素的特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [管理项目和解决方案属性](/visualstudio/ide/managing-project-and-solution-properties)  
 [变量](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Imports 语句（.NET 命名空间和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [Public](../../../../visual-basic/language-reference/modifiers/public.md)

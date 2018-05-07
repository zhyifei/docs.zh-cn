---
title: 扩展方法 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: 1cc2ccef09dd027c6f1e82f60ed4ac5f50db6ebe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="extension-methods-visual-basic"></a>扩展方法 (Visual Basic)
扩展方法使开发人员能够将自定义功能添加到已定义而无需创建新的派生的类型的数据类型。 扩展方法使您可以用来编写可以就像它是现有类型的实例方法调用的方法。  
  
## <a name="remarks"></a>备注  
 扩展方法可以是仅`Sub`过程或`Function`过程。 不能定义扩展属性、 字段或事件。 所有扩展方法必须具有扩展属性都标记`<Extension()>`从<xref:System.Runtime.CompilerServices?displayProperty=nameWithType>命名空间。  
  
 扩展方法定义中的第一个参数指定该方法所扩展的数据类型。 当运行该方法时，第一个参数绑定到调用方法的数据类型的实例。  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的示例定义`Print`扩展<xref:System.String>数据类型。 该方法使用`Console.WriteLine`显示的字符串。 参数`Print`方法， `aString`，建立该方法扩展<xref:System.String>类。  
  
 [!code-vb[VbVbalrExtensionMethods#1](./codesnippet/VisualBasic/extension-methods_1.vb)]  
  
 请注意，标记扩展方法定义为具有扩展属性`<Extension()>`。 标记在其中定义该方法的模块是可选的但必须标记每个扩展方法。 <xref:System.Runtime.CompilerServices> 必须导入才能访问扩展属性。  
  
 扩展方法可以仅在模块内声明。 通常，在其中定义的扩展方法的模块不是调用它的一个相同的模块。 相反，包含扩展方法是导入的模块，如果它必须是，以使其进入作用域。 包含该模块后`Print`是在作用域，就像它是普通的实例方法，如不采用任何参数，可以调用该方法`ToUpper`:  
  
 [!code-vb[VbVbalrExtensionMethods#2](./codesnippet/VisualBasic/extension-methods_2.vb)]  
  
 下一步的示例中， `PrintAndPunctuate`，也是扩展<xref:System.String>，这包含两个参数定义一次。 第一个参数， `aString`，建立，扩展方法将扩展<xref:System.String>。 第二个参数， `punc`，但应是作为自变量时传入调用该方法的标点符号的字符串。 该方法显示跟标点符号的字符串。  
  
 [!code-vb[VbVbalrExtensionMethods#3](./codesnippet/VisualBasic/extension-methods_3.vb)]  
  
 默认情况下，调用方法的字符串参数发送`punc`: `example.PrintAndPunctuate(".")`  
  
 下面的示例演示`Print`和`PrintAndPunctuate`定义和调用。 <xref:System.Runtime.CompilerServices> 将以导入定义模块以启用扩展属性的访问权限。  
  
### <a name="code"></a>代码  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
  
    <Extension()>   
    Public Sub Print(ByVal aString As String)  
        Console.WriteLine(aString)  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 接下来，扩展方法置于范围中并调用。  
  
```vb  
Imports ConsoleApplication2.StringExtensions  
Module Module1  
  
    Sub Main()  
  
        Dim example As String = "Example string"  
        example.Print()  
  
        example = "Hello"  
        example.PrintAndPunctuate(".")  
        example.PrintAndPunctuate("!!!!")  
  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>注释  
 来说，只需要能够运行这些或类似的扩展方法是，它们是在作用域中。 如果包含扩展方法的模块在作用域，它在 IntelliSense 中可见，并可以就像它是一个普通的实例方法调用。  
  
 请注意，当时会调用这些方法，任何自变量的发送的第一个参数。 参数`aString`在前一种方法定义将绑定到`example`，实例`String`调用它们。 编译器将使用`example`作为自变量发送到第一个参数。  
  
 如果设置为某个对象调用扩展方法`Nothing`，扩展方法执行。 这不适用于普通的实例方法。 你可以显式检查`Nothing`扩展方法中。  
  
## <a name="types-that-can-be-extended"></a>可以扩展的类型  
 你可以定义对可在 Visual Basic 参数列表，其中包括中表示的大多数类型的扩展方法：  
  
-   类 （引用类型）  
  
-   结构 （值类型）  
  
-   接口  
  
-   委托  
  
-   ByRef 和 ByVal 参数  
  
-   泛型方法参数  
  
-   数组  
  
 第一个参数指定的扩展方法扩展的数据类型，因为它是必需的并不能为可选。 为此，`Optional`参数和`ParamArray`参数不能是参数列表中的第一个参数。  
  
 扩展方法被认为不在后期绑定。 在下面的示例中，该语句`anObject.PrintMe()`引发<xref:System.MissingMemberException>异常，而相同的异常时将看到第二个`PrintMe`扩展方法定义中删除。  
  
 [!code-vb[VbVbalrExtensionMethods#9](./codesnippet/VisualBasic/extension-methods_4.vb)]  
  
## <a name="best-practices"></a>最佳做法  
 扩展方法提供便利和功能强大的方法来扩展现有类型。 但是，若要成功使用，还是有一些需要考虑的要点。 这些注意事项主要适用于作者的类库，但它们可能会影响任何应用程序使用扩展方法。  
  
 大多数情况下，你将添加到不属于您的类型的扩展方法是添加到您控制的类型的扩展方法比更易受攻击。 可能会干扰你的扩展方法的类不拥有会出现多种情况。  
  
-   如果任何可访问的实例成员存在具有与任何从自变量所需参数的收缩转换与调用语句中中的自变量兼容的签名，将优先于任何扩展方法使用实例方法。 因此，如果相应的实例方法添加到在某一时刻的类，依赖于某个现有扩展成员变得不可访问。  
  
-   扩展方法的作者无法阻止其他程序员编写冲突可能具有优先于的原始扩展的扩展方法。  
  
-   可以通过将自己的命名空间中的扩展方法来提高可靠性。 你的库的使用者可以包含命名空间或排除它，或在命名空间，分开的库的其余部分之间选择。  
  
-   它可能会比来扩展类，尤其是如果你不具有所有权的接口或类扩展接口更安全。 接口中的更改会影响每个类来实现它。 因此，作者可能不太可能添加或更改接口中的方法。 但是，如果一个类实现具有相同签名的扩展方法的两个接口，这两种扩展方法是可见的。  
  
-   扩展的最具体的类型，你可以。 在类型的结构中，如果您选择从中派生的许多其他类型，类型有层的实例方法或其他可能会影响您的扩展方法引入的可能性。  
  
## <a name="extension-methods-instance-methods-and-properties"></a>扩展方法、 实例方法和属性  
 当在范围内实例方法具有与调用语句的自变量兼容的签名时，将任何扩展方法优先选择的实例方法。 实例方法具有优先级，即使该扩展方法是更好的匹配项。 在下面的示例中，`ExampleClass`包含名为的实例方法`ExampleMethod`它具有一个参数的类型`Integer`。 扩展方法`ExampleMethod`扩展`ExampleClass`，并且具有一个类型的参数`Long`。  
  
 [!code-vb[VbVbalrExtensionMethods#4](./codesnippet/VisualBasic/extension-methods_5.vb)]  
  
 首次调用`ExampleMethod`下面的代码中调用扩展方法，因为`arg1`是`Long`并且仅与兼容`Long`扩展方法中的参数。 第二次调用`ExampleMethod`具有`Integer`自变量， `arg2`，它会调用实例方法。  
  
 [!code-vb[VbVbalrExtensionMethods#5](./codesnippet/VisualBasic/extension-methods_6.vb)]  
  
 现在反向中的两个方法的参数的数据类型：  
  
 [!code-vb[VbVbalrExtensionMethods#6](./codesnippet/VisualBasic/extension-methods_7.vb)]  
  
 这次中的代码`Main`两次都调用实例方法。 这是因为同时`arg1`和`arg2`有扩大转换为`Long`，和实例方法将优先于这两种情况中的扩展方法。  
  
 [!code-vb[VbVbalrExtensionMethods#7](./codesnippet/VisualBasic/extension-methods_8.vb)]  
  
 因此，扩展方法不能替换现有的实例方法。 但是，如果扩展方法具有相同的名称作为实例方法，但签名不会发生冲突，则这两种方法可以访问。 例如，如果类`ExampleClass`包含一个名为方法`ExampleMethod`采用任何自变量、 具有相同名称的扩展方法，但是允许不同的签名，如下面的代码中所示。  
  
 [!code-vb[VbVbalrExtensionMethods#8](./codesnippet/VisualBasic/extension-methods_9.vb)]  
  
 此代码的输出如下所示：  
  
 `Extension method`  
  
 `Instance method`  
  
 这种情况是简单的属性： 如果扩展方法具有与它所扩展的类的属性相同的名称，该扩展方法不可见，并且无法访问。  
  
## <a name="extension-method-precedence"></a>扩展方法优先级  
 作用域中并且可以访问两个具有相同签名的扩展方法时，将调用具有高优先级的一个。 扩展方法的优先顺序取决于用于将方法引入作用域的机制。 以下列表显示了优先级层次结构中的，从高到最低。  
  
1.  当前模块中定义的扩展方法。  
  
2.  扩展方法内定义数据类型在当前命名空间或其父级的任一与具有优先权要高于父命名空间的子命名空间。  
  
3.  当前文件中任何类型导入内部定义的扩展方法。  
  
4.  当前文件中任何命名空间导入内部定义的扩展方法。  
  
5.  在任何项目级类型导入内部定义的扩展方法。  
  
6.  在任何项目级命名空间导入内部定义的扩展方法。  
  
 如果优先不解析多义性，可以使用完全限定的名称以指定要调用的方法。 如果`Print`前面示例中的方法定义一个名为模块中`StringExtensions`，完全限定的名称是`StringExtensions.Print(example)`而不是`example.Print()`。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Runtime.CompilerServices>  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>  
 [扩展方法](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
 [Module 语句](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [可选参数](./optional-parameters.md)  
 [参数数组](./parameter-arrays.md)  
 [属性概述](../../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)

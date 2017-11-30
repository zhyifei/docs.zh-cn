---
title: "如何：编写扩展方法 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65cdabf59886e7457a327ee9cde968a6a73f2280
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>如何：编写扩展方法 (Visual Basic)
扩展方法使你能够向现有类添加方法。 可以调用扩展方法，就像它是该类的实例。  
  
### <a name="to-define-an-extension-method"></a>若要定义的扩展方法  
  
1.  在 Visual Studio 中打开新的或现有 Visual Basic 应用程序。  
  
2.  在你要在其中定义的扩展方法的文件的顶部，包括以下 import 语句：  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  新的或现有应用程序中的模块内, 开始使用扩展属性的方法定义：  
  
    ```  
    <Extension()>  
    ```  
  
4.  你的方法声明的方式声明普通，只不过的第一个参数的类型必须是你想要扩展的数据类型。  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a>示例  
 下面的示例声明模块中的扩展方法`StringExtensions`。 第二个模块， `Module1`，导入`StringExtensions`和调用的方法。 扩展方法必须在范围内，被调用时。 扩展方法`PrintAndPunctuate`扩展<xref:System.String>的显示字符串实例的方法的类后, 跟作为一个参数发送的标点符号的字符串。  
  
```vb  
' Declarations will typically be in a separate module.  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
```vb  
' Import the module that holds the extension method you want to use,   
' and call it.  
  
Imports ConsoleApplication2.StringExtensions  
  
Module Module1  
  
    Sub Main()  
        Dim example = "Hello"  
        example.PrintAndPunctuate("?")  
        example.PrintAndPunctuate("!!!!")  
    End Sub  
  
End Module  
```  
  
 请注意，方法是使用两个参数定义的只使用一个调用。 第一个参数， `aString`，方法中定义绑定到`example`，实例`String`调用的方法。 该示例输出如下所示：  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>  
 [扩展方法](./extension-methods.md)  
 [Module 语句](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [过程参数和自变量](./procedure-parameters-and-arguments.md)  
 [在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)

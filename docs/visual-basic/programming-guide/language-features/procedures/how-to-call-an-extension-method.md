---
title: 如何：调用扩展方法 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: 5cb0684637a716dfec947740ba345c62eaabddd7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59313796"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>如何：调用扩展方法 (Visual Basic)
扩展方法，可将方法添加到现有类。 声明的扩展方法并将其引入到范围后，可以调用它类似于它所扩展的类型的实例方法。 有关如何编写扩展方法的详细信息，请参阅[如何：编写扩展方法](./how-to-write-an-extension-method.md)。  
  
 以下说明，请参阅扩展方法`PrintAndPunctuate`，随后会显示调用它的任何值后跟的字符串实例中发送的第二个参数， `punc`。  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 该方法必须在范围内，被调用时。  
  
### <a name="to-call-an-extension-method"></a>若要调用扩展方法  
  
1. 声明具有扩展方法的第一个参数的数据类型的变量。 有关`PrintAndPunctuate`，你需要<xref:System.String>变量：  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2. 变量将调用扩展方法，和它的值绑定到的第一个参数， `aString`。 将显示以下调用语句`Ready?`。  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     请注意，对此扩展方法的调用看起来就像对任何一个调用<xref:System.String>实例需要一个参数的方法：  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3. 声明另一个字符串变量，并再次调用方法以查看其工作与任何字符串。  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     结果这一次是： `or not!!!`。  
  
## <a name="example"></a>示例  
 下面的代码是创建的一个完整的示例和使用简单的扩展方法。  
  
```vb  
Imports System.Runtime.CompilerServices  
Imports ConsoleApplication1.StringExtensions  
  
Module Module1  
  
    Sub Main()  
  
        Dim example = "Hello"  
        example.PrintAndPunctuate(".")  
        example.PrintAndPunctuate("!!!!")  
  
        Dim example2 = "Goodbye"  
        example2.PrintAndPunctuate("?")  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
End Module  
  
' Output:  
' Hello.  
' Hello!!!!  
' Goodbye?  
```  
  
## <a name="see-also"></a>请参阅

- [如何：编写扩展方法](./how-to-write-an-extension-method.md)
- [扩展方法](./extension-methods.md)
- [Visual Basic 中的范围](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)

---
title: 如何：调用扩展方法 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: 32691183bcd1632a82b1e9a2668790abbf8f80fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648562"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>如何：调用扩展方法 (Visual Basic)
扩展方法使你能够向现有类添加方法。 声明数据并扩展方法置于范围后，你可以调用它类似于它所扩展的类型的实例方法。 有关如何编写扩展方法的详细信息，请参阅[如何： 编写扩展方法](./how-to-write-an-extension-method.md)。  
  
 下面的说明，请参阅对扩展方法`PrintAndPunctuate`，这将显示调用它，并且后跟任意值的字符串实例发送第二个参数，用于`punc`。  
  
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
  
1.  声明具有扩展方法的第一个参数的数据类型的变量。 有关`PrintAndPunctuate`，你需要<xref:System.String>变量：  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2.  变量将调用扩展方法，并且其值将绑定到的第一个参数， `aString`。 将显示以下调用语句`Ready?`。  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     请注意，对此扩展方法的调用看起来就像对任何之一的调用<xref:System.String>实例需要一个参数的方法：  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3.  声明另一个字符串变量，并再次调用方法以查看其工作与任何字符串。  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     结果此时是： `or not!!!`。  
  
## <a name="example"></a>示例  
 下面的代码是创建的完整示例和使用简单的扩展方法。  
  
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
 [如何：编写扩展方法](./how-to-write-an-extension-method.md)  
 [扩展方法](./extension-methods.md)  
 [在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)

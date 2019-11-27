---
title: 如何：调用扩展方法
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: a19705a8f90833d48869df26a18d19b0ad1488e0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340398"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>如何：调用扩展方法 (Visual Basic)

扩展方法使你能够向现有类添加方法。 在扩展方法被声明并引入作用域后，可以像它所扩展的类型的实例方法一样调用它。 有关如何编写扩展方法的详细信息，请参阅[如何：编写扩展方法](./how-to-write-an-extension-method.md)。

 以下说明引用扩展方法 `PrintAndPunctuate`，这将显示调用该方法的字符串实例，然后在中为第二个参数 `punc`发送任何值。

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

调用方法时，该方法必须在范围内。

### <a name="to-call-an-extension-method"></a>调用扩展方法

1. 声明一个变量，该变量的数据类型为扩展方法的第一个参数。 对于 `PrintAndPunctuate`，需要一个 <xref:System.String> 变量：

    ```vb
    Dim example = "Ready"
    ```

2. 该变量将调用扩展方法，并将其值绑定到第一个参数，`aString`。 以下调用语句将显示 `Ready?`。

    ```vb
    example.PrintAndPunctuate("?")
    ```

     请注意，对此扩展方法的调用看起来就像调用需要一个参数的 <xref:System.String> 实例方法之一：

    ```vb
    example.EndsWith("dy")
    example.IndexOf("R")
    ```

3. 声明另一个字符串变量并再次调用方法，以查看它是否适用于任何字符串。

    ```vb
    Dim example2 = " or not"
    example2.PrintAndPunctuate("!!!")
    ```

     此时间的结果为： `or not!!!`。

## <a name="example"></a>示例
 下面的代码是创建和使用简单扩展方法的完整示例。

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

## <a name="see-also"></a>另请参阅

- [如何：编写扩展方法](./how-to-write-an-extension-method.md)
- [扩展方法](./extension-methods.md)
- [范围 Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)

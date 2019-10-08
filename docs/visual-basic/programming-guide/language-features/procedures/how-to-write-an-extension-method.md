---
title: 如何：编写扩展方法（Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: d01596d50db8ba1078e8ac82caa951418645c977
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004613"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>如何：编写扩展方法（Visual Basic）

扩展方法使你能够向现有类添加方法。 可以调用扩展方法，就像它是该类的实例一样。

### <a name="to-define-an-extension-method"></a>定义扩展方法

1. 在 Visual Studio 中打开新的或现有的 Visual Basic 应用程序。

2. 在要在其中定义扩展方法的文件的顶部，请包含以下 import 语句：

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. 在新应用程序或现有应用程序的模块中，使用[`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute)属性开始方法定义：

    ```vb
    <Extension()>
    ```
 
   请注意，`Extension` 属性只能应用于 Visual Basic[模块](../../../language-reference/statements/module-statement.md)中的方法（@no__t 1 或 @no__t 2 过程）。 如果将它应用于 @no__t 0 或 `Structure` 中的方法，则 Visual Basic 编译器将生成错误[BC36551](../../../misc/bc36551.md)，"只能在模块中定义扩展方法。"

4. 用普通方法声明方法，但第一个参数的类型必须是要扩展的数据类型。

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a>示例

 下面的示例声明模块 `StringExtensions` 中的扩展方法。 第二个模块 `Module1`，导入 `StringExtensions` 并调用方法。 在调用扩展方法时，该方法必须在范围内。 扩展方法 `PrintAndPunctuate` 使用一种方法来扩展 @no__t 1 类，该方法将后跟以参数形式发送的标点符号字符串作为参数。
  
```vb
' Declarations will typically be in a separate module.
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
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
  
 请注意，方法是用两个参数定义的，并且只能用一个参数调用。 方法定义中的第一个参数 `aString` 绑定到 `example`，它是调用方法的 @no__t 的实例。 示例输出如下所示：
  
 ```console
 Hello?
 Hello!!!!
 ```
  
## <a name="see-also"></a>请参阅

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [扩展方法](extension-methods.md)
- [Module 语句](../../../language-reference/statements/module-statement.md)
- [过程参数和自变量](procedure-parameters-and-arguments.md)
- [范围 Visual Basic](../declared-elements/scope.md)

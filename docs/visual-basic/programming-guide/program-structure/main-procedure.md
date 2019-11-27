---
title: 主要过程
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: 61cd397b82b4bb9a8b24a1a7d30eaea68e37368f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347349"
---
# <a name="main-procedure-in-visual-basic"></a>Visual Basic 中的 Main 过程
每个 Visual Basic 应用程序都必须包含一个名为 `Main`的过程。 此过程可用作应用程序的起点和总体控制。 .NET Framework 在加载了应用程序并准备好向其传递控制时调用 `Main` 过程。 除非要创建 Windows 窗体应用程序，否则必须为自己运行的应用程序编写 `Main` 过程。

 `Main` 包含首先运行的代码。 在 `Main`中，你可以在程序启动时确定首先加载哪一窗体，查明你的应用程序的副本是否已在系统上运行，为你的应用程序建立一组变量，或者打开该应用程序所需的数据库。

## <a name="requirements-for-the-main-procedure"></a>Main 过程的要求
 独立运行的文件（通常使用扩展名）必须包含 `Main` 过程。 库（例如，具有扩展名 .dll）本身不会运行，并且不需要 `Main` 过程。 可以创建的不同类型的项目的要求如下：

- 控制台应用程序会自行运行，你必须至少提供一个 `Main` 过程。

- Windows 窗体应用程序独立运行。 不过，Visual Basic 编译器会自动在此类应用程序中生成 `Main` 过程，而不需要编写一个。

- 类库不需要 `Main` 过程。 其中包括 Windows 控件库和 Web 控件库。 Web 应用程序部署为类库。

## <a name="declaring-the-main-procedure"></a>声明 Main 过程
 有四种方法可以声明 `Main` 过程。 它可以接受参数，也可以返回值。

> [!NOTE]
> 如果在类中声明 `Main`，则必须使用 `Shared` 关键字。 在模块中，无需 `Shared``Main`。

- 最简单的方法是声明不采用参数或返回值的 `Sub` 过程。

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- `Main` 还可以返回一个 `Integer` 值，操作系统使用该值作为程序的退出代码。 其他程序可以通过检查 Windows ERRORLEVEL 值来测试此代码。 若要返回退出代码，必须将 `Main` 声明为 `Function` 过程，而不是 `Sub` 过程。

    ```vb
    Module mainModule
        Function Main() As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' Insert call to appropriate starting place in your code.
            ' On return, assign appropriate value to returnValue.
            ' 0 usually means successful completion.
            MsgBox("The application is terminating with error level " &
                 CStr(returnValue) & ".")
            Return returnValue
        End Function
    End Module
    ```

- `Main` 还可以采用 `String` 数组作为参数。 数组中的每个字符串都包含一个用于调用程序的命令行参数。 您可以根据它们的值执行不同的操作。

    ```vb
    Module mainModule
        Function Main(ByVal cmdArgs() As String) As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
            End If
            ' Insert call to appropriate starting place in your code.
            ' On return, assign appropriate value to returnValue.
            ' 0 usually means successful completion.
            MsgBox("The application is terminating with error level " &
                 CStr(returnValue) & ".")
            Return returnValue
        End Function
    End Module
    ```

- 可以声明 `Main` 来检查命令行参数，但不会返回退出代码，如下所示。

    ```vb
    Module mainModule
        Sub Main(ByVal cmdArgs() As String)
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
            End If
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```
  
## <a name="see-also"></a>另请参阅

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [Visual Basic 程序的结构](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)
- [Integer 数据类型](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [String 数据类型](../../../visual-basic/language-reference/data-types/string-data-type.md)

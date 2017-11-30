---
title: "如何：调用采用无符号类型的 Windows 函数 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1d59c29a83ede97d90926c8e499788676e2c235
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>如何：调用采用无符号类型的 Windows 函数 (Visual Basic)
如果你使用的类、 模块或结构，它具有无符号的整数类型的成员，则可以访问与这些成员[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>若要调用采用无符号的类型的 Windows 函数  
  
1.  使用[声明语句](../../../visual-basic/language-reference/statements/declare-statement.md)告诉[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]哪些库包含函数、 什么其名称是在库中，其调用的序列是什么，和如何将字符串转换调用它时。  
  
2.  在`Declare`语句，使用`UInteger`， `ULong`， `UShort`，或`Byte`为适合于与无符号类型的每个参数。  
  
3.  查阅文档以获取要调用若要查找的名称和它所使用的常量值的 Windows 函数。 其中许多参见 WinUser.h 文件中定义。  
  
4.  声明在代码中的必要常量。 许多 Windows 常量是 32 位无符号的值，并应将这些声明`As``UInteger`。  
  
5.  以常规方式调用函数。 下面的示例调用 Windows 函数`MessageBox`，它将采用一个无符号的整数自变量。  
  
    ```  
    Public Class windowsMessage  
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (  
            ByVal hWnd As Integer,   
            ByVal lpText As String,   
            ByVal lpCaption As String,   
            ByVal uType As UInteger) As Integer  
        Private Const MB_OK As UInteger = 0  
        Private Const MB_ICONEXCLAMATION As UInteger = &H30  
        Private Const IDOK As UInteger = 1  
        Private Const IDCLOSE As UInteger = 8  
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION  
        Public Function messageThroughWindows() As String  
            Dim r As Integer = mb(0, "Click OK if you see this!",   
                "Windows API call", c)  
            Dim s As String = "Windows API MessageBox returned " &  
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &  
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"  
            Return s  
        End Function  
    End Class  
    ```  
  
     你可以测试函数`messageThroughWindows`替换为以下代码。  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  `UInteger`， `ULong`， `UShort`，和`SByte`数据类型不属于[语言独立性和独立于语言的组件](https://msdn.microsoft.com/library/12a7a7h3)(CLS)，因此符合 cls 的代码不能使用的组件，使用它们。  
  
    > [!IMPORTANT]
    >  Windows 应用程序编程接口 (API)，例如在调用非托管代码，公开将代码移植到潜在的安全风险。  
  
    > [!IMPORTANT]
    >  调用 Windows API 需要非托管的代码的权限，这可能会影响在部分信任情况下其执行。 有关详细信息，请参阅<xref:System.Security.Permissions.SecurityPermission>和[代码访问权限](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675)。  
  
## <a name="see-also"></a>另请参阅  
 [数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Integer 数据类型](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [UInteger 数据类型](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [演练：调用 Windows API](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)

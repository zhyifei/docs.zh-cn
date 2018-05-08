---
title: 如何：释放系统资源 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
ms.openlocfilehash: cbb66934833da2bd6f0b797944dbb9c4df267cfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>如何：释放系统资源 (Visual Basic)
你可以使用`Using`块来确保系统在代码退出块时释放资源。 这很有用，如果你使用的这样做会消耗大量的内存，或其他组件还想要使用的系统资源。  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>若要释放数据库连接时用完你的代码  
  
1.  请确保包括相应[Imports 语句 （.NET Namespace 和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)开头的源文件的数据库连接 (在这种情况下， <xref:System.Data.SqlClient>)。  
  
2.  创建`Using`块`Using`和`End Using`语句。 在块中，将使用的数据库连接处理的代码。  
  
3.  声明连接并创建它的实例作为的一部分`Using`语句。  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     不管您如何退出块，包括未处理的异常的大小写的资源，系统都会释放。  
  
     请注意，不能访问`sqc`从外部`Using`阻止，因为其作用域仅限于块。  
  
     系统资源，例如文件句柄或 COM 包装器，可以使用此相同技术。 你使用`Using`时你以确保想要保留的资源可供其他组件，均退出之后阻止`Using`块。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Data.SqlClient.SqlConnection>  
 [控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [决策结构](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [其他控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [嵌套的控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Using 语句](../../../../visual-basic/language-reference/statements/using-statement.md)

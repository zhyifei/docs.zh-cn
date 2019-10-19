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
ms.openlocfilehash: c780ee1a174ad044593960bc30a3ee2e1f929390
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583144"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a>如何：释放系统资源 (Visual Basic)
您可以使用 `Using` 块确保系统在代码退出块时释放资源。 如果你使用的系统资源占用大量内存，或者其他组件也想要使用，则此方法很有用。  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a>使用数据库连接完成代码时释放数据库连接  
  
1. 请确保在源文件开头包含数据库连接的相应[Imports 语句（.Net 命名空间和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) （在本例中为 <xref:System.Data.SqlClient>）。  
  
2. 使用 `Using` 和 `End Using` 语句创建 `Using` 块。 在块中，放置用于处理数据库连接的代码。  
  
3. 声明连接并在 `Using` 语句中创建它的实例。  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     无论退出块的方式如何（包括未经处理的异常的情况），系统都将释放资源。  
  
     请注意，不能从 `Using` 块外访问 `sqc`，因为它的作用域限制为块。  
  
     您可以对系统资源（如文件句柄或 COM 包装）使用这种方法。 当你希望在退出 `Using` 块后，请使用 `Using` 块，以确保保留其他组件的资源。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Data.SqlClient.SqlConnection>
- [控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [决策结构](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [其他控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [嵌套的控件结构](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Using 语句](../../../../visual-basic/language-reference/statements/using-statement.md)

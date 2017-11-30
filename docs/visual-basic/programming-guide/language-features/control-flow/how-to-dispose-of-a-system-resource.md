---
title: "如何：释放系统资源 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5b5c65c9d123c6f481852eb249cb4d479a180c5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="32b44-102">如何：释放系统资源 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32b44-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="32b44-103">你可以使用`Using`块来确保系统在代码退出块时释放资源。</span><span class="sxs-lookup"><span data-stu-id="32b44-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="32b44-104">这很有用，如果你使用的这样做会消耗大量的内存，或其他组件还想要使用的系统资源。</span><span class="sxs-lookup"><span data-stu-id="32b44-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="32b44-105">若要释放数据库连接时用完你的代码</span><span class="sxs-lookup"><span data-stu-id="32b44-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1.  <span data-ttu-id="32b44-106">请确保包括相应[Imports 语句 （.NET Namespace 和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)开头的源文件的数据库连接 (在这种情况下， <xref:System.Data.SqlClient>)。</span><span class="sxs-lookup"><span data-stu-id="32b44-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2.  <span data-ttu-id="32b44-107">创建`Using`块`Using`和`End Using`语句。</span><span class="sxs-lookup"><span data-stu-id="32b44-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="32b44-108">在块中，将使用的数据库连接处理的代码。</span><span class="sxs-lookup"><span data-stu-id="32b44-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3.  <span data-ttu-id="32b44-109">声明连接并创建它的实例作为的一部分`Using`语句。</span><span class="sxs-lookup"><span data-stu-id="32b44-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="32b44-110">不管您如何退出块，包括未处理的异常的大小写的资源，系统都会释放。</span><span class="sxs-lookup"><span data-stu-id="32b44-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="32b44-111">请注意，不能访问`sqc`从外部`Using`阻止，因为其作用域仅限于块。</span><span class="sxs-lookup"><span data-stu-id="32b44-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="32b44-112">系统资源，例如文件句柄或 COM 包装器，可以使用此相同技术。</span><span class="sxs-lookup"><span data-stu-id="32b44-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="32b44-113">你使用`Using`时你以确保想要保留的资源可供其他组件，均退出之后阻止`Using`块。</span><span class="sxs-lookup"><span data-stu-id="32b44-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32b44-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32b44-114">See Also</span></span>  
 <xref:System.Data.SqlClient.SqlConnection>  
 [<span data-ttu-id="32b44-115">控制流</span><span class="sxs-lookup"><span data-stu-id="32b44-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="32b44-116">决策结构</span><span class="sxs-lookup"><span data-stu-id="32b44-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="32b44-117">循环结构</span><span class="sxs-lookup"><span data-stu-id="32b44-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="32b44-118">其他控件结构</span><span class="sxs-lookup"><span data-stu-id="32b44-118">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="32b44-119">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="32b44-119">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="32b44-120">Using 语句</span><span class="sxs-lookup"><span data-stu-id="32b44-120">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)

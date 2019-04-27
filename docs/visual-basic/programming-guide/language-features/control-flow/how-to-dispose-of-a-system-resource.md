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
ms.openlocfilehash: e3594db036edc3a6288b0373737c1ee26a691a57
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906732"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="2b343-102">如何：释放系统资源 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b343-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="2b343-103">可以使用`Using`块来确保系统在你的代码退出块时释放资源。</span><span class="sxs-lookup"><span data-stu-id="2b343-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="2b343-104">这是很有用，如果使用的这样做会消耗大量内存，或其他组件也想要使用的系统资源。</span><span class="sxs-lookup"><span data-stu-id="2b343-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="2b343-105">若要释放数据库连接时用完您的代码</span><span class="sxs-lookup"><span data-stu-id="2b343-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1. <span data-ttu-id="2b343-106">请务必加入相应[Imports 语句 （.NET Namespace 和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)开头的源文件的数据库连接 (在这种情况下， <xref:System.Data.SqlClient>)。</span><span class="sxs-lookup"><span data-stu-id="2b343-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2. <span data-ttu-id="2b343-107">创建`Using`块`Using`和`End Using`语句。</span><span class="sxs-lookup"><span data-stu-id="2b343-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="2b343-108">在块中，将处理与数据库连接的代码。</span><span class="sxs-lookup"><span data-stu-id="2b343-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3. <span data-ttu-id="2b343-109">声明连接并创建它的一个实例作为的一部分`Using`语句。</span><span class="sxs-lookup"><span data-stu-id="2b343-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="2b343-110">不管您如何退出块，包括大小写的未经处理的异常的资源，系统都会释放。</span><span class="sxs-lookup"><span data-stu-id="2b343-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="2b343-111">请注意，不能访问`sqc`从外部`Using`阻止，因为其作用域被限制为块。</span><span class="sxs-lookup"><span data-stu-id="2b343-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="2b343-112">对系统资源，例如文件句柄或 COM 包装器，可以使用此相同的技术。</span><span class="sxs-lookup"><span data-stu-id="2b343-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="2b343-113">您使用`Using`当你以确保想要保留的资源可供其他组件后您退出时，阻止`Using`块。</span><span class="sxs-lookup"><span data-stu-id="2b343-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b343-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b343-114">See also</span></span>

- <xref:System.Data.SqlClient.SqlConnection>
- [<span data-ttu-id="2b343-115">控制流</span><span class="sxs-lookup"><span data-stu-id="2b343-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="2b343-116">决策结构</span><span class="sxs-lookup"><span data-stu-id="2b343-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="2b343-117">循环结构</span><span class="sxs-lookup"><span data-stu-id="2b343-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="2b343-118">其他控件结构</span><span class="sxs-lookup"><span data-stu-id="2b343-118">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="2b343-119">嵌套的控件结构</span><span class="sxs-lookup"><span data-stu-id="2b343-119">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="2b343-120">Using 语句</span><span class="sxs-lookup"><span data-stu-id="2b343-120">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)

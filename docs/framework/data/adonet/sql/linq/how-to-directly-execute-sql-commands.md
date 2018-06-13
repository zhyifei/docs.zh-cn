---
title: 如何：直接执行 SQL 命令
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 90fb0d7027946ce4f38c2ba4930ac3510e2a42b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351867"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="8fcdc-102">如何：直接执行 SQL 命令</span><span class="sxs-lookup"><span data-stu-id="8fcdc-102">How to: Directly Execute SQL Commands</span></span>
<span data-ttu-id="8fcdc-103">采用 <xref:System.Data.Linq.DataContext> 连接时，可以使用 <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> 来执行不返回对象的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="8fcdc-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fcdc-104">示例</span><span class="sxs-lookup"><span data-stu-id="8fcdc-104">Example</span></span>  
 <span data-ttu-id="8fcdc-105">下面的示例会导致 SQL Server 将 UnitPrice 增加 1.00。</span><span class="sxs-lookup"><span data-stu-id="8fcdc-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8fcdc-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="8fcdc-106">See Also</span></span>  
 [<span data-ttu-id="8fcdc-107">如何：直接执行 SQL 查询</span><span class="sxs-lookup"><span data-stu-id="8fcdc-107">How to: Directly Execute SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)  
 [<span data-ttu-id="8fcdc-108">与数据库通信</span><span class="sxs-lookup"><span data-stu-id="8fcdc-108">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)

---
title: 如何：直接执行 SQL 命令
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 0ca62c0affc282140eb36979baafb8e3f9c89c35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737541"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="11cf7-102">如何：直接执行 SQL 命令</span><span class="sxs-lookup"><span data-stu-id="11cf7-102">How to: Directly Execute SQL Commands</span></span>
<span data-ttu-id="11cf7-103">采用 <xref:System.Data.Linq.DataContext> 连接时，可以使用 <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> 来执行不返回对象的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="11cf7-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11cf7-104">示例</span><span class="sxs-lookup"><span data-stu-id="11cf7-104">Example</span></span>  
 <span data-ttu-id="11cf7-105">下面的示例会导致 SQL Server 将 UnitPrice 增加 1.00。</span><span class="sxs-lookup"><span data-stu-id="11cf7-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="11cf7-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="11cf7-106">See also</span></span>
- [<span data-ttu-id="11cf7-107">如何：直接执行 SQL 查询</span><span class="sxs-lookup"><span data-stu-id="11cf7-107">How to: Directly Execute SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)
- [<span data-ttu-id="11cf7-108">与数据库通信</span><span class="sxs-lookup"><span data-stu-id="11cf7-108">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)

---
title: 如何：显示 LINQ to SQL 命令
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1decb05e-37ad-4ed6-ab2f-071eb4c4f628
ms.openlocfilehash: a70f1e0dd471e86afe2e744c157d4aed2a217deb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630822"
---
# <a name="how-to-display-linq-to-sql-commands"></a><span data-ttu-id="a60e3-102">如何：显示 LINQ to SQL 命令</span><span class="sxs-lookup"><span data-stu-id="a60e3-102">How to: Display LINQ to SQL Commands</span></span>
<span data-ttu-id="a60e3-103">使用 <xref:System.Data.Linq.DataContext.GetCommand%2A> 可显示 SQL 命令及其他信息。</span><span class="sxs-lookup"><span data-stu-id="a60e3-103">Use <xref:System.Data.Linq.DataContext.GetCommand%2A> to display SQL commands and other information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a60e3-104">示例</span><span class="sxs-lookup"><span data-stu-id="a60e3-104">Example</span></span>  
 <span data-ttu-id="a60e3-105">在下面的示例中，控制台窗口会显示执行查询所产生的输出，接着显示所生成的 SQL 命令、命令的类型和连接的类型。</span><span class="sxs-lookup"><span data-stu-id="a60e3-105">In the following example, the console window displays the output from the query, followed by the SQL commands that are generated, the type of commands, and the type of connection.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#3)]
 [!code-vb[DLinqDebuggingSupport#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#3)]  
  
 <span data-ttu-id="a60e3-106">输出形式如下：</span><span class="sxs-lookup"><span data-stu-id="a60e3-106">Output appears as follows:</span></span>  
  
```  
Customers from London:  
    Thomas Hardy  
    Victoria Ashworth  
    Elizabeth Brown  
    Ann Devon  
    Simon Crowther  
    Marie Bertrand  
    Hari Kumar  
    Dominique Perrier  
```  
  
```  
Command Text:  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
  
Command Type: Text  
  
Connection: System.Data.SqlClient.SqlConnection  
```  
  
## <a name="see-also"></a><span data-ttu-id="a60e3-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="a60e3-107">See also</span></span>
- [<span data-ttu-id="a60e3-108">调试支持</span><span class="sxs-lookup"><span data-stu-id="a60e3-108">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)

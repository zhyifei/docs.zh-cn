---
title: 如何：显示生成的 SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: 8a69b3ae83d7f701428b3183f2b80e0d44a06537
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103618"
---
# <a name="how-to-display-generated-sql"></a><span data-ttu-id="0285f-102">如何：显示生成的 SQL</span><span class="sxs-lookup"><span data-stu-id="0285f-102">How to: Display Generated SQL</span></span>
<span data-ttu-id="0285f-103">您可以通过使用 <xref:System.Data.Linq.DataContext.Log%2A> 属性查看为查询生成的 SQL 代码和更改处理方式。</span><span class="sxs-lookup"><span data-stu-id="0285f-103">You can view the SQL code generated for queries and change processing by using the <xref:System.Data.Linq.DataContext.Log%2A> property.</span></span> <span data-ttu-id="0285f-104">此方法对了解 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 功能和调试特定的问题可能很有用。</span><span class="sxs-lookup"><span data-stu-id="0285f-104">This approach can be useful for understanding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] functionality and for debugging specific problems.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0285f-105">示例</span><span class="sxs-lookup"><span data-stu-id="0285f-105">Example</span></span>  
 <span data-ttu-id="0285f-106">下面的示例使用 <xref:System.Data.Linq.DataContext.Log%2A> 属性在 SQL 代码执行前在控制台窗口中显示此代码。</span><span class="sxs-lookup"><span data-stu-id="0285f-106">The following example uses the <xref:System.Data.Linq.DataContext.Log%2A> property to display SQL code in the console window before the code is executed.</span></span>  <span data-ttu-id="0285f-107">您可以将此属性与查询、插入、更新和删除命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="0285f-107">You can use this property with query, insert, update, and delete commands.</span></span>  
  
 <span data-ttu-id="0285f-108">在控制台窗口中显示的行是 Visual Basic 中执行时看到的内容或C#下面的代码。</span><span class="sxs-lookup"><span data-stu-id="0285f-108">The lines from the console window are what you see when you execute the Visual Basic or C# code that follows.</span></span>  
  
```  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0285f-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="0285f-109">See also</span></span>

- [<span data-ttu-id="0285f-110">调试支持</span><span class="sxs-lookup"><span data-stu-id="0285f-110">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)

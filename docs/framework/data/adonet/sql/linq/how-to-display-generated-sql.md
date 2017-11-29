---
title: "如何：显示生成的 SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 523a6cbd0174da4c294e5fd2ab2d0217fc63cb5c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-generated-sql"></a><span data-ttu-id="b95de-102">如何：显示生成的 SQL</span><span class="sxs-lookup"><span data-stu-id="b95de-102">How to: Display Generated SQL</span></span>
<span data-ttu-id="b95de-103">您可以通过使用 <xref:System.Data.Linq.DataContext.Log%2A> 属性查看为查询生成的 SQL 代码和更改处理方式。</span><span class="sxs-lookup"><span data-stu-id="b95de-103">You can view the SQL code generated for queries and change processing by using the <xref:System.Data.Linq.DataContext.Log%2A> property.</span></span> <span data-ttu-id="b95de-104">此方法对了解 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 功能和调试特定的问题可能很有用。</span><span class="sxs-lookup"><span data-stu-id="b95de-104">This approach can be useful for understanding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] functionality and for debugging specific problems.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b95de-105">示例</span><span class="sxs-lookup"><span data-stu-id="b95de-105">Example</span></span>  
 <span data-ttu-id="b95de-106">下面的示例使用 <xref:System.Data.Linq.DataContext.Log%2A> 属性在 SQL 代码执行前在控制台窗口中显示此代码。</span><span class="sxs-lookup"><span data-stu-id="b95de-106">The following example uses the <xref:System.Data.Linq.DataContext.Log%2A> property to display SQL code in the console window before the code is executed.</span></span>  <span data-ttu-id="b95de-107">您可以将此属性与查询、插入、更新和删除命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="b95de-107">You can use this property with query, insert, update, and delete commands.</span></span>  
  
 <span data-ttu-id="b95de-108">控制台窗口中显示的行就是您在执行后面的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 或 C# 代码时看到的内容。</span><span class="sxs-lookup"><span data-stu-id="b95de-108">The lines from the console window are what you see when you execute the [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# code that follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b95de-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b95de-109">See Also</span></span>  
 [<span data-ttu-id="b95de-110">调试支持</span><span class="sxs-lookup"><span data-stu-id="b95de-110">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)

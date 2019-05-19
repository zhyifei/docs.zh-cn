---
title: 如何：重复使用 ADO.NET 命令和 DataContext 之间的连接
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 92b0d8cf2c4904fabc17241ef2c31175f0c87baf
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878541"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="e6ac1-102">如何：重复使用 ADO.NET 命令和 DataContext 之间的连接</span><span class="sxs-lookup"><span data-stu-id="e6ac1-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="e6ac1-103">因为[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]属于 ADO.NET 系列技术，通过 ADO.NET 中，您可以重复使用 ADO.NET 命令之间的连接提供基于服务和一个<xref:System.Data.Linq.DataContext>。</span><span class="sxs-lookup"><span data-stu-id="e6ac1-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the ADO.NET family of technologies and is based on services provided by ADO.NET, you can reuse a connection between an ADO.NET command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6ac1-104">示例</span><span class="sxs-lookup"><span data-stu-id="e6ac1-104">Example</span></span>  
 <span data-ttu-id="e6ac1-105">下面的示例演示如何重用 ADO.NET 命令之间的相同连接和<xref:System.Data.Linq.DataContext>。</span><span class="sxs-lookup"><span data-stu-id="e6ac1-105">The following example shows how to reuse the same connection between an ADO.NET command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="e6ac1-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6ac1-106">See also</span></span>

- [<span data-ttu-id="e6ac1-107">背景信息</span><span class="sxs-lookup"><span data-stu-id="e6ac1-107">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="e6ac1-108">ADO.NET 和 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e6ac1-108">ADO.NET and LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)
- [<span data-ttu-id="e6ac1-109">与数据库通信</span><span class="sxs-lookup"><span data-stu-id="e6ac1-109">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)

---
title: 如何：重复使用 ADO.NET 命令和 DataContext 之间的连接
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: f1ee7726042327eae88e69e9e6d062909c5bc74e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793286"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>如何：重复使用 ADO.NET 命令和 DataContext 之间的连接
由于[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]是 ADO.NET 系列技术的一部分，并且基于 ADO.NET 提供的服务，因此你可以重复使用 ADO.NET 命令<xref:System.Data.Linq.DataContext>和之间的连接。  
  
## <a name="example"></a>示例  
 下面的示例演示如何在 ADO.NET 命令和<xref:System.Data.Linq.DataContext>之间重复使用相同的连接。  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>请参阅

- [背景信息](background-information.md)
- [ADO.NET 和 LINQ to SQL](ado-net-and-linq-to-sql.md)
- [与数据库通信](communicating-with-the-database.md)

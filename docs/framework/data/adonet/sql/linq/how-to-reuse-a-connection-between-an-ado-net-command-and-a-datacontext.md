---
title: "如何：重复使用 ADO.NET 命令和 DataContext 之间的连接"
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
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 483a97817162140af61df6a58c3e9ab003235c74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>如何：重复使用 ADO.NET 命令和 DataContext 之间的连接
因为[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]属于[!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]系列技术，并根据所提供的服务[!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]，你可以重复使用之间的连接[!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]命令和<xref:System.Data.Linq.DataContext>。  
  
## <a name="example"></a>示例  
 下面的代码说明了如何重用 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 命令和 <xref:System.Data.Linq.DataContext> 之间的同一连接。  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>另请参阅  
 [背景信息](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [ADO.NET 和 LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)  
 [与数据库通信](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)

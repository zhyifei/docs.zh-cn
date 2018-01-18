---
title: "入门"
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
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6cea3468732367a7c179528601327f0110c0e38c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="getting-started"></a>入门
通过使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]，你可以使用[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]技术访问 SQL 数据库，就像您访问内存中的集合。  
  
 例如，在下面的代码中，创建了 `nw` 对象来表示 `Northwind` 数据库，将 `Customers` 表作为目标，筛选出了来自 `Customers` 的 `London` 行，并选择了一个表示 `CompanyName` 的字符串以进行检索。  
  
 执行循环时，将检索到 `CompanyName` 值的集合。  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a>后续步骤  
 有关其他的一些示例，包括插入和更新，请参阅[什么你可以执行与 LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md)。  
  
 接下来，请试着按一些演练和教程中的说明动手操作，实际体验一下 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的使用。 请参阅[通过演练学习](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)。  
  
 最后，了解如何开始使用你自己[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]通过读取项目[使用 linq to SQL 的典型步骤](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)。  
  
## <a name="see-also"></a>请参阅  
 [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [LINQ 简介](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e)  
 [LINQ to SQL 对象模型](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)

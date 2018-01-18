---
title: "如何：通过使用事务对数据提交进行分类"
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
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a5d7f1e0b0419874f694a0b3953f6b037a777016
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>如何：通过使用事务对数据提交进行分类
您可以使用 <xref:System.Transactions.TransactionScope> 来封闭您提交到数据库的数据。 有关详细信息，请参阅[事务支持](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)。  
  
## <a name="example"></a>示例  
 下面的代码将数据库提交数据封闭在 <xref:System.Transactions.TransactionScope> 中。  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>请参阅  
 [下载示例数据库](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [进行和提交数据更改](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [事务支持](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)

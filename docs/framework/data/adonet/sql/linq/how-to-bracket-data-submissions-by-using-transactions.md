---
title: 如何：通过使用事务对数据提交进行分类
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 6a4c5ba7c4938b48fe489e43ff4a3ff806bd8916
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793814"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>如何：通过使用事务对数据提交进行分类
您可以使用 <xref:System.Transactions.TransactionScope> 来封闭您提交到数据库的数据。 有关详细信息，请参阅[事务支持](transaction-support.md)。  
  
## <a name="example"></a>示例  
 下面的代码将数据库提交数据封闭在 <xref:System.Transactions.TransactionScope> 中。  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>请参阅

- [下载示例数据库](downloading-sample-databases.md)
- [进行和提交数据更改](making-and-submitting-data-changes.md)
- [事务支持](transaction-support.md)

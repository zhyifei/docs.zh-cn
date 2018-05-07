---
title: 通过仅使用存储过程自定义操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 3c60a9e430b4228117fd03a43a30f27342154b1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a>通过仅使用存储过程自定义操作
通过仅使用存储过程来访问数据是常见的情况。  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 你可以修改提供的示例[自定义操作通过使用存储过程](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)通过甚至第一个查询 （这会导致动态 SQL 执行） 将替换为用于包装存储的过程的方法调用。  
  
 假定 `CustomersByCity` 就是此方法，如下面的示例所示。  
  
### <a name="code"></a>代码  
 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 下面的代码不用任何动态 SQL 即可执行。  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>请参阅  
 [开发人员在重写默认行为中的责任](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)

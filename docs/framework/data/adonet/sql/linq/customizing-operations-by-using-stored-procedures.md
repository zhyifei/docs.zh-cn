---
title: "通过使用存储过程自定义操作"
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
ms.assetid: aedbecc1-c33c-4fb4-8861-fdf7e1dc6b8a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9110cec32075c85807d3ef1550ae1a9e63b4239f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="customizing-operations-by-using-stored-procedures"></a>通过使用存储过程自定义操作
存储过程代表用于重写默认行为的常见方法。 本主题中的示例演示了如何将生成的方法包装用于存储过程，以及如何直接调用存储过程。  
  
 如果您使用的是 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]，则可以使用 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 分配存储过程以执行插入、更新和删除。  
  
> [!NOTE]
>  若要读回数据库生成的值，请在存储过程中使用输出参数。 如果无法使用输出参数，请编写分部方法实现，而不是依靠[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]生成的重写。 在成功完成 `INSERT` 或 `UPDATE` 操作后，必须将映射到数据库生成的值的成员设置为适当的值。 有关详细信息，请参阅[开发人员在重写默认行为中的责任](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)。  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 在下面的示例中，假定 `Northwind` 类包含两个方法，这两个方法可用来调用要用于派生类中的重写的存储过程。  
  
### <a name="code"></a>代码  
 [!code-csharp[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefaultSproc#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#1)]  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的类将这些方法用于重写。  
  
### <a name="code"></a>代码  
 [!code-csharp[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefaultSproc#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#2)]  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 您可以完全像使用 `NorthwindThroughSprocs` 一样使用 `Northwnd`。  
  
### <a name="code"></a>代码  
 [!code-csharp[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefaultSproc#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>另请参阅  
 [开发人员在重写默认行为的职责](../../../../../../docs/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior.md)

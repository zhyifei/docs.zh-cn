---
title: KEY (Entity SQL)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cbaa97a8-c89c-4460-8c74-00474695789f
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: aa18efd32998f881d49d7ebd71bad0cdf8122457
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="key-entity-sql"></a>KEY (Entity SQL)
提取引用或实体表达式的键。  
  
## <a name="syntax"></a>语法  
  
```  
KEY(createref_expression)  
```  
  
## <a name="remarks"></a>备注  
 实体键按指定实体或实体引用的正确顺序包含键值。 因为多个实体集可以基于相同的类型，所以同一个键可能出现在每个实体集中。 若要获取唯一引用，请使用 `REF`。 KEY 运算符的返回类型为行类型，该行类型按相同顺序为实体的每个键包含一个字段。  
  
 在下面的示例中，键运算符传递对 BadOrder 实体的引用，并返回该引用的键部分。 在此示例中，一个记录类型恰好包含对应于 `Id` 属性的一个字段。  
  
```  
select Key( CreateRef(LOB.BadOrders, row(o.Id)) )   
from LOB.Orders as o  
```  
  
## <a name="example"></a>示例  
 下面的 Entity SQL 查询使用 KEY 运算符提取具有类型引用的表达式的键部分。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2.  将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#KEY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#key)]  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)

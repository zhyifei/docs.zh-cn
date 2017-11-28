---
title: REF (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: dfc91b60c68f55def8e7f81c2c5dd068c23f6e69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ref-entity-sql"></a>REF (Entity SQL)
返回对实体实例的引用。  
  
## <a name="syntax"></a>语法  
  
```  
REF( expression )   
```  
  
## <a name="arguments"></a>参数  
 `expression`  
 产生实体类型实例的任何有效表达式。  
  
## <a name="return-value"></a>返回值  
 对指定实体实例的引用。  
  
## <a name="remarks"></a>备注  
 实体引用由实体键和实体集名称组成。 不同的实体集可以基于相同的实体类型，因此一个特定实体键可以出现在多个实体集中。 但是，实体引用始终是唯一的。 如果输入表达式表示一个持久化实体，则会返回对此实体的引用。 如果输入表达式不是一个持久化实体，则会返回空引用。  
  
 如果使用属性提取运算符 (.) 访问实体的属性，则会自动取消引用。  
  
## <a name="example"></a>示例  
 下面的 Entity SQL 查询使用 REF 运算符返回输入实体参数的引用。 由于使用属性提取运算符 (.) 访问 Product 实体的属性，同一查询会取消引用。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  按照中的步骤[如何： 执行查询该返回 PrimitiveType 结果](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。  
  
2.  将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## <a name="see-also"></a>另请参阅  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [密钥](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [类型定义](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)

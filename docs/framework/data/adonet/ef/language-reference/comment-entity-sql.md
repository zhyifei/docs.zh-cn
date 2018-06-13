---
title: --（注释）(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
ms.openlocfilehash: 4b3c801999d520a775c1a7026c945c027145b59d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764159"
---
# <a name="---comment-entity-sql"></a>--（注释）(Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 查询可以包含注释。 注释行以两个短划线 (`--`) 开头。  
  
## <a name="syntax"></a>语法  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a>自变量  
 `text_of_comment`  
 包含注释文本的字符串。  
  
## <a name="example"></a>示例  
 下面的 Entity SQL 查询演示如何使用注释。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2.  将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 概述](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

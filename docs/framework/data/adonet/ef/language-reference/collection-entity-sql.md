---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 2b13d373e6c54221249b17de4fa91347cbc0f9e6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="collection-entity-sql"></a>COLLECTION (Entity SQL)
COLLECTION 关键字仅在内联函数的定义中使用。 集合函数是对值的集合进行操作并生成标量输出的函数。  
  
## <a name="syntax"></a>语法  
  
```  
COLLECTION(type_definition)   
```  
  
## <a name="arguments"></a>自变量  
 `type_definition`  
 一个表达式，返回受支持类型、行或引用的集合。  
  
## <a name="remarks"></a>备注  
 有关 COLLECTION 关键字的详细信息，请参阅 [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 COLLECTION 关键字将十进制值集合声明为内联查询函数的参数。  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

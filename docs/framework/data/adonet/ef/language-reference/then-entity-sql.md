---
title: THEN (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d7a669cc87c14e4213d702b639a1956f04cb485d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="then-entity-sql"></a>THEN (Entity SQL)
当 WHEN 子句取值为 `true`时的结果。  
  
## <a name="syntax"></a>语法  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a>自变量  
 `when_expression`  
 任何有效的 Boolean 表达式。  
  
 `then_expression`  
 任何返回集合的有效查询表达式。  
  
## <a name="remarks"></a>备注  
 如果 `when_expression` 取值为 `true`，则结果为对应的 `then-expression`。 如果任何 WHEN 条件均未得以满足，将求出 `else-expression` 的值。 然而，如果没有 `else-expression`，则结果为空值。  
  
 有关示例，请参阅[用例](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)。  
  
## <a name="example"></a>示例  
 以下 Entity SQL 查询使用 CASE 表达式计算一组 `Boolean` 表达式的值。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  按照中的步骤[如何： 执行查询该返回 PrimitiveType 结果](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)。  
  
2.  将以下查询作为参数传递给 `ExecutePrimitiveTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>请参阅  
 [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

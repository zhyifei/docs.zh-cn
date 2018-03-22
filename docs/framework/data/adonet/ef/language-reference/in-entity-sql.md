---
title: IN (Entity SQL)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: d32e5012b4acbf0ecd6830f549de5dccf79bb38b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="in-entity-sql"></a>IN (Entity SQL)
确定某个值是否与某个集合中的任何值匹配。  
  
## <a name="syntax"></a>语法  
  
```  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a>自变量  
 `value`  
 返回匹配值的任何有效表达式。  
  
 [ NOT ]  
 指定对 IN 的 `Boolean` 结果取反。  
  
 `expression`  
 返回集合以测试是否具有匹配的任何有效表达式。 所有表达式都必须与 `value` 一样属于同一类型或属于公共基类型或派生类型。  
  
## <a name="return-value"></a>返回值  
 如果在集合中找到此值，则为 `true`；如果值为空或集合为空，则为空；否则为 `false`。 使用 NOT IN 可对 IN 的结果取反。  
  
## <a name="example"></a>示例  
 以下 Entity SQL 查询使用 IN 运算符以确定某个值是否与集合中的任何值匹配。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2.  将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

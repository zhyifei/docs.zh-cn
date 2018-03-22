---
title: '&lt;=（小于或等于）(Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: c6ad4e03a2221491276ae64cf292df8ce3ccd53d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="lt-less-than-or-equal-to-entity-sql"></a>&lt;=（小于或等于）(Entity SQL)
比较两个表达式以确定左侧表达式的值是否小于或等于右侧表达式的值。  
  
## <a name="syntax"></a>语法  
  
```  
expression <= expression  
```  
  
## <a name="arguments"></a>自变量  
 `expression`  
 任何有效表达式。 两个表达式都必须具有可隐式转换的数据类型。  
  
## <a name="result-types"></a>结果类型  
 如果左侧表达式的值小于或等于右侧表达式的值，则为`true` ；否则为 `false`。  
  
## <a name="example"></a>示例  
 下面的 Entity SQL 查询使用 <= 比较运算符比较两个表达式，以确定左侧表达式的值是否小于或等于右侧表达式的值。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2.  将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less_or_equals)]  
  
## <a name="see-also"></a>请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

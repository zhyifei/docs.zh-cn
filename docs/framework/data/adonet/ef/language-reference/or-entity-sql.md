---
title: '|| (OR) (Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: b44934aa0db73f872f0ab27a4c36c5c615855de1
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="-or-entity-sql"></a>|| (OR) (Entity SQL)
组合两个 `Boolean` 表达式。  
  
## <a name="syntax"></a>语法  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a>自变量  
 `boolean_expression`  
 返回 `Boolean`的任何有效表达式。  
  
## <a name="return-value"></a>返回值  
 当任何一个条件为`true` 时，为 `true`；否则为 `false`。  
  
## <a name="remarks"></a>备注  
 OR 是 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 逻辑运算符。 它用于组合两个条件。 在一个语句中使用多个逻辑运算符时，首先计算 AND 运算符，然后计算 OR 运算符。 不过，使用括号可以更改求值的顺序。  
  
 双竖线 (&#124;&#124;) 具有相同的功能与 OR 运算符。  
  
 下表显示可能的输入值和返回类型。  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|true|TRUE|TRUE|  
|`FALSE`|TRUE|FALSE|NULL|  
|`NULL`|TRUE|NULL|NULL|  
  
## <a name="example"></a>示例  
 以下 Entity SQL 查询使用 OR 运算符以组合两个 `Boolean` 表达式。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  执行 [如何：执行返回 StructuralType 结果的查询](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2.  将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a>另请参阅  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

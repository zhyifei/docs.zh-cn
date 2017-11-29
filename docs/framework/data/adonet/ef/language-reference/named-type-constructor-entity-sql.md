---
title: "命名类型构造函数 (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 72a19094beb03982448a102a4c7362a026d9e611
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="named-type-constructor-entity-sql"></a>命名类型构造函数 (Entity SQL)
用于创建概念模型名义类型（如实体或复杂类型）的实例。  
  
## <a name="syntax"></a>语法  
  
```  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a>参数  
 `identifier`  
 作为简单标识符或带引号的标识符的值。 有关详细信息，请参阅[标识符](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
  
 `expression`  
 类型的属性，假设这些属性的顺序与它们在类型声明中的顺序相同。  
  
## <a name="return-value"></a>返回值  
 命名复杂类型和实体类型的实例。  
  
## <a name="remarks"></a>备注  
 下面的示例演示如何构造名义类型和复杂类型：  
  
 下面的表达式创建 `Person` 类型的实例：  
  
 `Person("abc", 12)`  
  
 下面的表达式创建复杂类型的实例：  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 下面的表达式创建嵌套复杂类型的实例：  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 下面的表达式创建具有嵌套复杂类型的实体的实例：  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 下面的示例演示如何将复杂类型的属性初始化为 null：`MyModel.ZipCode(‘98118’, null)`  
  
## <a name="example"></a>示例  
 下面的 Entity SQL 查询使用命名类型构造函数创建概念模型类型的实例。 此查询基于 AdventureWorks 销售模型。 若要编译并运行此查询，请执行下列步骤：  
  
1.  执行 [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)中的过程。  
  
2.  将以下查询作为参数传递给 `ExecuteStructuralTypeQuery` 方法：  
  
 [!code-csharp[DP EntityServices Concepts 2#NAMED_TYPE_CONSTRUCTOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#named_type_constructor)]  
  
## <a name="see-also"></a>另请参阅  
 [构造类型](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
 [实体 SQL 引用](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)

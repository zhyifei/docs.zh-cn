---
title: COLLECTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 5a1af1aab8a084b19e48fbdbb159d7ddd8a8dd7c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039906"
---
# <a name="collection-entity-sql"></a>COLLECTION (Entity SQL)
COLLECTION 关键字仅在内联函数的定义中使用。 集合函数是对值的集合进行操作并生成标量输出的函数。  
  
## <a name="syntax"></a>语法  
  
```csharp  
COLLECTION(type_definition)
```  
  
## <a name="arguments"></a>自变量  
 `type_definition`  
 一个表达式，返回受支持类型、行或引用的集合。  
  
## <a name="remarks"></a>备注  
 有关 COLLECTION 关键字的详细信息，请参阅 [Type Definitions](type-definitions-entity-sql.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 COLLECTION 关键字将十进制值集合声明为内联查询函数的参数。  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a>请参阅

- [实体 SQL 引用](entity-sql-reference.md)

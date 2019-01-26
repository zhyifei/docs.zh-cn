---
title: 如何：执行多态查询
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 2b1493ffc2aaa4c3716cbd6d1ac0f350ed39a8f1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746578"
---
# <a name="how-to-execute-a-polymorphic-query"></a>如何：执行多态查询
本主题演示如何执行多态[!INCLUDE[esql](../../../../../includes/esql-md.md)]使用查询[OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md)运算符。  
  
### <a name="to-run-the-code-in-this-example"></a>运行本示例中的代码  
  
1.  添加[School 模型](https://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac)到你的项目和配置项目以使用实体框架。 有关详细信息，请参阅[如何：使用实体数据模型向导](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d)。  
  
2.  在应用程序的代码页中，添加以下 `using` 语句（在 Visual Basic 中为 `Imports`）：  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  修改概念模型中的步骤具有表每个层次结构继承[演练：映射继承-每个层次结构一个表](https://msdn.microsoft.com/library/49b685cf-9db8-4d6d-b885-8837ed238f55)。  
  
## <a name="example"></a>示例  
 下面的示例使用 OFTYPE 运算符从 `OnsiteCourses` 的集合中获取和显示仅包含 `Courses` 的集合。  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## <a name="see-also"></a>请参阅
- [用于实体框架的 EntityClient 提供程序](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
- [实体 SQL 语言](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)

---
title: 比较表达式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec7637a9-01d5-4a95-8bb0-478311cd263b
ms.openlocfilehash: 5d201d331d766d865d0ee7afb164813084fa3651
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="comparison-expressions"></a>比较表达式
比较表达式检查常量值、属性值或方法结果是否等于、不等于、大于或小于另一个值。 如果特定比较对 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 无效，则将引发异常。 所有比较（无论隐式和显式）都要求所有组件在数据源中是可比较的。 比较表达式通常在 `Where` 子句中用于限制查询结果。  
  
 以下查询表达式语法示例演示一个查询，该查询返回销售订单编号等于“SO43663”的结果：  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression)]  
  
 以下基于方法的查询语法示例演示一个查询，该查询返回销售订单编号等于“SO43663”的结果：  
  
 [!code-csharp[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#restrictionexpression_mq)]
 [!code-vb[DP L2E Conceptual Examples#RestrictionExpression_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#restrictionexpression_mq)]  
  
 以下查询表达式语法示例演示一个查询，该查询返回发货日期等于“July 8, 2001”的销售订单信息：  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison)]  
  
 以下基于方法的查询语法示例演示一个查询，该查询返回发货日期等于“July 8, 2001”的销售订单信息：  
  
 [!code-csharp[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#datetimecomparison_mq)]
 [!code-vb[DP L2E Conceptual Examples#DateTimeComparison_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#datetimecomparison_mq)]  
  
 生成常量的表达式在服务器上进行转换，不会尝试执行本地计算。 下面的示例在 `Where` 子句中使用生成常量的表达式。  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constantexpression)]
 [!code-vb[DP L2E Conceptual Examples#ConstantExpression](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constantexpression)]  
  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 不支持将用户类用作常量。 但是，用户类上的属性引用被视为常量，将转换为命令目录树常量表达式并在数据源上执行。  
  
 [!code-csharp[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#myclass)]
 [!code-vb[DP L2E Conceptual Examples#MyClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#myclass)]  
  
 [!code-csharp[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#propertyasconstant)]
 [!code-vb[DP L2E Conceptual Examples#PropertyAsConstant](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#propertyasconstant)]  
  
 不支持返回常量表达式的方法。 下面的示例在 `Where` 子句中使用一个返回常量的方法。 此示例将在运行时引发异常。  
  
 [!code-csharp[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#methodasconstantfails)]
 [!code-vb[DP L2E Conceptual Examples#MethodAsConstantFails](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#methodasconstantfails)]  
  
## <a name="see-also"></a>请参阅  
 [LINQ to Entities 查询中的表达式](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)

---
title: 基于方法的查询语法示例：分区
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b7b64874-c3c8-4bdb-862c-89a168d07827
ms.openlocfilehash: 6a1f4d13a75f787730d6155161296c3307b845f6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528353"
---
# <a name="method-based-query-syntax-examples-partitioning"></a>基于方法的查询语法示例：分区
本主题中的示例演示如何使用<xref:System.Linq.Enumerable.Skip%2A>，并<xref:System.Linq.Enumerable.Take%2A>方法来查询[AdventureWorks 销售模型](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)使用查询表达式语法。 这些示例中使用的 AdventureWorks 销售模型从 AdventureWorks 示例数据库中的 Contact、Address、Product、SalesOrderHeader 和 SalesOrderDetail 等表生成。  
  
 本主题中的示例使用以下`using` / `Imports`语句：  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a>Skip  
  
### <a name="example"></a>示例  
 以下示例使用 <xref:System.Linq.Enumerable.Skip%2A> 方法以获取 Contact 表中除前五个联系人之外的所有联系人。  
  
 [!code-csharp[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a>示例  
 以下示例使用 <xref:System.Linq.Enumerable.Skip%2A> 方法以获取 Seattle 的前两个地址之外的所有地址。  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a>Take  
  
### <a name="example"></a>示例  
 以下示例使用 <xref:System.Linq.Enumerable.Take%2A> 方法以只从 Contact 表中获取前五个联系人。  
  
 [!code-csharp[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a>示例  
 以下示例使用 <xref:System.Linq.Enumerable.Take%2A> 方法以获取 Seattle 的前三个地址。  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a>请参阅  
 [LINQ to Entities 中的查询](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)

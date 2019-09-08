---
title: 构建投影
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
ms.openlocfilehash: 0dfd5d951750de2ab918c51dd9f4f2deeb8a6318
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793829"
---
# <a name="formulate-projections"></a>构建投影
下面的示例演示如何将`select`中的C#和`Select` Visual Basic 语句中的语句与其他功能组合起来以形成查询投影。  
  
## <a name="example"></a>示例  
 下面的示例使用中`Select` `select` C#Visual Basic （子句）中的子句来`Customers`返回的联系人名称序列。  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a>示例  
 下面的示例使用 Visual Basic `Select` （`select`中C#的子句）和*匿名类型*中的子句来返回的联系人姓名和电话号码`Customers`序列。  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a>示例  
 下面的示例使用 Visual Basic `Select` （`select`中C#的子句）和*匿名类型*中的子句来返回雇员的姓名和电话号码序列。 在产生的序列中，`FirstName` 和 `LastName` 字段组合成单个字段 (`Name`)，`HomePhone` 字段重命名为 `Phone`。  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a>示例  
 下面的示例使用中`Select` Visual Basic （`select`子句中C#的子句）和*匿名类型*中的子句来返回所有`ProductID`和名为`HalfPrice`的计算值的序列。 此值设置为 `UnitPrice` 的 1/2。  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a>示例  
 下面的示例使用 Visual Basic `Select` （`select`中C#的子句）和一个*条件语句*中的子句来返回产品名称和产品可用性序列。  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a>示例  
 下面的`Select`示例使用 Visual Basic 子句（`select` in 中C#的子句）和一个*已知类型*（Name）返回雇员姓名的序列。  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a>示例  
 下面的示例在`Select` Visual Basic `Where` （`select` `where`和中C#）使用和，以返回伦敦的客户的联系人姓名的*筛选序列*。  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a>示例  
 下面的示例在的`Select` `select` C#Visual Basic （子句）和*匿名类型*中使用子句来返回有关客户的数据的*形状子集*。  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a>示例  
 下面的示例使用嵌套查询返回以下结果：  
  
- 由所有订单及其对应的 `OrderID` 组成的序列。  
  
- 由订单中具有折扣的项组成的子序列。  
  
- 不含运费时节省的资金数额。  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a>请参阅

- [查询示例](query-examples.md)

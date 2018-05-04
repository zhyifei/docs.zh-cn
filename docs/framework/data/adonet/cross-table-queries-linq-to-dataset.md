---
title: 跨表查询 (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
ms.openlocfilehash: 17f9e683161fba0fe57279952acecd9e4399d0aa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="cross-table-queries-linq-to-dataset"></a>跨表查询 (LINQ to DataSet)
除了查询单个表外，也可以在 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 中执行交叉表查询。 这可通过使用*联接*。 联接就是将一个数据源中的对象与另一个数据源中具有相同公共属性的对象（例如产品或联系人 ID）相关联。 在面向对象的编程中，由于每个对象都有引用另一个对象的成员，所以对象间的关系相对较容易导航。 但在外部数据库表中，导航关系不像这样简单。 数据库表不包含内置关系。 在这些情况下，可以通过联接操作来匹配每个源中的元素。 例如，假设有两个分别包含产品信息和销售信息的表，您可以使用联接操作来匹配同一销售订单的销售信息和产品。  
  
 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] Framework 提供了两个联接运算符，<xref:System.Linq.Enumerable.Join%2A>和<xref:System.Linq.Enumerable.GroupJoin%2A>。 这些运算符执行*的同等联接*： 即，来匹配两个数据联接源仅当其键是否相等时。 （相对而言，[!INCLUDE[tsql](../../../../includes/tsql-md.md)] 支持 `equals` 以外的其他连接运算符，如 `less than` 运算符）。  
  
 对于关系数据库，<xref:System.Linq.Enumerable.Join%2A> 实现内部联接。 内部联接是仅返回在相对数据集中具有匹配对象的那些对象的一种联接类型。  
  
 <xref:System.Linq.Enumerable.GroupJoin%2A>运算符在关系数据库术语中具有无直接等效项; 它们实现内部联接和左外部联接的超集。 左外部联接是一种联接，返回的第一个 （左侧） 集合，每个元素，即使它具有第二个集合中没有关联的元素。  
  
 有关连接的详细信息，请参阅[联接运算](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107)。  
  
## <a name="example"></a>示例  
 下面的示例对 AdventureWorks 示例数据库中的 `SalesOrderHeader` 和 `SalesOrderDetail` 表执行传统联接以获取 8 月份以来的在线订单。  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a>请参阅  
 [查询数据集](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [单表查询](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)  
 [查询类型化数据集](../../../../docs/framework/data/adonet/querying-typed-datasets.md)  
 [联接运算](http://msdn.microsoft.com/library/442d176d-028c-4beb-8d22-407d4ef89107)  
 [LINQ to DataSet 示例](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)

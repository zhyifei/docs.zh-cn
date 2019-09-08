---
title: 导航数据表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 5008f8397b7d396b14fdfe8e24f1e59785c4319d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785250"
---
# <a name="navigating-datatables"></a>导航数据表
<xref:System.Data.DataTableReader> 以一个或多个只读、只进结果集的形式获取一个或多个 <xref:System.Data.DataTable> 对象的内容。  
  
 如果 <xref:System.Data.DataTableReader> 是使用 <xref:System.Data.DataSet.CreateDataReader%2A> 方法创建，则可以包含多个结果集。 如果包含多个结果集，<xref:System.Data.DataTableReader.NextResult%2A> 方法会将游标前进到下一个结果集。 这是一个只进过程。 无法返回到前一个结果集。  
  
## <a name="example"></a>示例  
 在下面的示例中， `TestConstructor`方法创建两<xref:System.Data.DataTable>个实例。 为了演示此<xref:System.Data.DataTableReader>类的构造函数，该示例基于包含两个数据表的数组创建新的**DataTableReader** ，并执行一个简单的操作，打印前几个**数据表**中的内容列到控制台窗口。  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a>请参阅

- [DataTableReader](datatablereaders.md)
- [ADO.NET 概述](../ado-net-overview.md)

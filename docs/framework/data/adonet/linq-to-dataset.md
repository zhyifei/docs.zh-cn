---
title: LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
ms.openlocfilehash: 36335f90c7850fa00a15e7112b7473637250c656
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306239"
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
使用 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 可以更快更容易地查询在 <xref:System.Data.DataSet> 对象中缓存的数据。 具体而言，通过使开发人员能够使用编程语言本身而不是通过使用单独的查询语言来编写查询，[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 可以简化查询。 这是非常适合 Visual Studio 开发人员，他们现在可以充分利用编译时语法检查、 静态类型化，并在其查询中的 Visual Studio 提供 IntelliSense 支持。  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 也可用于查询从一个或多个数据源合并的数据。 这可以使许多需要灵活表示和处理数据的方案（例如查询本地聚合的数据和 Web 应用程序中的中间层缓存）能够实现。 具体地说，一般报告、分析和业务智能应用程序将需要这种操作方法。  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]功能主要通过中的扩展方法公开<xref:System.Data.DataRowExtensions>和<xref:System.Data.DataTableExtensions>类。 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 基于并使用现有的 ADO.NET 体系结构，而不是为了替换应用程序代码中的 ADO.NET。 现有的 ADO.NET 代码将继续工作在[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]应用程序。 之间的关系[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]ADO.NET 和数据存储区在下图中所示。  
  
 ![显示 LINQ to DataSet 基于 ADO.NET 提供程序关系图。](./media/linq-to-dataset/linq-dataset-ado-dotnet-provider.gif)  
  
## <a name="in-this-section"></a>本节内容  
 [入门](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [编程指南](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>参考  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>请参阅

- [语言集成查询 (LINQ) - C#](../../../csharp/programming-guide/concepts/linq/index.md)
- [语言集成查询 (LINQ) - Visual Basic](../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ 和 ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [ADO.NET](../../../../docs/framework/data/adonet/index.md)

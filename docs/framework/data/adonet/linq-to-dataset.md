---
title: LINQ to DataSet
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 743e3755-3ecb-45a2-8d9b-9ed41f0dcf17
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 3746fb31c66202dc75c6aff3ce69952f25b06931
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="linq-to-dataset"></a>LINQ to DataSet
使用 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 可以更快更容易地查询在 <xref:System.Data.DataSet> 对象中缓存的数据。 具体而言，通过使开发人员能够使用编程语言本身而不是通过使用单独的查询语言来编写查询，[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 可以简化查询。 这是非常适合 Visual Studio 开发人员，他们现在可以充分利用编译时语法检查、 静态类型和提供的 Visual Studio 在查询中的 IntelliSense 支持。  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 也可用于查询从一个或多个数据源合并的数据。 这可以使许多需要灵活表示和处理数据的方案（例如查询本地聚合的数据和 Web 应用程序中的中间层缓存）能够实现。 具体地说，一般报告、分析和业务智能应用程序将需要这种操作方法。  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]主要通过中的扩展方法公开功能<xref:System.Data.DataRowExtensions>和<xref:System.Data.DataTableExtensions>类。 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 基于并使用现有[!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)]体系结构，不能替换[!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)]应用程序代码中。 现有的 ADO.NET 2.0 代码将继续在 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 应用程序中有效。 下图阐释了 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 与 [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] 和数据存储区的关系。  
  
 ![LINQ to DataSet 基于 ADO.NET 提供程序](../../../../docs/framework/data/adonet/media/linqtodataset.gif "LINQtoDataSet")  
  
## <a name="in-this-section"></a>本节内容  
 [入门](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)  
  
 [编程指南](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
  
## <a name="reference"></a>参考  
 <xref:System.Data.DataTableExtensions>  
  
 <xref:System.Data.DataRowExtensions>  
  
 <xref:System.Data.DataRowComparer>  
  
## <a name="see-also"></a>请参阅  
 [LINQ（语言集成查询）](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [LINQ 和 ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)

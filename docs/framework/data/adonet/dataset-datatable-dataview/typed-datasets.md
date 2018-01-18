---
title: "类型化数据集"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a68d4a10b01285a7e1b33238409351ca04d0aeb4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="typed-datasets"></a>类型化数据集
在允许通过弱类型化变量对值进行后期绑定访问的同时，<xref:System.Data.DataSet> 还允许通过强类型化比喻对数据进行访问。 表和列属于**数据集**可以使用用户友好名称来访问和强类型化变量。  
  
 类型化**数据集**是派生自的类**数据集**。 在这种情况下，它继承所有方法、 事件和属性的**数据集**。 此外，类型化**数据集**提供强类型化的方法、 事件和属性。 这意味着可以按名称（而不是使用基于集合的方法）访问表和列。 除了提高代码，类型化的可读性之外**数据集**还允许 Visual Studio.NET 代码编辑器自动填写您键入的行。  
  
 此外，强类型**数据集**在编译时提供正确的类型为值的访问。 通过强类型化**数据集**，代码时编译而不是在运行时捕获类型不匹配错误。  
  
## <a name="in-this-section"></a>本节内容  
 [生成强类型化数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 描述如何创建和使用强类型化**数据集**。  
  
 [为类型化的数据集进行注释](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 描述如何批注 XML 架构定义语言 (XSD) 架构用于生成强类型化**数据集**，使**数据集**元素友好的名称，而无需更改基础架构。  
  
## <a name="see-also"></a>请参阅  
 [数据集、数据表和数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)

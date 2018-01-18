---
title: DataTableReader
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b5160f5a2c68cab798dde154275c062e2bf31739
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="datatablereaders"></a>DataTableReader
<xref:System.Data.DataTableReader> 以一个或多个只读、只进结果集的形式提供 <xref:System.Data.DataTable> 或的 <xref:System.Data.DataSet> 的内容。  
  
 当你创建**DataTableReader**从**DataTable**，生成**DataTableReader**对象包含一个结果集具有相同的数据**DataTable**从创建它，除已标记为删除任何行。 列将显示在相同的顺序与在原始**DataTable**。  
  
 A **DataTableReader**可能包含多个结果集，如果它由调用<xref:System.Data.DataSet.CreateDataReader%2A>。 结果采用的顺序相同**数据表**中**数据集**对象的<xref:System.Data.DataSet.Tables%2A>集合。  
  
## <a name="in-this-section"></a>本节内容  
 [创建 DataReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 讨论如何创建**DataTableReader**对象。  
  
 [导航数据表](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 描述如何使用**读取**方法来移动的内容通过**DataTableReader**。  
  
## <a name="see-also"></a>请参阅  
 [在 ADO.NET 中检索和修改数据](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)

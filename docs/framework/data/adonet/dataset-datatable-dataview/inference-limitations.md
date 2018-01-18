---
title: "推断限制"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: af344055e511a2657007e216e1df304e2243362c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="inference-limitations"></a>推断限制
根据每个文档中的 XML 元素，从 XML 推断 <xref:System.Data.DataSet> 架构的过程会产生不同的架构。 例如，考虑以下 XML 文档。  
  
 Document1：  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Document2：  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 对于"Document1"，推断过程将生成**数据集**命名为"DocumentElement"和名为"Element1"的表，因为"Element1"是重复的元素。  
  
 **数据集：** DocumentElement  
  
 **表：** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
 但是，对于"Document2，"推断过程产生**数据集**名为"NewDataSet"和名为"DocumentElement。"的表 由于“Element1”不具有属性和子元素，它将被推断为列。  
  
 **数据集：** NewDataSet  
  
 **表：** DocumentElement  
  
|Element1|  
|--------------|  
|Text1|  
  
 这两个 XML 文档可能本应生成相同的架构，但根据每个文档中包含的不同元素，推断过程生成了极不相同的结果。  
  
 若要避免的差异，从 XML 文档生成架构时可能发生，我们建议您显式指定在加载时使用 XML 架构定义语言 (XSD) 或 XML 数据简化 (XDR) 架构**数据集**从XML。 有关显式指定的详细信息**数据集**架构和 XML 架构，请参阅[派生数据集关系结构从 XML 架构 (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)。  
  
## <a name="see-also"></a>请参阅  
 [从 XML 推断数据集关系结构](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [从 XML 加载数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [从 XML 加载数据集构架信息](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [在数据集中使用 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [数据集、数据表和数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)

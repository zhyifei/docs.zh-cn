---
title: "推断关系"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 79f79c1dbc74b98cff10de81c2bd7bd32d7d286b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="inferring-relationships"></a>推断关系
如果被推断为表的元素具有一个同样被推断为表的子元素，则将在这两个表之间创建 <xref:System.Data.DataRelation>。 名称的新列**ParentTableName_Id**将添加到父元素中，创建的表和子元素创建的表。 **ColumnMapping**此标识列的属性将设置为**MappingType.Hidden**。 列将用于父表中，已自动递增的主关键字和将用于**DataRelation**两个表之间。 添加的标识列的数据类型将是**System.Int32**，与所有其他被推断的列的数据类型，这是**System.String**。 A<xref:System.Data.ForeignKeyConstraint>与**DeleteRule** = **Cascade**还将在父与子表中使用新的列创建。  
  
 例如，考虑以下 XML：  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 推断过程将生成两个表： **Element1**和**ChildElement1**。  
  
 **Element1**表将有两个列： **Element1_Id**和**ChildElement2**。 **ColumnMapping**属性**Element1_Id**列将设置为**MappingType.Hidden**。 **ColumnMapping**属性**ChildElement2**列将设置为**MappingType.Element**。 **Element1_Id**列将设置为主键的**Element1**表。  
  
 **ChildElement1**表将具有三列： **attr1**， **attr2**和**Element1_Id**。 **ColumnMapping**属性**attr1**和**attr2**列将设置为**MappingType.Attribute**。 **ColumnMapping**属性**Element1_Id**列将设置为**MappingType.Hidden**。  
  
 A **DataRelation**和**ForeignKeyConstraint**将使用创建**Element1_Id**这两个表中的列。  
  
 **数据集：** DocumentElement  
  
 **表：** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **表：** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation:** Element1_ChildElement1  
  
 **ParentTable:** Element1  
  
 **ParentColumn:** Element1_Id  
  
 **ChildTable:** ChildElement1  
  
 **ChildColumn:** Element1_Id  
  
 **嵌套：** True  
  
 **ForeignKeyConstraint:** Element1_ChildElement1  
  
 **列：** Element1_Id  
  
 **ParentTable:** Element1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** Cascade  
  
 **AcceptRejectRule:**无  
  
## <a name="see-also"></a>请参阅  
 [从 XML 推断数据集关系结构](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [从 XML 加载数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [从 XML 加载数据集构架信息](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [嵌套 DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [在数据集中使用 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [数据集、数据表和数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)

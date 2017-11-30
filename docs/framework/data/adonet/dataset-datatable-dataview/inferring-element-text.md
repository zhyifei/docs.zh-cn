---
title: "推断元素文本"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 66dcc6a98d365f20da6c7f4c075c2fdd8ab936e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="inferring-element-text"></a>推断元素文本
如果元素包含文本但不包含任何子元素被推断为表如 （具有属性的元素） 或重复的元素名称的新列**TableName_Text**将添加到为该元素推断的表。 该元素中包含的文本将添加到此表中的一行，并存储在新列中。 **ColumnMapping**新列的属性将设置为**MappingType.SimpleContent**。  
  
 例如，考虑以下 XML。  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 推断过程将生成名为的表**Element1**具有两列： **attr1**和**Element1_Text**。 **ColumnMapping**属性**attr1**列将设置为**MappingType.Attribute**。 **ColumnMapping**属性**Element1_Text**列将设置为**MappingType.SimpleContent**。  
  
 **数据集：** DocumentElement  
  
 **表：** Element1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|value1|Text1|  
  
 如果某元素包含文本，并且还具有包含文本的子元素，则不会将列添加到表中来存储该元素所包含的文本。 该元素中包含的文本将被忽略，但子元素中的文本将包含在表的一行中。 例如，考虑以下 XML。  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 推断过程将生成名为的表**Element1**与名为的一个列**ChildElement1**。 文本**ChildElement1**元素将包括在表中的行。 其他文本则将被忽略。 **ColumnMapping**属性**ChildElement1**列将设置为**MappingType.Element**。  
  
 **数据集：** DocumentElement  
  
 **表：** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## <a name="see-also"></a>另请参阅  
 [从 XML 推断数据集关系结构](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [从 XML 加载数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [从 XML 加载数据集架构信息](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [在数据集中使用 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [数据集、数据表和数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)

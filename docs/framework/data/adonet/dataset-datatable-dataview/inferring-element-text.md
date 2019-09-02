---
title: 推断元素文本
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: d8d64c0cbb0aecf736a54fa6816e286ab7efa191
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203538"
---
# <a name="inferring-element-text"></a>推断元素文本
如果某个元素包含文本, 并且没有要推断为表的子元素 (例如具有属性或重复元素的元素), 则会将名为**TableName_Text**的新列添加到为该元素推断的表中。 该元素中包含的文本将添加到此表中的一行，并存储在新列中。 新列的**ColumnMapping**属性将设置为**mappingtype.attribute**。  
  
 例如，考虑以下 XML。  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 推理过程将生成一个名为**Element1**的表, 该表包含两列: **attr1**和**Element1_Text**。 **Attr1**列的**ColumnMapping**属性将设置为**mappingtype.attribute**。 **Element1_Text**列的**ColumnMapping**属性将设置为**mappingtype.attribute**。  
  
 **集会**DocumentElement  
  
 **数据表**Element1  
  
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
  
 推理过程将生成一个名为**Element1**的表, 该表包含一个名为**ChildElement1**的列。 **ChildElement1**元素的文本将包含在表的行中。 其他文本则将被忽略。 **ChildElement1**列的**ColumnMapping**属性将设置为**mappingtype.attribute**。  
  
 **集会**DocumentElement  
  
 **数据表**Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## <a name="see-also"></a>请参阅

- [从 XML 推断数据集关系结构](inferring-dataset-relational-structure-from-xml.md)
- [从 XML 加载数据集](loading-a-dataset-from-xml.md)
- [从 XML 加载数据集构架信息](loading-dataset-schema-information-from-xml.md)
- [在数据集中使用 XML](using-xml-in-a-dataset.md)
- [数据集、数据表和数据视图](index.md)
- [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)

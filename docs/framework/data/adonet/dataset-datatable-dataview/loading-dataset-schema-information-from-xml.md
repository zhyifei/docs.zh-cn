---
title: 从 XML 加载数据集架构信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 69994c546fea842ffef1c8c43d6d6f5bc35e0629
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151047"
---
# <a name="loading-dataset-schema-information-from-xml"></a>从 XML 加载数据集架构信息
的<xref:System.Data.DataSet>架构（其表、列、关系和约束）可以以编程方式定义、由<xref:System.Data.Common.DataAdapter>的**填充**或**填充架构**方法创建，也可以从 XML 文档加载。 要从 XML 文档加载**DataSet**架构信息，可以使用**DataSet**的**ReadXmlSchema**或**InferXmlSchema**方法。 **ReadXmlSchema**允许您从包含 XML 架构定义语言 （XSD） 架构的文档或具有内联 XML 架构的 XML 文档加载或推断**DataSet**架构信息。 **InferXmlSchema**允许您从 XML 文档中推断架构，而忽略您指定的某些 XML 命名空间。  
  
> [!NOTE]
> 当您使用 Web 服务或 XML 序列化传输使用 XSD 构造（如嵌套关系）在内存中创建的**DataSet**时 **，DataSet**中的表排序可能无法保留。 因此，在这种情况下 **，DataSet**的收件人不应依赖于表排序。 但是，如果从 XSD 文件读取要传输的**DataSet**的架构，而不是在内存中创建，则始终保留表排序。  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 要从 XML 文档加载**DataSet**的架构而不加载任何数据，可以使用**DataSet**的**ReadXmlSchema**方法。 **ReadXmlSchema**创建使用 XML 架构定义语言 （XSD） 架构定义的**数据集**架构。  
  
 **ReadXmlSchema**方法采用文件名、流或**XmlReader**的单个参数，其中包含要加载的 XML 文档。 XML 文档可以仅包含架构，也可以包含与包含数据的 XML 元素内联的架构。 有关将内联架构编写为 XML 架构的详细信息，请参阅[从 XML 架构 （XSD） 派生数据集关系结构](deriving-dataset-relational-structure-from-xml-schema-xsd.md)。  
  
 如果传递给**ReadXmlSchema 的**XML 文档不包含内联架构信息，**则 ReadXmlSchema**将从 XML 文档中的元素推断架构。 如果**DataSet**已包含架构，则如果新表不存在，则通过添加新表来扩展当前架构。 不会将新列添加到现有表中。 如果正在添加的列在**DataSet**中已存在，但与 XML 中找到的列的类型不兼容，则引发异常。 有关**ReadXmlSchema**如何从 XML 文档中推断架构的详细信息，请参阅[从 XML 推断 DataSet 关系结构](inferring-dataset-relational-structure-from-xml.md)。  
  
 尽管**ReadXmlSchema**仅加载或推断**DataSet**的架构，但**DataSet**的**ReadXml**方法加载或推断架构和 XML 文档中的数据。 有关详细信息，请参阅从[XML 加载数据集](loading-a-dataset-from-xml.md)。  
  
 以下代码示例演示如何从 XML 文档或流加载**DataSet**架构。 第一个示例显示将 XML 架构文件名传递给**ReadXmlSchema**方法。 第二个示例显示了**System.IO.StreamReader**。  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As New System.IO.StreamReader("schema.xsd")
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema(xmlStream)  
xmlStream.Close()  
```  
  
```csharp  
System.IO.StreamReader xmlStream = new System.IO.StreamReader("schema.xsd");  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema(xmlStream);  
xmlStream.Close();  
```  
  
## <a name="inferxmlschema"></a>InferXmlSchema  
 您还可以指示**DataSet**使用**DataSet**的**InferXmlSchema**方法从 XML 文档中推断其架构。 **InferXml 架构**的功能与使用**推断模式****的 XmlReadMode**的**ReadXml（** 加载数据以及推断架构）的功能相同，如果正在读取的文档不包含内联架构，则**ReadXmlSchema**的功能相同。 但是 **，InferXmlSchema**提供了一种附加功能，允许您指定在推断架构时要忽略的特定 XML 命名空间。 **inferXmlSchema**采用两个必需的参数：XML 文档的位置，由文件名、流或**XmlReader**指定;以及要由操作忽略的 XML 命名空间的字符串数组。  
  
 例如，考虑以下 XML：  
  
```xml  
<NewDataSet xmlns:od="urn:schemas-microsoft-com:officedata">  
<Categories>  
  <CategoryID od:adotype="3">1</CategoryID>
  <CategoryName od:maxLength="15" od:adotype="130">Beverages</CategoryName>
  <Description od:adotype="203">Soft drinks and teas</Description>
</Categories>  
<Products>  
  <ProductID od:adotype="20">1</ProductID>
  <ReorderLevel od:adotype="3">10</ReorderLevel>
  <Discontinued od:adotype="11">0</Discontinued>
</Products>  
</NewDataSet>  
```  
  
 由于为前面的XML文档中的元素指定的属性 **，ReadXmlSchema**方法和具有**InferSchema** Xml 的**ReadXml** **XmlReadMode**方法都将为文档中的每个元素创建表：**类别**、**类别 ID、****类别名称**、**描述**、**产品**、产品**ID、****重新排序级别**和**已停产**。 （有关详细信息，请参阅从[XML 推断数据集关系结构](inferring-dataset-relational-structure-from-xml.md)。但是，更合适的结构是只创建 **"类别**和**产品**"表，然后在 **"类别"** 表中创建**类别 ID、****类别名称**和**说明**列，并在 **"产品**"表中创建 **"产品 ID"、"****重新排序级别****"和"停产**"列。 为确保推断的架构忽略 XML 元素中指定的属性，请使用**InferXmlSchema**方法并指定要忽略**的 Officedata 的**XML 命名空间，如下例所示。  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>另请参阅

- [在数据集中使用 XML](using-xml-in-a-dataset.md)
- [从 XML 架构派生数据集关系结构 (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [从 XML 推断数据集关系结构](inferring-dataset-relational-structure-from-xml.md)
- [从 XML 加载数据集](loading-a-dataset-from-xml.md)
- [数据集、数据表和数据视图](index.md)
- [ADO.NET 概述](../ado-net-overview.md)

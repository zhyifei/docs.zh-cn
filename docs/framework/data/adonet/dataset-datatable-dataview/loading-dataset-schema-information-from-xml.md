---
title: "从 XML 加载数据集架构信息"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 09fc69ba6d82fdab5aa03dd3987ec1acdf0be17e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="loading-dataset-schema-information-from-xml"></a>从 XML 加载数据集架构信息
架构<xref:System.Data.DataSet>（其表、 列、 关系和约束） 可以定义，以编程方式创建的**填充**或**FillSchema**方法<xref:System.Data.Common.DataAdapter>，或从加载XML 文档。 若要加载**数据集**架构信息从 XML 文档，你可以使用**ReadXmlSchema**或**InferXmlSchema**方法**数据集**. **ReadXmlSchema**允许你加载或推断**数据集**文档包含 XML 架构定义语言 (XSD) 架构或包含内联 XML 架构的 XML 文档中的架构信息。 **InferXmlSchema**可以推断 XML 文档中的架构时忽略某些你指定的 XML 命名空间。  
  
> [!NOTE]
>  中的表顺序**数据集**时你使用 Web 服务或 XML 序列化传输可能不会保留**数据集**在内存中创建使用 XSD 构造 （如嵌套关系）。 因此，接收方的**数据集**不应依赖表顺序在这种情况下。 但是，表如果始终保留顺序的架构**数据集**传输从 XSD 文件，而不创建内存中读取。  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 若要加载的架构**数据集**从 XML 文档不加载任何数据的情况下，你可以使用**ReadXmlSchema**方法**数据集**。 **ReadXmlSchema**创建**数据集**使用 XML 架构定义语言 (XSD) 架构定义的架构。  
  
 **ReadXmlSchema**方法采用单个参数的文件名，流，或**XmlReader**包含要加载的 XML 文档。 XML 文档可以仅包含架构，也可以包含与包含数据的 XML 元素内联的架构。 有关编写内联架构作为 XML 架构的详细信息，请参阅[派生数据集关系结构从 XML 架构 (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)。  
  
 如果 XML 文档传递给**ReadXmlSchema**不包含任何内联架构信息， **ReadXmlSchema**将推断 XML 文档中的元素中的架构。 如果**数据集**已包含架构，将通过添加新表，如果不存在扩展当前架构。 不会将新列添加到现有表中。 如果已正在添加某列中存在**数据集**但不兼容的类型与列找到了在 XML 中，将引发异常。 有关详细信息，有关如何**ReadXmlSchema**推断架构从 XML 文档，请参阅[推断数据集关系结构从 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)。  
  
 尽管**ReadXmlSchema**加载或推断的架构**数据集**、 **ReadXml**方法**数据集**加载或推断同时架构和 XML 文档中包含的数据。 有关详细信息，请参阅[从 XML 加载数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)。  
  
 下面的代码示例显示如何加载**数据集**架构从一个 XML 文档或流。 第一个示例会显示 XML 架构文件名称传递给**ReadXmlSchema**方法。 第二个示例显示**System.IO.StreamReader**。  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As System.IO.StreamReader = New System.IO.StreamReader ("schema.xsd");  
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
 你还可以指示**数据集**推断其架构从 XML 文档使用**InferXmlSchema**方法**数据集**。 **InferXmlSchema**执行上述操作的功能相同**ReadXml**与**XmlReadMode**的**InferSchema** （加载数据，以及推断架构），和**ReadXmlSchema**如果所读取的文档不包含任何内联架构。 但是， **InferXmlSchema**提供其他功能，使你能够指定特定的 XML 命名空间来推断架构时，会忽略。 **InferXmlSchema**采用两个必需的参数： 文件名、 流、 指定的 XML 文档的位置或**XmlReader**; 以及要忽略由该操作的 XML 命名空间的字符串数组。  
  
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
  
 由于指定前面的 XML 文档中的元素的属性同时**ReadXmlSchema**方法和**ReadXml**方法替换**XmlReadMode**的**InferSchema**将在文档中创建表为每个元素：**类别**， **CategoryID**， **CategoryName**，**说明**，**产品**， **ProductID**，**再订购量**，和**停止使用**. (有关详细信息，请参阅[推断数据集关系结构从 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)。)但是，更合适的结构就是仅创建**类别**和**产品**表，并随后创建**CategoryID**， **CategoryName**，和**说明**中的列**类别**表，和**ProductID**，**再订购量**，和**已中断**中的列**产品**表。 若要确保推断的架构忽略在 XML 元素中指定的属性，使用**InferXmlSchema**方法并指定的 XML 命名空间**officedata**被忽略中, 所示下面的示例。  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>另请参阅  
 [在数据集中使用 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [从 XML 架构 (XSD) 派生数据集关系结构](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [从 XML 推断数据集关系结构](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [从 XML 加载数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [数据集、数据表和数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: 从 XML 加载数据集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: c21ed3bb31add285d64272040680433fff4e16fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151060"
---
# <a name="loading-a-dataset-from-xml"></a>从 XML 加载数据集
ADO.NET <xref:System.Data.DataSet> 的内容可以从 XML 流或文档创建。 此外，利用 .NET Framework，您可以相当灵活地控制从 XML 中加载哪些信息以及如何创建 <xref:System.Data.DataSet> 的架构（即关系结构）。  
  
 要用<xref:System.Data.DataSet>XML 的数据填充 ， 请使用<xref:System.Data.DataSet>对象的**ReadXml**方法。 **ReadXml**方法从文件、流或**XmlReader**读取，并将 XML 的源加上可选的**XmlReadMode**参数作为参数。 有关**XmlReader**的详细信息，请参阅[使用 XmlTextReader 读取 XML 数据](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100))。 **ReadXml**方法读取 XML 流或文档的内容，并<xref:System.Data.DataSet>加载数据。 它还将根据指定的**XmlReadMode**以及关系<xref:System.Data.DataSet>架构是否存在创建 的关系架构。  
  
 下表描述了**XmlReadMode**参数的选项。  
  
|选项|说明|  
|------------|-----------------|  
|**Auto**|这是默认值。 检查 XML 并按如下顺序选择最适合的选项：<br /><br /> - 如果 XML 是 DiffGram，则使用**DiffGram。**<br />- 如果<xref:System.Data.DataSet>包含架构或 XML 包含内联架构，则使用**ReadSchema。**<br />- 如果<xref:System.Data.DataSet>不包含架构，并且 XML 不包含内联架构，则使用**InferSchema。**<br /><br /> 如果您知道正在读取的 XML 的格式，建议您设置显式**XmlReadMode，** 而不是接受**自动**默认值。|  
|**ReadSchema**|读取内联架构并加载数据和架构。<br /><br /> 如果 <xref:System.Data.DataSet> 已包含架构，则新表将从内联架构添加到 <xref:System.Data.DataSet> 中的现有架构。 如果 <xref:System.Data.DataSet> 中已存在内联架构中的任何表，则将引发异常。 您将无法使用**XmlReadMode.ReadSchema**修改现有表的架构。<br /><br /> 如果 <xref:System.Data.DataSet> 不包含架构，并且没有内联架构，则不会读取任何数据。<br /><br /> 内联架构可以使用 XML 架构定义语言 (XSD) 架构来定义。 有关将内联架构编写为 XML 架构的详细信息，请参阅[从 XML 架构 （XSD） 派生数据集关系结构](deriving-dataset-relational-structure-from-xml-schema-xsd.md)。|  
|**IgnoreSchema**|忽略任何内联架构并将数据加载到现有的 <xref:System.Data.DataSet> 架构中。 任何与现有架构不匹配的数据都将被丢弃。 如果 <xref:System.Data.DataSet> 中不存在任何架构，则不会加载任何数据。<br /><br /> 如果数据是 DiffGram，**则忽略架构**具有与**DiffGram**相同的功能 *。*|  
|**InferSchema**|忽略任何内联架构并按照 XML 数据的结构推断架构，然后加载数据。<br /><br /> 如果 <xref:System.Data.DataSet> 已经包含架构，则会通过向现有表中添加列来扩展当前架构。 如果不存在表，则不会添加其他表。 如果已存在具有不同命名空间的推断表或者任何推断表与现有列发生冲突，则会引发异常。<br /><br /> 有关**ReadXmlSchema**如何从 XML 文档中推断架构的详细信息，请参阅[从 XML 推断 DataSet 关系结构](inferring-dataset-relational-structure-from-xml.md)。|  
|**迪夫格拉姆**|读取 DiffGram 并将数据添加到当前架构中。 **DiffGram**将新行与唯一标识符值匹配的现有行合并。 请参见本主题末尾的“合并 XML 中的数据”。 有关差异图的更多信息，请参阅[差异图](diffgrams.md)。|  
|**片段**|持续读取多个 XML 片断，直至到达流的末尾。 与 <xref:System.Data.DataSet> 架构匹配的片断会追加到相应的表。 与 <xref:System.Data.DataSet> 架构不匹配的片断将被丢弃。|  
  
> [!NOTE]
> 如果将**XmlReader**传递给将**XmlReader**定位到 XML 文档中的一部分，**则 ReadXml**将读取到下一个元素节点，并将其视为根元素，只读取到元素节点结束。 如果指定**XmlReadMode.片段**，则不适用。  
  
## <a name="dtd-entities"></a>DTD 实体  
 如果 XML 包含在文档类型定义 （DTD） 架构中定义的实体），则如果尝试<xref:System.Data.DataSet>通过将文件名、流或非验证**XmlReader**传递到**ReadXml**来加载 ，将引发异常。 相反，您必须创建一个**Xml 验证读取器**，其中**实体处理**设置为**实体处理.展开实体**，并将**您的 Xml 验证读取器**传递给**ReadXml**。 在 读取 之前 **，XmlValidingReader**将展开实体<xref:System.Data.DataSet>。  
  
 以下代码示例显示如何从 XML 流中加载 <xref:System.Data.DataSet>。 第一个示例显示文件名传递给**ReadXml**方法。 第二个示例显示一个字符串，包含使用 <xref:System.IO.StringReader> 加载的 XML。  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXml("input.xml", XmlReadMode.ReadSchema);  
```  
  
```vb  
Dim dataSet As DataSet = New DataSet  
Dim dataTable As DataTable = New DataTable("table1")  
dataTable.Columns.Add("col1", Type.GetType("System.String"))  
dataSet.Tables.Add(dataTable)  
  
Dim xmlData As String = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>"  
  
Dim xmlSR As System.IO.StringReader = New System.IO.StringReader(xmlData)  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema)  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
DataTable dataTable = new DataTable("table1");  
dataTable.Columns.Add("col1", typeof(string));  
dataSet.Tables.Add(dataTable);  
  
string xmlData = "<XmlDS><table1><col1>Value1</col1></table1><table1><col1>Value2</col1></table1></XmlDS>";  
  
System.IO.StringReader xmlSR = new System.IO.StringReader(xmlData);  
  
dataSet.ReadXml(xmlSR, XmlReadMode.IgnoreSchema);  
```  
  
> [!NOTE]
> 如果调用**ReadXml**加载非常大的文件，则可能会遇到性能降低的问题。 为了确保**ReadXml**在大型文件中的最佳性能，请调用 中<xref:System.Data.DataTable.BeginLoadData%2A>每个表<xref:System.Data.DataSet>的方法，然后调用**ReadXml**。 最后，为 <xref:System.Data.DataTable.EndLoadData%2A> 中的每个表调用 <xref:System.Data.DataSet>，如下面的示例所示。  
  
```vb  
Dim dataTable As DataTable  
  
For Each dataTable In dataSet.Tables  
   dataTable.BeginLoadData()  
Next  
  
dataSet.ReadXml("file.xml")  
  
For Each dataTable in dataSet.Tables  
   dataTable.EndLoadData()  
Next  
```  
  
```csharp  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.BeginLoadData();  
  
dataSet.ReadXml("file.xml");
  
foreach (DataTable dataTable in dataSet.Tables)  
   dataTable.EndLoadData();  
```  
  
> [!NOTE]
> 如果您的<xref:System.Data.DataSet>XSD 架构包含**目标命名空间**，则数据可能无法读取，并且在调用**ReadXml**以加载<xref:System.Data.DataSet>包含没有限定命名空间的元素时可能会遇到异常。 在这种情况下，要读取非限定元素，请将**元素FormDefault**设置为 XSD 架构中的"合格"。 例如：  
  
```xml  
<xsd:schema id="customDataSet"
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"
  xmlns="http://www.tempuri.org/customDataSet.xsd"
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a>合并 XML 中的数据  
 如果 <xref:System.Data.DataSet> 已经包含数据，则会向已存在于 <xref:System.Data.DataSet> 中的数据添加 XML 中的新数据。 **ReadXml**不会从 XML 合并到<xref:System.Data.DataSet>具有匹配主键的任何行信息中。 要用 XML 中的新信息覆盖现有行信息，请使用**ReadXml**创建新<xref:System.Data.DataSet>的<xref:System.Data.DataSet.Merge%2A>，然后将<xref:System.Data.DataSet>新信息写入<xref:System.Data.DataSet>现有 。 请注意，使用**ReadXML**使用**DiffGram**的**XmlReadMode**加载 DiffGram 将合并具有相同唯一标识符的行。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [在数据集中使用 XML](using-xml-in-a-dataset.md)
- [DiffGrams](diffgrams.md)
- [从 XML 架构派生数据集关系结构 (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [从 XML 推断数据集关系结构](inferring-dataset-relational-structure-from-xml.md)
- [从 XML 加载数据集架构信息](loading-dataset-schema-information-from-xml.md)
- [数据集、数据表和数据视图](index.md)
- [ADO.NET 概述](../ado-net-overview.md)

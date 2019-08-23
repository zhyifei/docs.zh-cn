---
title: DiffGrams
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: 2bf736445a041ec678ab30474da51fddfba1773b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934484"
---
# <a name="diffgrams"></a>DiffGrams
DiffGram 是用于标识数据元素的当前和原始版本的 XML 格式。 <xref:System.Data.DataSet> 使用 DiffGram 格式来加载和保持其内容，并将其内容序列化，以便通过网络连接来进行传输。 当以<xref:System.Data.DataSet> DiffGram 形式编写时, 它将使用所有必要的信息来填充 diffgram, 以准确地重新创建的内容 (尽管不是的<xref:System.Data.DataSet>架构), 其中包括来自**原始**和**的列值当前**行版本、行错误消息和行顺序。  
  
 当从 XML Web services 发送和检索 <xref:System.Data.DataSet> 时，将隐式地使用 DiffGram 格式。 此外, 当<xref:System.Data.DataSet>使用**ReadXml**方法从 xml 加载的内容时, 或使用**WriteXml**方法在 xml 中编写的<xref:System.Data.DataSet>内容时, 可以指定以 DiffGram 读取或写入内容。 有关详细信息, 请参阅[从 Xml 加载数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)和[以 Xml 数据形式编写数据集内容](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)。  
  
 虽然 DiffGram 格式主要由 .NET Framework 用作 <xref:System.Data.DataSet> 内容的序列化格式，但也可以使用 DiffGram 来修改 Microsoft SQL Server 数据库中表的数据。  
  
 Diffgram 是通过将所有表 **\<** 的内容写入 diffgram > 元素生成的。  
  
### <a name="to-generate-a-diffgram"></a>生成 Diffgram  
  
1. 生成根表（即没有任何父级的表）的列表。  
  
2. 对于列表中每个表及其子代，在 Diffgram 的第一部分中写出所有行的当前版本。  
  
3. 对于中<xref:System.Data.DataSet>的每个表, 在 Diffgram 的 "  **\<之前 >** " 部分中写出所有行的原始版本 (如果有)。  
  
4. 对于有错误的行, 在 Diffgram 的 "  **\<错误 >** " 部分中写入错误内容。  
  
 将按照从 XML 文件的开头到结尾的顺序处理 Diffgram。  
  
### <a name="to-process-a-diffgram"></a>处理 Diffgram  
  
1. 处理包含行当前版本的 Diffgram 的第一部分。  
  
2. 处理包含已修改行和已删除行的原始行版本的第二个或 **\<之前的 >** 部分。  
  
    > [!NOTE]
    > 如果某行标记为已删除，则删除操作还可删除该行的子代，具体取决于当前 `Cascade` 的 <xref:System.Data.DataSet> 属性。  
  
3. **\<>** "部分处理错误。 为本部分中各项的指定行和列设置错误信息。  
  
> [!NOTE]
> 如果将 <xref:System.Data.XmlWriteMode> 设置为 Diffgram，则目标 <xref:System.Data.DataSet> 和原始 <xref:System.Data.DataSet> 的内容可能会不同。  
  
## <a name="diffgram-format"></a>DiffGram 格式  
 DiffGram 格式可分为三部分：当前数据、原始（或“before”）数据和错误部分，如下面的示例中所示。  
  
```xml  
<?xml version="1.0"?>  
<diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  
   <DataInstance>  
   </DataInstance>  
  
  <diffgr:before>  
  </diffgr:before>  
  
  <diffgr:errors>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
 DiffGram 格式由以下数据块组成：  
  
 **\<**  ***DataInstance***  **>**  
 此元素的名称***DataInstance***用于此文档中的说明。 ***DataInstance***元素表示<xref:System.Data.DataSet>或的行。 <xref:System.Data.DataTable> 元素将包含<xref:System.Data.DataSet>或<xref:System.Data.DataTable>的名称, 而不是 DataInstance。 此 DiffGram 格式块包含当前数据（无论是否经过修改）。 使用**diffgr: hasChanges**批注标识已修改的元素或行。  
  
 **\<diffgr:before>**  
 此 DiffGram 格式块包含行的原始版本。 此块中的元素与使用**diffgr: id**批注的***DataInstance***块中的元素匹配。  
  
 **\<diffgr:errors>**  
 此 DiffGram 格式块包含***DataInstance***块中特定行的错误信息。 此块中的元素与使用**diffgr: id**批注的***DataInstance***块中的元素匹配。  
  
## <a name="diffgram-annotations"></a>DiffGram 批注  
 DiffGram 使用一些批注来使来自不同 DiffGram 块的元素相关，这些块表示 <xref:System.Data.DataSet> 中的不同行版本或错误信息。  
  
 下表描述了在 DiffGram 命名空间 urn 中定义的 DiffGram 注释 **: 架构-microsoft-com: xml-DiffGram-v1**。  
  
|批注|描述|  
|----------------|-----------------|  
|**id**|用于对 **\<diffgr**中的元素进行配对: 在 > 和 **\<diffgr 之前: 错误 >** 块到***DataInstance*** **>** 块 **\<** 中的元素。 带有**diffgr: id**批注的值的格式为 *[TableName] [RowIdentifier]* 。 例如：`<Customers diffgr:id="Customers1">`。|  
|**parentId**|标识 **\<** DataInstance**块>** 中的哪个元素是当前元素的父元素。 具有**diffgr: parentId**批注的值的格式为 *[TableName] [RowIdentifier]* 。 例如：`<Orders diffgr:parentId="Customers1">`。|  
|**hasChanges**|将 **\<** DataInstance**块>** 中的行标识为已修改。 **HasChanges**批注可以具有以下两个值之一:<br /><br /> **inserted**<br /> 标识**已添加**的行。<br /><br /> **时间**<br /> 标识**修改后**的行, 其中包含 **\<diffgr: > 块之前**的**原始**行版本。 请注意,**已删除**的行在 **\<diffgr**中具有**原始**行版本: 在 > 块之前, 但在***DataInstance*** **>** 块中 **\<** 将不存在批注元素。|  
|**hasErrors**|使用**RowError**标识***DataInstance*** **>** 块 **\<** 中的行。 Error 元素放置在 **\<diffgr: errors >** 块中。|  
|**错误**|**包含\<diffgr: errors >** 块中特定元素的**RowError**文本。|  
  
 当以 DiffGram 格式读写 <xref:System.Data.DataSet> 的内容时，还包含附加的批注。 下表描述了在命名空间**urn: 架构-microsoft-msdata**中定义的这些附加批注。  
  
|批注|描述|  
|----------------|-----------------|  
|**RowOrder**|保留原始数据的行顺序并标识特定 <xref:System.Data.DataTable> 中行的索引。|  
|**消隐**|将**ColumnMapping**属性设置为 mappingtype.attribute 的列标识为**隐藏**。 该属性以**msdata: hidden** *[ColumnName]* = "*value*" 格式编写。 例如：`<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`。<br /><br /> 请注意，只有当隐藏列包含数据时才以 DiffGram 属性的形式来编写隐藏列。 否则将忽略隐藏列。|  
  
## <a name="sample-diffgram"></a>DiffGram 示例  
 下面是 DiffGram 格式的示例。 该示例显示对表行的更新在提交更改之前的结果。 CustomerID 为“ALFKI”的行已被修改，但尚未更新。 因此, 在***DataInstance*** **\<** **块中有一个具有diffgr:id"Customers1"的当前行,而在中有一个具有diffgr:id>** "Customers1" 的原始行  **\<diffgr: 在 > 块之前**。 CustomerID 为 "ANATR" 的行包含一个**RowError**, 因此它使用`diffgr:hasErrors="true"`进行批注, 且 **\<diffgr: errors >** 块中有一个相关的元素。  
  
```xml  
<diffgr:diffgram xmlns:msdata="urn:schemas-microsoft-com:xml-msdata" xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
  <CustomerDataSet>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0" diffgr:hasChanges="modified">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>New Company</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers2" msdata:rowOrder="1" diffgram:hasErrors="true">  
      <CustomerID>ANATR</CustomerID>  
      <CompanyName>Ana Trujillo Emparedados y Helados</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers3" msdata:rowOrder="2">  
      <CustomerID>ANTON</CustomerID>  
      <CompanyName>Antonio Moreno Taquera</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers4" msdata:rowOrder="3">  
      <CustomerID>AROUT</CustomerID>  
      <CompanyName>Around the Horn</CompanyName>  
    </Customers>  
  </CustomerDataSet>  
  <diffgr:before>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>Alfreds Futterkiste</CompanyName>  
    </Customers>  
  </diffgr:before>  
  <diffgr:errors>  
    <Customers diffgr:id="Customers2" diffgr:Error="An optimistic concurrency violation has occurred for this row."/>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
## <a name="see-also"></a>请参阅

- [在数据集中使用 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [从 XML 加载数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [以 XML 数据的形式编写数据集内容](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)
- [数据集、数据表和数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 托管提供程序和数据集开发人员中心](https://go.microsoft.com/fwlink/?LinkId=217917)

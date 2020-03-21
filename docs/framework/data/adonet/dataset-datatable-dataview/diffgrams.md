---
title: DiffGrams
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: 2c521ef33c98234dac5f4b819a800cd524218462
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151151"
---
# <a name="diffgrams"></a>DiffGrams
DiffGram 是用于标识数据元素的当前和原始版本的 XML 格式。 <xref:System.Data.DataSet> 使用 DiffGram 格式来加载和保持其内容，并将其内容序列化，以便通过网络连接来进行传输。 <xref:System.Data.DataSet>当 编写为 DiffGram 时，它将使用所有必要的信息填充 DiffGram，以准确重新创建<xref:System.Data.DataSet>的内容（尽管不是架构），包括**原始**行和**当前**行版本的列值、行错误信息和行顺序。  
  
 当从 XML Web services 发送和检索 <xref:System.Data.DataSet> 时，将隐式地使用 DiffGram 格式。 此外，使用**ReadXml**方法<xref:System.Data.DataSet>从 XML 加载 的内容时，或使用**WriteXml**方法<xref:System.Data.DataSet>在 XML 中写入 的内容时，可以指定将内容作为 DiffGram 读取或写入。 有关详细信息，请参阅从[XML 加载数据集](loading-a-dataset-from-xml.md)并将[数据集内容写入 XML 数据](writing-dataset-contents-as-xml-data.md)。  
  
 虽然 DiffGram 格式主要由 .NET Framework 用作 <xref:System.Data.DataSet> 内容的序列化格式，但也可以使用 DiffGram 来修改 Microsoft SQL Server 数据库中表的数据。  
  
 通过将所有表的内容写入**\<衍分图>** 元素生成衍分图。  
  
### <a name="to-generate-a-diffgram"></a>生成 Diffgram  
  
1. 生成根表（即没有任何父级的表）的列表。  
  
2. 对于列表中每个表及其子代，在 Diffgram 的第一部分中写出所有行的当前版本。  
  
3. 对于 中的每个表<xref:System.Data.DataSet>，请写出 Diffgram**\<的>前**部分中所有行的原始版本（如果有）。  
  
4. 对于有错误的行，请在 Diffgram>部分**\<的错误**中写入错误内容。  
  
 将按照从 XML 文件的开头到结尾的顺序处理 Diffgram。  
  
### <a name="to-process-a-diffgram"></a>处理 Diffgram  
  
1. 处理包含行当前版本的 Diffgram 的第一部分。  
  
2. 处理包含已修改行和已删除行的原始行版本的第二**\<个**或>节。  
  
    > [!NOTE]
    > 如果某行标记为已删除，则删除操作还可删除该行的子代，具体取决于当前 `Cascade` 的 <xref:System.Data.DataSet> 属性。  
  
3. 处理>部分**\<的错误**。 为本部分中各项的指定行和列设置错误信息。  
  
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
  
 **\<**  ***数据实例***  **>**  
 此元素的名称***DataInstance***用于本文档中的说明目的。 ***DataInstance***元素表示<xref:System.Data.DataSet>的 或 行<xref:System.Data.DataTable>。 元素将包含<xref:System.Data.DataSet>或<xref:System.Data.DataTable>的名称，而不是*DataInstance。* 此 DiffGram 格式块包含当前数据（无论是否经过修改）。 已修改的元素或行使用**diffgr：hasChanges**注释标识。  
  
 **\<困难：>之前**  
 此 DiffGram 格式块包含行的原始版本。 此块中的元素使用**diffgr：id**注释与***DataInstance***块中的元素匹配。  
  
 **\<差异：错误>**  
 此 DiffGram 格式块包含***DataInstance***块中特定行的错误信息。 此块中的元素使用**diffgr：id**注释与***DataInstance***块中的元素匹配。  
  
## <a name="diffgram-annotations"></a>DiffGram 批注  
 DiffGram 使用一些批注来使来自不同 DiffGram 块的元素相关，这些块表示 <xref:System.Data.DataSet> 中的不同行版本或错误信息。  
  
 下表描述了在 DiffGram 命名空间 urn 中定义的 DiffGram 注释 **：架构-microsoft-com：xml-diffgram-v1**。  
  
|Annotation|说明|  
|----------------|-----------------|  
|**id**|用于将**\<分差中的元素：在>和****\<差异：错误之前，>** 块与***DataInstance*****>** 块**\<** 中的元素配对。 具有**diffgr：id**注释的值位于窗体 *[表名称][Row标识符]* 中。 例如：`<Customers diffgr:id="Customers1">`。|  
|**parentId**|标识**\<*****DataInstance*****>** 块中的哪个元素是当前元素的父元素。 具有**差异值的值：父Id**注释位于窗体 *[表名称][Row标识符]* 中。 例如：`<Orders diffgr:parentId="Customers1">`。|  
|**hasChanges**|将**\<*****DataInstance*****>** 块中的行标识为已修改的行。 **具有更改**注释可以具有以下两个值之一：<br /><br /> **插入**<br /> 标识 **"已添加**的行"。<br /><br /> **改 性**<br /> 标识**在\<分段：>块之前**包含**原始**行版本的 **"已修改**"行。 请注意，**删除的**行将在**\<diffgr：>** 块之前具有**原始**行版本，但在**\<*****DataInstance*****>** 块中没有注释的元素。|  
|**hasErrors**|使用**RowError**标识**\<** ***DataInstance*****>** 块中的行。 错误元素放置在**\<差异：错误>** 块中。|  
|**错误**|包含**\<diffgr：error>** 块中特定元素的**RowError**文本。|  
  
 当以 DiffGram 格式读写 <xref:System.Data.DataSet> 的内容时，还包含附加的批注。 下表描述了这些附加注释，这些注释在命名空间**urn：架构-微软-com：xml-msdata**中定义。  
  
|Annotation|说明|  
|----------------|-----------------|  
|**RowOrder**|保留原始数据的行顺序并标识特定 <xref:System.Data.DataTable> 中行的索引。|  
|**Hidden**|将列标识为将**列映射**属性设置为**映射类型。** 该属性以**msdata 格式编写：隐藏** *[列名]*="*值*"。 例如：`<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`。<br /><br /> 请注意，只有当隐藏列包含数据时才以 DiffGram 属性的形式来编写隐藏列。 否则会忽视优先级。|  
  
## <a name="sample-diffgram"></a>DiffGram 示例  
 下面是 DiffGram 格式的示例。 该示例显示对表行的更新在提交更改之前的结果。 CustomerID 为“ALFKI”的行已被修改，但尚未更新。 因此，在**\<*****DataInstance*****>** 块中有一个 **"** 客户1"的"客户1"**的"** 当前"行，在**\<diffgr：>** 块之前，有一个**原始**行，其中具有"客户1"的**diffgr：id。** 具有"ANATR"客户 ID 的行包含一个**RowError，** 因此带有"`diffgr:hasErrors="true"`**\<带**"的批号，并且在 diffgr：error>块中存在相关元素。  
  
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
  
## <a name="see-also"></a>另请参阅

- [在数据集中使用 XML](using-xml-in-a-dataset.md)
- [从 XML 加载数据集](loading-a-dataset-from-xml.md)
- [写入数据集内容作为 XML 数据](writing-dataset-contents-as-xml-data.md)
- [数据集、数据表和数据视图](index.md)
- [ADO.NET 概述](../ado-net-overview.md)

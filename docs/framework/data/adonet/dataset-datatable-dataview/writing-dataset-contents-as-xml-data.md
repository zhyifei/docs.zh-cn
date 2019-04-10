---
title: 写入数据集内容作为 XML 数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: dae044a9d7802e858f1f24dd4aa0f1de8f6cba7a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158946"
---
# <a name="writing-dataset-contents-as-xml-data"></a><span data-ttu-id="d7d07-102">写入数据集内容作为 XML 数据</span><span class="sxs-lookup"><span data-stu-id="d7d07-102">Writing DataSet Contents as XML Data</span></span>
<span data-ttu-id="d7d07-103">在 ADO.NET 中可以编写 <xref:System.Data.DataSet> 的 XML 表示形式（包含或不包含其架构）。</span><span class="sxs-lookup"><span data-stu-id="d7d07-103">In ADO.NET you can write an XML representation of a <xref:System.Data.DataSet>, with or without its schema.</span></span> <span data-ttu-id="d7d07-104">如果架构信息以内联形式包含在 XML 表示形式中，则使用 XML 架构定义语言 (XSD) 来编写。</span><span class="sxs-lookup"><span data-stu-id="d7d07-104">If schema information is included inline with the XML, it is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="d7d07-105">架构包含 <xref:System.Data.DataSet> 的表定义以及关系和约束定义。</span><span class="sxs-lookup"><span data-stu-id="d7d07-105">The schema contains the table definitions of the <xref:System.Data.DataSet> as well as the relation and constraint definitions.</span></span>  
  
 <span data-ttu-id="d7d07-106">当以 XML 数据形式编写 <xref:System.Data.DataSet> 时，<xref:System.Data.DataSet> 中的行将以它们的当前版本编写。</span><span class="sxs-lookup"><span data-stu-id="d7d07-106">When a <xref:System.Data.DataSet> is written as XML data, the rows in the <xref:System.Data.DataSet> are written in their current versions.</span></span> <span data-ttu-id="d7d07-107">不过，也可以用 DiffGram 形式编写 <xref:System.Data.DataSet>，从而使行的当前值和原始值都将包含在内。</span><span class="sxs-lookup"><span data-stu-id="d7d07-107">However, the <xref:System.Data.DataSet> can also be written as a DiffGram so that both the current and the original values of the rows will be included.</span></span>  
  
 <span data-ttu-id="d7d07-108">XML 表示形式<xref:System.Data.DataSet>可以写入到文件、 流， **XmlWriter**，或字符串。</span><span class="sxs-lookup"><span data-stu-id="d7d07-108">The XML representation of the <xref:System.Data.DataSet> can be written to a file, a stream, an **XmlWriter**, or a string.</span></span> <span data-ttu-id="d7d07-109">这些选择在如何传输 <xref:System.Data.DataSet> 的 XML 表示形式方面提供了很大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="d7d07-109">These choices provide great flexibility for how you transport the XML representation of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="d7d07-110">若要获取的 XML 表示形式<xref:System.Data.DataSet>作为一个字符串，使用**GetXml**方法，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="d7d07-110">To obtain the XML representation of the <xref:System.Data.DataSet> as a string, use the **GetXml** method as shown in the following example.</span></span>  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 <span data-ttu-id="d7d07-111">**GetXml**返回的 XML 表示形式<xref:System.Data.DataSet>不包含架构信息。</span><span class="sxs-lookup"><span data-stu-id="d7d07-111">**GetXml** returns the XML representation of the <xref:System.Data.DataSet> without schema information.</span></span> <span data-ttu-id="d7d07-112">若要从架构信息写入<xref:System.Data.DataSet>（作为 XML 架构） 到一个字符串，使用**GetXmlSchema**。</span><span class="sxs-lookup"><span data-stu-id="d7d07-112">To write the schema information from the <xref:System.Data.DataSet> (as XML Schema) to a string, use **GetXmlSchema**.</span></span>  
  
 <span data-ttu-id="d7d07-113">若要编写<xref:System.Data.DataSet>到一个文件流，或**XmlWriter**，使用**WriteXml**方法。</span><span class="sxs-lookup"><span data-stu-id="d7d07-113">To write a <xref:System.Data.DataSet> to a file, stream, or **XmlWriter**, use the **WriteXml** method.</span></span> <span data-ttu-id="d7d07-114">第一个参数传递给**WriteXml**目标的 XML 输出。</span><span class="sxs-lookup"><span data-stu-id="d7d07-114">The first parameter you pass to **WriteXml** is the destination of the XML output.</span></span> <span data-ttu-id="d7d07-115">例如，传递包含文件名的字符串**System.IO.TextWriter**对象，依次类推。</span><span class="sxs-lookup"><span data-stu-id="d7d07-115">For example, pass a string containing a file name, a **System.IO.TextWriter** object, and so on.</span></span> <span data-ttu-id="d7d07-116">可以传递另一个可选参数**XmlWriteMode**来指定要写入的 XML 输出的方式。</span><span class="sxs-lookup"><span data-stu-id="d7d07-116">You can pass an optional second parameter of an **XmlWriteMode** to specify how the XML output is to be written.</span></span>  
  
 <span data-ttu-id="d7d07-117">下表显示的选项**XmlWriteMode**。</span><span class="sxs-lookup"><span data-stu-id="d7d07-117">The following table shows the options for **XmlWriteMode**.</span></span>  
  
|<span data-ttu-id="d7d07-118">XmlWriteMode 选项</span><span class="sxs-lookup"><span data-stu-id="d7d07-118">XmlWriteMode option</span></span>|<span data-ttu-id="d7d07-119">描述</span><span class="sxs-lookup"><span data-stu-id="d7d07-119">Description</span></span>|  
|-------------------------|-----------------|  
|**<span data-ttu-id="d7d07-120">IgnoreSchema</span><span class="sxs-lookup"><span data-stu-id="d7d07-120">IgnoreSchema</span></span>**|<span data-ttu-id="d7d07-121">以 XML 数据形式编写 <xref:System.Data.DataSet> 的当前内容，不包含 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="d7d07-121">Writes the current contents of the <xref:System.Data.DataSet> as XML data, without an XML Schema.</span></span> <span data-ttu-id="d7d07-122">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="d7d07-122">This is the default.</span></span>|  
|**<span data-ttu-id="d7d07-123">WriteSchema</span><span class="sxs-lookup"><span data-stu-id="d7d07-123">WriteSchema</span></span>**|<span data-ttu-id="d7d07-124">以 XML 数据形式编写 <xref:System.Data.DataSet> 的当前内容，以关系结构作为内联 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="d7d07-124">Writes the current contents of the <xref:System.Data.DataSet> as XML data with the relational structure as inline XML Schema.</span></span>|  
|**<span data-ttu-id="d7d07-125">DiffGram</span><span class="sxs-lookup"><span data-stu-id="d7d07-125">DiffGram</span></span>**|<span data-ttu-id="d7d07-126">以 DiffGram 形式编写整个 <xref:System.Data.DataSet>，包括原始值和当前值。</span><span class="sxs-lookup"><span data-stu-id="d7d07-126">Writes the entire <xref:System.Data.DataSet> as a DiffGram, including original and current values.</span></span> <span data-ttu-id="d7d07-127">有关详细信息，请参阅[Diffgram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)。</span><span class="sxs-lookup"><span data-stu-id="d7d07-127">For more information, see [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span></span>|  
  
 <span data-ttu-id="d7d07-128">当编写的 XML 表示形式<xref:System.Data.DataSet>，其中包含**DataRelation**对象，您很可能希望生成的 XML 将每个关系嵌套在它们相关的父元素的子行。</span><span class="sxs-lookup"><span data-stu-id="d7d07-128">When writing an XML representation of a <xref:System.Data.DataSet> that contains **DataRelation** objects, you will most likely want the resulting XML to have the child rows of each relation nested within their related parent elements.</span></span> <span data-ttu-id="d7d07-129">若要完成此操作，设置**嵌套**的属性**DataRelation**到**true**添加时**DataRelation**到<xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="d7d07-129">To accomplish this, set the **Nested** property of the **DataRelation** to **true** when you add the **DataRelation** to the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="d7d07-130">有关详细信息，请参阅[嵌套 Datarelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)。</span><span class="sxs-lookup"><span data-stu-id="d7d07-130">For more information, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
 <span data-ttu-id="d7d07-131">下面是两个有关如何将 <xref:System.Data.DataSet> 的 XML 表示形式写入文件的示例。</span><span class="sxs-lookup"><span data-stu-id="d7d07-131">Following are two examples of how to write the XML representation of a <xref:System.Data.DataSet> to a file.</span></span> <span data-ttu-id="d7d07-132">第一个示例将生成的 XML 的文件名称的字符串作为传递**WriteXml**。</span><span class="sxs-lookup"><span data-stu-id="d7d07-132">The first example passes the file name for the resulting XML as a string to **WriteXml**.</span></span> <span data-ttu-id="d7d07-133">第二个示例传递**System.IO.StreamWriter**对象。</span><span class="sxs-lookup"><span data-stu-id="d7d07-133">The second example passes a **System.IO.StreamWriter** object.</span></span>  
  
```vb  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema)  
```  
  
```csharp  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema);  
```  
  
```vb  
Dim xmlSW As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xml")  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema)  
xmlSW.Close()  
```  
  
```csharp  
System.IO.StreamWriter xmlSW = new System.IO.StreamWriter("Customers.xml");  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema);  
xmlSW.Close();  
```  
  
## <a name="mapping-columns-to-xml-elements-attributes-and-text"></a><span data-ttu-id="d7d07-134">将列映射到 XML 元素、属性和文本</span><span class="sxs-lookup"><span data-stu-id="d7d07-134">Mapping Columns to XML Elements, Attributes, and Text</span></span>  
 <span data-ttu-id="d7d07-135">您可以指定如何在 XML 中表示表的列使用**ColumnMapping**的属性**DataColumn**对象。</span><span class="sxs-lookup"><span data-stu-id="d7d07-135">You can specify how a column of a table is represented in XML using the **ColumnMapping** property of the **DataColumn** object.</span></span> <span data-ttu-id="d7d07-136">下表显示了不同**MappingType**值为**ColumnMapping**的表列和生成的 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="d7d07-136">The following table shows the different **MappingType** values for the **ColumnMapping** property of a table column, and the resulting XML.</span></span>  
  
|<span data-ttu-id="d7d07-137">MappingType 值</span><span class="sxs-lookup"><span data-stu-id="d7d07-137">MappingType value</span></span>|<span data-ttu-id="d7d07-138">描述</span><span class="sxs-lookup"><span data-stu-id="d7d07-138">Description</span></span>|  
|-----------------------|-----------------|  
|**<span data-ttu-id="d7d07-139">元素</span><span class="sxs-lookup"><span data-stu-id="d7d07-139">Element</span></span>**|<span data-ttu-id="d7d07-140">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="d7d07-140">This is the default.</span></span> <span data-ttu-id="d7d07-141">列以元素名称为 ColumnName 的 XML 元素形式编写，列的内容以元素文本形式编写。</span><span class="sxs-lookup"><span data-stu-id="d7d07-141">The column is written as an XML element where the ColumnName is the name of the element and the contents of the column are written as the text of the element.</span></span> <span data-ttu-id="d7d07-142">例如：</span><span class="sxs-lookup"><span data-stu-id="d7d07-142">For example:</span></span><br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|**<span data-ttu-id="d7d07-143">特性</span><span class="sxs-lookup"><span data-stu-id="d7d07-143">Attribute</span></span>**|<span data-ttu-id="d7d07-144">对于属性名称为 ColumnName 的当前行，列以 XML 元素的 XML 属性形式编写，列的内容以属性值形式编写。</span><span class="sxs-lookup"><span data-stu-id="d7d07-144">The column is written as an XML attribute of the XML element for the current row where the ColumnName is the name of the attribute and the contents of the column are written as the value of the attribute.</span></span> <span data-ttu-id="d7d07-145">例如：</span><span class="sxs-lookup"><span data-stu-id="d7d07-145">For example:</span></span><br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|**<span data-ttu-id="d7d07-146">SimpleContent</span><span class="sxs-lookup"><span data-stu-id="d7d07-146">SimpleContent</span></span>**|<span data-ttu-id="d7d07-147">列的内容以 XML 元素中当前行文本的形式编写。</span><span class="sxs-lookup"><span data-stu-id="d7d07-147">The contents of the column are written as text in the XML element for the current row.</span></span> <span data-ttu-id="d7d07-148">例如：</span><span class="sxs-lookup"><span data-stu-id="d7d07-148">For example:</span></span><br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> <span data-ttu-id="d7d07-149">请注意， **SimpleContent**不能设置为具有表的列**元素**列或嵌套的关系。</span><span class="sxs-lookup"><span data-stu-id="d7d07-149">Note that **SimpleContent** cannot be set for a column of a table that has **Element** columns or nested relations.</span></span>|  
|**<span data-ttu-id="d7d07-150">Hidden</span><span class="sxs-lookup"><span data-stu-id="d7d07-150">Hidden</span></span>**|<span data-ttu-id="d7d07-151">不在 XML 输出中编写该列。</span><span class="sxs-lookup"><span data-stu-id="d7d07-151">The column is not written in the XML output.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d7d07-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7d07-152">See also</span></span>

- [<span data-ttu-id="d7d07-153">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="d7d07-153">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="d7d07-154">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="d7d07-154">DiffGrams</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)
- [<span data-ttu-id="d7d07-155">嵌套 DataRelation</span><span class="sxs-lookup"><span data-stu-id="d7d07-155">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)
- [<span data-ttu-id="d7d07-156">写入数据集架构信息作为 XSD</span><span class="sxs-lookup"><span data-stu-id="d7d07-156">Writing DataSet Schema Information as XSD</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-schema-information-as-xsd.md)
- [<span data-ttu-id="d7d07-157">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="d7d07-157">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="d7d07-158">ADO.NET 托管提供程序和 DataSet 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="d7d07-158">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

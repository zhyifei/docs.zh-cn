---
title: 从 XML 加载数据集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49c083b7-a5ed-41cf-aabc-5aaba96f00e6
ms.openlocfilehash: 0c53e3a15bcbe61db7da1edb31ecd3fd562603f5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099887"
---
# <a name="loading-a-dataset-from-xml"></a><span data-ttu-id="2130c-102">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="2130c-102">Loading a DataSet from XML</span></span>
<span data-ttu-id="2130c-103">ADO.NET <xref:System.Data.DataSet> 的内容可以从 XML 流或文档创建。</span><span class="sxs-lookup"><span data-stu-id="2130c-103">The contents of an ADO.NET <xref:System.Data.DataSet> can be created from an XML stream or document.</span></span> <span data-ttu-id="2130c-104">此外，利用 .NET Framework，您可以相当灵活地控制从 XML 中加载哪些信息以及如何创建 <xref:System.Data.DataSet> 的架构（即关系结构）。</span><span class="sxs-lookup"><span data-stu-id="2130c-104">In addition, with the .NET Framework you have great flexibility over what information is loaded from XML, and how the schema or relational structure of the <xref:System.Data.DataSet> is created.</span></span>  
  
 <span data-ttu-id="2130c-105">若要填充<xref:System.Data.DataSet>XML 中的数据，使用**ReadXml**方法的<xref:System.Data.DataSet>对象。</span><span class="sxs-lookup"><span data-stu-id="2130c-105">To fill a <xref:System.Data.DataSet> with data from XML, use the **ReadXml** method of the <xref:System.Data.DataSet> object.</span></span> <span data-ttu-id="2130c-106">**ReadXml**方法读取文件、 流，或**XmlReader**，并将作为参数的 XML 以及可选源**XmlReadMode**参数。</span><span class="sxs-lookup"><span data-stu-id="2130c-106">The **ReadXml** method reads from a file, a stream, or an **XmlReader**, and takes as arguments the source of the XML plus an optional **XmlReadMode** argument.</span></span> <span data-ttu-id="2130c-107">有关详细信息**XmlReader**，请参阅[使用 XmlTextReader 读取 XML 数据](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="2130c-107">For more information about the **XmlReader**, see [Reading XML Data with XmlTextReader](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/tfz3cz6w(v=vs.100)).</span></span> <span data-ttu-id="2130c-108">**ReadXml**方法读取 XML 流或文档和加载的内容<xref:System.Data.DataSet>的数据。</span><span class="sxs-lookup"><span data-stu-id="2130c-108">The **ReadXml** method reads the contents of the XML stream or document and loads the <xref:System.Data.DataSet> with data.</span></span> <span data-ttu-id="2130c-109">它还将创建的关系架构<xref:System.Data.DataSet>具体取决于**XmlReadMode**指定且是否关系架构已经存在。</span><span class="sxs-lookup"><span data-stu-id="2130c-109">It will also create the relational schema of the <xref:System.Data.DataSet> depending on the **XmlReadMode** specified and whether or not a relational schema already exists.</span></span>  
  
 <span data-ttu-id="2130c-110">下表描述的选项**XmlReadMode**参数。</span><span class="sxs-lookup"><span data-stu-id="2130c-110">The following table describes the options for the **XmlReadMode** argument.</span></span>  
  
|<span data-ttu-id="2130c-111">选项</span><span class="sxs-lookup"><span data-stu-id="2130c-111">Option</span></span>|<span data-ttu-id="2130c-112">描述</span><span class="sxs-lookup"><span data-stu-id="2130c-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2130c-113">**Auto**</span><span class="sxs-lookup"><span data-stu-id="2130c-113">**Auto**</span></span>|<span data-ttu-id="2130c-114">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="2130c-114">This is the default.</span></span> <span data-ttu-id="2130c-115">检查 XML 并按如下顺序选择最适合的选项：</span><span class="sxs-lookup"><span data-stu-id="2130c-115">Examines the XML and chooses the most appropriate option in the following order:</span></span><br /><br /> <span data-ttu-id="2130c-116">-如果 XML 为 DiffGram **DiffGram**使用。</span><span class="sxs-lookup"><span data-stu-id="2130c-116">-   If the XML is a DiffGram, **DiffGram** is used.</span></span><br /><span data-ttu-id="2130c-117">-如果<xref:System.Data.DataSet>包含一个架构或 XML 包含内联架构**ReadSchema**使用。</span><span class="sxs-lookup"><span data-stu-id="2130c-117">-   If the <xref:System.Data.DataSet> contains a schema or the XML contains an inline schema, **ReadSchema** is used.</span></span><br /><span data-ttu-id="2130c-118">-如果<xref:System.Data.DataSet>不包含架构且 XML 不包含内联架构**InferSchema**使用。</span><span class="sxs-lookup"><span data-stu-id="2130c-118">-   If the <xref:System.Data.DataSet> does not contain a schema and the XML does not contain an inline schema, **InferSchema** is used.</span></span><br /><br /> <span data-ttu-id="2130c-119">如果您知道所读取的 XML 的格式，为获得最佳性能建议设置显式**XmlReadMode**，而不是不是接受**自动**默认值。</span><span class="sxs-lookup"><span data-stu-id="2130c-119">If you know the format of the XML being read, for best performance it is recommended that you set an explicit **XmlReadMode**, rather than accept the **Auto** default.</span></span>|  
|<span data-ttu-id="2130c-120">**ReadSchema**</span><span class="sxs-lookup"><span data-stu-id="2130c-120">**ReadSchema**</span></span>|<span data-ttu-id="2130c-121">读取内联架构并加载数据和架构。</span><span class="sxs-lookup"><span data-stu-id="2130c-121">Reads any inline schema and loads the data and schema.</span></span><br /><br /> <span data-ttu-id="2130c-122">如果 <xref:System.Data.DataSet> 已包含架构，则新表将从内联架构添加到 <xref:System.Data.DataSet> 中的现有架构。</span><span class="sxs-lookup"><span data-stu-id="2130c-122">If the <xref:System.Data.DataSet> already contains a schema, new tables are added from the inline schema to the existing schema in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="2130c-123">如果 <xref:System.Data.DataSet> 中已存在内联架构中的任何表，则将引发异常。</span><span class="sxs-lookup"><span data-stu-id="2130c-123">If any tables in the inline schema already exist in the <xref:System.Data.DataSet>, an exception is thrown.</span></span> <span data-ttu-id="2130c-124">你将不能修改现有的表使用的架构**XmlReadMode.ReadSchema**。</span><span class="sxs-lookup"><span data-stu-id="2130c-124">You will not be able to modify the schema of an existing table using **XmlReadMode.ReadSchema**.</span></span><br /><br /> <span data-ttu-id="2130c-125">如果 <xref:System.Data.DataSet> 不包含架构，并且没有内联架构，则不会读取任何数据。</span><span class="sxs-lookup"><span data-stu-id="2130c-125">If the <xref:System.Data.DataSet> does not contain a schema, and there is no inline schema, no data is read.</span></span><br /><br /> <span data-ttu-id="2130c-126">内联架构可以使用 XML 架构定义语言 (XSD) 架构来定义。</span><span class="sxs-lookup"><span data-stu-id="2130c-126">Inline schema can be defined using XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="2130c-127">有关编写内联架构作为 XML 架构的详细信息，请参阅[派生数据集关系结构从 XML 架构 (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)。</span><span class="sxs-lookup"><span data-stu-id="2130c-127">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>|  
|<span data-ttu-id="2130c-128">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="2130c-128">**IgnoreSchema**</span></span>|<span data-ttu-id="2130c-129">忽略任何内联架构并将数据加载到现有的 <xref:System.Data.DataSet> 架构中。</span><span class="sxs-lookup"><span data-stu-id="2130c-129">Ignores any inline schema and loads the data into the existing <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="2130c-130">任何与现有架构不匹配的数据都将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="2130c-130">Any data that does not match the existing schema is discarded.</span></span> <span data-ttu-id="2130c-131">如果 <xref:System.Data.DataSet> 中不存在任何架构，则不会加载任何数据。</span><span class="sxs-lookup"><span data-stu-id="2130c-131">If no schema exists in the <xref:System.Data.DataSet>, no data is loaded.</span></span><br /><br /> <span data-ttu-id="2130c-132">如果数据是 DiffGram **IgnoreSchema**具有相同的功能**DiffGram** *。*</span><span class="sxs-lookup"><span data-stu-id="2130c-132">If the data is a DiffGram, **IgnoreSchema** has the same functionality as **DiffGram** *.*</span></span>|  
|<span data-ttu-id="2130c-133">**InferSchema**</span><span class="sxs-lookup"><span data-stu-id="2130c-133">**InferSchema**</span></span>|<span data-ttu-id="2130c-134">忽略任何内联架构并按照 XML 数据的结构推断架构，然后加载数据。</span><span class="sxs-lookup"><span data-stu-id="2130c-134">Ignores any inline schema and infers the schema per the structure of the XML data, then loads the data.</span></span><br /><br /> <span data-ttu-id="2130c-135">如果 <xref:System.Data.DataSet> 已经包含架构，则会通过向现有表中添加列来扩展当前架构。</span><span class="sxs-lookup"><span data-stu-id="2130c-135">If the <xref:System.Data.DataSet> already contains a schema, the current schema is extended by adding columns to existing tables.</span></span> <span data-ttu-id="2130c-136">如果不存在表，则不会添加其他表。</span><span class="sxs-lookup"><span data-stu-id="2130c-136">Extra tables will not be added if there are not existing tables.</span></span> <span data-ttu-id="2130c-137">如果已存在具有不同命名空间的推断表或者任何推断表与现有列发生冲突，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="2130c-137">An exception is thrown if an inferred table already exists with a different namespace, or if any inferred columns conflict with existing columns.</span></span><br /><br /> <span data-ttu-id="2130c-138">详细了解如何**ReadXmlSchema**推断架构从 XML 文档，请参阅[推断数据集关系结构从 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="2130c-138">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>|  
|<span data-ttu-id="2130c-139">**DiffGram**</span><span class="sxs-lookup"><span data-stu-id="2130c-139">**DiffGram**</span></span>|<span data-ttu-id="2130c-140">读取 DiffGram 并将数据添加到当前架构中。</span><span class="sxs-lookup"><span data-stu-id="2130c-140">Reads a DiffGram and adds the data to the current schema.</span></span> <span data-ttu-id="2130c-141">**DiffGram**合并现有行的唯一标识符的值匹配的新行。</span><span class="sxs-lookup"><span data-stu-id="2130c-141">**DiffGram** merges new rows with existing rows where the unique identifier values match.</span></span> <span data-ttu-id="2130c-142">请参见本主题末尾的“合并 XML 中的数据”。</span><span class="sxs-lookup"><span data-stu-id="2130c-142">See "Merging Data from XML" at the end of this topic.</span></span> <span data-ttu-id="2130c-143">有关 Diffgram 的详细信息，请参阅[Diffgram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)。</span><span class="sxs-lookup"><span data-stu-id="2130c-143">For more information about DiffGrams, see [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span></span>|  
|<span data-ttu-id="2130c-144">**片段**</span><span class="sxs-lookup"><span data-stu-id="2130c-144">**Fragment**</span></span>|<span data-ttu-id="2130c-145">持续读取多个 XML 片断，直至到达流的末尾。</span><span class="sxs-lookup"><span data-stu-id="2130c-145">Continues reading multiple XML fragments until the end of the stream is reached.</span></span> <span data-ttu-id="2130c-146">与 <xref:System.Data.DataSet> 架构匹配的片断会追加到相应的表。</span><span class="sxs-lookup"><span data-stu-id="2130c-146">Fragments that match the <xref:System.Data.DataSet> schema are appended to the appropriate tables.</span></span> <span data-ttu-id="2130c-147">与 <xref:System.Data.DataSet> 架构不匹配的片断将被丢弃。</span><span class="sxs-lookup"><span data-stu-id="2130c-147">Fragments that do not match the <xref:System.Data.DataSet> schema are discarded.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="2130c-148">如果传递**XmlReader**到**ReadXml**作为该定位的一部分插入 XML 文档的方式**ReadXml**将读取至下一个元素节点并将其当作根元素，直到仅在元素节点末尾读取。</span><span class="sxs-lookup"><span data-stu-id="2130c-148">If you pass an **XmlReader** to **ReadXml** that is positioned part of the way into an XML document, **ReadXml** will read to the next element node and will treat that as the root element, reading until the end of the element node only.</span></span> <span data-ttu-id="2130c-149">这不适用于如果指定**XmlReadMode.Fragment**。</span><span class="sxs-lookup"><span data-stu-id="2130c-149">This does not apply if you specify **XmlReadMode.Fragment**.</span></span>  
  
## <a name="dtd-entities"></a><span data-ttu-id="2130c-150">DTD 实体</span><span class="sxs-lookup"><span data-stu-id="2130c-150">DTD Entities</span></span>  
 <span data-ttu-id="2130c-151">如果您的 XML 包含文档类型定义 (DTD) 架构中定义的实体，将引发异常，如果你尝试加载<xref:System.Data.DataSet>通过传递文件名称、 流或非验证**XmlReader**到**ReadXml**。</span><span class="sxs-lookup"><span data-stu-id="2130c-151">If your XML contains entities defined in a document type definition (DTD) schema, an exception will be thrown if you attempt to load a <xref:System.Data.DataSet> by passing a file name, stream, or non-validating **XmlReader** to **ReadXml**.</span></span> <span data-ttu-id="2130c-152">相反，必须创建**XmlValidatingReader**，使用**EntityHandling**设置为**EntityHandling.ExpandEntities**，并传递你**XmlValidatingReader**到**ReadXml**。</span><span class="sxs-lookup"><span data-stu-id="2130c-152">Instead, you must create an **XmlValidatingReader**, with **EntityHandling** set to **EntityHandling.ExpandEntities**, and pass your **XmlValidatingReader** to **ReadXml**.</span></span> <span data-ttu-id="2130c-153">**XmlValidatingReader**将扩展这些实体读取之前<xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="2130c-153">The **XmlValidatingReader** will expand the entities prior to being read by the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="2130c-154">以下代码示例显示如何从 XML 流中加载 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="2130c-154">The following code examples show how to load a <xref:System.Data.DataSet> from an XML stream.</span></span> <span data-ttu-id="2130c-155">第一个示例显示了文件名称传递给**ReadXml**方法。</span><span class="sxs-lookup"><span data-stu-id="2130c-155">The first example shows a file name being passed to the **ReadXml** method.</span></span> <span data-ttu-id="2130c-156">第二个示例显示一个字符串，包含使用 <xref:System.IO.StringReader> 加载的 XML。</span><span class="sxs-lookup"><span data-stu-id="2130c-156">The second example shows a string that contains XML being loaded using a <xref:System.IO.StringReader>.</span></span>  
  
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
>  <span data-ttu-id="2130c-157">如果您调用**ReadXml**加载非常大的文件，可能会遇到性能变慢。</span><span class="sxs-lookup"><span data-stu-id="2130c-157">If you call **ReadXml** to load a very large file, you may encounter slow performance.</span></span> <span data-ttu-id="2130c-158">若要确保最佳性能**ReadXml**，在大型文件上调用<xref:System.Data.DataTable.BeginLoadData%2A>每个表中的方法<xref:System.Data.DataSet>，然后调用**ReadXml**。</span><span class="sxs-lookup"><span data-stu-id="2130c-158">To ensure best performance for **ReadXml**, on a large file, call the <xref:System.Data.DataTable.BeginLoadData%2A> method for each table in the <xref:System.Data.DataSet>, and then call **ReadXml**.</span></span> <span data-ttu-id="2130c-159">最后，为 <xref:System.Data.DataTable.EndLoadData%2A> 中的每个表调用 <xref:System.Data.DataSet>，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="2130c-159">Finally, call <xref:System.Data.DataTable.EndLoadData%2A> for each table in the <xref:System.Data.DataSet>, as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="2130c-160">如果的 XSD 架构你<xref:System.Data.DataSet>包括**targetNamespace**，可能无法读取数据，并调用时，可能会发生异常**ReadXml**加载<xref:System.Data.DataSet>使用包含的 XML使用非限定命名空间的元素。</span><span class="sxs-lookup"><span data-stu-id="2130c-160">If the XSD schema for your <xref:System.Data.DataSet> includes a **targetNamespace**, data may not be read, and you may encounter exceptions, when calling **ReadXml** to load the <xref:System.Data.DataSet> with XML that contains elements with no qualifying namespace.</span></span> <span data-ttu-id="2130c-161">若要读取未限定的元素在这种情况下，设置**elementFormDefault**等于"qualified"中的 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="2130c-161">To read unqualified elements in this case, set **elementFormDefault** equal to "qualified" in your XSD schema.</span></span> <span data-ttu-id="2130c-162">例如：</span><span class="sxs-lookup"><span data-stu-id="2130c-162">For example:</span></span>  
  
```xml  
<xsd:schema id="customDataSet"   
  elementFormDefault="qualified"  
  targetNamespace="http://www.tempuri.org/customDataSet.xsd"   
  xmlns="http://www.tempuri.org/customDataSet.xsd"   
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
  xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
</xsd:schema>  
```  
  
## <a name="merging-data-from-xml"></a><span data-ttu-id="2130c-163">合并 XML 中的数据</span><span class="sxs-lookup"><span data-stu-id="2130c-163">Merging Data from XML</span></span>  
 <span data-ttu-id="2130c-164">如果 <xref:System.Data.DataSet> 已经包含数据，则会向已存在于 <xref:System.Data.DataSet> 中的数据添加 XML 中的新数据。</span><span class="sxs-lookup"><span data-stu-id="2130c-164">If the <xref:System.Data.DataSet> already contains data, the new data from the XML is added to the data already present in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="2130c-165">**ReadXml**不会合并从 XML 向<xref:System.Data.DataSet>任何行具有匹配主键的信息。</span><span class="sxs-lookup"><span data-stu-id="2130c-165">**ReadXml** does not merge from the XML into the <xref:System.Data.DataSet> any row information with matching primary keys.</span></span> <span data-ttu-id="2130c-166">若要使用 XML 中的新信息覆盖现有行信息，请使用**ReadXml**若要创建一个新<xref:System.Data.DataSet>，然后<xref:System.Data.DataSet.Merge%2A>新<xref:System.Data.DataSet>到现有<xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="2130c-166">To overwrite existing row information with new information from XML, use **ReadXml** to create a new <xref:System.Data.DataSet>, and then <xref:System.Data.DataSet.Merge%2A> the new <xref:System.Data.DataSet> into the existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="2130c-167">请注意该装载时使用的 DiffGram **ReadXML**与**XmlReadMode**的**DiffGram**将合并具有相同的唯一标识符的行。</span><span class="sxs-lookup"><span data-stu-id="2130c-167">Note that loading a DiffGram using **ReadXML** with an **XmlReadMode** of **DiffGram** will merge rows that have the same unique identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2130c-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="2130c-168">See also</span></span>

- <xref:System.Data.DataSet.Merge%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2130c-169">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="2130c-169">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="2130c-170">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="2130c-170">DiffGrams</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md)
- [<span data-ttu-id="2130c-171">从 XML 架构派生数据集关系结构 (XSD)</span><span class="sxs-lookup"><span data-stu-id="2130c-171">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="2130c-172">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="2130c-172">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="2130c-173">从 XML 加载数据集构架信息</span><span class="sxs-lookup"><span data-stu-id="2130c-173">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="2130c-174">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="2130c-174">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="2130c-175">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="2130c-175">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

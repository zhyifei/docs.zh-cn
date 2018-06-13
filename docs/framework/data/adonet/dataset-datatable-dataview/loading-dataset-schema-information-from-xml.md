---
title: 从 XML 加载数据集架构信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 4b212a7233e6eec93cdce3e521b58e08745e35e0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760240"
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="3e97c-102">从 XML 加载数据集架构信息</span><span class="sxs-lookup"><span data-stu-id="3e97c-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="3e97c-103">架构<xref:System.Data.DataSet>（其表、 列、 关系和约束） 可以定义，以编程方式创建的**填充**或**FillSchema**方法<xref:System.Data.Common.DataAdapter>，或从加载XML 文档。</span><span class="sxs-lookup"><span data-stu-id="3e97c-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="3e97c-104">若要加载**数据集**架构信息从 XML 文档，你可以使用**ReadXmlSchema**或**InferXmlSchema**方法**数据集**.</span><span class="sxs-lookup"><span data-stu-id="3e97c-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="3e97c-105">**ReadXmlSchema**允许你加载或推断**数据集**文档包含 XML 架构定义语言 (XSD) 架构或包含内联 XML 架构的 XML 文档中的架构信息。</span><span class="sxs-lookup"><span data-stu-id="3e97c-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="3e97c-106">**InferXmlSchema**可以推断 XML 文档中的架构时忽略某些你指定的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="3e97c-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e97c-107">中的表顺序**数据集**时你使用 Web 服务或 XML 序列化传输可能不会保留**数据集**在内存中创建使用 XSD 构造 （如嵌套关系）。</span><span class="sxs-lookup"><span data-stu-id="3e97c-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="3e97c-108">因此，接收方的**数据集**不应依赖表顺序在这种情况下。</span><span class="sxs-lookup"><span data-stu-id="3e97c-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="3e97c-109">但是，表如果始终保留顺序的架构**数据集**传输从 XSD 文件，而不创建内存中读取。</span><span class="sxs-lookup"><span data-stu-id="3e97c-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="3e97c-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="3e97c-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="3e97c-111">若要加载的架构**数据集**从 XML 文档不加载任何数据的情况下，你可以使用**ReadXmlSchema**方法**数据集**。</span><span class="sxs-lookup"><span data-stu-id="3e97c-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="3e97c-112">**ReadXmlSchema**创建**数据集**使用 XML 架构定义语言 (XSD) 架构定义的架构。</span><span class="sxs-lookup"><span data-stu-id="3e97c-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="3e97c-113">**ReadXmlSchema**方法采用单个参数的文件名，流，或**XmlReader**包含要加载的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="3e97c-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="3e97c-114">XML 文档可以仅包含架构，也可以包含与包含数据的 XML 元素内联的架构。</span><span class="sxs-lookup"><span data-stu-id="3e97c-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="3e97c-115">有关编写内联架构作为 XML 架构的详细信息，请参阅[派生数据集关系结构从 XML 架构 (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)。</span><span class="sxs-lookup"><span data-stu-id="3e97c-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="3e97c-116">如果 XML 文档传递给**ReadXmlSchema**不包含任何内联架构信息， **ReadXmlSchema**将推断 XML 文档中的元素中的架构。</span><span class="sxs-lookup"><span data-stu-id="3e97c-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="3e97c-117">如果**数据集**已包含架构，将通过添加新表，如果不存在扩展当前架构。</span><span class="sxs-lookup"><span data-stu-id="3e97c-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="3e97c-118">不会将新列添加到现有表中。</span><span class="sxs-lookup"><span data-stu-id="3e97c-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="3e97c-119">如果已正在添加某列中存在**数据集**但不兼容的类型与列找到了在 XML 中，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="3e97c-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="3e97c-120">有关详细信息，有关如何**ReadXmlSchema**推断架构从 XML 文档，请参阅[推断数据集关系结构从 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="3e97c-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="3e97c-121">尽管**ReadXmlSchema**加载或推断的架构**数据集**、 **ReadXml**方法**数据集**加载或推断同时架构和 XML 文档中包含的数据。</span><span class="sxs-lookup"><span data-stu-id="3e97c-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="3e97c-122">有关详细信息，请参阅[从 XML 加载数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="3e97c-122">For more information, see [Loading a DataSet from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="3e97c-123">下面的代码示例显示如何加载**数据集**架构从一个 XML 文档或流。</span><span class="sxs-lookup"><span data-stu-id="3e97c-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="3e97c-124">第一个示例会显示 XML 架构文件名称传递给**ReadXmlSchema**方法。</span><span class="sxs-lookup"><span data-stu-id="3e97c-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="3e97c-125">第二个示例显示**System.IO.StreamReader**。</span><span class="sxs-lookup"><span data-stu-id="3e97c-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
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
  
## <a name="inferxmlschema"></a><span data-ttu-id="3e97c-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="3e97c-126">InferXmlSchema</span></span>  
 <span data-ttu-id="3e97c-127">你还可以指示**数据集**推断其架构从 XML 文档使用**InferXmlSchema**方法**数据集**。</span><span class="sxs-lookup"><span data-stu-id="3e97c-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="3e97c-128">**InferXmlSchema**执行上述操作的功能相同**ReadXml**与**XmlReadMode**的**InferSchema** （加载数据，以及推断架构），和**ReadXmlSchema**如果所读取的文档不包含任何内联架构。</span><span class="sxs-lookup"><span data-stu-id="3e97c-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="3e97c-129">但是， **InferXmlSchema**提供其他功能，使你能够指定特定的 XML 命名空间来推断架构时，会忽略。</span><span class="sxs-lookup"><span data-stu-id="3e97c-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="3e97c-130">**InferXmlSchema**采用两个必需的参数： 文件名、 流、 指定的 XML 文档的位置或**XmlReader**; 以及要忽略由该操作的 XML 命名空间的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="3e97c-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="3e97c-131">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="3e97c-131">For example, consider the following XML:</span></span>  
  
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
  
 <span data-ttu-id="3e97c-132">由于指定前面的 XML 文档中的元素的属性同时**ReadXmlSchema**方法和**ReadXml**方法替换**XmlReadMode**的**InferSchema**将在文档中创建表为每个元素：**类别**， **CategoryID**， **CategoryName**，**说明**，**产品**， **ProductID**，**再订购量**，和**停止使用**.</span><span class="sxs-lookup"><span data-stu-id="3e97c-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="3e97c-133">(有关详细信息，请参阅[推断数据集关系结构从 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)。)但是，更合适的结构就是仅创建**类别**和**产品**表，并随后创建**CategoryID**， **CategoryName**，和**说明**中的列**类别**表，和**ProductID**，**再订购量**，和**已中断**中的列**产品**表。</span><span class="sxs-lookup"><span data-stu-id="3e97c-133">(For more information, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="3e97c-134">若要确保推断的架构忽略在 XML 元素中指定的属性，使用**InferXmlSchema**方法并指定的 XML 命名空间**officedata**被忽略中, 所示下面的示例。</span><span class="sxs-lookup"><span data-stu-id="3e97c-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e97c-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e97c-135">See Also</span></span>  
 [<span data-ttu-id="3e97c-136">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="3e97c-136">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="3e97c-137">从 XML 架构派生数据集关系结构 (XSD)</span><span class="sxs-lookup"><span data-stu-id="3e97c-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="3e97c-138">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="3e97c-138">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="3e97c-139">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="3e97c-139">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="3e97c-140">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="3e97c-140">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="3e97c-141">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="3e97c-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

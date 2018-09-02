---
title: 写入数据集架构信息作为 XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: 2a59a9fc1c3b2f52543f4cc69de22a5703fa9b8b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43407784"
---
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="7deb1-102">写入数据集架构信息作为 XSD</span><span class="sxs-lookup"><span data-stu-id="7deb1-102">Writing DataSet Schema Information as XSD</span></span>
<span data-ttu-id="7deb1-103">您可以用 XML 架构定义语言 (XSD) 架构的形式来编写 <xref:System.Data.DataSet> 的架构，以便在 XML 文档中传输包含或不包含相关数据的架构。</span><span class="sxs-lookup"><span data-stu-id="7deb1-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="7deb1-104">XML 架构可以写入文件、 流， <xref:System.Xml.XmlWriter>，或字符串，它可用于生成强类型化**数据集**。</span><span class="sxs-lookup"><span data-stu-id="7deb1-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="7deb1-105">有关详细信息强类型化**数据集**对象，请参阅[类型化数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)。</span><span class="sxs-lookup"><span data-stu-id="7deb1-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 <span data-ttu-id="7deb1-106">您可以指定如何将表的列表示 XML 架构中使用**ColumnMapping**属性的<xref:System.Data.DataColumn>对象。</span><span class="sxs-lookup"><span data-stu-id="7deb1-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="7deb1-107">详细信息，请参阅"将列映射到 XML 元素、 属性和文本"中[写入数据集内容作为 XML 数据](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)。</span><span class="sxs-lookup"><span data-stu-id="7deb1-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="7deb1-108">若要写入的架构**数据集**作为 XML 架构，写入一个文件流，或**XmlWriter**，使用**WriteXmlSchema**方法**数据集**。</span><span class="sxs-lookup"><span data-stu-id="7deb1-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="7deb1-109">**WriteXmlSchema**采用一个参数以指定生成的 XML 架构的目标。</span><span class="sxs-lookup"><span data-stu-id="7deb1-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="7deb1-110">下面的代码示例演示如何编写的 XML 架构**数据集**通过传递包含文件名的字符串的文件和一个<xref:System.IO.StreamWriter>对象。</span><span class="sxs-lookup"><span data-stu-id="7deb1-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
```vb  
dataSet.WriteXmlSchema("Customers.xsd")  
```  
  
```csharp  
dataSet.WriteXmlSchema("Customers.xsd");  
```  
  
```vb  
Dim writer As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xsd")  
dataSet.WriteXmlSchema(writer)  
writer.Close()  
```  
  
```csharp  
System.IO.StreamWriter writer = new System.IO.StreamWriter("Customers.xsd");  
dataSet.WriteXmlSchema(writer);  
writer.Close();  
```  
  
 <span data-ttu-id="7deb1-111">若要获取的架构**数据集**并将其保存为 XML 架构字符串，请使用**GetXmlSchema**方法，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="7deb1-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="7deb1-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="7deb1-112">See Also</span></span>  
 [<span data-ttu-id="7deb1-113">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="7deb1-113">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="7deb1-114">以 XML 数据的形式编写数据集内容</span><span class="sxs-lookup"><span data-stu-id="7deb1-114">Writing DataSet Contents as XML Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [<span data-ttu-id="7deb1-115">类型化数据集</span><span class="sxs-lookup"><span data-stu-id="7deb1-115">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="7deb1-116">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="7deb1-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="7deb1-117">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="7deb1-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

---
title: 对数据集执行 XPath 查询
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: c785cc69289440918f45974c711ae0b112130c5d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762405"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a><span data-ttu-id="a624d-102">对数据集执行 XPath 查询</span><span class="sxs-lookup"><span data-stu-id="a624d-102">Performing an XPath Query on a DataSet</span></span>
<span data-ttu-id="a624d-103">同步之间的关系<xref:System.Data.DataSet>和<xref:System.Xml.XmlDataDocument>让你可以使用 XML 访问的服务，例如 XML 路径语言 (XPath) 查询， **XmlDataDocument**和可以执行某些功能比访问更方便地**数据集**直接。</span><span class="sxs-lookup"><span data-stu-id="a624d-103">The relationship between a synchronized <xref:System.Data.DataSet> and <xref:System.Xml.XmlDataDocument> allows you to make use of XML services, such as the XML Path Language (XPath) query, that access the **XmlDataDocument** and can perform certain functionality more conveniently than accessing the **DataSet** directly.</span></span> <span data-ttu-id="a624d-104">例如，而不是使用**选择**方法<xref:System.Data.DataTable>来导航到其他表中的关系**数据集**，你可以对执行 XPath 查询**XmlDataDocument**与同步**数据集**，若要获取的窗体中的 XML 元素的列表<xref:System.Xml.XmlNodeList>。</span><span class="sxs-lookup"><span data-stu-id="a624d-104">For example, rather than using the **Select** method of a <xref:System.Data.DataTable> to navigate relationships to other tables in a **DataSet**, you can perform an XPath query on an **XmlDataDocument** that is synchronized with the **DataSet**, to get a list of XML elements in the form of an <xref:System.Xml.XmlNodeList>.</span></span> <span data-ttu-id="a624d-105">中的节点**XmlNodeList**、 强制转换为<xref:System.Xml.XmlElement>节点，则传递给**GetRowFromElement**方法**XmlDataDocument**，则返回匹配<xref:System.Data.DataRow>对中同步的表的行的引用**数据集**。</span><span class="sxs-lookup"><span data-stu-id="a624d-105">The nodes in the **XmlNodeList**, cast as <xref:System.Xml.XmlElement> nodes, can then be passed to the **GetRowFromElement** method of the **XmlDataDocument**, to return matching <xref:System.Data.DataRow> references to the rows of the table in the synchronized **DataSet**.</span></span>  
  
 <span data-ttu-id="a624d-106">例如，以下代码示例执行“孙级”XPath 查询。</span><span class="sxs-lookup"><span data-stu-id="a624d-106">For example, the following code sample performs a "grandchild" XPath query.</span></span> <span data-ttu-id="a624d-107">**数据集**将填充这三个表：**客户**，**订单**，和**OrderDetails**。</span><span class="sxs-lookup"><span data-stu-id="a624d-107">The **DataSet** is filled with three tables: **Customers**, **Orders**, and **OrderDetails**.</span></span> <span data-ttu-id="a624d-108">在示例中，父-子关系首次创建之间**客户**和**订单**表，和介于**订单**和**OrderDetails**表。</span><span class="sxs-lookup"><span data-stu-id="a624d-108">In the sample, a parent-child relation is first created between the **Customers** and **Orders** tables, and between the **Orders** and **OrderDetails** tables.</span></span> <span data-ttu-id="a624d-109">然后，执行 XPath 查询来返回**XmlNodeList**的**客户**节点，孙级**OrderDetails**节点具有**ProductID**节点值为 43。</span><span class="sxs-lookup"><span data-stu-id="a624d-109">An XPath query is then performed to return an **XmlNodeList** of **Customers** nodes where a grandchild **OrderDetails** node has a **ProductID** node with the value of 43.</span></span> <span data-ttu-id="a624d-110">从根本上而言，该示例使用 XPath 查询来确定哪些客户订购的产品**ProductID**为 43。</span><span class="sxs-lookup"><span data-stu-id="a624d-110">In essence, the sample is using the XPath query to determine which customers have ordered the product that has the **ProductID** of 43.</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection.  
connection.Open()  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
Dim detailAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM [Order Details]", connection)  
detailAdapter.Fill(dataSet, "OrderDetails")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
dataSet.Relations.Add("OrderDetail", _  
  dataSet.Tables("Orders").Columns("OrderID"), _  
dataSet.Tables("OrderDetails").Columns("OrderID"), false).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim nodeList As XmlNodeList = xmlDoc.DocumentElement.SelectNodes( _  
  "descendant::Customers[*/OrderDetails/ProductID=43]")  
  
Dim dataRow As DataRow  
Dim xmlNode As XmlNode  
  
For Each xmlNode In nodeList  
  dataRow = xmlDoc.GetRowFromElement(CType(xmlNode, XmlElement))  
  
  If Not dataRow Is Nothing then Console.WriteLine(xmlRow(0).ToString())  
Next  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection.  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(dataSet, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(dataSet, "Orders");  
  
SqlDataAdapter detailAdapter = new SqlDataAdapter(  
  "SELECT * FROM [Order Details]", connection);  
detailAdapter.Fill(dataSet, "OrderDetails");  
  
connection.Close();  
  
dataSet.Relations.Add("CustOrders",  
  dataSet.Tables["Customers"].Columns["CustomerID"],  
 dataSet.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
dataSet.Relations.Add("OrderDetail",  
  dataSet.Tables["Orders"].Columns["OrderID"],  
  dataSet.Tables["OrderDetails"].Columns["OrderID"],   
  false).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);   
  
XmlNodeList nodeList = xmlDoc.DocumentElement.SelectNodes(  
  "descendant::Customers[*/OrderDetails/ProductID=43]");  
  
DataRow dataRow;  
foreach (XmlNode xmlNode in nodeList)  
{  
  dataRow = xmlDoc.GetRowFromElement((XmlElement)xmlNode);  
  if (dataRow != null)  
    Console.WriteLine(dataRow[0]);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a624d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="a624d-111">See Also</span></span>  
 [<span data-ttu-id="a624d-112">数据集和 XmlDataDocument 同步</span><span class="sxs-lookup"><span data-stu-id="a624d-112">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [<span data-ttu-id="a624d-113">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="a624d-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

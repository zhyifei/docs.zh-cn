---
title: 嵌套 DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 3f17d81ac41c90e7f1c48523a4ced91bc788a962
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="nesting-datarelations"></a>嵌套 DataRelation
在数据的关系表示形式中，各个表都包含使用一个列或一组列来相互关联的行。 在 ADO.NET <xref:System.Data.DataSet> 中，表之间的关系使用 <xref:System.Data.DataRelation> 来实现。 当你创建**DataRelation**，仅通过关系管理列的父-子关系。 表和列是独立的实体。 在 XML 提供的数据的分层表示形式中，父子关系通过包含嵌套子元素的父元素来表示。  
  
 为了便于子对象的嵌套时**数据集**与同步<xref:System.Xml.XmlDataDocument>或以 XML 数据写入**WriteXml**、 **DataRelation**公开**嵌套**属性。 设置**嵌套**属性**DataRelation**到**true**使的子行嵌套在父列以 XML 数据形式编写时的关系或与同步**XmlDataDocument**。 **嵌套**属性**DataRelation**是**false**，默认情况下。  
  
 例如，考虑以下**数据集**。  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection)  
  
connection.Open()  
  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
customerAdapter.Fill(dataSet, "Customers")  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
Dim customerOrders As DataRelation = dataSet.Relations.Add( _  
  "CustOrders", dataSet.Tables("Customers").Columns("CustomerID"), _  
  dataSet.Tables("Orders").Columns("CustomerID"))  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection);  
  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
customerAdapter.Fill(dataSet, "Customers");  
orderAdapter.Fill(dataSet, "Orders");  
  
connection.Close();  
  
DataRelation customerOrders = dataSet.Relations.Add(  
  "CustOrders", dataSet.Tables["Customers"].Columns["CustomerID"],  
  dataSet.Tables["Orders"].Columns["CustomerID"]);  
```  
  
 因为**嵌套**属性**DataRelation**对象未设置为**true**此**数据集**，不嵌套的子对象父元素中时这**数据集**表示为 XML 数据。 转换其 XML 表示形式**数据集**包含相关**数据集**具有非嵌套数据关系可能导致性能降低。 建议您嵌套数据关系。 若要执行此操作，将设置**嵌套**属性**true**。 然后在使用上下分层 XPath 查询表达式的 XSLT 样式表中编写代码以定位和转换数据。  
  
 下面的代码示例演示调用的结果**WriteXml**上**数据集**。  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
  <Orders>  
    <OrderID>10643</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-08-25T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10692</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-10-03T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10308</OrderID>  
    <CustomerID>ANATR</CustomerID>  
    <OrderDate>1996-09-18T00:00:00</OrderDate>  
  </Orders>  
</CustomerOrders>  
```  
  
 请注意，**客户**元素和**订单**元素显示为同级元素。 如果你想**订单**元素才会显示为其各自的父元素的子级**嵌套**属性**DataRelation**需要设置为**true**并将添加以下：  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 下面的代码演示生成的输出将如下所示，使用**订单**元素嵌套在它们各自的父元素。  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <Orders>  
      <OrderID>10643</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-08-25T00:00:00</OrderDate>  
    </Orders>  
    <Orders>  
      <OrderID>10692</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-10-03T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <Orders>  
      <OrderID>10308</OrderID>  
      <CustomerID>ANATR</CustomerID>  
      <OrderDate>1996-09-18T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
</CustomerOrders>  
```  
  
## <a name="see-also"></a>请参阅  
 [在数据集中使用 XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [添加数据关系](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 [数据集、数据表和数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)

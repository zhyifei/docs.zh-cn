---
title: 为类型化的数据集进行批注
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 757a87f92d8dc6049de1844fed892d95dc57c990
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151515"
---
# <a name="annotating-typed-datasets"></a>为类型化的数据集进行批注
批注使您能够在不修改基础架构的情况下修改类型化 <xref:System.Data.DataSet> 中元素的名称。 修改基础架构中元素的名称将导致键入的**DataSet**引用数据源中不存在的对象，并丢失对数据源中确实存在对象的引用。  
  
 使用注释，您可以使用更有意义的名称自定义键入的**DataSet**中的对象名称，使代码更具可读性，并使键入的**DataSet**更易于客户端使用，同时保留基础架构不变。 例如 **，Northwind**数据库**的客户**表的以下架构元素将导致**客户行**的<xref:System.Data.DataRowCollection>**DataRow**对象名称和命名的**客户**。  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 **客户** **DataRow 集合**名称在客户端代码中有意义，但**客户行** **DataRow**名称具有误导性，因为它是单个对象。 此外，在常见方案中，将引用该对象而不带**行**标识符，而将简单地称为**客户**对象。 解决方案是对架构进行批号，并标识**DataRow**和**DataRowCollection**对象的新名称。 下面是上一架构的批注版本。  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 指定**客户的****类型名称**值将导致**客户**的**DataRow**对象名称。 指定客户的**键入的复数**值**Customers**将保留**客户****的数据罗集合**名称。  
  
 下表显示可用的批注。  
  
|Annotation|说明|  
|----------------|-----------------|  
|**typedName**|对象的名称。|  
|**typedPlural**|对象集合的名称。|  
|**typedParent**|对象在父关系中被引用时的名称。|  
|**typedChildren**|用于从子关系中返回对象的方法的名称。|  
|**nullValue**|如果基础值为**DBNull**，则值。 有关**nullValue**注释，请参阅下表。 默认值为 **_throw**。|  
  
 下表显示了可以为**nullValue**注释指定的值。  
  
|nullValue 值|说明|  
|---------------------|-----------------|  
|*重置值*|指定要返回的值。 所返回的值必须匹配该元素的类型。 例如，使用 `nullValue="0"` 可为空整数字段返回 0。|  
|**_throw**|引发异常。 这是默认值。|  
|**_null**|如果遇到基元类型，则返回空引用或引发异常。|  
|**_empty**|对于字符串，返回**String.empty**，否则返回从空构造函数创建的对象。 如果遇到基元类型，则引发异常。|  
  
 下表显示了类型**化 DataSet**中对象的默认值和可用的批注。  
  
|对象/方法/事件|默认|Annotation|  
|---------------------------|-------------|----------------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|**数据表**方法|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**数据行**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**属性**|PropertyName|typedName|  
|**儿童**访问|GetChildTableNameRows|typedChildren|  
|**父级**访问|TableNameRow|typedParent|  
|**数据集**事件|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 要使用键入的**DataSet**注释，必须在 XML 架构定义语言 （XSD） 架构中包括以下**xmlns**引用。 要从数据库表创建 xsd，请参阅<xref:System.Data.DataSet.WriteXmlSchema%2A>或使用[可视化工作室中的数据集](/visualstudio/data-tools/dataset-tools-in-visual-studio)。  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 下面是一个带批号的示例架构，该架构公开了**Northwind**数据库**的客户**表，该表与包含**的订单**表相关。  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet"
      xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
      xmlns=""
      xmlns:xs="http://www.w3.org/2001/XMLSchema"
      xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID" type="xs:string" minOccurs="0" />  
              <xs:element name="CompanyName"  
codegen:typedName="CompanyName" type="xs:string" minOccurs="0" />  
              <xs:element name="Phone" codegen:typedName="Phone" codegen:nullValue="" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Orders" codegen:typedName="Order" codegen:typedPlural="Orders">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" codegen:typedName="OrderID"  
type="xs:int" minOccurs="0" />  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID"                  codegen:nullValue="" type="xs:string" minOccurs="0" />  
              <xs:element name="EmployeeID"  
codegen:typedName="EmployeeID" codegen:nullValue="0"
type="xs:int" minOccurs="0" />  
              <xs:element name="OrderAdapter"  
codegen:typedName="OrderAdapter" codegen:nullValue="1980-01-01T00:00:00"
type="xs:dateTime" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
    <xs:unique name="Constraint1">  
      <xs:selector xpath=".//Customers" />  
      <xs:field xpath="CustomerID" />  
    </xs:unique>  
    <xs:keyref name="CustOrders" refer="Constraint1"  
codegen:typedParent="Customer" codegen:typedChildren="GetOrders">  
      <xs:selector xpath=".//Orders" />  
      <xs:field xpath="CustomerID" />  
    </xs:keyref>  
  </xs:element>  
</xs:schema>  
```  
  
 以下代码示例使用从示例架构创建的强类型**数据集**。 它使用一<xref:System.Data.SqlClient.SqlDataAdapter>个填充**客户**表，另一<xref:System.Data.SqlClient.SqlDataAdapter>个用于填充**订单**表。 强类型**数据集**定义**数据关系**。  
  
```vb  
' Assumes a valid SqlConnection object named connection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT CustomerID, CompanyName, Phone FROM Customers", &  
    connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders", &  
    connection)  
  
' Populate a strongly typed DataSet.  
connection.Open()  
Dim customers As CustomerDataSet = New CustomerDataSet()  
customerAdapter.Fill(customers, "Customers")  
orderAdapter.Fill(customers, "Orders")  
connection.Close()  
  
' Add a strongly typed event.  
AddHandler customers.Customers.CustomerChanged, &  
    New CustomerDataSet.CustomerChangeEventHandler( _  
    AddressOf OnCustomerChanged)  
  
' Add a strongly typed DataRow.  
Dim newCustomer As CustomerDataSet.Customer = _  
    customers.Customers.NewCustomer()  
newCustomer.CustomerID = "NEW01"  
newCustomer.CompanyName = "My New Company"  
customers.Customers.AddCustomer(newCustomer)  
  
' Navigate the child relation.  
Dim customer As CustomerDataSet.Customer  
Dim order As CustomerDataSet.Order  
  
For Each customer In customers.Customers  
  Console.WriteLine(customer.CustomerID)  
  For Each order In customer.GetOrders()  
    Console.WriteLine(vbTab & order.OrderID)  
  Next  
Next  
  
Private Shared Sub OnCustomerChanged( _  
    sender As Object, e As CustomerDataSet.CustomerChangeEvent)  
  
End Sub  
```  
  
```csharp  
// Assumes a valid SqlConnection object named connection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
    "SELECT CustomerID, CompanyName, Phone FROM Customers",  
    connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders",
    connection);  
  
// Populate a strongly typed DataSet.  
connection.Open();  
CustomerDataSet customers = new CustomerDataSet();  
customerAdapter.Fill(customers, "Customers");  
orderAdapter.Fill(customers, "Orders");  
connection.Close();  
  
// Add a strongly typed event.  
customers.Customers.CustomerChanged += new
  CustomerDataSet.CustomerChangeEventHandler(OnCustomerChanged);  
  
// Add a strongly typed DataRow.  
CustomerDataSet.Customer newCustomer =
    customers.Customers.NewCustomer();  
newCustomer.CustomerID = "NEW01";  
newCustomer.CompanyName = "My New Company";  
customers.Customers.AddCustomer(newCustomer);  
  
// Navigate the child relation.  
foreach(CustomerDataSet.Customer customer in customers.Customers)  
{  
  Console.WriteLine(customer.CustomerID);  
  foreach(CustomerDataSet.Order order in customer.GetOrders())  
    Console.WriteLine("\t" + order.OrderID);  
}  
  
protected static void OnCustomerChanged(object sender, CustomerDataSet.CustomerChangeEvent e)  
    {  
  
    }  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [类型化数据集](typed-datasets.md)
- [数据集、数据表和数据视图](index.md)
- [ADO.NET 概述](../ado-net-overview.md)

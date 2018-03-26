---
title: 为类型化的数据集进行批注
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: cc09f3f9b43b70b7f9b302d7a9d75428b5a0e6c7
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2018
---
# <a name="annotating-typed-datasets"></a>为类型化的数据集进行批注
批注使您能够在不修改基础架构的情况下修改类型化 <xref:System.Data.DataSet> 中元素的名称。 如果修改基础架构中元素的名称会使类型化**数据集**来指代执行不存在于数据源，并且会丢失对存在于数据源中的对象的引用的对象。  
  
 使用批注，您可以自定义的对象的名称在类型化**数据集**替换为更有意义的名称，使代码更易于阅读，类型化**数据集**客户端使用，同时保持更容易基础架构不变。 例如，下面的架构元素**客户**表**Northwind**数据库将导致**DataRow**对象名称**CustomersRow**和<xref:System.Data.DataRowCollection>名为**客户**。  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 A **DataRowCollection**名称**客户**在客户端代码中有意义但**DataRow**名称**CustomersRow**具有误导性，因为它是单个对象。 此外，在常见方案，该对象来引用而无需**行**标识符和改为将只需称为**客户**对象。 解决方案是为架构添加批注并标识新名称**DataRow**和**DataRowCollection**对象。 下面是上一架构的批注版本。  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 指定**typedName**值**客户**将导致**DataRow**对象名称**客户**。 指定**typedPlural**值**客户**保留**DataRowCollection**名称**客户**。  
  
 下表显示可用的批注。  
  
|批注|描述|  
|----------------|-----------------|  
|**typedName**|对象的名称。|  
|**typedPlural**|对象集合的名称。|  
|**typedParent**|对象在父关系中被引用时的名称。|  
|**typedChildren**|用于从子关系中返回对象的方法的名称。|  
|**nullValue**|值的基础值是否**DBNull**。 请参阅下的表获取**nullValue**批注。 默认值是**_throw**。|  
  
 下表显示可以为指定的值**nullValue**批注。  
  
|nullValue 值|描述|  
|---------------------|-----------------|  
|*替换值*|指定要返回的值。 所返回的值必须匹配该元素的类型。 例如，使用 `nullValue="0"` 可为空整数字段返回 0。|  
|**_throw**|引发异常。 这是默认设置。|  
|**_null**|如果遇到基元类型，则返回空引用或引发异常。|  
|**_empty**|对于字符串返回**String.Empty**，否则返回从空构造函数创建的对象。 如果遇到基元类型，则引发异常。|  
  
 下表显示在类型化的对象的默认值**数据集**以及可用的批注。  
  
|对象/方法/事件|默认|批注|  
|---------------------------|-------------|----------------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|**DataTable**方法|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**DataRow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Property**|PropertyName|typedName|  
|**子**访问器|GetChildTableNameRows|typedChildren|  
|**父**访问器|TableNameRow|typedParent|  
|**数据集**事件|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 若要使用类型**数据集**批注，您必须包括以下**xmlns**在你的 XML 架构定义语言 (XSD) 架构的引用。 (若要从数据库表创建 xsd，请参阅<xref:System.Data.DataSet.WriteXmlSchema%2A>或[使用 Visual Studio 中的数据集](http://msdn.microsoft.com/library/8bw9ksd6.aspx))。  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 下面是示例带批注的架构公开**客户**表**Northwind**的关系数据库**订单**包含的表。  
  
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
  
 下面的代码示例使用强类型化**数据集**从示例架构创建。 它使用一个<xref:System.Data.SqlClient.SqlDataAdapter>来填充**客户**表，另一个<xref:System.Data.SqlClient.SqlDataAdapter>来填充**订单**表。 强类型化**数据集**定义**Datarelation**。  
  
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
    customers.Customers.NewCustomeromer()  
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
    customers.Customers.NewCustomeromer();  
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
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [类型化数据集](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [数据集、数据表和数据视图](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)

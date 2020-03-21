---
title: 将唯一 XML 架构 (XSD) 约束映射到数据集约束
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8bcf705ce4415929e685be79f813846bbb40bb36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150839"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>将唯一 XML 架构 (XSD) 约束映射到数据集约束
在 XML 架构定义语言 （XSD） 架构中，**唯一**元素指定元素或属性的唯一性约束。 在将 XML 架构转换为关系架构的过程中，对 XML 架构中的元素或属性指定的唯一约束将映射到所生成的相应 <xref:System.Data.DataTable> 中的 <xref:System.Data.DataSet> 中的唯一约束。  
  
 下表概述了可以在**唯一**元素中指定的**msdata**属性。  
  
|属性名称|说明|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|如果指定了该属性，它的值将用作约束名。 否则，**名称**属性提供约束名称的值。|  
|**msdata:PrimaryKey**|如果`PrimaryKey="true"`存在**唯**一元素中，则使用**IsPrimaryKey**属性设置为**true**时将创建唯一约束。|  
  
 下面的示例显示了使用**唯**一元素指定唯一性约束的 XML 架构。  
  
```xml  
<xs:schema id="SampleDataSet"
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 架构中**的唯一**元素指定，对于文档实例中的所有**客户**元素 **，CustomerID**子元素的值必须是唯一的。 在构建**DataSet**时，映射过程读取此架构并生成下表：  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 映射过程还会在**CustomerID**列上创建唯一的约束，如下**DataSet**所示。 （为简便起见，只显示相关属性。）  
  
```text  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID
      IsPrimaryKey: False  
```  
  
 在生成的**DataSet**中 **，IsPrimaryKey**属性设置为唯一约束的**False。** 列上**的唯**一属性指示**CustomerID**列值必须是唯一的（但它们可以是空引用，由列的**AllowDBNull**属性指定）。  
  
 如果修改架构并将可选**msdata：主键**属性值设置为**True，** 则在表上创建唯一约束。 **AllowDBNull**列属性设置为**False**，约束的**IsPrimaryKey**属性设置为**True，** 从而使**CustomerID**列成为主键列。  
  
 您可以对 XML 架构中元素或属性的组合指定唯一约束。 下面的示例演示如何通过在架构中添加另一个**xs：field**元素来指定**客户 ID** **和公司名称**值的组合在任何情况下对所有**客户**都是唯一的。  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 这是在生成的**DataSet**中创建的约束。  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>另请参阅

- [将 XML 架构 (XSD) 约束映射到数据集约束](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [从 XML 架构生成数据集关系 (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [ADO.NET 概述](../ado-net-overview.md)

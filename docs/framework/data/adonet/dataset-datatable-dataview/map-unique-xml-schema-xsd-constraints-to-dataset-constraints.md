---
title: 将唯一 XML 架构 (XSD) 约束映射到数据集约束
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8aed9830d613eeb7d49d2339a8ac1892c0e28e93
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>将唯一 XML 架构 (XSD) 约束映射到数据集约束
在 XML 架构定义语言 (XSD) 架构中，**唯一**元素指定的元素或属性的唯一性约束。 在将 XML 架构转换为关系架构的过程中，对 XML 架构中的元素或属性指定的唯一约束将映射到所生成的相应 <xref:System.Data.DataTable> 中的 <xref:System.Data.DataSet> 中的唯一约束。  
  
 下表概括了**msdata**属性可以在中指定**唯一**元素。  
  
|特性名|描述|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|如果指定了该属性，它的值将用作约束名。 否则为**名称**属性会提供约束名的值。|  
|**msdata:PrimaryKey**|如果`PrimaryKey="true"`位于**唯一**元素，与创建唯一约束**IsPrimaryKey**属性设置为**true**。|  
  
 下面的示例显示使用一个 XML 架构**唯一**元素指定的唯一性约束。  
  
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
  
 **唯一**架构中的元素指定所有**客户**实例的文档中的元素的值**CustomerID**必须是唯一的子元素。 在构建**数据集**，映射过程读取此架构，并生成下表：  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 映射过程还创建唯一约束上**CustomerID**列，如下所示**数据集**。 （为简便起见，只显示相关属性。）  
  
```  
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
  
 在**数据集**生成， **IsPrimaryKey**属性设置为**False**对于唯一约束。 **唯一**列属性指示**CustomerID**列的值必须是唯一的 (但它们可以是空引用，为指定的**AllowDBNull**列的属性）。  
  
 如果你修改架构并将设置可选**msdata: primarykey**属性值到**True**，在表上创建唯一约束。 **AllowDBNull**列属性设置为**False**，和**IsPrimaryKey**属性设置为的约束**True**，从而使**CustomerID**列主键列。  
  
 您可以对 XML 架构中元素或属性的组合指定唯一约束。 下面的示例演示如何指定的组合**CustomerID**和**CompanyName**值必须是唯一的所有**客户**在任何情况下，通过添加另一个**xs:field**架构中的元素。  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 这是创建在随后出现的限制**数据集**。  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>请参阅  
 [将 XML 架构 (XSD) 约束映射到数据集约束](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [从 XML 架构生成数据集关系 (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)

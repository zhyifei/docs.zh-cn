---
title: "将 keyref XML 架构 (XSD) 约束映射到数据集约束"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4ca72292bd2c43fec6f3833d521ddb83c01c32c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>将 keyref XML 架构 (XSD) 约束映射到数据集约束
**Keyref**元素，你可以在文档内的元素之间建立链接。 它类似于关系数据库中的外键关系。 如果架构指定**keyref**元素，该元素转换到的表中的列上的相应外键约束在架构映射过程<xref:System.Data.DataSet>。 默认情况下， **keyref**元素还会生成关系，使用**ParentTable**， **ChildTable**， **ParentColumn**，和**ChildColumn**对关系指定的属性。  
  
 下表概括了**msdata**属性可以指定在**keyref**元素。  
  
|特性名|描述|  
|--------------------|-----------------|  
|**msdata:ConstraintOnly**|如果**ConstraintOnly ="true"**上指定**keyref**架构中的元素，将创建一个约束，但不创建任何关系。 如果未指定此属性 (或设置为**False**)，在中创建约束和关系**数据集**。|  
|**msdata:ConstraintName**|如果**ConstraintName**指定属性，其值用作约束的名称。 否则为**名称**属性**keyref**架构中的元素提供中的约束名称**数据集**。|  
|**msdata:UpdateRule**|如果**UpdateRule**中指定属性**keyref**架构中的元素，其值分配给**UpdateRule**中的约束属性**数据集**。 否则为**UpdateRule**属性设置为**Cascade**。|  
|**msdata:DeleteRule**|如果**DeleteRule**中指定属性**keyref**架构中的元素，其值分配给**DeleteRule**中的约束属性**数据集**。 否则为**DeleteRule**属性设置为**Cascade**。|  
|**msdata:AcceptRejectRule**|如果**AcceptRejectRule**中指定属性**keyref**架构中的元素，其值分配给**AcceptRejectRule** 中的约束属性**数据集**。 否则为**AcceptRejectRule**属性设置为**无**。|  
  
 下面的示例包含一个架构，指定**密钥**和**keyref**之间的关系**OrderNumber**的子元素**顺序**元素和**OrderNo**的子元素**OrderDetail**元素。  
  
 在示例中， **OrderNumber**的子元素**OrderDetail**元素是指**OrderNo**的密钥的子元素**顺序**元素。  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 XML 架构定义语言 (XSD) 架构映射过程将生成以下**数据集**包含两个表：  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 此外，**数据集**定义以下约束：  
  
-   上的唯一约束**顺序**表。  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   之间的关系**顺序**和**OrderDetail**表。 **嵌套**属性设置为**False**因为两个元素不嵌套在架构中。  
  
    ```  
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
-   上的外键约束**OrderDetail**表。  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a>另请参阅  
 [将 XML 架构 (XSD) 约束映射到数据集约束](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [从 XML 架构 (XSD) 生成数据集关系](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)

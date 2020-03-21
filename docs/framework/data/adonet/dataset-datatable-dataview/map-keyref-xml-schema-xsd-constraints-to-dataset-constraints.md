---
title: 将 keyref XML 架构 (XSD) 约束映射到数据集约束
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 902b79b73f494ced0f54b29babff1b2e767bd47a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150878"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>将 keyref XML 架构 (XSD) 约束映射到数据集约束
**keyref**元素允许您在文档中的元素之间建立链接。 它类似于关系数据库中的外键关系。 如果架构指定**keyref**元素，则在架构映射过程中将元素转换为 对<xref:System.Data.DataSet>表中的列的相应外键约束。 默认情况下 **，keyref**元素还会生成一个关系，该关系在关系上指定了**父表**、**子表**、**父列**和**子列**属性。  
  
 下表概述了可在**keyref**元素中指定的**msdata**属性。  
  
|属性名称|说明|  
|--------------------|-----------------|  
|**msdata:ConstraintOnly**|如果在架构中的**keyref**元素上指定了 **"约束唯一""true"，** 则将创建约束，但不创建任何关系。 如果未指定此属性（或设置为**False），** 则约束和关系都在**DataSet 中**创建。|  
|**msdata:ConstraintName**|如果指定了 **"约束名称"** 属性，则其值将用作约束的名称。 否则，架构中**keyref**元素**的名称**属性在**DataSet**中提供约束名称。|  
|**msdata:UpdateRule**|如果在架构中的**keyref**元素中指定**了 UpdateRule**属性，则其值将分配给**DataSet**中的**UpdateRule**约束属性。 否则 **，UpdateRule**属性将设置为**级联**。|  
|**msdata:DeleteRule**|如果在架构中的**keyref**元素中指定**了 DeleteRule**属性，则其值将分配给**DataSet**中的**DeleteRule**约束属性。 否则 **，DeleteRule**属性将设置为**级联**。|  
|**msdata:AcceptRejectRule**|如果在架构中的**keyref**元素中指定了**AcceptRejectRule 属性**，则其值将分配给**DataSet**中的**AcceptRejectRule**约束属性。 否则，"**接受拒绝规则"** 属性将设置为 **"无**"。|  
  
 下面的示例包含一个架构，该架构指定**Order**元素的**OrderNumber**子元素和**OrderDetail**元素的**OrderNo**子元素之间的**键**和**键 ref**关系。  
  
 在此示例中，"**订单详细信息"** 元素的**OrderNumber**子元素引用**订单**元素的 **"订单无**"键子元素。  
  
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
  
 XML 架构定义语言 （XSD） 架构映射过程生成具有两个表的以下**DataSet：**  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 此外，**数据集**定义以下约束：  
  
- **订单**表上的唯一约束。  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- **订单**和**订单详细信息**表之间的关系。 **嵌套**属性设置为**False，** 因为两个元素未嵌套在架构中。  
  
    ```text
              ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
- **"订单详细信息**"表上的外键约束。  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a>另请参阅

- [将 XML 架构 (XSD) 约束映射到数据集约束](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [从 XML 架构生成数据集关系 (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [ADO.NET 概述](../ado-net-overview.md)

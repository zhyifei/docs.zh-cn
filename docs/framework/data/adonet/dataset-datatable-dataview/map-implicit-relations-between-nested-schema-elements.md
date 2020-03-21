---
title: 映射嵌套架构元素之间的隐式关系
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: dc5b81fd06f2860283c8c5fa028af4b945e2b1e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150958"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>映射嵌套架构元素之间的隐式关系
XML 架构定义语言 (XSD) 架构可以具有相互嵌套的复杂类型。 在这种情况下，映射过程将应用默认映射并在 <xref:System.Data.DataSet> 中创建以下内容：  
  
- 为每个复杂类型（父和子）创建一个表。  
  
- 如果父项上不存在唯一约束，则每个表定义（称为*表Name）_Id*一个额外的主键列，*其中表名称*是父表的名称。  
  
- 父表上的主键约束将附加列标识为主键（通过将**IsPrimaryKey**属性设置为**True）。** 该约束以 Constraint\# 的形式来命名，其中 \# 为 1、2、3...。 例如，第一个约束的默认名称为 Constraint1。  
  
- 在子表上创建外键约束，该约束将附加列标识为引用父表主键的外键。 约束*ParentTable_ChildTable命名*，其中*parentTable*是父表的名称，*子表*是子表的名称。  
  
- 在父表和子表之间创建数据关系。  
  
 下面的示例显示了**OrderDetail**是**Order**的子元素的架构。  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
   <xs:complexType>  
     <xs:choice maxOccurs="unbounded">  
       <xs:element name="Order">  
         <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:string" />  
            <xs:element name="EmpNumber" type="xs:string" />  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:string" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:choice>  
   </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 XML 架构映射过程在**DataSet**中创建以下内容：  
  
- **订单**和**订单详细信息**表。  
  
    ```text  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- **订单**表上的唯一约束。 请注意 **，IsPrimaryKey**属性设置为**True**。  
  
    ```text  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id
    IsPrimaryKey: True  
    ```  
  
- **"订单详细信息**"表上的外键约束。  
  
    ```text  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id
    RelatedTable: Order  
    RelatedColumns: Order_Id
    ```  
  
- **订单**和**订单详细信息**表之间的关系。 此关系的**嵌套**属性设置为**True，** 因为 **"订单"** 和"**订单详细信息"** 元素嵌套在架构中。  
  
    ```text  
    ParentTable: Order  
    ParentColumns: Order_Id
    ChildTable: OrderDetail  
    ChildColumns: Order_Id
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a>另请参阅

- [从 XML 架构生成数据集关系 (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [将 XML 架构 (XSD) 约束映射到数据集约束](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [ADO.NET 概述](../ado-net-overview.md)

---
title: 映射为嵌套元素指定的关系
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: cd652f51f01dcfa16a8b707f35c658043c20670d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150891"
---
# <a name="map-relations-specified-for-nested-elements"></a>映射为嵌套元素指定的关系
架构可以包括**msdata：关系**注释，以显式指定架构中任意两个元素之间的映射。 msdata 中指定的两个元素 **：关系**可以在架构中嵌套，但不必嵌套。 映射过程使用**msdata：** 架构中的关系来生成两列之间的主键/外键关系。  
  
 下面的示例显示了一个 XML 架构，其中**OrderDetail**元素是**order**的子元素。 **msdata：关系**标识此父子关系，并指定结果**订单**表的**OrderNumber**列与生成的**订单详细信息**表的 **"订单无**"列相关。  
  
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
          <xs:annotation>  
           <xs:appinfo>  
            <msdata:Relationship name="OrdODRelation"
                                msdata:parent="Order"
                                msdata:child="OrderDetail"
                                msdata:parentkey="OrderNumber"
                                msdata:childkey="OrderNo"/>  
           </xs:appinfo>  
          </xs:annotation>  
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
  
 XML 架构映射过程在 <xref:System.Data.DataSet> 中创建以下内容：  
  
- **订单**和**订单详细信息**表。  
  
    ```text  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- **订单**和**订单详细信息**表之间的关系。 此关系的**嵌套**属性设置为**True，** 因为 **"订单"** 和"**订单详细信息"** 元素嵌套在架构中。  
  
    ```text  
    ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 映射过程不创建任何约束。  
  
## <a name="see-also"></a>另请参阅

- [从 XML 架构生成数据集关系 (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [将 XML 架构 (XSD) 约束映射到数据集约束](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [ADO.NET 概述](../ado-net-overview.md)

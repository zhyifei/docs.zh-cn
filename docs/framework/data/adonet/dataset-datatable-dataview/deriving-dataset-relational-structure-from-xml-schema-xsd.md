---
title: 从 XML 架构派生数据集关系结构 (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: d32b5cb86bc5a138f9a5f438629d8e231be4ba94
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151164"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>从 XML 架构派生数据集关系结构 (XSD)
本节将概述如何从 XML 架构定义语言 (XSD) 架构文档生成 `DataSet` 的关系架构。 通常，对于架构元素`complexType`的每个子元素，在 中生成表`DataSet`。 表结构取决于复杂类型的定义。 表在 架构中`DataSet`的顶级元素中创建。 但是，仅当`complexType``complexType``complexType`元素嵌套在另一个元素中时，才为顶级元素创建表，在这种情况下，嵌套`complexType`元素映射到 中的 。 `DataTable` `DataSet`  
  
 有关 XSD 的详细信息，请参阅万维网联盟 （W3C） [XML 架构第 0 部分：引物建议](https://www.w3.org/TR/xmlschema-0/)[、XML 架构第 1 部分：结构建议](https://www.w3.org/TR/xmlschema-1/)和[XML 架构第 2 部分：数据类型建议](https://www.w3.org/TR/xmlschema-2/)。  
  
 下面的示例演示了 XML 架构`customers`，其中元素的`MyDataSet`子元素是**DataSet**元素。  
  
```xml  
<xs:schema id="SomeID"
            xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 在上例中，`customers` 元素为复杂类型元素。 因此，将对复杂类型定义进行分析，而映射过程会创建下表。  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 该表中各列的数据类型是从所指定的相应元素或属性的 XML 架构类型派生的。  
  
> [!NOTE]
> 如果元素`customers`是简单的 XML 架构数据类型（如**整数**），则不生成任何表。 表仅为属于复杂类型的顶级元素而创建。  
  
 在以下 XML 架构中，**架构**元素有两个元素`InStateCustomers`子`OutOfStateCustomers`元素和 。  
  
```xml  
<xs:schema id="SomeID"
            xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 `InStateCustomers` 和 `OutOfStateCustomers` 两个子元素都是复杂类型元素 (`customerType`)。 因此，映射过程在 中生成以下两个相同的表`DataSet`。  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>本节内容  
 [将 XML 架构 (XSD) 约束映射到数据集约束](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 描述用于在 中创建唯一`DataSet`和外键约束的 XML 架构元素。  
  
 [从 XML 架构生成数据集关系 (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 描述用于在 中的表列之间创建关系的 XML 架构`DataSet`元素。  
  
 [XML 架构约束和关系](xml-schema-constraints-and-relationships.md)  
 描述在 中使用 XML 架构元素在 中创建约束时如何`DataSet`隐式创建关系。  
  
## <a name="related-sections"></a>相关章节  
 [在数据集中使用 XML](using-xml-in-a-dataset.md)  
 描述如何将关系结构和数据`DataSet`加载和持久化为 XML 数据。  
  
## <a name="see-also"></a>另请参阅

- [ADO.NET 概述](../ado-net-overview.md)

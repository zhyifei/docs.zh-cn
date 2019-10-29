---
title: 从 XML 架构派生数据集关系结构 (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: ef77030b4e847f91fea074b68e223ac622539048
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040102"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>从 XML 架构派生数据集关系结构 (XSD)
本节将概述如何从 XML 架构定义语言 (XSD) 架构文档生成 `DataSet` 的关系架构。 通常，对于 schema 元素的每个 `complexType` 子元素，都将在 `DataSet`中生成一个表。 表结构取决于复杂类型的定义。 在架构中顶级元素的 `DataSet` 中创建表。 但是，仅当 `complexType` 元素嵌套在另一个 `complexType` 元素中时，才会为顶级 `complexType` 元素创建一个表，在这种情况下，嵌套的 `complexType` 元素将映射到 `DataTable` 中的 `DataSet`。  
  
 有关 XSD 的详细信息，请参阅万维网联合会（W3C） [XML 架构第0部分：入门建议](https://www.w3.org/TR/xmlschema-0/)、 [xml 架构第1部分：结构建议](https://www.w3.org/TR/xmlschema-1/)和[xml 架构第2部分：数据类型建议](https://www.w3.org/TR/xmlschema-2/)。  
  
 下面的示例演示了一个 XML 架构，其中 `customers` 是一个**数据集**元素 `MyDataSet` 元素的子元素。  
  
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
> 如果元素 `customers` 为简单的 XML 架构数据类型（如**integer**），则不会生成任何表。 表仅为属于复杂类型的顶级元素而创建。  
  
 在下面的 XML 架构中， **Schema**元素具有两个子元素，`InStateCustomers` 和 `OutOfStateCustomers`。  
  
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
  
 `InStateCustomers` 和 `OutOfStateCustomers` 两个子元素都是复杂类型元素 (`customerType`)。 因此，映射过程会在 `DataSet`中生成以下两个相同的表。  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>本节内容  
 [将 XML 架构 (XSD) 约束映射到数据集约束](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 介绍用于在 `DataSet`中创建唯一约束和外键约束的 XML 架构元素。  
  
 [从 XML 架构生成数据集关系 (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 描述用于在 `DataSet`中的表列之间创建关系的 XML 架构元素。  
  
 [XML 架构约束和关系](xml-schema-constraints-and-relationships.md)  
 描述在使用 XML 架构元素在 `DataSet`中创建约束时如何隐式地创建关系。  
  
## <a name="related-sections"></a>相关章节  
 [在数据集中使用 XML](using-xml-in-a-dataset.md)  
 描述如何以 XML 数据的形式加载和保留 `DataSet` 中的关系结构和数据。  
  
## <a name="see-also"></a>请参阅

- [ADO.NET 概述](../ado-net-overview.md)

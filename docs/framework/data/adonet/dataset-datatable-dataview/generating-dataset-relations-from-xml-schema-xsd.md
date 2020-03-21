---
title: 从 XML 架构生成数据集关系 (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: feb0be7f66bf0f407e54ef0830c13f0c4a8a6418
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151125"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a>从 XML 架构生成数据集关系 (XSD)
在 <xref:System.Data.DataSet> 中，可通过创建父子关系来形成两个或更多个列之间的关联。 在 XML 架构定义语言 （XSD） 架构中，有三种方法可以表示**DataSet**关系：  
  
- 指定嵌套复杂类型。  
  
- 使用**msdata：关系**注释。  
  
- 指定一个没有 msdata**的 xs：keyref：****仅约束**注释。  
  
## <a name="nested-complex-types"></a>嵌套的复杂类型  
 架构中的嵌套复杂类型定义指示元素的父子关系。 以下 XML 架构片段显示**OrderDetail**是**Order**元素的子元素。  
  
```xml  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>
       <xs:element name="OrderDetail" />  
           <xs:complexType>
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 XML 架构映射过程在**DataSet**中创建对应于架构中嵌套复杂类型的表。 它还创建其他列，这些列用作生成的表**-** 的父子列。 请注意，这些父**-** 子列指定关系，这与指定主键/外键约束不同。  
  
## <a name="msdatarelationship-annotation"></a>msdata:Relationship 批注  
 **msdata：关系**注释允许您显式指定架构中未嵌套的元素之间的父子关系。 下面的示例显示了**关系**元素的结构。  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 **msdata：关系**注释的属性标识父子关系中涉及的元素，以及关系中涉及的**父键**和**子键**元素和属性。 映射过程使用此信息在**DataSet**中生成表，并在这些表之间创建主键/外键关系。  
  
 例如，以下架构片段指定同一级别的 **"订单"** 和"**订单详细信息"** 元素（未嵌套）。 架构指定**msdata：关系**注释，它指定这两个元素之间的父子关系。 在这种情况下，必须使用**msdata：关系**注释指定显式关系。  
  
```xml  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
```  
  
 映射过程使用 **"关系"** 元素在 **"订单**"表中的**OrderNumber**列和**DataSet**中的 **"订单详细信息**"表中的 **"订单无"** 列之间创建父子关系。 映射进程仅指定关系；与关系数据库中的主键/外键约束不同，它并不会自动为这些列中的值指定任何约束。  
  
### <a name="in-this-section"></a>本节内容  
 [映射嵌套架构元素之间的隐式关系](map-implicit-relations-between-nested-schema-elements.md)  
 描述在 XML 架构中遇到嵌套元素时在**DataSet**中隐式创建的约束和关系。  
  
 [映射为嵌套元素指定的关系](map-relations-specified-for-nested-elements.md)  
 描述如何在 XML 架构中为嵌套元素在**DataSet**中显式设置关系。  
  
 [指定无嵌套元素之间的关系](specify-relations-between-elements-with-no-nesting.md)  
 描述如何在未嵌套的 XML 架构元素之间的**DataSet**中创建关系。  
  
### <a name="related-sections"></a>相关章节  
 [从 XML 架构派生数据集关系结构 (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 描述从 XML 架构定义语言 （XSD） 架构创建的**DataSet**的关系结构或架构。  
  
 [将 XML 架构 (XSD) 约束映射到数据集约束](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 描述用于在**DataSet**中创建唯一和外键约束的 XML 架构元素。  
  
## <a name="see-also"></a>另请参阅

- [ADO.NET 概述](../ado-net-overview.md)

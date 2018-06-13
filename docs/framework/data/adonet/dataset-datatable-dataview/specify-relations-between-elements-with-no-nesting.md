---
title: 指定无嵌套的元素之间的关系
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: 1d178287150dfca4c379cf6e934370434c3cfc98
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760084"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="ca0db-102">指定无嵌套的元素之间的关系</span><span class="sxs-lookup"><span data-stu-id="ca0db-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="ca0db-103">当元素不嵌套时，将不创建任何隐式关系。</span><span class="sxs-lookup"><span data-stu-id="ca0db-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="ca0db-104">但是，可以显式指定不使用嵌套的元素之间的关系**msdata: relationship**批注。</span><span class="sxs-lookup"><span data-stu-id="ca0db-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="ca0db-105">下面的示例显示一个 XML 架构，在其中**msdata: relationship**之间指定批注**顺序**和**OrderDetail**元素，它们不是嵌套。</span><span class="sxs-lookup"><span data-stu-id="ca0db-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="ca0db-106">**Msdata: relationship**批注指定的子元素为**架构**元素。</span><span class="sxs-lookup"><span data-stu-id="ca0db-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
           <xs:element name="OrderNo" type="xs:string" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNumber" type="xs:string" />  
           <xs:element name="EmpNumber" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  </xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrderDetailRelation"  
                            msdata:parent="Order"   
                            msdata:child="OrderDetail"   
                            msdata:parentkey="OrderNumber"   
                            msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
</xs:schema>  
```  
  
 <span data-ttu-id="ca0db-107">XML 架构定义语言 (XSD) 架构映射过程创建<xref:System.Data.DataSet>与**顺序**和**OrderDetail**表和如下所示指定这两个表之间的关系。</span><span class="sxs-lookup"><span data-stu-id="ca0db-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber   
ChildTable: OrderDetail  
ChildColumns: OrderNo   
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca0db-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca0db-108">See Also</span></span>  
 [<span data-ttu-id="ca0db-109">从 XML 架构生成数据集关系 (XSD)</span><span class="sxs-lookup"><span data-stu-id="ca0db-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="ca0db-110">将 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="ca0db-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="ca0db-111">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="ca0db-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

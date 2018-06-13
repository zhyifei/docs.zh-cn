---
title: XML 架构约束和关系
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 4b62b6bafa9ceeafd250e722314c4bd6c594bf82
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759837"
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="a75c0-102">XML 架构约束和关系</span><span class="sxs-lookup"><span data-stu-id="a75c0-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="a75c0-103">在 XML 架构定义语言 (XSD) 架构中，你可以指定约束 (唯一的键和 keyref 约束) 和关系 (使用**msdata: relationship**批注)。</span><span class="sxs-lookup"><span data-stu-id="a75c0-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="a75c0-104">本主题说明如何解释在 XML 架构中指定的约束和关系，以生成 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="a75c0-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="a75c0-105">通常情况下，在 XML 架构中，你指定**msdata: relationship**批注，如果你想要生成仅中的关系**数据集**。</span><span class="sxs-lookup"><span data-stu-id="a75c0-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="a75c0-106">有关详细信息，请参阅[生成数据集关系从 XML 架构 (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)。</span><span class="sxs-lookup"><span data-stu-id="a75c0-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="a75c0-107">指定约束 (唯一的键和 keyref) 如果你想要生成中的约束**数据集**。</span><span class="sxs-lookup"><span data-stu-id="a75c0-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="a75c0-108">请注意，如本主题稍后所述，键和 keyref 约束也可用于生成关系。</span><span class="sxs-lookup"><span data-stu-id="a75c0-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="a75c0-109">从键和 keyref 约束生成关系</span><span class="sxs-lookup"><span data-stu-id="a75c0-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="a75c0-110">而不是指定**msdata: relationship**批注，您可以指定键和 keyref 约束，用于在 XML 架构映射过程生成约束不仅关系中**数据集**。</span><span class="sxs-lookup"><span data-stu-id="a75c0-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="a75c0-111">但是，如果你指定`msdata:ConstraintOnly="true"`中**keyref**元素，**数据集**将包括仅约束并且不会包括关系。</span><span class="sxs-lookup"><span data-stu-id="a75c0-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="a75c0-112">下面的示例显示包含一个 XML 架构**顺序**和**OrderDetail**不嵌套的元素。</span><span class="sxs-lookup"><span data-stu-id="a75c0-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="a75c0-113">该架构还指定键约束和 keyref 约束。</span><span class="sxs-lookup"><span data-stu-id="a75c0-113">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="a75c0-114">**数据集**生成在 XML 架构映射过程包括**顺序**和**OrderDetail**表。</span><span class="sxs-lookup"><span data-stu-id="a75c0-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="a75c0-115">此外，**数据集**包含关系和约束。</span><span class="sxs-lookup"><span data-stu-id="a75c0-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="a75c0-116">以下示例将显示这些关系和约束。</span><span class="sxs-lookup"><span data-stu-id="a75c0-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="a75c0-117">请注意，架构未指定**msdata: relationship**批注; 相反，使用键和 keyref 约束来生成关系。</span><span class="sxs-lookup"><span data-stu-id="a75c0-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```  
....ConstraintName: OrderNumberKey  
....Type: UniqueConstraint  
....Table: Order  
....Columns: OrderNumber  
....IsPrimaryKey: False  
  
....ConstraintName: OrderNoRef  
....Type: ForeignKeyConstraint  
....Table: OrderDetail  
....Columns: OrderNo  
....RelatedTable: Order  
....RelatedColumns: OrderNumber  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
```  
  
 <span data-ttu-id="a75c0-118">在以前的架构示例中，**顺序**和**OrderDetail**元素不嵌套。</span><span class="sxs-lookup"><span data-stu-id="a75c0-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="a75c0-119">在以下架构示例中，这些元素嵌套。</span><span class="sxs-lookup"><span data-stu-id="a75c0-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="a75c0-120">但是，没有**msdata: relationship**指定批注; 因此，假定一个隐式关系。</span><span class="sxs-lookup"><span data-stu-id="a75c0-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="a75c0-121">有关详细信息，请参阅[地图隐式关系之间嵌套架构元素](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="a75c0-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="a75c0-122">该架构还指定键约束和 keyref 约束。</span><span class="sxs-lookup"><span data-stu-id="a75c0-122">The schema also specifies key and keyref constraints.</span></span>  
  
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
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:integer" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
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
  
 <span data-ttu-id="a75c0-123">**数据集**导致 XML 架构映射过程包括两个表：</span><span class="sxs-lookup"><span data-stu-id="a75c0-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="a75c0-124">**数据集**还包含两个关系 (基于一个**msdata: relationship**批注，另一个基于键和 keyref 约束) 和各种约束。</span><span class="sxs-lookup"><span data-stu-id="a75c0-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="a75c0-125">以下示例将显示这些关系和约束。</span><span class="sxs-lookup"><span data-stu-id="a75c0-125">The following example shows the relations and constraints.</span></span>  
  
```  
..RelationName: Order_OrderDetail  
..ParentTable: Order  
..ParentColumns: Order_Id  
..ChildTable: OrderDetail  
..ChildColumns: Order_Id  
..ParentKeyConstraint: Constraint1  
..ChildKeyConstraint: Order_OrderDetail  
..Nested: True  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
  
..ConstraintName: OrderNumberKey  
..Type: UniqueConstraint  
..Table: Order  
..Columns: OrderNumber  
..IsPrimaryKey: False  
  
..ConstraintName: Constraint1  
..Type: UniqueConstraint  
..Table: Order  
..Columns: Order_Id  
..IsPrimaryKey: True  
  
..ConstraintName: Order_OrderDetail  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: Order_Id  
..RelatedTable: Order  
..RelatedColumns: Order_Id  
  
..ConstraintName: OrderNoRef  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: OrderNo  
..RelatedTable: Order  
..RelatedColumns: OrderNumber  
```  
  
 <span data-ttu-id="a75c0-126">如果引用嵌套表的 keyref 约束包含**msdata: isnested ="true"** 批注，**数据集**将创建单个嵌套的关系基于 keyref 约束和相关的唯一/键约束。</span><span class="sxs-lookup"><span data-stu-id="a75c0-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a75c0-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="a75c0-127">See Also</span></span>  
 [<span data-ttu-id="a75c0-128">从 XML 架构派生数据集关系结构 (XSD)</span><span class="sxs-lookup"><span data-stu-id="a75c0-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="a75c0-129">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="a75c0-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: XML 架构约束和关系
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 2388d7c277ba1f01bea8d419e5aedf487b843ed7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150709"
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="c8d57-102">XML 架构约束和关系</span><span class="sxs-lookup"><span data-stu-id="c8d57-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="c8d57-103">在 XML 架构定义语言 （XSD） 架构中，您可以指定约束（唯一、键和键ref约束）和关系（使用**msdata：关系**注释）。</span><span class="sxs-lookup"><span data-stu-id="c8d57-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="c8d57-104">本主题说明如何解释在 XML 架构中指定的约束和关系，以生成 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="c8d57-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="c8d57-105">通常，在 XML 架构中，如果只想在**DataSet**中生成关系，请指定**msdata：关系**注释。</span><span class="sxs-lookup"><span data-stu-id="c8d57-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="c8d57-106">有关详细信息，请参阅从[XML 架构 （XSD） 生成数据集关系](generating-dataset-relations-from-xml-schema-xsd.md)。</span><span class="sxs-lookup"><span data-stu-id="c8d57-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="c8d57-107">如果要在**DataSet**中生成约束，请指定约束（唯一、键和键ref）。</span><span class="sxs-lookup"><span data-stu-id="c8d57-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="c8d57-108">请注意，如本主题稍后所述，键和 keyref 约束也可用于生成关系。</span><span class="sxs-lookup"><span data-stu-id="c8d57-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="c8d57-109">从键和 keyref 约束生成关系</span><span class="sxs-lookup"><span data-stu-id="c8d57-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="c8d57-110">您可以指定键和键ref约束，这些约束在 XML 架构映射过程中不仅用于生成约束，而且生成**DataSet**中的关系，而不是指定**msdata：关系**注释。</span><span class="sxs-lookup"><span data-stu-id="c8d57-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="c8d57-111">但是，如果在`msdata:ConstraintOnly="true"`**keyref**元素中指定 **，DataSet**将仅包含约束，并且不包括关系。</span><span class="sxs-lookup"><span data-stu-id="c8d57-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="c8d57-112">下面的示例显示了一个 XML 架构，该架构包括**未嵌套的订单**和**订单详细信息**元素。</span><span class="sxs-lookup"><span data-stu-id="c8d57-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="c8d57-113">该架构还指定键约束和 keyref 约束。</span><span class="sxs-lookup"><span data-stu-id="c8d57-113">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="c8d57-114">在 XML 架构映射过程中生成的**数据集**包括**订单**和**订单详细信息**表。</span><span class="sxs-lookup"><span data-stu-id="c8d57-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="c8d57-115">此外，**数据集**还包括关系和约束。</span><span class="sxs-lookup"><span data-stu-id="c8d57-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="c8d57-116">以下示例将显示这些关系和约束。</span><span class="sxs-lookup"><span data-stu-id="c8d57-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="c8d57-117">请注意，架构未指定**msdata：关系**注释;相反，键和键ref约束用于生成关系。</span><span class="sxs-lookup"><span data-stu-id="c8d57-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```text
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
  
 <span data-ttu-id="c8d57-118">在前面的架构示例中，**顺序**和**订单详细信息**元素不嵌套。</span><span class="sxs-lookup"><span data-stu-id="c8d57-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="c8d57-119">在以下架构示例中，这些元素嵌套。</span><span class="sxs-lookup"><span data-stu-id="c8d57-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="c8d57-120">但是，未指定**msdata：关系**注释指定;因此，假定了隐式关系。</span><span class="sxs-lookup"><span data-stu-id="c8d57-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="c8d57-121">有关详细信息，请参阅[嵌套架构元素之间的映射隐式关系](map-implicit-relations-between-nested-schema-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="c8d57-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="c8d57-122">该架构还指定键约束和 keyref 约束。</span><span class="sxs-lookup"><span data-stu-id="c8d57-122">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="c8d57-123">XML 架构映射过程产生的**数据集**包括两个表：</span><span class="sxs-lookup"><span data-stu-id="c8d57-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="c8d57-124">**DataSet**还包括两个关系（一个基于**msdata：关系**注释，另一个基于键和键ref约束）和各种约束。</span><span class="sxs-lookup"><span data-stu-id="c8d57-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="c8d57-125">以下示例将显示这些关系和约束。</span><span class="sxs-lookup"><span data-stu-id="c8d57-125">The following example shows the relations and constraints.</span></span>  
  
```text
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
  
 <span data-ttu-id="c8d57-126">如果引用嵌套表的 keyref 约束包含**msdata：IsNested_"true"** 注释 **，DataSet**将创建基于 keyref 约束和相关唯一/键约束的单个嵌套关系。</span><span class="sxs-lookup"><span data-stu-id="c8d57-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d57-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8d57-127">See also</span></span>

- [<span data-ttu-id="c8d57-128">从 XML 架构派生数据集关系结构 (XSD)</span><span class="sxs-lookup"><span data-stu-id="c8d57-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="c8d57-129">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="c8d57-129">ADO.NET Overview</span></span>](../ado-net-overview.md)

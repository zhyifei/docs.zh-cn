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
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="7e4f9-102">将 keyref XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="7e4f9-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="7e4f9-103">**keyref**元素允许您在文档中的元素之间建立链接。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="7e4f9-104">它类似于关系数据库中的外键关系。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="7e4f9-105">如果架构指定**keyref**元素，则在架构映射过程中将元素转换为 对<xref:System.Data.DataSet>表中的列的相应外键约束。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="7e4f9-106">默认情况下 **，keyref**元素还会生成一个关系，该关系在关系上指定了**父表**、**子表**、**父列**和**子列**属性。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="7e4f9-107">下表概述了可在**keyref**元素中指定的**msdata**属性。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="7e4f9-108">属性名称</span><span class="sxs-lookup"><span data-stu-id="7e4f9-108">Attribute name</span></span>|<span data-ttu-id="7e4f9-109">说明</span><span class="sxs-lookup"><span data-stu-id="7e4f9-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7e4f9-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="7e4f9-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="7e4f9-111">如果在架构中的**keyref**元素上指定了 **"约束唯一""true"，** 则将创建约束，但不创建任何关系。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="7e4f9-112">如果未指定此属性（或设置为**False），** 则约束和关系都在**DataSet 中**创建。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="7e4f9-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="7e4f9-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="7e4f9-114">如果指定了 **"约束名称"** 属性，则其值将用作约束的名称。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="7e4f9-115">否则，架构中**keyref**元素**的名称**属性在**DataSet**中提供约束名称。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="7e4f9-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="7e4f9-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="7e4f9-117">如果在架构中的**keyref**元素中指定**了 UpdateRule**属性，则其值将分配给**DataSet**中的**UpdateRule**约束属性。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="7e4f9-118">否则 **，UpdateRule**属性将设置为**级联**。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="7e4f9-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="7e4f9-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="7e4f9-120">如果在架构中的**keyref**元素中指定**了 DeleteRule**属性，则其值将分配给**DataSet**中的**DeleteRule**约束属性。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="7e4f9-121">否则 **，DeleteRule**属性将设置为**级联**。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="7e4f9-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="7e4f9-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="7e4f9-123">如果在架构中的**keyref**元素中指定了**AcceptRejectRule 属性**，则其值将分配给**DataSet**中的**AcceptRejectRule**约束属性。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="7e4f9-124">否则，"**接受拒绝规则"** 属性将设置为 **"无**"。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="7e4f9-125">下面的示例包含一个架构，该架构指定**Order**元素的**OrderNumber**子元素和**OrderDetail**元素的**OrderNo**子元素之间的**键**和**键 ref**关系。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="7e4f9-126">在此示例中，"**订单详细信息"** 元素的**OrderNumber**子元素引用**订单**元素的 **"订单无**"键子元素。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="7e4f9-127">XML 架构定义语言 （XSD） 架构映射过程生成具有两个表的以下**DataSet：**</span><span class="sxs-lookup"><span data-stu-id="7e4f9-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="7e4f9-128">此外，**数据集**定义以下约束：</span><span class="sxs-lookup"><span data-stu-id="7e4f9-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="7e4f9-129">**订单**表上的唯一约束。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-129">A unique constraint on the **Order** table.</span></span>  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="7e4f9-130">**订单**和**订单详细信息**表之间的关系。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="7e4f9-131">**嵌套**属性设置为**False，** 因为两个元素未嵌套在架构中。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
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
  
- <span data-ttu-id="7e4f9-132">**"订单详细信息**"表上的外键约束。</span><span class="sxs-lookup"><span data-stu-id="7e4f9-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7e4f9-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e4f9-133">See also</span></span>

- [<span data-ttu-id="7e4f9-134">将 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="7e4f9-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="7e4f9-135">从 XML 架构生成数据集关系 (XSD)</span><span class="sxs-lookup"><span data-stu-id="7e4f9-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="7e4f9-136">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="7e4f9-136">ADO.NET Overview</span></span>](../ado-net-overview.md)

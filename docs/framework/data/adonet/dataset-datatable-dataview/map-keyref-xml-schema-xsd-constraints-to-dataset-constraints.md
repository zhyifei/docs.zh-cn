---
title: 将 keyref XML 架构 (XSD) 约束映射到数据集约束
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 86bc1961fb23b0b2f98a2849eaabd4eecd65cd64
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43777543"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="2b5b4-102">将 keyref XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="2b5b4-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="2b5b4-103">**Keyref**元素可用于在文档内的元素之间建立链接。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="2b5b4-104">它类似于关系数据库中的外键关系。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="2b5b4-105">如果指定了架构**keyref**元素，元素转换到的表中的列上的相应外键约束在架构映射过程<xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="2b5b4-106">默认情况下**keyref**元素还会生成关系，使用**ParentTable**， **ChildTable**， **ParentColumn**，和**ChildColumn**对关系指定的属性。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="2b5b4-107">下表概括**msdata**您可以在指定的属性**keyref**元素。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="2b5b4-108">特性名</span><span class="sxs-lookup"><span data-stu-id="2b5b4-108">Attribute name</span></span>|<span data-ttu-id="2b5b4-109">描述</span><span class="sxs-lookup"><span data-stu-id="2b5b4-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="2b5b4-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="2b5b4-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="2b5b4-111">如果**ConstraintOnly ="true"** 上指定**keyref**架构中的元素，创建一个约束，但不创建任何关系。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="2b5b4-112">如果未指定此属性 (或将设置为**False**)，在创建约束和关系**数据集**。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="2b5b4-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="2b5b4-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="2b5b4-114">如果**ConstraintName**指定属性，其值将用作约束的名称。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="2b5b4-115">否则为**名称**的属性**keyref**架构中的元素提供中的约束名称**数据集**。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="2b5b4-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="2b5b4-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="2b5b4-117">如果**UpdateRule**中指定特性**keyref**架构中的元素，其值分配给**UpdateRule**约束属性中的**数据集**。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="2b5b4-118">否则为**UpdateRule**属性设置为**Cascade**。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="2b5b4-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="2b5b4-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="2b5b4-120">如果**DeleteRule**中指定特性**keyref**架构中的元素，其值分配给**DeleteRule**约束属性中的**数据集**。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="2b5b4-121">否则为**DeleteRule**属性设置为**Cascade**。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="2b5b4-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="2b5b4-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="2b5b4-123">如果**AcceptRejectRule**中指定特性**keyref**架构中的元素，其值分配给**AcceptRejectRule** 中的约束属性**数据集**。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="2b5b4-124">否则为**AcceptRejectRule**属性设置为**None**。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="2b5b4-125">下面的示例包含一个架构，指定**键**并**keyref**之间的关系**OrderNumber**的子元素**顺序**元素和**OrderNo**的子元素**OrderDetail**元素。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="2b5b4-126">在示例中， **OrderNumber**的子元素**OrderDetail**元素是指**OrderNo**键子元素**顺序**元素。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="2b5b4-127">XML 架构定义语言 (XSD) 架构映射过程会生成以下**数据集**这两个表：</span><span class="sxs-lookup"><span data-stu-id="2b5b4-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="2b5b4-128">此外，**数据集**定义以下约束：</span><span class="sxs-lookup"><span data-stu-id="2b5b4-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
-   <span data-ttu-id="2b5b4-129">Unique 约束**顺序**表。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-129">A unique constraint on the **Order** table.</span></span>  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   <span data-ttu-id="2b5b4-130">之间的关系**顺序**并**OrderDetail**表。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="2b5b4-131">**嵌套**属性设置为**False**因为两个元素未嵌套在架构中。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
    ```  
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
-   <span data-ttu-id="2b5b4-132">上的外键约束**OrderDetail**表。</span><span class="sxs-lookup"><span data-stu-id="2b5b4-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2b5b4-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b5b4-133">See Also</span></span>  
 [<span data-ttu-id="2b5b4-134">将 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="2b5b4-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="2b5b4-135">从 XML 架构生成数据集关系 (XSD)</span><span class="sxs-lookup"><span data-stu-id="2b5b4-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="2b5b4-136">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="2b5b4-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

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
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="effb2-102">从 XML 架构生成数据集关系 (XSD)</span><span class="sxs-lookup"><span data-stu-id="effb2-102">Generating DataSet Relations from XML Schema (XSD)</span></span>
<span data-ttu-id="effb2-103">在 <xref:System.Data.DataSet> 中，可通过创建父子关系来形成两个或更多个列之间的关联。</span><span class="sxs-lookup"><span data-stu-id="effb2-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="effb2-104">在 XML 架构定义语言 （XSD） 架构中，有三种方法可以表示**DataSet**关系：</span><span class="sxs-lookup"><span data-stu-id="effb2-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
- <span data-ttu-id="effb2-105">指定嵌套复杂类型。</span><span class="sxs-lookup"><span data-stu-id="effb2-105">Specify nested complex types.</span></span>  
  
- <span data-ttu-id="effb2-106">使用**msdata：关系**注释。</span><span class="sxs-lookup"><span data-stu-id="effb2-106">Use the **msdata:Relationship** annotation.</span></span>  
  
- <span data-ttu-id="effb2-107">指定一个没有 msdata**的 xs：keyref：\*\*\*\*仅约束**注释。</span><span class="sxs-lookup"><span data-stu-id="effb2-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="effb2-108">嵌套的复杂类型</span><span class="sxs-lookup"><span data-stu-id="effb2-108">Nested Complex Types</span></span>  
 <span data-ttu-id="effb2-109">架构中的嵌套复杂类型定义指示元素的父子关系。</span><span class="sxs-lookup"><span data-stu-id="effb2-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="effb2-110">以下 XML 架构片段显示**OrderDetail**是**Order**元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="effb2-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="effb2-111">XML 架构映射过程在**DataSet**中创建对应于架构中嵌套复杂类型的表。</span><span class="sxs-lookup"><span data-stu-id="effb2-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="effb2-112">它还创建其他列，这些列用作生成的表**-** 的父子列。</span><span class="sxs-lookup"><span data-stu-id="effb2-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="effb2-113">请注意，这些父**-** 子列指定关系，这与指定主键/外键约束不同。</span><span class="sxs-lookup"><span data-stu-id="effb2-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="effb2-114">msdata:Relationship 批注</span><span class="sxs-lookup"><span data-stu-id="effb2-114">msdata:Relationship Annotation</span></span>  
 <span data-ttu-id="effb2-115">**msdata：关系**注释允许您显式指定架构中未嵌套的元素之间的父子关系。</span><span class="sxs-lookup"><span data-stu-id="effb2-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="effb2-116">下面的示例显示了**关系**元素的结构。</span><span class="sxs-lookup"><span data-stu-id="effb2-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 <span data-ttu-id="effb2-117">**msdata：关系**注释的属性标识父子关系中涉及的元素，以及关系中涉及的**父键**和**子键**元素和属性。</span><span class="sxs-lookup"><span data-stu-id="effb2-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="effb2-118">映射过程使用此信息在**DataSet**中生成表，并在这些表之间创建主键/外键关系。</span><span class="sxs-lookup"><span data-stu-id="effb2-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="effb2-119">例如，以下架构片段指定同一级别的 **"订单"** 和"**订单详细信息"** 元素（未嵌套）。</span><span class="sxs-lookup"><span data-stu-id="effb2-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="effb2-120">架构指定**msdata：关系**注释，它指定这两个元素之间的父子关系。</span><span class="sxs-lookup"><span data-stu-id="effb2-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="effb2-121">在这种情况下，必须使用**msdata：关系**注释指定显式关系。</span><span class="sxs-lookup"><span data-stu-id="effb2-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
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
  
 <span data-ttu-id="effb2-122">映射过程使用 **"关系"** 元素在 **"订单**"表中的**OrderNumber**列和**DataSet**中的 **"订单详细信息**"表中的 **"订单无"** 列之间创建父子关系。</span><span class="sxs-lookup"><span data-stu-id="effb2-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="effb2-123">映射进程仅指定关系；与关系数据库中的主键/外键约束不同，它并不会自动为这些列中的值指定任何约束。</span><span class="sxs-lookup"><span data-stu-id="effb2-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="effb2-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="effb2-124">In This Section</span></span>  
 [<span data-ttu-id="effb2-125">映射嵌套架构元素之间的隐式关系</span><span class="sxs-lookup"><span data-stu-id="effb2-125">Map Implicit Relations Between Nested Schema Elements</span></span>](map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="effb2-126">描述在 XML 架构中遇到嵌套元素时在**DataSet**中隐式创建的约束和关系。</span><span class="sxs-lookup"><span data-stu-id="effb2-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="effb2-127">映射为嵌套元素指定的关系</span><span class="sxs-lookup"><span data-stu-id="effb2-127">Map Relations Specified for Nested Elements</span></span>](map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="effb2-128">描述如何在 XML 架构中为嵌套元素在**DataSet**中显式设置关系。</span><span class="sxs-lookup"><span data-stu-id="effb2-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="effb2-129">指定无嵌套元素之间的关系</span><span class="sxs-lookup"><span data-stu-id="effb2-129">Specify Relations Between Elements with No Nesting</span></span>](specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="effb2-130">描述如何在未嵌套的 XML 架构元素之间的**DataSet**中创建关系。</span><span class="sxs-lookup"><span data-stu-id="effb2-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="effb2-131">相关章节</span><span class="sxs-lookup"><span data-stu-id="effb2-131">Related Sections</span></span>  
 [<span data-ttu-id="effb2-132">从 XML 架构派生数据集关系结构 (XSD)</span><span class="sxs-lookup"><span data-stu-id="effb2-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="effb2-133">描述从 XML 架构定义语言 （XSD） 架构创建的**DataSet**的关系结构或架构。</span><span class="sxs-lookup"><span data-stu-id="effb2-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="effb2-134">将 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="effb2-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="effb2-135">描述用于在**DataSet**中创建唯一和外键约束的 XML 架构元素。</span><span class="sxs-lookup"><span data-stu-id="effb2-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="effb2-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="effb2-136">See also</span></span>

- [<span data-ttu-id="effb2-137">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="effb2-137">ADO.NET Overview</span></span>](../ado-net-overview.md)

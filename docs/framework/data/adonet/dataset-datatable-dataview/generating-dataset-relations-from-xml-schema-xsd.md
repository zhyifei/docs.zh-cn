---
title: 从 XML 架构生成数据集关系 (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: fdf22c311ef7b4267f4a4da8566e4ea59504b103
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="ff902-102">从 XML 架构生成数据集关系 (XSD)</span><span class="sxs-lookup"><span data-stu-id="ff902-102">Generating DataSet Relations from XML Schema (XSD)</span></span>
<span data-ttu-id="ff902-103">在 <xref:System.Data.DataSet> 中，可通过创建父子关系来形成两个或更多个列之间的关联。</span><span class="sxs-lookup"><span data-stu-id="ff902-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="ff902-104">有三种方法来表示**数据集**XML 架构定义语言 (XSD) 架构中的关系：</span><span class="sxs-lookup"><span data-stu-id="ff902-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
-   <span data-ttu-id="ff902-105">指定嵌套复杂类型。</span><span class="sxs-lookup"><span data-stu-id="ff902-105">Specify nested complex types.</span></span>  
  
-   <span data-ttu-id="ff902-106">使用**msdata: relationship**批注。</span><span class="sxs-lookup"><span data-stu-id="ff902-106">Use the **msdata:Relationship** annotation.</span></span>  
  
-   <span data-ttu-id="ff902-107">指定**xs:keyref**而无需**msdata:ConstraintOnly**批注。</span><span class="sxs-lookup"><span data-stu-id="ff902-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="ff902-108">嵌套的复杂类型</span><span class="sxs-lookup"><span data-stu-id="ff902-108">Nested Complex Types</span></span>  
 <span data-ttu-id="ff902-109">架构中的嵌套复杂类型定义指示元素的父子关系。</span><span class="sxs-lookup"><span data-stu-id="ff902-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="ff902-110">下面的 XML 架构片断显示**OrderDetail**是的子元素**顺序**元素。</span><span class="sxs-lookup"><span data-stu-id="ff902-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="ff902-111">在 XML 架构映射过程创建中的表**数据集**对应于架构中嵌套的复杂类型。</span><span class="sxs-lookup"><span data-stu-id="ff902-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="ff902-112">它还将创建用作父的其他列**-** 所生成的表的子列。</span><span class="sxs-lookup"><span data-stu-id="ff902-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="ff902-113">请注意，这些父子**-** 子列指定关系，这是不与指定主键/外键约束相同。</span><span class="sxs-lookup"><span data-stu-id="ff902-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="ff902-114">msdata:Relationship 批注</span><span class="sxs-lookup"><span data-stu-id="ff902-114">msdata:Relationship Annotation</span></span>  
 <span data-ttu-id="ff902-115">**Msdata: relationship**批注可以显式指定架构中不嵌套的元素之间的父-子关系。</span><span class="sxs-lookup"><span data-stu-id="ff902-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="ff902-116">下面的示例演示的结构**关系**元素。</span><span class="sxs-lookup"><span data-stu-id="ff902-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 <span data-ttu-id="ff902-117">属性**msdata: relationship**批注标识为父-子关系中所涉及的元素**parentkey**和**childkey**元素和关系所涉及的属性。</span><span class="sxs-lookup"><span data-stu-id="ff902-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="ff902-118">映射过程使用此信息来生成中的表**数据集**并创建这些表之间主键/外的键关系。</span><span class="sxs-lookup"><span data-stu-id="ff902-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="ff902-119">例如，以下架构片断指定**顺序**和**OrderDetail**同一级别的元素 （不嵌套）。</span><span class="sxs-lookup"><span data-stu-id="ff902-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="ff902-120">该架构指定**msdata: relationship**批注，指定这两个元素之间的父-子关系。</span><span class="sxs-lookup"><span data-stu-id="ff902-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="ff902-121">在这种情况下，显式关系必须指定使用**msdata: relationship**批注。</span><span class="sxs-lookup"><span data-stu-id="ff902-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
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
  
 <span data-ttu-id="ff902-122">映射进程使用**关系**元素以创建之间的父-子关系**OrderNumber**中的列**顺序**表和**OrderNo**中的列**OrderDetail**表中**数据集**。</span><span class="sxs-lookup"><span data-stu-id="ff902-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="ff902-123">映射进程仅指定关系；与关系数据库中的主键/外键约束不同，它并不会自动为这些列中的值指定任何约束。</span><span class="sxs-lookup"><span data-stu-id="ff902-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="ff902-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="ff902-124">In This Section</span></span>  
 [<span data-ttu-id="ff902-125">映射嵌套架构元素之间的隐式关系</span><span class="sxs-lookup"><span data-stu-id="ff902-125">Map Implicit Relations Between Nested Schema Elements</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="ff902-126">描述的约束和关系在中隐式创建**数据集**XML 架构中遇到嵌套的元素时。</span><span class="sxs-lookup"><span data-stu-id="ff902-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="ff902-127">映射为嵌套元素指定的关系</span><span class="sxs-lookup"><span data-stu-id="ff902-127">Map Relations Specified for Nested Elements</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="ff902-128">描述如何在中显式设置关系**数据集**XML 架构中的嵌套元素。</span><span class="sxs-lookup"><span data-stu-id="ff902-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="ff902-129">指定无嵌套元素之间的关系</span><span class="sxs-lookup"><span data-stu-id="ff902-129">Specify Relations Between Elements with No Nesting</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="ff902-130">描述如何创建中的关系**数据集**之间不嵌套的 XML 架构元素。</span><span class="sxs-lookup"><span data-stu-id="ff902-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="ff902-131">相关章节</span><span class="sxs-lookup"><span data-stu-id="ff902-131">Related Sections</span></span>  
 [<span data-ttu-id="ff902-132">从 XML 架构派生数据集关系结构 (XSD)</span><span class="sxs-lookup"><span data-stu-id="ff902-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="ff902-133">描述的关系结构，即架构，**数据集**从 XML 架构定义语言 (XSD) 架构创建。</span><span class="sxs-lookup"><span data-stu-id="ff902-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="ff902-134">将 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="ff902-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="ff902-135">描述用于创建唯一约束和外键约束中的 XML 架构元素**数据集**。</span><span class="sxs-lookup"><span data-stu-id="ff902-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff902-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff902-136">See Also</span></span>  
 [<span data-ttu-id="ff902-137">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="ff902-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

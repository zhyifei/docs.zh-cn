---
title: "将唯一 XML 架构 (XSD) 约束映射到数据集约束"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 5276697ebdc065965d970afc4ac2ef6be61c8f20
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="6d0cb-102">将唯一 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="6d0cb-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="6d0cb-103">在 XML 架构定义语言 (XSD) 架构中，**唯一**元素指定的元素或属性的唯一性约束。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="6d0cb-104">在将 XML 架构转换为关系架构的过程中，对 XML 架构中的元素或属性指定的唯一约束将映射到所生成的相应 <xref:System.Data.DataTable> 中的 <xref:System.Data.DataSet> 中的唯一约束。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="6d0cb-105">下表概括了**msdata**属性可以在中指定**唯一**元素。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="6d0cb-106">特性名</span><span class="sxs-lookup"><span data-stu-id="6d0cb-106">Attribute name</span></span>|<span data-ttu-id="6d0cb-107">描述</span><span class="sxs-lookup"><span data-stu-id="6d0cb-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6d0cb-108">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="6d0cb-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="6d0cb-109">如果指定了该属性，它的值将用作约束名。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="6d0cb-110">否则为**名称**属性会提供约束名的值。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="6d0cb-111">**msdata: primarykey**</span><span class="sxs-lookup"><span data-stu-id="6d0cb-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="6d0cb-112">如果`PrimaryKey="true"`位于**唯一**元素，与创建唯一约束**IsPrimaryKey**属性设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="6d0cb-113">下面的示例显示使用一个 XML 架构**唯一**元素指定的唯一性约束。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
```xml  
<xs:schema id="SampleDataSet"   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"   
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"   
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="6d0cb-114">**唯一**架构中的元素指定所有**客户**实例的文档中的元素的值**CustomerID**必须是唯一的子元素。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="6d0cb-115">在构建**数据集**，映射过程读取此架构，并生成下表：</span><span class="sxs-lookup"><span data-stu-id="6d0cb-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="6d0cb-116">映射过程还创建唯一约束上**CustomerID**列，如下所示**数据集**。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="6d0cb-117">（为简便起见，只显示相关属性。）</span><span class="sxs-lookup"><span data-stu-id="6d0cb-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID   
      IsPrimaryKey: False  
```  
  
 <span data-ttu-id="6d0cb-118">在**数据集**生成， **IsPrimaryKey**属性设置为**False**对于唯一约束。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="6d0cb-119">**唯一**列属性指示**CustomerID**列的值必须是唯一的 (但它们可以是空引用，为指定的**AllowDBNull**列的属性）。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="6d0cb-120">如果你修改架构并将设置可选**msdata: primarykey**属性值到**True**，在表上创建唯一约束。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="6d0cb-121">**AllowDBNull**列属性设置为**False**，和**IsPrimaryKey**属性设置为的约束**True**，从而使**CustomerID**列主键列。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="6d0cb-122">您可以对 XML 架构中元素或属性的组合指定唯一约束。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="6d0cb-123">下面的示例演示如何指定的组合**CustomerID**和**CompanyName**值必须是唯一的所有**客户**在任何情况下，通过添加另一个**xs:field**架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 <span data-ttu-id="6d0cb-124">这是创建在随后出现的限制**数据集**。</span><span class="sxs-lookup"><span data-stu-id="6d0cb-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d0cb-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d0cb-125">See Also</span></span>  
 [<span data-ttu-id="6d0cb-126">将 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="6d0cb-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="6d0cb-127">从 XML 架构生成数据集关系 (XSD)</span><span class="sxs-lookup"><span data-stu-id="6d0cb-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="6d0cb-128">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="6d0cb-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: 将唯一 XML 架构 (XSD) 约束映射到数据集约束
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 231f23ccf47f60b902fdd5c66b63fe1a750445f9
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203414"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="791a8-102">将唯一 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="791a8-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="791a8-103">在 XML 架构定义语言 (XSD) 架构中, **unique**元素指定元素或属性的唯一性约束。</span><span class="sxs-lookup"><span data-stu-id="791a8-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="791a8-104">在将 XML 架构转换为关系架构的过程中，对 XML 架构中的元素或属性指定的唯一约束将映射到所生成的相应 <xref:System.Data.DataTable> 中的 <xref:System.Data.DataSet> 中的唯一约束。</span><span class="sxs-lookup"><span data-stu-id="791a8-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="791a8-105">下表概述了可在**unique**元素中指定的**msdata**属性。</span><span class="sxs-lookup"><span data-stu-id="791a8-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="791a8-106">特性名</span><span class="sxs-lookup"><span data-stu-id="791a8-106">Attribute name</span></span>|<span data-ttu-id="791a8-107">描述</span><span class="sxs-lookup"><span data-stu-id="791a8-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="791a8-108">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="791a8-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="791a8-109">如果指定了该属性，它的值将用作约束名。</span><span class="sxs-lookup"><span data-stu-id="791a8-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="791a8-110">否则, **name**属性提供约束名称的值。</span><span class="sxs-lookup"><span data-stu-id="791a8-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="791a8-111">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="791a8-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="791a8-112">如果`PrimaryKey="true"`在**unique**元素中存在, 则将创建一个唯一约束, 并将**IsPrimaryKey**属性设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="791a8-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="791a8-113">下面的示例演示一个使用**unique**元素指定唯一性约束的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="791a8-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
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
  
 <span data-ttu-id="791a8-114">架构中的**unique**元素指定对于文档实例中的所有**Customers**元素, **CustomerID**子元素的值必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="791a8-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="791a8-115">在生成**数据集**时, 映射过程将读取此架构并生成下表:</span><span class="sxs-lookup"><span data-stu-id="791a8-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="791a8-116">映射过程还会在**CustomerID**列上创建唯一约束, 如下面的**数据集**中所示。</span><span class="sxs-lookup"><span data-stu-id="791a8-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="791a8-117">（为简便起见，只显示相关属性。）</span><span class="sxs-lookup"><span data-stu-id="791a8-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
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
  
 <span data-ttu-id="791a8-118">在生成的**数据集中**, unique 约束的**IsPrimaryKey**属性设置为**False** 。</span><span class="sxs-lookup"><span data-stu-id="791a8-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="791a8-119">列的**unique**属性指示**CustomerID**列值必须唯一 (但可以是空引用, 如列的**AllowDBNull**属性所指定)。</span><span class="sxs-lookup"><span data-stu-id="791a8-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="791a8-120">如果修改架构并将可选的**msdata: PrimaryKey**特性值设置为**True**, 则会在表中创建 unique 约束。</span><span class="sxs-lookup"><span data-stu-id="791a8-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="791a8-121">**AllowDBNull**列属性设置为**False**, 并且约束的**IsPrimaryKey**属性设置为**True**, 从而使**CustomerID**列成为主键列。</span><span class="sxs-lookup"><span data-stu-id="791a8-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="791a8-122">您可以对 XML 架构中元素或属性的组合指定唯一约束。</span><span class="sxs-lookup"><span data-stu-id="791a8-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="791a8-123">下面的示例演示了如何通过在架构中添加另一个 **xs: field**元素, 为任何实例中的所有**客户**指定**CustomerID**和值的组合必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="791a8-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 <span data-ttu-id="791a8-124">这是在生成的**数据集中**创建的约束。</span><span class="sxs-lookup"><span data-stu-id="791a8-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="791a8-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="791a8-125">See also</span></span>

- [<span data-ttu-id="791a8-126">将 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="791a8-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="791a8-127">从 XML 架构生成数据集关系 (XSD)</span><span class="sxs-lookup"><span data-stu-id="791a8-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="791a8-128">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="791a8-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

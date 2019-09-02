---
title: 将关键 XML 架构 (XSD) 约束映射到数据集约束
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: d6fcdae77c2f2ac07ea5cd16baf07cd5de36d25b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203465"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="fb3a8-102">将关键 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="fb3a8-102">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="fb3a8-103">在架构中, 可以使用**key**元素对元素或属性指定键约束。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-103">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="fb3a8-104">对其指定键约束的元素或属性必须在任何架构实例中都具有唯一值，并且不能具有空值。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-104">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="fb3a8-105">除了对其定义键约束的列不能具有空值之外，键约束与唯一约束类似。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-105">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="fb3a8-106">下表概述了可以在**key**元素中指定的**msdata**属性。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-106">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="fb3a8-107">特性名</span><span class="sxs-lookup"><span data-stu-id="fb3a8-107">Attribute name</span></span>|<span data-ttu-id="fb3a8-108">描述</span><span class="sxs-lookup"><span data-stu-id="fb3a8-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="fb3a8-109">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="fb3a8-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="fb3a8-110">如果指定了该属性，它的值将用作约束名。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="fb3a8-111">否则, **name**属性提供约束名称的值。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="fb3a8-112">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="fb3a8-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="fb3a8-113">如果`PrimaryKey="true"`存在, 则**IsPrimaryKey**约束属性设置为**true**, 从而使其成为主键。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-113">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="fb3a8-114">**AllowDBNull**列属性设置为**false**, 因为主键不能具有 null 值。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-114">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="fb3a8-115">在转换指定了键约束的架构时, 映射过程会对约束中的每一列将**AllowDBNull** column 属性设置为**false**的表创建 unique 约束。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-115">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="fb3a8-116">除非已对**key**元素指定`msdata:PrimaryKey="true"` , 否则 unique 约束的**IsPrimaryKey**属性也设置为**false** 。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-116">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="fb3a8-117">它与 `PrimaryKey="true"` 的架构中的唯一约束相同。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-117">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="fb3a8-118">在下面的架构示例中, **key**元素指定了**CustomerID**元素的键约束。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-118">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>   
```  
  
 <span data-ttu-id="fb3a8-119">**Key**元素指定**Customers**元素的**CustomerID**子元素的值必须具有唯一值, 且不能具有 null 值。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-119">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="fb3a8-120">在转换 XML 架构定义语言 (XSD) 架构时，映射过程将创建下表：</span><span class="sxs-lookup"><span data-stu-id="fb3a8-120">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="fb3a8-121">XML 架构映射还会在**CustomerID**列上创建<xref:System.Data.DataSet> **UniqueConstraint** , 如下所示。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-121">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="fb3a8-122">（为简便起见，只显示相关属性。）</span><span class="sxs-lookup"><span data-stu-id="fb3a8-122">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID   
      IsPrimaryKey: True  
```  
  
 <span data-ttu-id="fb3a8-123">在生成的**数据集中**, **UniqueConstraint**的**IsPrimaryKey**属性设置为**true** , 因为架构指定`msdata:PrimaryKey="true"`了**key**元素中的。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-123">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="fb3a8-124">**DataSet**中**UniqueConstraint**的**ConstraintName**属性的值是在架构的**Key**元素中指定的**msdata: ConstraintName**属性的值。</span><span class="sxs-lookup"><span data-stu-id="fb3a8-124">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb3a8-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb3a8-125">See also</span></span>

- [<span data-ttu-id="fb3a8-126">将 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="fb3a8-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="fb3a8-127">从 XML 架构生成数据集关系 (XSD)</span><span class="sxs-lookup"><span data-stu-id="fb3a8-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="fb3a8-128">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="fb3a8-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

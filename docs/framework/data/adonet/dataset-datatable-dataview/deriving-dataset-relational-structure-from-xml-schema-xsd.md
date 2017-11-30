---
title: "从 XML 架构派生数据集关系结构 (XSD)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0aae23c295401d4b9565c35d4d47c5ab913029d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="ad1e6-102">从 XML 架构派生数据集关系结构 (XSD)</span><span class="sxs-lookup"><span data-stu-id="ad1e6-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="ad1e6-103">本节将概述如何从 XML 架构定义语言 (XSD) 架构文档生成 `DataSet` 的关系架构。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="ad1e6-104">一般情况下，为每个`complexType`的架构元素的子元素，在生成一个表`DataSet`。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="ad1e6-105">表结构取决于复杂类型的定义。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="ad1e6-106">在中创建表`DataSet`架构中的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="ad1e6-107">但是，仅为创建了表的顶级`complexType`元素时`complexType`元素嵌套在另一个`complexType`元素，在这种情况下嵌套`complexType`元素映射到`DataTable`内`DataSet`。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="ad1e6-108">有关 XSD 的更多信息，请参阅万维网联合会 (W3C) XML 架构第 0 部分： 入门建议，XML 架构第 1 部分： 结构建议和 XML 架构第 2 部分： 数据类型建议，位于[http://www.w3.org/](http://www.w3.org/TR/)。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-108">For more information about the XSD, see the World Wide Web Consortium (W3C) XML Schema Part 0: Primer Recommendation, the XML Schema Part 1: Structures Recommendation, and the XML Schema Part 2: Datatypes Recommendation, located at [http://www.w3.org/](http://www.w3.org/TR/).</span></span>  
  
 <span data-ttu-id="ad1e6-109">下面的示例演示一个 XML 架构其中`customers`是的子元素`MyDataSet`元素，它是**数据集**元素。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="ad1e6-110">在上例中，`customers` 元素为复杂类型元素。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="ad1e6-111">因此，将对复杂类型定义进行分析，而映射过程会创建下表。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 <span data-ttu-id="ad1e6-112">该表中各列的数据类型是从所指定的相应元素或属性的 XML 架构类型派生的。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad1e6-113">如果元素`customers`是简单的 XML 架构数据类型的如**整数**，不生成任何表。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="ad1e6-114">表仅为属于复杂类型的顶级元素而创建。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="ad1e6-115">在下面的 XML 架构中，**架构**元素具有两个元素子级，`InStateCustomers`和`OutOfStateCustomers`。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="ad1e6-116">`InStateCustomers` 和 `OutOfStateCustomers` 两个子元素都是复杂类型元素 (`customerType`)。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="ad1e6-117">因此，映射过程生成中的以下两个相同表格`DataSet`。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="ad1e6-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="ad1e6-118">In This Section</span></span>  
 [<span data-ttu-id="ad1e6-119">将 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="ad1e6-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="ad1e6-120">描述用于创建唯一约束和外键约束中的 XML 架构元素`DataSet`。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="ad1e6-121">从 XML 架构 (XSD) 生成数据集关系</span><span class="sxs-lookup"><span data-stu-id="ad1e6-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="ad1e6-122">描述用于创建表中各列之间的关系的 XML 架构元素`DataSet`。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="ad1e6-123">XML 架构约束和关系</span><span class="sxs-lookup"><span data-stu-id="ad1e6-123">XML Schema Constraints and Relationships</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="ad1e6-124">描述如何关系创建隐式使用 XML 架构元素创建中的约束时`DataSet`。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ad1e6-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="ad1e6-125">Related Sections</span></span>  
 [<span data-ttu-id="ad1e6-126">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="ad1e6-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="ad1e6-127">介绍如何加载和保持的关系结构和中的数据`DataSet`以 XML 数据形式。</span><span class="sxs-lookup"><span data-stu-id="ad1e6-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad1e6-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad1e6-128">See Also</span></span>  
 [<span data-ttu-id="ad1e6-129">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="ad1e6-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

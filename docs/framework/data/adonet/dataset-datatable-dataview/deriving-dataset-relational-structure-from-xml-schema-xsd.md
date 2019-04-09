---
title: 从 XML 架构派生数据集关系结构 (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 549579fca0179994191987097c12b6085ee91756
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119686"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="55cdb-102">从 XML 架构派生数据集关系结构 (XSD)</span><span class="sxs-lookup"><span data-stu-id="55cdb-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="55cdb-103">本节将概述如何从 XML 架构定义语言 (XSD) 架构文档生成 `DataSet` 的关系架构。</span><span class="sxs-lookup"><span data-stu-id="55cdb-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="55cdb-104">一般情况下，为每个`complexType`架构元素的子元素，将生成一个表中`DataSet`。</span><span class="sxs-lookup"><span data-stu-id="55cdb-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="55cdb-105">表结构取决于复杂类型的定义。</span><span class="sxs-lookup"><span data-stu-id="55cdb-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="55cdb-106">在中创建表`DataSet`架构中的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="55cdb-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="55cdb-107">但是，一个表只能创建为顶级`complexType`元素时`complexType`元素嵌套在另一个`complexType`元素，在这种情况下嵌套`complexType`元素映射到`DataTable`内`DataSet`。</span><span class="sxs-lookup"><span data-stu-id="55cdb-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="55cdb-108">有关 XSD 的详细信息，请参阅 World Wide Web 联合会 (W3C) [XML 架构第 0 部分：入门建议](https://www.w3.org/TR/xmlschema-0/)，则[XML 架构第 1 部分：结构建议](https://www.w3.org/TR/xmlschema-1/)，和[XML 架构第 2 部分：数据类型建议](https://www.w3.org/TR/xmlschema-2/)。</span><span class="sxs-lookup"><span data-stu-id="55cdb-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="55cdb-109">下面的示例演示一个 XML 架构位置`customers`子元素的`MyDataSet`元素，即**数据集**元素。</span><span class="sxs-lookup"><span data-stu-id="55cdb-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
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
  
 <span data-ttu-id="55cdb-110">在上例中，`customers` 元素为复杂类型元素。</span><span class="sxs-lookup"><span data-stu-id="55cdb-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="55cdb-111">因此，将对复杂类型定义进行分析，而映射过程会创建下表。</span><span class="sxs-lookup"><span data-stu-id="55cdb-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 <span data-ttu-id="55cdb-112">该表中各列的数据类型是从所指定的相应元素或属性的 XML 架构类型派生的。</span><span class="sxs-lookup"><span data-stu-id="55cdb-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55cdb-113">如果该元素`customers`是简单的 XML 架构数据类型，如**整数**，不生成任何表。</span><span class="sxs-lookup"><span data-stu-id="55cdb-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="55cdb-114">表仅为属于复杂类型的顶级元素而创建。</span><span class="sxs-lookup"><span data-stu-id="55cdb-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="55cdb-115">在下面的 XML 架构中，**架构**元素具有两个子元素`InStateCustomers`和`OutOfStateCustomers`。</span><span class="sxs-lookup"><span data-stu-id="55cdb-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
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
  
 <span data-ttu-id="55cdb-116">`InStateCustomers` 和 `OutOfStateCustomers` 两个子元素都是复杂类型元素 (`customerType`)。</span><span class="sxs-lookup"><span data-stu-id="55cdb-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="55cdb-117">因此，映射过程生成中的以下两个相同表`DataSet`。</span><span class="sxs-lookup"><span data-stu-id="55cdb-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="55cdb-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="55cdb-118">In This Section</span></span>  
 [<span data-ttu-id="55cdb-119">将关键 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="55cdb-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="55cdb-120">描述用于创建唯一约束和外键约束中的 XML 架构元素`DataSet`。</span><span class="sxs-lookup"><span data-stu-id="55cdb-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="55cdb-121">从 XML 架构生成数据集关系 (XSD)</span><span class="sxs-lookup"><span data-stu-id="55cdb-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="55cdb-122">描述用于创建表中的列之间的关系的 XML 架构元素`DataSet`。</span><span class="sxs-lookup"><span data-stu-id="55cdb-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="55cdb-123">XML 架构约束和关系</span><span class="sxs-lookup"><span data-stu-id="55cdb-123">XML Schema Constraints and Relationships</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="55cdb-124">描述如何关系创建隐式使用 XML 架构元素创建中的约束时`DataSet`。</span><span class="sxs-lookup"><span data-stu-id="55cdb-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="55cdb-125">相关章节</span><span class="sxs-lookup"><span data-stu-id="55cdb-125">Related Sections</span></span>  
 [<span data-ttu-id="55cdb-126">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="55cdb-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="55cdb-127">介绍如何加载和保持关系的结构和中的数据`DataSet`作为 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="55cdb-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55cdb-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="55cdb-128">See also</span></span>

- [<span data-ttu-id="55cdb-129">ADO.NET 托管提供程序和 DataSet 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="55cdb-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

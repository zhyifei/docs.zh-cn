---
title: 将关键 XML 架构 (XSD) 约束映射到数据集约束
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: 0a23e7a7ab6456125559ffd8fa19ffa5eba9335d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="23777-102">将关键 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="23777-102">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="23777-103">XML 架构定义语言 (XSD) 允许对它所定义的元素和属性指定约束。</span><span class="sxs-lookup"><span data-stu-id="23777-103">The XML Schema definition language (XSD) allows constraints to be specified on the elements and attributes it defines.</span></span> <span data-ttu-id="23777-104">映射到关系架构中的 XML 架构时<xref:System.Data.DataSet>，XML 架构约束将映射到上的表和列中的相应关系约束**数据集**。</span><span class="sxs-lookup"><span data-stu-id="23777-104">When mapping an XML Schema to relational schema in a <xref:System.Data.DataSet>, XML Schema constraints are mapped to appropriate relational constraints on the tables and columns within the **DataSet**.</span></span>  
  
 <span data-ttu-id="23777-105">本节讨论以下 XML 架构约束的映射：</span><span class="sxs-lookup"><span data-stu-id="23777-105">This section discusses the mapping of the following XML Schema constraints:</span></span>  
  
-   <span data-ttu-id="23777-106">使用指定的唯一性约束**唯一**元素。</span><span class="sxs-lookup"><span data-stu-id="23777-106">The uniqueness constraint specified using the **unique** element.</span></span>  
  
-   <span data-ttu-id="23777-107">使用指定的键约束**密钥**元素。</span><span class="sxs-lookup"><span data-stu-id="23777-107">The key constraint specified using the **key** element.</span></span>  
  
-   <span data-ttu-id="23777-108">使用指定的 keyref 约束**keyref**元素。</span><span class="sxs-lookup"><span data-stu-id="23777-108">The keyref constraint specified using the **keyref** element.</span></span>  
  
 <span data-ttu-id="23777-109">使用对元素或属性的约束，可以对任何文档实例中元素的值指定特定的限制。</span><span class="sxs-lookup"><span data-stu-id="23777-109">By using a constraint on an element or attribute, you specify certain restrictions on the values of the element in any instance of the document.</span></span> <span data-ttu-id="23777-110">例如上的键约束**CustomerID**的子元素**客户**架构中的元素指示的值**CustomerID**子元素必须是在任何文档实例中，唯一且不允许 null 值。</span><span class="sxs-lookup"><span data-stu-id="23777-110">For example, a key constraint on a **CustomerID** child element of a **Customer** element in the schema indicates that the values of the **CustomerID** child element must be unique in any document instance, and that null values are not allowed.</span></span>  
  
 <span data-ttu-id="23777-111">为了在文档中建立关系，也可以在文档中的元素和属性之间指定约束。</span><span class="sxs-lookup"><span data-stu-id="23777-111">Constraints can also be specified between elements and attributes in a document, in order to establish a relationship within the document.</span></span> <span data-ttu-id="23777-112">key 和 keyref 约束用于在架构中指定文档中的约束，从而生成文档元素和属性之间的关系。</span><span class="sxs-lookup"><span data-stu-id="23777-112">The key and keyref constraints are used in the schema to specify the constraints within the document, resulting in a relationship between document elements and attributes.</span></span>  
  
 <span data-ttu-id="23777-113">映射过程将这些架构约束转换内创建的表上的相应约束为**数据集**。</span><span class="sxs-lookup"><span data-stu-id="23777-113">The mapping process converts these schema constraints into appropriate constraints on the tables created within the **DataSet**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23777-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="23777-114">In This Section</span></span>  
 [<span data-ttu-id="23777-115">将唯一 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="23777-115">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="23777-116">描述用于创建唯一约束中的 XML 架构元素**数据集**。</span><span class="sxs-lookup"><span data-stu-id="23777-116">Describes the XML Schema elements used to create unique constraints in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="23777-117">将关键 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="23777-117">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="23777-118">介绍用于创建键约束 （唯一约束不允许空值） 的 XML 架构元素**数据集**。</span><span class="sxs-lookup"><span data-stu-id="23777-118">Describes the XML Schema elements used to create key constraints (unique constraints where null values are not allowed) in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="23777-119">将 keyref XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="23777-119">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="23777-120">描述用于创建 keyref （外键） 约束中的 XML 架构元素**数据集**。</span><span class="sxs-lookup"><span data-stu-id="23777-120">Describes the XML Schema elements used to create keyref (foreign key) constraints in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="23777-121">相关章节</span><span class="sxs-lookup"><span data-stu-id="23777-121">Related Sections</span></span>  
 [<span data-ttu-id="23777-122">从 XML 架构派生数据集关系结构 (XSD)</span><span class="sxs-lookup"><span data-stu-id="23777-122">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="23777-123">描述的关系结构，即架构，**数据集**从 XSD 架构创建。</span><span class="sxs-lookup"><span data-stu-id="23777-123">Describes the relational structure, or schema, of a **DataSet** that is created from XSD schema.</span></span>  
  
 [<span data-ttu-id="23777-124">从 XML 架构生成数据集关系 (XSD)</span><span class="sxs-lookup"><span data-stu-id="23777-124">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="23777-125">描述用于创建表中各列之间的关系的 XML 架构元素**数据集**。</span><span class="sxs-lookup"><span data-stu-id="23777-125">Describes the XML Schema elements used to create relations between table columns in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23777-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="23777-126">See Also</span></span>  
 [<span data-ttu-id="23777-127">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="23777-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

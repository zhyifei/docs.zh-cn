---
title: 将关键 XML 架构 (XSD) 约束映射到数据集约束
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: c9cd97535a0165b82f0823c1f17f621491d4255c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43534214"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="757c8-102">将关键 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="757c8-102">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="757c8-103">XML 架构定义语言 (XSD) 允许对它所定义的元素和属性指定约束。</span><span class="sxs-lookup"><span data-stu-id="757c8-103">The XML Schema definition language (XSD) allows constraints to be specified on the elements and attributes it defines.</span></span> <span data-ttu-id="757c8-104">映射到关系架构中的 XML 架构时<xref:System.Data.DataSet>，XML 架构约束将映射到上的表和列中的相应关系约束**数据集**。</span><span class="sxs-lookup"><span data-stu-id="757c8-104">When mapping an XML Schema to relational schema in a <xref:System.Data.DataSet>, XML Schema constraints are mapped to appropriate relational constraints on the tables and columns within the **DataSet**.</span></span>  
  
 <span data-ttu-id="757c8-105">本节讨论以下 XML 架构约束的映射：</span><span class="sxs-lookup"><span data-stu-id="757c8-105">This section discusses the mapping of the following XML Schema constraints:</span></span>  
  
-   <span data-ttu-id="757c8-106">使用指定的唯一性约束**唯一**元素。</span><span class="sxs-lookup"><span data-stu-id="757c8-106">The uniqueness constraint specified using the **unique** element.</span></span>  
  
-   <span data-ttu-id="757c8-107">使用指定的键约束**密钥**元素。</span><span class="sxs-lookup"><span data-stu-id="757c8-107">The key constraint specified using the **key** element.</span></span>  
  
-   <span data-ttu-id="757c8-108">使用指定的 keyref 约束**keyref**元素。</span><span class="sxs-lookup"><span data-stu-id="757c8-108">The keyref constraint specified using the **keyref** element.</span></span>  
  
 <span data-ttu-id="757c8-109">使用对元素或属性的约束，可以对任何文档实例中元素的值指定特定的限制。</span><span class="sxs-lookup"><span data-stu-id="757c8-109">By using a constraint on an element or attribute, you specify certain restrictions on the values of the element in any instance of the document.</span></span> <span data-ttu-id="757c8-110">例如上, 一个键约束**CustomerID**的子元素**客户**架构中的元素指示的值**CustomerID**子元素必须为在任何文档实例中唯一，不允许 null 值。</span><span class="sxs-lookup"><span data-stu-id="757c8-110">For example, a key constraint on a **CustomerID** child element of a **Customer** element in the schema indicates that the values of the **CustomerID** child element must be unique in any document instance, and that null values are not allowed.</span></span>  
  
 <span data-ttu-id="757c8-111">为了在文档中建立关系，也可以在文档中的元素和属性之间指定约束。</span><span class="sxs-lookup"><span data-stu-id="757c8-111">Constraints can also be specified between elements and attributes in a document, in order to establish a relationship within the document.</span></span> <span data-ttu-id="757c8-112">key 和 keyref 约束用于在架构中指定文档中的约束，从而生成文档元素和属性之间的关系。</span><span class="sxs-lookup"><span data-stu-id="757c8-112">The key and keyref constraints are used in the schema to specify the constraints within the document, resulting in a relationship between document elements and attributes.</span></span>  
  
 <span data-ttu-id="757c8-113">映射过程将这些架构约束转换中创建的表上的相应约束**数据集**。</span><span class="sxs-lookup"><span data-stu-id="757c8-113">The mapping process converts these schema constraints into appropriate constraints on the tables created within the **DataSet**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="757c8-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="757c8-114">In This Section</span></span>  
 [<span data-ttu-id="757c8-115">将唯一 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="757c8-115">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="757c8-116">描述用于创建唯一约束中的 XML 架构元素**数据集**。</span><span class="sxs-lookup"><span data-stu-id="757c8-116">Describes the XML Schema elements used to create unique constraints in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="757c8-117">将关键 XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="757c8-117">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="757c8-118">描述用于创建键约束 （唯一约束不允许空值） 的 XML 架构元素中**数据集**。</span><span class="sxs-lookup"><span data-stu-id="757c8-118">Describes the XML Schema elements used to create key constraints (unique constraints where null values are not allowed) in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="757c8-119">将 keyref XML 架构 (XSD) 约束映射到数据集约束</span><span class="sxs-lookup"><span data-stu-id="757c8-119">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="757c8-120">描述用于创建 keyref （外键） 约束中的 XML 架构元素**数据集**。</span><span class="sxs-lookup"><span data-stu-id="757c8-120">Describes the XML Schema elements used to create keyref (foreign key) constraints in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="757c8-121">相关章节</span><span class="sxs-lookup"><span data-stu-id="757c8-121">Related Sections</span></span>  
 [<span data-ttu-id="757c8-122">从 XML 架构派生数据集关系结构 (XSD)</span><span class="sxs-lookup"><span data-stu-id="757c8-122">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="757c8-123">描述的关系结构或架构**数据集**创建从 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="757c8-123">Describes the relational structure, or schema, of a **DataSet** that is created from XSD schema.</span></span>  
  
 [<span data-ttu-id="757c8-124">从 XML 架构生成数据集关系 (XSD)</span><span class="sxs-lookup"><span data-stu-id="757c8-124">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="757c8-125">描述用于创建表中的列之间的关系的 XML 架构元素**数据集**。</span><span class="sxs-lookup"><span data-stu-id="757c8-125">Describes the XML Schema elements used to create relations between table columns in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="757c8-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="757c8-126">See Also</span></span>  
 [<span data-ttu-id="757c8-127">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="757c8-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

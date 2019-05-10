---
title: 数据集架构接口过程摘要
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 3c43b834f7a85f43cefd29a1ceba2260145e7d1b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607081"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="744eb-102">数据集架构接口过程摘要</span><span class="sxs-lookup"><span data-stu-id="744eb-102">Summary of the DataSet Schema Inference Process</span></span>
<span data-ttu-id="744eb-103">推断过程首先从 XML 文档中确定将哪些元素推断为表。</span><span class="sxs-lookup"><span data-stu-id="744eb-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="744eb-104">从剩余的 XML 中，推断过程确定这些表的列。</span><span class="sxs-lookup"><span data-stu-id="744eb-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="744eb-105">对于嵌套表，推断过程会生成嵌套的 <xref:System.Data.DataRelation> 和 <xref:System.Data.ForeignKeyConstraint> 对象。</span><span class="sxs-lookup"><span data-stu-id="744eb-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="744eb-106">下面是推断规则的简要概述：</span><span class="sxs-lookup"><span data-stu-id="744eb-106">Following is a brief summary of inference rules:</span></span>  
  
- <span data-ttu-id="744eb-107">具有属性的元素会被推断为表。</span><span class="sxs-lookup"><span data-stu-id="744eb-107">Elements that have attributes are inferred as tables.</span></span>  
  
- <span data-ttu-id="744eb-108">具有子元素的元素会被推断为表。</span><span class="sxs-lookup"><span data-stu-id="744eb-108">Elements that have child elements are inferred as tables.</span></span>  
  
- <span data-ttu-id="744eb-109">重复的元素会被推断为单个表。</span><span class="sxs-lookup"><span data-stu-id="744eb-109">Elements that repeat are inferred as a single table.</span></span>  
  
- <span data-ttu-id="744eb-110">如果文档元素（即根元素）不具有属性和将被推断为列的子元素，则将被推断为 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="744eb-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="744eb-111">否则，文档元素会被推断为表。</span><span class="sxs-lookup"><span data-stu-id="744eb-111">Otherwise, the document element is inferred as a table.</span></span>  
  
- <span data-ttu-id="744eb-112">属性会被推断为列。</span><span class="sxs-lookup"><span data-stu-id="744eb-112">Attributes are inferred as columns.</span></span>  
  
- <span data-ttu-id="744eb-113">不具有属性或子元素且不重复的元素会被推断为列。</span><span class="sxs-lookup"><span data-stu-id="744eb-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
- <span data-ttu-id="744eb-114">元素被推断为嵌套表中其他元素，同样被推断为表，嵌套**DataRelation**在两个表之间创建。</span><span class="sxs-lookup"><span data-stu-id="744eb-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="744eb-115">名为的新的主要密钥列**TableName_Id**添加到这两个表并使用**DataRelation**。</span><span class="sxs-lookup"><span data-stu-id="744eb-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="744eb-116">一个**ForeignKeyConstraint**使用在两个表之间创建**TableName_Id**列。</span><span class="sxs-lookup"><span data-stu-id="744eb-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
- <span data-ttu-id="744eb-117">对于被推断为表和包含文本但没有子元素的元素，新列命名为**TableName_Text**创建的每个元素的文本。</span><span class="sxs-lookup"><span data-stu-id="744eb-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="744eb-118">如果元素被推断为表并包含文本和子元素，则将忽略文本。</span><span class="sxs-lookup"><span data-stu-id="744eb-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="744eb-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="744eb-119">See also</span></span>

- [<span data-ttu-id="744eb-120">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="744eb-120">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="744eb-121">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="744eb-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="744eb-122">从 XML 加载数据集构架信息</span><span class="sxs-lookup"><span data-stu-id="744eb-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="744eb-123">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="744eb-123">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="744eb-124">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="744eb-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="744eb-125">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="744eb-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

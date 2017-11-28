---
title: "数据集架构接口过程摘要"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 15469e917129db7668df17f22fb71b166993d4fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="eb3c2-102">数据集架构接口过程摘要</span><span class="sxs-lookup"><span data-stu-id="eb3c2-102">Summary of the DataSet Schema Inference Process</span></span>
<span data-ttu-id="eb3c2-103">推断过程首先从 XML 文档中确定将哪些元素推断为表。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="eb3c2-104">从剩余的 XML 中，推断过程确定这些表的列。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="eb3c2-105">对于嵌套表，推断过程会生成嵌套的 <xref:System.Data.DataRelation> 和 <xref:System.Data.ForeignKeyConstraint> 对象。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="eb3c2-106">下面是推断规则的简要概述：</span><span class="sxs-lookup"><span data-stu-id="eb3c2-106">Following is a brief summary of inference rules:</span></span>  
  
-   <span data-ttu-id="eb3c2-107">具有属性的元素会被推断为表。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-107">Elements that have attributes are inferred as tables.</span></span>  
  
-   <span data-ttu-id="eb3c2-108">具有子元素的元素会被推断为表。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-108">Elements that have child elements are inferred as tables.</span></span>  
  
-   <span data-ttu-id="eb3c2-109">重复的元素会被推断为单个表。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-109">Elements that repeat are inferred as a single table.</span></span>  
  
-   <span data-ttu-id="eb3c2-110">如果文档元素（即根元素）不具有属性和将被推断为列的子元素，则将被推断为 <xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="eb3c2-111">否则，文档元素会被推断为表。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-111">Otherwise, the document element is inferred as a table.</span></span>  
  
-   <span data-ttu-id="eb3c2-112">属性会被推断为列。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-112">Attributes are inferred as columns.</span></span>  
  
-   <span data-ttu-id="eb3c2-113">不具有属性或子元素且不重复的元素会被推断为列。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
-   <span data-ttu-id="eb3c2-114">元素被推断为嵌套表内其他元素，同样被推断为表，嵌套**DataRelation**两个表之间创建。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="eb3c2-115">名为的新的主键列**TableName_Id**是添加到这两个表，供**DataRelation**。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="eb3c2-116">A **ForeignKeyConstraint**使用两个表之间创建**TableName_Id**列。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
-   <span data-ttu-id="eb3c2-117">对于被推断为表和包含文本但没有子元素的元素，新列命名为**TableName_Text**创建的每个元素的文本。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="eb3c2-118">如果元素被推断为表并包含文本和子元素，则将忽略文本。</span><span class="sxs-lookup"><span data-stu-id="eb3c2-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb3c2-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb3c2-119">See Also</span></span>  
 [<span data-ttu-id="eb3c2-120">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="eb3c2-120">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="eb3c2-121">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="eb3c2-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="eb3c2-122">从 XML 加载数据集架构信息</span><span class="sxs-lookup"><span data-stu-id="eb3c2-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="eb3c2-123">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="eb3c2-123">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="eb3c2-124">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="eb3c2-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="eb3c2-125">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="eb3c2-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

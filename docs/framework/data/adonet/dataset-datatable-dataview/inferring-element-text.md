---
title: "推断元素文本"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 66dcc6a98d365f20da6c7f4c075c2fdd8ab936e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="inferring-element-text"></a><span data-ttu-id="91467-102">推断元素文本</span><span class="sxs-lookup"><span data-stu-id="91467-102">Inferring Element Text</span></span>
<span data-ttu-id="91467-103">如果元素包含文本但不包含任何子元素被推断为表如 （具有属性的元素） 或重复的元素名称的新列**TableName_Text**将添加到为该元素推断的表。</span><span class="sxs-lookup"><span data-stu-id="91467-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="91467-104">该元素中包含的文本将添加到此表中的一行，并存储在新列中。</span><span class="sxs-lookup"><span data-stu-id="91467-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="91467-105">**ColumnMapping**新列的属性将设置为**MappingType.SimpleContent**。</span><span class="sxs-lookup"><span data-stu-id="91467-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="91467-106">例如，考虑以下 XML。</span><span class="sxs-lookup"><span data-stu-id="91467-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="91467-107">推断过程将生成名为的表**Element1**具有两列： **attr1**和**Element1_Text**。</span><span class="sxs-lookup"><span data-stu-id="91467-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="91467-108">**ColumnMapping**属性**attr1**列将设置为**MappingType.Attribute**。</span><span class="sxs-lookup"><span data-stu-id="91467-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="91467-109">**ColumnMapping**属性**Element1_Text**列将设置为**MappingType.SimpleContent**。</span><span class="sxs-lookup"><span data-stu-id="91467-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="91467-110">**数据集：** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="91467-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="91467-111">**表：** Element1</span><span class="sxs-lookup"><span data-stu-id="91467-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="91467-112">attr1</span><span class="sxs-lookup"><span data-stu-id="91467-112">attr1</span></span>|<span data-ttu-id="91467-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="91467-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="91467-114">value1</span><span class="sxs-lookup"><span data-stu-id="91467-114">value1</span></span>|<span data-ttu-id="91467-115">Text1</span><span class="sxs-lookup"><span data-stu-id="91467-115">Text1</span></span>|  
  
 <span data-ttu-id="91467-116">如果某元素包含文本，并且还具有包含文本的子元素，则不会将列添加到表中来存储该元素所包含的文本。</span><span class="sxs-lookup"><span data-stu-id="91467-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="91467-117">该元素中包含的文本将被忽略，但子元素中的文本将包含在表的一行中。</span><span class="sxs-lookup"><span data-stu-id="91467-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="91467-118">例如，考虑以下 XML。</span><span class="sxs-lookup"><span data-stu-id="91467-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="91467-119">推断过程将生成名为的表**Element1**与名为的一个列**ChildElement1**。</span><span class="sxs-lookup"><span data-stu-id="91467-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="91467-120">文本**ChildElement1**元素将包括在表中的行。</span><span class="sxs-lookup"><span data-stu-id="91467-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="91467-121">其他文本则将被忽略。</span><span class="sxs-lookup"><span data-stu-id="91467-121">The other text will be ignored.</span></span> <span data-ttu-id="91467-122">**ColumnMapping**属性**ChildElement1**列将设置为**MappingType.Element**。</span><span class="sxs-lookup"><span data-stu-id="91467-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="91467-123">**数据集：** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="91467-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="91467-124">**表：** Element1</span><span class="sxs-lookup"><span data-stu-id="91467-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="91467-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="91467-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="91467-126">Text2</span><span class="sxs-lookup"><span data-stu-id="91467-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91467-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91467-127">See Also</span></span>  
 [<span data-ttu-id="91467-128">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="91467-128">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="91467-129">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="91467-129">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="91467-130">从 XML 加载数据集架构信息</span><span class="sxs-lookup"><span data-stu-id="91467-130">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="91467-131">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="91467-131">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="91467-132">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="91467-132">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="91467-133">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="91467-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

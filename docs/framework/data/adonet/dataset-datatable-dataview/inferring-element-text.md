---
title: 推断元素文本
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: d8d64c0cbb0aecf736a54fa6816e286ab7efa191
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203538"
---
# <a name="inferring-element-text"></a><span data-ttu-id="49398-102">推断元素文本</span><span class="sxs-lookup"><span data-stu-id="49398-102">Inferring Element Text</span></span>
<span data-ttu-id="49398-103">如果某个元素包含文本, 并且没有要推断为表的子元素 (例如具有属性或重复元素的元素), 则会将名为**TableName_Text**的新列添加到为该元素推断的表中。</span><span class="sxs-lookup"><span data-stu-id="49398-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="49398-104">该元素中包含的文本将添加到此表中的一行，并存储在新列中。</span><span class="sxs-lookup"><span data-stu-id="49398-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="49398-105">新列的**ColumnMapping**属性将设置为**mappingtype.attribute**。</span><span class="sxs-lookup"><span data-stu-id="49398-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="49398-106">例如，考虑以下 XML。</span><span class="sxs-lookup"><span data-stu-id="49398-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="49398-107">推理过程将生成一个名为**Element1**的表, 该表包含两列: **attr1**和**Element1_Text**。</span><span class="sxs-lookup"><span data-stu-id="49398-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="49398-108">**Attr1**列的**ColumnMapping**属性将设置为**mappingtype.attribute**。</span><span class="sxs-lookup"><span data-stu-id="49398-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="49398-109">**Element1_Text**列的**ColumnMapping**属性将设置为**mappingtype.attribute**。</span><span class="sxs-lookup"><span data-stu-id="49398-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="49398-110">**集会**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="49398-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="49398-111">**数据表**Element1</span><span class="sxs-lookup"><span data-stu-id="49398-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="49398-112">attr1</span><span class="sxs-lookup"><span data-stu-id="49398-112">attr1</span></span>|<span data-ttu-id="49398-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="49398-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="49398-114">value1</span><span class="sxs-lookup"><span data-stu-id="49398-114">value1</span></span>|<span data-ttu-id="49398-115">Text1</span><span class="sxs-lookup"><span data-stu-id="49398-115">Text1</span></span>|  
  
 <span data-ttu-id="49398-116">如果某元素包含文本，并且还具有包含文本的子元素，则不会将列添加到表中来存储该元素所包含的文本。</span><span class="sxs-lookup"><span data-stu-id="49398-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="49398-117">该元素中包含的文本将被忽略，但子元素中的文本将包含在表的一行中。</span><span class="sxs-lookup"><span data-stu-id="49398-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="49398-118">例如，考虑以下 XML。</span><span class="sxs-lookup"><span data-stu-id="49398-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="49398-119">推理过程将生成一个名为**Element1**的表, 该表包含一个名为**ChildElement1**的列。</span><span class="sxs-lookup"><span data-stu-id="49398-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="49398-120">**ChildElement1**元素的文本将包含在表的行中。</span><span class="sxs-lookup"><span data-stu-id="49398-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="49398-121">其他文本则将被忽略。</span><span class="sxs-lookup"><span data-stu-id="49398-121">The other text will be ignored.</span></span> <span data-ttu-id="49398-122">**ChildElement1**列的**ColumnMapping**属性将设置为**mappingtype.attribute**。</span><span class="sxs-lookup"><span data-stu-id="49398-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="49398-123">**集会**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="49398-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="49398-124">**数据表**Element1</span><span class="sxs-lookup"><span data-stu-id="49398-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="49398-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="49398-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="49398-126">Text2</span><span class="sxs-lookup"><span data-stu-id="49398-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="49398-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="49398-127">See also</span></span>

- [<span data-ttu-id="49398-128">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="49398-128">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="49398-129">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="49398-129">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="49398-130">从 XML 加载数据集构架信息</span><span class="sxs-lookup"><span data-stu-id="49398-130">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="49398-131">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="49398-131">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="49398-132">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="49398-132">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="49398-133">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="49398-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

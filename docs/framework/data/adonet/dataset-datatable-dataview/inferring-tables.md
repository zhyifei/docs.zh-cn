---
title: 推断表
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 2c2a93d413f301dc3006b701e4bc7979a3fa7a1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034250"
---
# <a name="inferring-tables"></a><span data-ttu-id="e52db-102">推断表</span><span class="sxs-lookup"><span data-stu-id="e52db-102">Inferring Tables</span></span>
<span data-ttu-id="e52db-103">当从 XML 文档推断 <xref:System.Data.DataSet> 的架构时，ADO.NET 首先会确定哪些 XML 元素表示表。</span><span class="sxs-lookup"><span data-stu-id="e52db-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="e52db-104">以下 XML 结构生成的表**数据集**架构：</span><span class="sxs-lookup"><span data-stu-id="e52db-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="e52db-105">具有属性的元素</span><span class="sxs-lookup"><span data-stu-id="e52db-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="e52db-106">具有子元素的元素</span><span class="sxs-lookup"><span data-stu-id="e52db-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="e52db-107">重复元素</span><span class="sxs-lookup"><span data-stu-id="e52db-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="e52db-108">具有属性的元素</span><span class="sxs-lookup"><span data-stu-id="e52db-108">Elements with Attributes</span></span>  
 <span data-ttu-id="e52db-109">在其中指定了属性的元素将生成推断表。</span><span class="sxs-lookup"><span data-stu-id="e52db-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="e52db-110">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="e52db-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="e52db-111">推断过程将生成名为“Element1”的表。</span><span class="sxs-lookup"><span data-stu-id="e52db-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="e52db-112">**数据集：** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="e52db-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="e52db-113">**表：** Element1</span><span class="sxs-lookup"><span data-stu-id="e52db-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="e52db-114">attr1</span><span class="sxs-lookup"><span data-stu-id="e52db-114">attr1</span></span>|<span data-ttu-id="e52db-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="e52db-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="e52db-116">value1</span><span class="sxs-lookup"><span data-stu-id="e52db-116">value1</span></span>||  
|<span data-ttu-id="e52db-117">value2</span><span class="sxs-lookup"><span data-stu-id="e52db-117">value2</span></span>|<span data-ttu-id="e52db-118">Text1</span><span class="sxs-lookup"><span data-stu-id="e52db-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="e52db-119">具有子元素的元素</span><span class="sxs-lookup"><span data-stu-id="e52db-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="e52db-120">具有子元素的元素将生成推断表。</span><span class="sxs-lookup"><span data-stu-id="e52db-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="e52db-121">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="e52db-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="e52db-122">推断过程将生成名为“Element1”的表。</span><span class="sxs-lookup"><span data-stu-id="e52db-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="e52db-123">**数据集：** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="e52db-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="e52db-124">**表：** Element1</span><span class="sxs-lookup"><span data-stu-id="e52db-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="e52db-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="e52db-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="e52db-126">Text1</span><span class="sxs-lookup"><span data-stu-id="e52db-126">Text1</span></span>|  
  
 <span data-ttu-id="e52db-127">如果文档元素（即根元素）具有将被推断为列的属性或子元素，将生成推断表。</span><span class="sxs-lookup"><span data-stu-id="e52db-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="e52db-128">如果文档元素不具有属性和将被推断为列没有子元素，该元素被推断为**数据集**。</span><span class="sxs-lookup"><span data-stu-id="e52db-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="e52db-129">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="e52db-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="e52db-130">推断过程将生成名为“DocumentElement”的表。</span><span class="sxs-lookup"><span data-stu-id="e52db-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="e52db-131">**数据集：** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="e52db-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="e52db-132">**表：** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="e52db-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="e52db-133">Element1</span><span class="sxs-lookup"><span data-stu-id="e52db-133">Element1</span></span>|<span data-ttu-id="e52db-134">Element2</span><span class="sxs-lookup"><span data-stu-id="e52db-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="e52db-135">Text1</span><span class="sxs-lookup"><span data-stu-id="e52db-135">Text1</span></span>|<span data-ttu-id="e52db-136">Text2</span><span class="sxs-lookup"><span data-stu-id="e52db-136">Text2</span></span>|  
  
 <span data-ttu-id="e52db-137">或者，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="e52db-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="e52db-138">推断过程将生成**数据集**名为"DocumentElement"的包含一个名为"Element1"。</span><span class="sxs-lookup"><span data-stu-id="e52db-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="e52db-139">**数据集：** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="e52db-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="e52db-140">**表：** Element1</span><span class="sxs-lookup"><span data-stu-id="e52db-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="e52db-141">attr1</span><span class="sxs-lookup"><span data-stu-id="e52db-141">attr1</span></span>|<span data-ttu-id="e52db-142">attr2</span><span class="sxs-lookup"><span data-stu-id="e52db-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="e52db-143">value1</span><span class="sxs-lookup"><span data-stu-id="e52db-143">value1</span></span>|<span data-ttu-id="e52db-144">value2</span><span class="sxs-lookup"><span data-stu-id="e52db-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="e52db-145">重复元素</span><span class="sxs-lookup"><span data-stu-id="e52db-145">Repeating Elements</span></span>  
 <span data-ttu-id="e52db-146">重复的元素将生成单个推断表。</span><span class="sxs-lookup"><span data-stu-id="e52db-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="e52db-147">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="e52db-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="e52db-148">推断过程将生成名为“Element1”的表。</span><span class="sxs-lookup"><span data-stu-id="e52db-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="e52db-149">**数据集：** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="e52db-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="e52db-150">**表：** Element1</span><span class="sxs-lookup"><span data-stu-id="e52db-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="e52db-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="e52db-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="e52db-152">Text1</span><span class="sxs-lookup"><span data-stu-id="e52db-152">Text1</span></span>|  
|<span data-ttu-id="e52db-153">Text2</span><span class="sxs-lookup"><span data-stu-id="e52db-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e52db-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="e52db-154">See also</span></span>

- [<span data-ttu-id="e52db-155">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="e52db-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="e52db-156">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="e52db-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="e52db-157">从 XML 加载数据集构架信息</span><span class="sxs-lookup"><span data-stu-id="e52db-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="e52db-158">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="e52db-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="e52db-159">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="e52db-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="e52db-160">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="e52db-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

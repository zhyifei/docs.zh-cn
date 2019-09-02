---
title: 推断表
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 84cee828f2d3c918a12e449da5b01a3d72d86333
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203516"
---
# <a name="inferring-tables"></a><span data-ttu-id="670c2-102">推断表</span><span class="sxs-lookup"><span data-stu-id="670c2-102">Inferring Tables</span></span>
<span data-ttu-id="670c2-103">当从 XML 文档推断 <xref:System.Data.DataSet> 的架构时，ADO.NET 首先会确定哪些 XML 元素表示表。</span><span class="sxs-lookup"><span data-stu-id="670c2-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="670c2-104">以下 XML 结构将为**数据集**架构生成一个表:</span><span class="sxs-lookup"><span data-stu-id="670c2-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="670c2-105">具有属性的元素</span><span class="sxs-lookup"><span data-stu-id="670c2-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="670c2-106">具有子元素的元素</span><span class="sxs-lookup"><span data-stu-id="670c2-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="670c2-107">重复元素</span><span class="sxs-lookup"><span data-stu-id="670c2-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="670c2-108">具有属性的元素</span><span class="sxs-lookup"><span data-stu-id="670c2-108">Elements with Attributes</span></span>  
 <span data-ttu-id="670c2-109">在其中指定了属性的元素将生成推断表。</span><span class="sxs-lookup"><span data-stu-id="670c2-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="670c2-110">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="670c2-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="670c2-111">推断过程将生成名为“Element1”的表。</span><span class="sxs-lookup"><span data-stu-id="670c2-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="670c2-112">**集会**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="670c2-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="670c2-113">**数据表**Element1</span><span class="sxs-lookup"><span data-stu-id="670c2-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="670c2-114">attr1</span><span class="sxs-lookup"><span data-stu-id="670c2-114">attr1</span></span>|<span data-ttu-id="670c2-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="670c2-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="670c2-116">value1</span><span class="sxs-lookup"><span data-stu-id="670c2-116">value1</span></span>||  
|<span data-ttu-id="670c2-117">value2</span><span class="sxs-lookup"><span data-stu-id="670c2-117">value2</span></span>|<span data-ttu-id="670c2-118">Text1</span><span class="sxs-lookup"><span data-stu-id="670c2-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="670c2-119">具有子元素的元素</span><span class="sxs-lookup"><span data-stu-id="670c2-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="670c2-120">具有子元素的元素将生成推断表。</span><span class="sxs-lookup"><span data-stu-id="670c2-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="670c2-121">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="670c2-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="670c2-122">推断过程将生成名为“Element1”的表。</span><span class="sxs-lookup"><span data-stu-id="670c2-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="670c2-123">**集会**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="670c2-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="670c2-124">**数据表**Element1</span><span class="sxs-lookup"><span data-stu-id="670c2-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="670c2-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="670c2-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="670c2-126">Text1</span><span class="sxs-lookup"><span data-stu-id="670c2-126">Text1</span></span>|  
  
 <span data-ttu-id="670c2-127">如果文档元素（即根元素）具有将被推断为列的属性或子元素，将生成推断表。</span><span class="sxs-lookup"><span data-stu-id="670c2-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="670c2-128">如果文档元素没有属性, 并且没有任何子元素将被推断为列, 则该元素将被推断为**数据集**。</span><span class="sxs-lookup"><span data-stu-id="670c2-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="670c2-129">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="670c2-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="670c2-130">推断过程将生成名为“DocumentElement”的表。</span><span class="sxs-lookup"><span data-stu-id="670c2-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="670c2-131">**集会**NewDataSet</span><span class="sxs-lookup"><span data-stu-id="670c2-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="670c2-132">**数据表**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="670c2-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="670c2-133">Element1</span><span class="sxs-lookup"><span data-stu-id="670c2-133">Element1</span></span>|<span data-ttu-id="670c2-134">Element2</span><span class="sxs-lookup"><span data-stu-id="670c2-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="670c2-135">Text1</span><span class="sxs-lookup"><span data-stu-id="670c2-135">Text1</span></span>|<span data-ttu-id="670c2-136">Text2</span><span class="sxs-lookup"><span data-stu-id="670c2-136">Text2</span></span>|  
  
 <span data-ttu-id="670c2-137">或者，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="670c2-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="670c2-138">推理过程将生成一个名为 "DocumentElement" 的**数据集**, 其中包含一个名为 "Element1" 的表。</span><span class="sxs-lookup"><span data-stu-id="670c2-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="670c2-139">**集会**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="670c2-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="670c2-140">**数据表**Element1</span><span class="sxs-lookup"><span data-stu-id="670c2-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="670c2-141">attr1</span><span class="sxs-lookup"><span data-stu-id="670c2-141">attr1</span></span>|<span data-ttu-id="670c2-142">attr2</span><span class="sxs-lookup"><span data-stu-id="670c2-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="670c2-143">value1</span><span class="sxs-lookup"><span data-stu-id="670c2-143">value1</span></span>|<span data-ttu-id="670c2-144">value2</span><span class="sxs-lookup"><span data-stu-id="670c2-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="670c2-145">重复元素</span><span class="sxs-lookup"><span data-stu-id="670c2-145">Repeating Elements</span></span>  
 <span data-ttu-id="670c2-146">重复的元素将生成单个推断表。</span><span class="sxs-lookup"><span data-stu-id="670c2-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="670c2-147">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="670c2-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="670c2-148">推断过程将生成名为“Element1”的表。</span><span class="sxs-lookup"><span data-stu-id="670c2-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="670c2-149">**集会**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="670c2-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="670c2-150">**数据表**Element1</span><span class="sxs-lookup"><span data-stu-id="670c2-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="670c2-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="670c2-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="670c2-152">Text1</span><span class="sxs-lookup"><span data-stu-id="670c2-152">Text1</span></span>|  
|<span data-ttu-id="670c2-153">Text2</span><span class="sxs-lookup"><span data-stu-id="670c2-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="670c2-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="670c2-154">See also</span></span>

- [<span data-ttu-id="670c2-155">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="670c2-155">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="670c2-156">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="670c2-156">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="670c2-157">从 XML 加载数据集构架信息</span><span class="sxs-lookup"><span data-stu-id="670c2-157">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="670c2-158">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="670c2-158">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="670c2-159">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="670c2-159">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="670c2-160">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="670c2-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

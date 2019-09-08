---
title: 推断表
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 52ffd3fe90eb491dd01acf8538276cc828fdb309
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784490"
---
# <a name="inferring-tables"></a><span data-ttu-id="f396a-102">推断表</span><span class="sxs-lookup"><span data-stu-id="f396a-102">Inferring Tables</span></span>
<span data-ttu-id="f396a-103">当从 XML 文档推断 <xref:System.Data.DataSet> 的架构时，ADO.NET 首先会确定哪些 XML 元素表示表。</span><span class="sxs-lookup"><span data-stu-id="f396a-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="f396a-104">以下 XML 结构将为**数据集**架构生成一个表：</span><span class="sxs-lookup"><span data-stu-id="f396a-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="f396a-105">具有属性的元素</span><span class="sxs-lookup"><span data-stu-id="f396a-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="f396a-106">具有子元素的元素</span><span class="sxs-lookup"><span data-stu-id="f396a-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="f396a-107">重复元素</span><span class="sxs-lookup"><span data-stu-id="f396a-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="f396a-108">具有属性的元素</span><span class="sxs-lookup"><span data-stu-id="f396a-108">Elements with Attributes</span></span>  
 <span data-ttu-id="f396a-109">在其中指定了属性的元素将生成推断表。</span><span class="sxs-lookup"><span data-stu-id="f396a-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="f396a-110">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="f396a-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="f396a-111">推断过程将生成名为“Element1”的表。</span><span class="sxs-lookup"><span data-stu-id="f396a-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="f396a-112">**集会**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f396a-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="f396a-113">**数据表**Element1</span><span class="sxs-lookup"><span data-stu-id="f396a-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="f396a-114">attr1</span><span class="sxs-lookup"><span data-stu-id="f396a-114">attr1</span></span>|<span data-ttu-id="f396a-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="f396a-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="f396a-116">value1</span><span class="sxs-lookup"><span data-stu-id="f396a-116">value1</span></span>||  
|<span data-ttu-id="f396a-117">value2</span><span class="sxs-lookup"><span data-stu-id="f396a-117">value2</span></span>|<span data-ttu-id="f396a-118">Text1</span><span class="sxs-lookup"><span data-stu-id="f396a-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="f396a-119">具有子元素的元素</span><span class="sxs-lookup"><span data-stu-id="f396a-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="f396a-120">具有子元素的元素将生成推断表。</span><span class="sxs-lookup"><span data-stu-id="f396a-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="f396a-121">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="f396a-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="f396a-122">推断过程将生成名为“Element1”的表。</span><span class="sxs-lookup"><span data-stu-id="f396a-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="f396a-123">**集会**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f396a-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="f396a-124">**数据表**Element1</span><span class="sxs-lookup"><span data-stu-id="f396a-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="f396a-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="f396a-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="f396a-126">Text1</span><span class="sxs-lookup"><span data-stu-id="f396a-126">Text1</span></span>|  
  
 <span data-ttu-id="f396a-127">如果文档元素（即根元素）具有将被推断为列的属性或子元素，将生成推断表。</span><span class="sxs-lookup"><span data-stu-id="f396a-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="f396a-128">如果文档元素没有属性，并且没有任何子元素将被推断为列，则该元素将被推断为**数据集**。</span><span class="sxs-lookup"><span data-stu-id="f396a-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="f396a-129">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="f396a-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="f396a-130">推断过程将生成名为“DocumentElement”的表。</span><span class="sxs-lookup"><span data-stu-id="f396a-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="f396a-131">**集会**NewDataSet</span><span class="sxs-lookup"><span data-stu-id="f396a-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="f396a-132">**数据表**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f396a-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="f396a-133">Element1</span><span class="sxs-lookup"><span data-stu-id="f396a-133">Element1</span></span>|<span data-ttu-id="f396a-134">Element2</span><span class="sxs-lookup"><span data-stu-id="f396a-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="f396a-135">Text1</span><span class="sxs-lookup"><span data-stu-id="f396a-135">Text1</span></span>|<span data-ttu-id="f396a-136">Text2</span><span class="sxs-lookup"><span data-stu-id="f396a-136">Text2</span></span>|  
  
 <span data-ttu-id="f396a-137">或者，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="f396a-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="f396a-138">推理过程将生成一个名为 "DocumentElement" 的**数据集**，其中包含一个名为 "Element1" 的表。</span><span class="sxs-lookup"><span data-stu-id="f396a-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="f396a-139">**集会**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f396a-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="f396a-140">**数据表**Element1</span><span class="sxs-lookup"><span data-stu-id="f396a-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="f396a-141">attr1</span><span class="sxs-lookup"><span data-stu-id="f396a-141">attr1</span></span>|<span data-ttu-id="f396a-142">attr2</span><span class="sxs-lookup"><span data-stu-id="f396a-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="f396a-143">value1</span><span class="sxs-lookup"><span data-stu-id="f396a-143">value1</span></span>|<span data-ttu-id="f396a-144">value2</span><span class="sxs-lookup"><span data-stu-id="f396a-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="f396a-145">重复元素</span><span class="sxs-lookup"><span data-stu-id="f396a-145">Repeating Elements</span></span>  
 <span data-ttu-id="f396a-146">重复的元素将生成单个推断表。</span><span class="sxs-lookup"><span data-stu-id="f396a-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="f396a-147">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="f396a-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="f396a-148">推断过程将生成名为“Element1”的表。</span><span class="sxs-lookup"><span data-stu-id="f396a-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="f396a-149">**集会**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f396a-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="f396a-150">**数据表**Element1</span><span class="sxs-lookup"><span data-stu-id="f396a-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="f396a-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="f396a-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="f396a-152">Text1</span><span class="sxs-lookup"><span data-stu-id="f396a-152">Text1</span></span>|  
|<span data-ttu-id="f396a-153">Text2</span><span class="sxs-lookup"><span data-stu-id="f396a-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f396a-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="f396a-154">See also</span></span>

- [<span data-ttu-id="f396a-155">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="f396a-155">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="f396a-156">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="f396a-156">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="f396a-157">从 XML 加载数据集构架信息</span><span class="sxs-lookup"><span data-stu-id="f396a-157">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="f396a-158">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="f396a-158">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="f396a-159">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="f396a-159">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="f396a-160">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="f396a-160">ADO.NET Overview</span></span>](../ado-net-overview.md)

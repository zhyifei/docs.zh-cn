---
title: 推断列
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 2718cbcf29799f99c8648b129fdb6079a6f6d344
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786177"
---
# <a name="inferring-columns"></a><span data-ttu-id="697ab-102">推断列</span><span class="sxs-lookup"><span data-stu-id="697ab-102">Inferring Columns</span></span>
<span data-ttu-id="697ab-103">ADO.NET 从 XML 文档中确定了哪些元素要作为 <xref:System.Data.DataSet> 的表进行推断后，即开始推断这些表的列。</span><span class="sxs-lookup"><span data-stu-id="697ab-103">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="697ab-104">ADO.NET 2.0 引入了一个新的架构推断引擎，该引擎可推断每个**simpleType**元素的强类型化数据类型。</span><span class="sxs-lookup"><span data-stu-id="697ab-104">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="697ab-105">在以前的版本中，推断的**simpleType**元素的数据类型始终为**xsd： string**。</span><span class="sxs-lookup"><span data-stu-id="697ab-105">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="697ab-106">迁移和向后兼容性</span><span class="sxs-lookup"><span data-stu-id="697ab-106">Migration and Backward Compatibility</span></span>  
 <span data-ttu-id="697ab-107">**ReadXml**方法采用**InferSchema**类型的参数。</span><span class="sxs-lookup"><span data-stu-id="697ab-107">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="697ab-108">使用此自变量可以指定与以前的版本兼容的推断行为。</span><span class="sxs-lookup"><span data-stu-id="697ab-108">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="697ab-109">下表显示了**InferSchema**枚举的可用值。</span><span class="sxs-lookup"><span data-stu-id="697ab-109">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="697ab-110">通过始终将简单类型作为 <xref:System.String> 进行推断，提供向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="697ab-110">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="697ab-111">推断强类型化的数据类型。</span><span class="sxs-lookup"><span data-stu-id="697ab-111">Infers a strongly typed data type.</span></span> <span data-ttu-id="697ab-112">如果与 <xref:System.Data.DataTable> 一起使用，会发生异常。</span><span class="sxs-lookup"><span data-stu-id="697ab-112">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="697ab-113">忽略任何内联架构并将数据读入现有的 <xref:System.Data.DataSet> 架构。</span><span class="sxs-lookup"><span data-stu-id="697ab-113">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="697ab-114">特性</span><span class="sxs-lookup"><span data-stu-id="697ab-114">Attributes</span></span>  
 <span data-ttu-id="697ab-115">如[推断表](inferring-tables.md)中所定义的，具有属性的元素将被推断为表。</span><span class="sxs-lookup"><span data-stu-id="697ab-115">As defined in [Inferring Tables](inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="697ab-116">然后，该元素的属性将被推断为该表的列。</span><span class="sxs-lookup"><span data-stu-id="697ab-116">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="697ab-117">列的**ColumnMapping**属性将设置为**mappingtype.attribute**，以确保在架构写回 XML 时，列名将写入为属性。</span><span class="sxs-lookup"><span data-stu-id="697ab-117">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="697ab-118">这些属性的值存储在表的行中。</span><span class="sxs-lookup"><span data-stu-id="697ab-118">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="697ab-119">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="697ab-119">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="697ab-120">推理过程将生成一个名为**Element1**的表，该表包含两列： **attr1**和**attr2**。</span><span class="sxs-lookup"><span data-stu-id="697ab-120">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="697ab-121">这两个列的**ColumnMapping**属性将设置为**mappingtype.attribute**。</span><span class="sxs-lookup"><span data-stu-id="697ab-121">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="697ab-122">**集会**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="697ab-122">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="697ab-123">**数据表**Element1</span><span class="sxs-lookup"><span data-stu-id="697ab-123">**Table:** Element1</span></span>  
  
|<span data-ttu-id="697ab-124">attr1</span><span class="sxs-lookup"><span data-stu-id="697ab-124">attr1</span></span>|<span data-ttu-id="697ab-125">attr2</span><span class="sxs-lookup"><span data-stu-id="697ab-125">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="697ab-126">value1</span><span class="sxs-lookup"><span data-stu-id="697ab-126">value1</span></span>|<span data-ttu-id="697ab-127">value2</span><span class="sxs-lookup"><span data-stu-id="697ab-127">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="697ab-128">不具有属性或子元素的元素</span><span class="sxs-lookup"><span data-stu-id="697ab-128">Elements Without Attributes or Child Elements</span></span>  
 <span data-ttu-id="697ab-129">如果元素不具有子元素或属性，它将被推断为列。</span><span class="sxs-lookup"><span data-stu-id="697ab-129">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="697ab-130">列的**ColumnMapping**属性将设置为**mappingtype.attribute**。</span><span class="sxs-lookup"><span data-stu-id="697ab-130">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="697ab-131">子元素的文本存储在表的行中。</span><span class="sxs-lookup"><span data-stu-id="697ab-131">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="697ab-132">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="697ab-132">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="697ab-133">推理过程将生成一个名为**Element1**的表，该表包含两列： **ChildElement1**和**ChildElement2**。</span><span class="sxs-lookup"><span data-stu-id="697ab-133">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="697ab-134">这两个列的**ColumnMapping**属性将设置为**mappingtype.attribute**。</span><span class="sxs-lookup"><span data-stu-id="697ab-134">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="697ab-135">**集会**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="697ab-135">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="697ab-136">**数据表**Element1</span><span class="sxs-lookup"><span data-stu-id="697ab-136">**Table:** Element1</span></span>  
  
|<span data-ttu-id="697ab-137">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="697ab-137">ChildElement1</span></span>|<span data-ttu-id="697ab-138">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="697ab-138">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="697ab-139">Text1</span><span class="sxs-lookup"><span data-stu-id="697ab-139">Text1</span></span>|<span data-ttu-id="697ab-140">Text2</span><span class="sxs-lookup"><span data-stu-id="697ab-140">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="697ab-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="697ab-141">See also</span></span>

- [<span data-ttu-id="697ab-142">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="697ab-142">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="697ab-143">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="697ab-143">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="697ab-144">从 XML 加载数据集构架信息</span><span class="sxs-lookup"><span data-stu-id="697ab-144">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="697ab-145">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="697ab-145">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="697ab-146">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="697ab-146">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="697ab-147">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="697ab-147">ADO.NET Overview</span></span>](../ado-net-overview.md)

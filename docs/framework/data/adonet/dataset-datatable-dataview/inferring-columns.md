---
title: "推断列"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ba06bce55db53de1da1c07d2a6451d5664fa23bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="inferring-columns"></a><span data-ttu-id="76421-102">推断列</span><span class="sxs-lookup"><span data-stu-id="76421-102">Inferring Columns</span></span>
<span data-ttu-id="76421-103">ADO.NET 从 XML 文档中确定了哪些元素要作为 <xref:System.Data.DataSet> 的表进行推断后，即开始推断这些表的列。</span><span class="sxs-lookup"><span data-stu-id="76421-103">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="76421-104">ADO.NET 2.0 引入了新的架构推断引擎，为每个推断强类型的数据类型**simpleType**元素。</span><span class="sxs-lookup"><span data-stu-id="76421-104">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="76421-105">在以前版本的数据类型推断**simpleType**元素始终是**xsd: string**。</span><span class="sxs-lookup"><span data-stu-id="76421-105">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="76421-106">迁移和向后兼容性</span><span class="sxs-lookup"><span data-stu-id="76421-106">Migration and Backward Compatibility</span></span>  
 <span data-ttu-id="76421-107">**ReadXml**方法采用类型的自变量**InferSchema**。</span><span class="sxs-lookup"><span data-stu-id="76421-107">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="76421-108">使用此自变量可以指定与以前的版本兼容的推断行为。</span><span class="sxs-lookup"><span data-stu-id="76421-108">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="76421-109">可用值**InferSchema**枚举显示下表中。</span><span class="sxs-lookup"><span data-stu-id="76421-109">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="76421-110">通过始终将简单类型作为 <xref:System.String> 进行推断，提供向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="76421-110">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="76421-111">推断强类型化的数据类型。</span><span class="sxs-lookup"><span data-stu-id="76421-111">Infers a strongly typed data type.</span></span> <span data-ttu-id="76421-112">如果与 <xref:System.Data.DataTable> 一起使用，会发生异常。</span><span class="sxs-lookup"><span data-stu-id="76421-112">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="76421-113">忽略任何内联架构并将数据读入现有的 <xref:System.Data.DataSet> 架构。</span><span class="sxs-lookup"><span data-stu-id="76421-113">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="76421-114">特性</span><span class="sxs-lookup"><span data-stu-id="76421-114">Attributes</span></span>  
 <span data-ttu-id="76421-115">中定义[推断表](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md)，具有属性的元素将被推断为表。</span><span class="sxs-lookup"><span data-stu-id="76421-115">As defined in [Inferring Tables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="76421-116">然后，该元素的属性将被推断为该表的列。</span><span class="sxs-lookup"><span data-stu-id="76421-116">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="76421-117">**ColumnMapping**的列的属性将设置为**MappingType.Attribute**，以确保列名称将写为属性中，如果架构写回 XML。</span><span class="sxs-lookup"><span data-stu-id="76421-117">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="76421-118">这些属性的值存储在表的行中。</span><span class="sxs-lookup"><span data-stu-id="76421-118">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="76421-119">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="76421-119">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="76421-120">推断过程将生成名为的表**Element1**具有两列， **attr1**和**attr2**。</span><span class="sxs-lookup"><span data-stu-id="76421-120">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="76421-121">**ColumnMapping**这两个列的属性将设置为**MappingType.Attribute**。</span><span class="sxs-lookup"><span data-stu-id="76421-121">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="76421-122">**数据集：** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="76421-122">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="76421-123">**表：** Element1</span><span class="sxs-lookup"><span data-stu-id="76421-123">**Table:** Element1</span></span>  
  
|<span data-ttu-id="76421-124">attr1</span><span class="sxs-lookup"><span data-stu-id="76421-124">attr1</span></span>|<span data-ttu-id="76421-125">attr2</span><span class="sxs-lookup"><span data-stu-id="76421-125">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="76421-126">value1</span><span class="sxs-lookup"><span data-stu-id="76421-126">value1</span></span>|<span data-ttu-id="76421-127">value2</span><span class="sxs-lookup"><span data-stu-id="76421-127">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="76421-128">不具有属性或子元素的元素</span><span class="sxs-lookup"><span data-stu-id="76421-128">Elements Without Attributes or Child Elements</span></span>  
 <span data-ttu-id="76421-129">如果元素不具有子元素或属性，它将被推断为列。</span><span class="sxs-lookup"><span data-stu-id="76421-129">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="76421-130">**ColumnMapping**列属性将设置为**MappingType.Element**。</span><span class="sxs-lookup"><span data-stu-id="76421-130">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="76421-131">子元素的文本存储在表的行中。</span><span class="sxs-lookup"><span data-stu-id="76421-131">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="76421-132">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="76421-132">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="76421-133">推断过程将生成名为的表**Element1**具有两列， **ChildElement1**和**ChildElement2**。</span><span class="sxs-lookup"><span data-stu-id="76421-133">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="76421-134">**ColumnMapping**这两个列的属性将设置为**MappingType.Element**。</span><span class="sxs-lookup"><span data-stu-id="76421-134">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="76421-135">**数据集：** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="76421-135">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="76421-136">**表：** Element1</span><span class="sxs-lookup"><span data-stu-id="76421-136">**Table:** Element1</span></span>  
  
|<span data-ttu-id="76421-137">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="76421-137">ChildElement1</span></span>|<span data-ttu-id="76421-138">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="76421-138">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="76421-139">Text1</span><span class="sxs-lookup"><span data-stu-id="76421-139">Text1</span></span>|<span data-ttu-id="76421-140">Text2</span><span class="sxs-lookup"><span data-stu-id="76421-140">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76421-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76421-141">See Also</span></span>  
 [<span data-ttu-id="76421-142">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="76421-142">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="76421-143">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="76421-143">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="76421-144">从 XML 加载数据集架构信息</span><span class="sxs-lookup"><span data-stu-id="76421-144">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="76421-145">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="76421-145">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="76421-146">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="76421-146">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="76421-147">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="76421-147">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

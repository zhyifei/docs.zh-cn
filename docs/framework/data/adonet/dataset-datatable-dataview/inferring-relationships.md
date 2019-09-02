---
title: 推断关系
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 92a4953dc7f5119ffbf171ff2a7bf5b58e896638
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204767"
---
# <a name="inferring-relationships"></a><span data-ttu-id="a8db5-102">推断关系</span><span class="sxs-lookup"><span data-stu-id="a8db5-102">Inferring Relationships</span></span>
<span data-ttu-id="a8db5-103">如果被推断为表的元素具有一个同样被推断为表的子元素，则将在这两个表之间创建 <xref:System.Data.DataRelation>。</span><span class="sxs-lookup"><span data-stu-id="a8db5-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="a8db5-104">名称为**ParentTableName_Id**的新列将添加到为父元素创建的表和为子元素创建的表中。</span><span class="sxs-lookup"><span data-stu-id="a8db5-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="a8db5-105">此标识列的**ColumnMapping**属性将设置为**mappingtype.attribute**。</span><span class="sxs-lookup"><span data-stu-id="a8db5-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="a8db5-106">列将是父表的自动递增主键, 并将用于这两个表之间的**DataRelation** 。</span><span class="sxs-lookup"><span data-stu-id="a8db5-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="a8db5-107">添加的标识列的数据类型将为 system.exception, 这与所有其他推断列的数据类型不同, 后者为**system.string**。</span><span class="sxs-lookup"><span data-stu-id="a8db5-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="a8db5-108">还<xref:System.Data.ForeignKeyConstraint>将使用父表和子表中的新列来创建具有**DeleteRule** = **级联**的。</span><span class="sxs-lookup"><span data-stu-id="a8db5-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="a8db5-109">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="a8db5-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a8db5-110">推理过程将生成两个表：**Element1**和**ChildElement1**。</span><span class="sxs-lookup"><span data-stu-id="a8db5-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="a8db5-111">**Element1**表包含两列:**Element1_Id**和**ChildElement2**。</span><span class="sxs-lookup"><span data-stu-id="a8db5-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="a8db5-112">**Element1_Id**列的**ColumnMapping**属性将设置为**mappingtype.attribute**。</span><span class="sxs-lookup"><span data-stu-id="a8db5-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="a8db5-113">**ChildElement2**列的**ColumnMapping**属性将设置为**mappingtype.attribute**。</span><span class="sxs-lookup"><span data-stu-id="a8db5-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="a8db5-114">**Element1_Id**列将设置为**Element1**表的主键。</span><span class="sxs-lookup"><span data-stu-id="a8db5-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="a8db5-115">**ChildElement1**表包含三列: **attr1**、 **attr2**和**Element1_Id**。</span><span class="sxs-lookup"><span data-stu-id="a8db5-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="a8db5-116">**Attr1**和**Attr2**列的**ColumnMapping**属性将设置为**mappingtype.attribute**。</span><span class="sxs-lookup"><span data-stu-id="a8db5-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="a8db5-117">**Element1_Id**列的**ColumnMapping**属性将设置为**mappingtype.attribute**。</span><span class="sxs-lookup"><span data-stu-id="a8db5-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="a8db5-118">将使用两个表中的**Element1_Id**列创建**DataRelation**和**ForeignKeyConstraint** 。</span><span class="sxs-lookup"><span data-stu-id="a8db5-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="a8db5-119">**集会**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a8db5-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a8db5-120">**数据表**Element1</span><span class="sxs-lookup"><span data-stu-id="a8db5-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a8db5-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="a8db5-121">Element1_Id</span></span>|<span data-ttu-id="a8db5-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="a8db5-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="a8db5-123">0</span><span class="sxs-lookup"><span data-stu-id="a8db5-123">0</span></span>|<span data-ttu-id="a8db5-124">Text2</span><span class="sxs-lookup"><span data-stu-id="a8db5-124">Text2</span></span>|  
  
 <span data-ttu-id="a8db5-125">**数据表**ChildElement1</span><span class="sxs-lookup"><span data-stu-id="a8db5-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="a8db5-126">attr1</span><span class="sxs-lookup"><span data-stu-id="a8db5-126">attr1</span></span>|<span data-ttu-id="a8db5-127">attr2</span><span class="sxs-lookup"><span data-stu-id="a8db5-127">attr2</span></span>|<span data-ttu-id="a8db5-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="a8db5-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="a8db5-129">value1</span><span class="sxs-lookup"><span data-stu-id="a8db5-129">value1</span></span>|<span data-ttu-id="a8db5-130">value2</span><span class="sxs-lookup"><span data-stu-id="a8db5-130">value2</span></span>|<span data-ttu-id="a8db5-131">0</span><span class="sxs-lookup"><span data-stu-id="a8db5-131">0</span></span>|  
  
 <span data-ttu-id="a8db5-132">**DataRelation**Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="a8db5-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="a8db5-133">**ParentTable**Element1</span><span class="sxs-lookup"><span data-stu-id="a8db5-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="a8db5-134">**ParentColumn**Element1_Id</span><span class="sxs-lookup"><span data-stu-id="a8db5-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="a8db5-135">**ChildTable**ChildElement1</span><span class="sxs-lookup"><span data-stu-id="a8db5-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="a8db5-136">**ChildColumn**Element1_Id</span><span class="sxs-lookup"><span data-stu-id="a8db5-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="a8db5-137">**嵌**True</span><span class="sxs-lookup"><span data-stu-id="a8db5-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="a8db5-138">**ForeignKeyConstraint**Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="a8db5-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="a8db5-139">**该列**Element1_Id</span><span class="sxs-lookup"><span data-stu-id="a8db5-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="a8db5-140">**ParentTable**Element1</span><span class="sxs-lookup"><span data-stu-id="a8db5-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="a8db5-141">**ChildTable**ChildElement1</span><span class="sxs-lookup"><span data-stu-id="a8db5-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="a8db5-142">**DeleteRule**Cascade</span><span class="sxs-lookup"><span data-stu-id="a8db5-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="a8db5-143">**AcceptRejectRule**无</span><span class="sxs-lookup"><span data-stu-id="a8db5-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8db5-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8db5-144">See also</span></span>

- [<span data-ttu-id="a8db5-145">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="a8db5-145">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="a8db5-146">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="a8db5-146">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="a8db5-147">从 XML 加载数据集构架信息</span><span class="sxs-lookup"><span data-stu-id="a8db5-147">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="a8db5-148">嵌套 DataRelation</span><span class="sxs-lookup"><span data-stu-id="a8db5-148">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="a8db5-149">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="a8db5-149">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="a8db5-150">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="a8db5-150">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="a8db5-151">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="a8db5-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

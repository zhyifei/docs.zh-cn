---
title: 推断关系
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 7dc3fb0c6098d636e640aaf52b72a404c1486492
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2018
ms.locfileid: "44705686"
---
# <a name="inferring-relationships"></a><span data-ttu-id="55945-102">推断关系</span><span class="sxs-lookup"><span data-stu-id="55945-102">Inferring Relationships</span></span>
<span data-ttu-id="55945-103">如果被推断为表的元素具有一个同样被推断为表的子元素，则将在这两个表之间创建 <xref:System.Data.DataRelation>。</span><span class="sxs-lookup"><span data-stu-id="55945-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="55945-104">名称的新列**ParentTableName_Id**将添加到父元素中，创建的表和子元素创建的表。</span><span class="sxs-lookup"><span data-stu-id="55945-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="55945-105">**ColumnMapping**此标识列的属性将设置为**MappingType.Hidden**。</span><span class="sxs-lookup"><span data-stu-id="55945-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="55945-106">列将为父表中，已自动递增主关键字和将用于**DataRelation**两个表之间。</span><span class="sxs-lookup"><span data-stu-id="55945-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="55945-107">添加的标识列的数据类型将是**System.Int32**，这是与所有其他推断列的数据类型，不同**System.String**。</span><span class="sxs-lookup"><span data-stu-id="55945-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="55945-108">一个<xref:System.Data.ForeignKeyConstraint>与**DeleteRule** = **级联**还将在父和子表中使用新的列创建。</span><span class="sxs-lookup"><span data-stu-id="55945-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="55945-109">例如，考虑以下 XML：</span><span class="sxs-lookup"><span data-stu-id="55945-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="55945-110">推断过程将生成两个表： **Element1**并**ChildElement1**。</span><span class="sxs-lookup"><span data-stu-id="55945-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="55945-111">**Element1**表将具有两个列： **Element1_Id**并**ChildElement2**。</span><span class="sxs-lookup"><span data-stu-id="55945-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="55945-112">**ColumnMapping**的属性**Element1_Id**列将设置为**MappingType.Hidden**。</span><span class="sxs-lookup"><span data-stu-id="55945-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="55945-113">**ColumnMapping**的属性**ChildElement2**列将设置为**MappingType.Element**。</span><span class="sxs-lookup"><span data-stu-id="55945-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="55945-114">**Element1_Id**列将设置为的主键**Element1**表。</span><span class="sxs-lookup"><span data-stu-id="55945-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="55945-115">**ChildElement1**表具有三个列： **attr1**， **attr2**并**Element1_Id**。</span><span class="sxs-lookup"><span data-stu-id="55945-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="55945-116">**ColumnMapping**属性**attr1**并**attr2**列将设置为**MappingType.Attribute**。</span><span class="sxs-lookup"><span data-stu-id="55945-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="55945-117">**ColumnMapping**的属性**Element1_Id**列将设置为**MappingType.Hidden**。</span><span class="sxs-lookup"><span data-stu-id="55945-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="55945-118">一个**DataRelation**并**ForeignKeyConstraint**将使用创建**Element1_Id**这两个表中的列。</span><span class="sxs-lookup"><span data-stu-id="55945-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="55945-119">**数据集：** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="55945-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="55945-120">**表：** Element1</span><span class="sxs-lookup"><span data-stu-id="55945-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="55945-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="55945-121">Element1_Id</span></span>|<span data-ttu-id="55945-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="55945-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="55945-123">0</span><span class="sxs-lookup"><span data-stu-id="55945-123">0</span></span>|<span data-ttu-id="55945-124">Text2</span><span class="sxs-lookup"><span data-stu-id="55945-124">Text2</span></span>|  
  
 <span data-ttu-id="55945-125">**表：** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="55945-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="55945-126">attr1</span><span class="sxs-lookup"><span data-stu-id="55945-126">attr1</span></span>|<span data-ttu-id="55945-127">attr2</span><span class="sxs-lookup"><span data-stu-id="55945-127">attr2</span></span>|<span data-ttu-id="55945-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="55945-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="55945-129">value1</span><span class="sxs-lookup"><span data-stu-id="55945-129">value1</span></span>|<span data-ttu-id="55945-130">value2</span><span class="sxs-lookup"><span data-stu-id="55945-130">value2</span></span>|<span data-ttu-id="55945-131">0</span><span class="sxs-lookup"><span data-stu-id="55945-131">0</span></span>|  
  
 <span data-ttu-id="55945-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="55945-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="55945-133">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="55945-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="55945-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="55945-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="55945-135">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="55945-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="55945-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="55945-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="55945-137">**嵌套：** ，则返回 True</span><span class="sxs-lookup"><span data-stu-id="55945-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="55945-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="55945-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="55945-139">**列：** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="55945-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="55945-140">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="55945-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="55945-141">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="55945-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="55945-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="55945-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="55945-143">**AcceptRejectRule:** None</span><span class="sxs-lookup"><span data-stu-id="55945-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55945-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="55945-144">See Also</span></span>  
 [<span data-ttu-id="55945-145">从 XML 推断数据集关系结构</span><span class="sxs-lookup"><span data-stu-id="55945-145">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="55945-146">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="55945-146">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="55945-147">从 XML 加载数据集构架信息</span><span class="sxs-lookup"><span data-stu-id="55945-147">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="55945-148">嵌套 DataRelation</span><span class="sxs-lookup"><span data-stu-id="55945-148">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [<span data-ttu-id="55945-149">在数据集中使用 XML</span><span class="sxs-lookup"><span data-stu-id="55945-149">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="55945-150">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="55945-150">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="55945-151">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="55945-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

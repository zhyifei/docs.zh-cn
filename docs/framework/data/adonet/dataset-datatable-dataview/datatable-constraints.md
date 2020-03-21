---
title: 数据表约束
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 4b7972c281786a4e36d0e9c1e455776a293423ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151281"
---
# <a name="datatable-constraints"></a><span data-ttu-id="c727b-102">数据表约束</span><span class="sxs-lookup"><span data-stu-id="c727b-102">DataTable Constraints</span></span>
<span data-ttu-id="c727b-103">为了维护数据的完整性，可以使用约束来对 <xref:System.Data.DataTable> 中的数据施加限制。</span><span class="sxs-lookup"><span data-stu-id="c727b-103">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="c727b-104">约束是应用于某列或相关各列的自动规则，它决定了某行的值以某种方式更改时的操作过程。</span><span class="sxs-lookup"><span data-stu-id="c727b-104">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="c727b-105">当 的属性`System.Data.DataSet.EnforceConstraints`<xref:System.Data.DataSet>**为 true**时，将强制执行约束。</span><span class="sxs-lookup"><span data-stu-id="c727b-105">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="c727b-106">有关显示如何设置 `EnforceConstraints` 属性的代码示例，请参见 <xref:System.Data.DataSet.EnforceConstraints%2A> 参考主题。</span><span class="sxs-lookup"><span data-stu-id="c727b-106">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="c727b-107">ADO.NET 中有两种约束：<xref:System.Data.ForeignKeyConstraint> 和 <xref:System.Data.UniqueConstraint>。</span><span class="sxs-lookup"><span data-stu-id="c727b-107">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="c727b-108">默认情况下，当您通过向<xref:System.Data.DataRelation>**DataSet**添加 创建 两个或多个表之间的关系时，将自动创建这两个约束。</span><span class="sxs-lookup"><span data-stu-id="c727b-108">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="c727b-109">但是，您可以通过在创建关系时指定**创建约束** = **为 false**来禁用此行为。</span><span class="sxs-lookup"><span data-stu-id="c727b-109">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="c727b-110">ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="c727b-110">ForeignKeyConstraint</span></span>  
 <span data-ttu-id="c727b-111">**外键约束**强制实施有关如何传播相关表的更新和删除的规则。</span><span class="sxs-lookup"><span data-stu-id="c727b-111">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="c727b-112">例如，如果更新或删除一个表行中的值，并且同一值也用于一个或多个相关表，**则外键约束**将确定相关表中发生的情况。</span><span class="sxs-lookup"><span data-stu-id="c727b-112">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="c727b-113">**外键约束**的<xref:System.Data.ForeignKeyConstraint.DeleteRule%2A>和<xref:System.Data.ForeignKeyConstraint.UpdateRule%2A>属性定义用户尝试删除或更新相关表中的行时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c727b-113">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="c727b-114">下表描述了**外键约束**的**DeleteRule**和**UpdateRule**属性可用的不同设置。</span><span class="sxs-lookup"><span data-stu-id="c727b-114">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="c727b-115">规则设置</span><span class="sxs-lookup"><span data-stu-id="c727b-115">Rule setting</span></span>|<span data-ttu-id="c727b-116">说明</span><span class="sxs-lookup"><span data-stu-id="c727b-116">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="c727b-117">**级 联**</span><span class="sxs-lookup"><span data-stu-id="c727b-117">**Cascade**</span></span>|<span data-ttu-id="c727b-118">删除或更新相关的行。</span><span class="sxs-lookup"><span data-stu-id="c727b-118">Delete or update related rows.</span></span>|  
|<span data-ttu-id="c727b-119">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="c727b-119">**SetNull**</span></span>|<span data-ttu-id="c727b-120">将相关行中的值设置为**DBNull**。</span><span class="sxs-lookup"><span data-stu-id="c727b-120">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="c727b-121">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="c727b-121">**SetDefault**</span></span>|<span data-ttu-id="c727b-122">将相关行中的值设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="c727b-122">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="c727b-123">**无**</span><span class="sxs-lookup"><span data-stu-id="c727b-123">**None**</span></span>|<span data-ttu-id="c727b-124">对相关行不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="c727b-124">Take no action on related rows.</span></span> <span data-ttu-id="c727b-125">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="c727b-125">This is the default.</span></span>|  
  
 <span data-ttu-id="c727b-126">**外键约束**可以限制并传播对相关列的更改。</span><span class="sxs-lookup"><span data-stu-id="c727b-126">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="c727b-127">根据为列的**外键约束**设置的属性，如果**DataSet**的**强制约束**属性**为 true，** 则对父行执行某些操作将导致异常。</span><span class="sxs-lookup"><span data-stu-id="c727b-127">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="c727b-128">例如，如果**外键约束**的**DeleteRule**属性为 **"无**"，则如果父行具有任何子行，则无法删除该行。</span><span class="sxs-lookup"><span data-stu-id="c727b-128">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="c727b-129">可以使用**外键约束**构造函数在单个列之间或列数组之间创建外键约束。</span><span class="sxs-lookup"><span data-stu-id="c727b-129">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="c727b-130">将生成的**外键约束**对象传递给**表的约束属性**的**Add**方法，该方法是**约束集合**。</span><span class="sxs-lookup"><span data-stu-id="c727b-130">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="c727b-131">还可以将构造函数参数传递给**约束集合**的**Add**方法的几个重载，以创建**外键约束**。</span><span class="sxs-lookup"><span data-stu-id="c727b-131">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="c727b-132">创建**外键约束**时，可以将**DeleteRule**和**UpdateRule**值作为参数传递给构造函数，也可以将它们设置为属性，如以下示例（其中**DeleteRule**值设置为 **"无**" ）。</span><span class="sxs-lookup"><span data-stu-id="c727b-132">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### <a name="acceptrejectrule"></a><span data-ttu-id="c727b-133">AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="c727b-133">AcceptRejectRule</span></span>  
 <span data-ttu-id="c727b-134">可以使用 **"接受更改**"方法接受对行的更改，或使用**数据集**、**数据表**或 DataRow 的**拒绝更改**方法取消对行**的更改**。</span><span class="sxs-lookup"><span data-stu-id="c727b-134">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="c727b-135">当**数据集**包含**外键约束**时，调用 **"接受更改**"或 **"拒绝更改"** 方法将强制执行 **"接受拒绝规则**"。</span><span class="sxs-lookup"><span data-stu-id="c727b-135">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="c727b-136">**外键约束**的 **"接受拒绝规则"** 属性确定在父行上调用 **"接受更改**"或 **"拒绝更改**"时将对子行执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="c727b-136">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="c727b-137">下表列出了 **"接受拒绝规则**"的可用设置。</span><span class="sxs-lookup"><span data-stu-id="c727b-137">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="c727b-138">规则设置</span><span class="sxs-lookup"><span data-stu-id="c727b-138">Rule setting</span></span>|<span data-ttu-id="c727b-139">说明</span><span class="sxs-lookup"><span data-stu-id="c727b-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="c727b-140">**级 联**</span><span class="sxs-lookup"><span data-stu-id="c727b-140">**Cascade**</span></span>|<span data-ttu-id="c727b-141">接受或拒绝对子行的更改。</span><span class="sxs-lookup"><span data-stu-id="c727b-141">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="c727b-142">**无**</span><span class="sxs-lookup"><span data-stu-id="c727b-142">**None**</span></span>|<span data-ttu-id="c727b-143">对子行不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="c727b-143">Take no action on child rows.</span></span> <span data-ttu-id="c727b-144">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="c727b-144">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="c727b-145">示例</span><span class="sxs-lookup"><span data-stu-id="c727b-145">Example</span></span>  
 <span data-ttu-id="c727b-146">下面的示例创建一个 <xref:System.Data.ForeignKeyConstraint>，设置它的一些属性（包括 <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>），并将它添加到 <xref:System.Data.ConstraintCollection> 对象的 <xref:System.Data.DataTable>。</span><span class="sxs-lookup"><span data-stu-id="c727b-146">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="c727b-147">UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="c727b-147">UniqueConstraint</span></span>  
 <span data-ttu-id="c727b-148">**唯一约束**对象可以分配给单个列或**DataTable**中的列数组，可确保指定列或列中的所有数据每行都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c727b-148">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="c727b-149">可以使用**唯一约束**构造函数为列或列数组创建唯一约束。</span><span class="sxs-lookup"><span data-stu-id="c727b-149">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="c727b-150">将生成的**唯一约束**对象传递给**表的约束属性**的**Add**方法，该方法是**约束集合**。</span><span class="sxs-lookup"><span data-stu-id="c727b-150">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="c727b-151">还可以将构造函数参数传递给**约束集合**的**Add**方法的几个重载，以创建**唯一约束**。</span><span class="sxs-lookup"><span data-stu-id="c727b-151">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="c727b-152">为列或列创建**唯一约束**时，可以选择指定列或列是主键。</span><span class="sxs-lookup"><span data-stu-id="c727b-152">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="c727b-153">还可以通过将列**的唯一**属性设置为**true，** 为列创建唯一约束。</span><span class="sxs-lookup"><span data-stu-id="c727b-153">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="c727b-154">或者，将单个列**的唯一**属性设置为**false**将删除可能存在的任何唯一约束。</span><span class="sxs-lookup"><span data-stu-id="c727b-154">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="c727b-155">如果将一列或多列定义为表的主键，会自动为一个或多个指定的列创建唯一的约束。</span><span class="sxs-lookup"><span data-stu-id="c727b-155">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="c727b-156">如果从**DataTable\*\*\*\*的主键**属性中删除列，则将删除**唯一约束**。</span><span class="sxs-lookup"><span data-stu-id="c727b-156">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="c727b-157">下面的示例为**DataTable**的两列创建**唯一约束**。</span><span class="sxs-lookup"><span data-stu-id="c727b-157">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]
    {custTable.Columns["CustomerID"],
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## <a name="see-also"></a><span data-ttu-id="c727b-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c727b-158">See also</span></span>

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [<span data-ttu-id="c727b-159">数据表架构定义</span><span class="sxs-lookup"><span data-stu-id="c727b-159">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="c727b-160">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="c727b-160">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="c727b-161">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="c727b-161">ADO.NET Overview</span></span>](../ado-net-overview.md)

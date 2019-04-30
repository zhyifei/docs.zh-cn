---
title: 数据表约束
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 254f486fa19d8af30759d9a9fd6642a1a40e82a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034354"
---
# <a name="datatable-constraints"></a><span data-ttu-id="112fa-102">数据表约束</span><span class="sxs-lookup"><span data-stu-id="112fa-102">DataTable Constraints</span></span>
<span data-ttu-id="112fa-103">为了维护数据的完整性，可以使用约束来对 <xref:System.Data.DataTable> 中的数据施加限制。</span><span class="sxs-lookup"><span data-stu-id="112fa-103">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="112fa-104">约束是应用于某列或相关各列的自动规则，它决定了某行的值以某种方式更改时的操作过程。</span><span class="sxs-lookup"><span data-stu-id="112fa-104">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="112fa-105">强制执行约束时`System.Data.DataSet.EnforceConstraints`的属性<xref:System.Data.DataSet>是**true**。</span><span class="sxs-lookup"><span data-stu-id="112fa-105">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="112fa-106">有关显示如何设置 `EnforceConstraints` 属性的代码示例，请参见 <xref:System.Data.DataSet.EnforceConstraints%2A> 参考主题。</span><span class="sxs-lookup"><span data-stu-id="112fa-106">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="112fa-107">ADO.NET 中有两种约束：<xref:System.Data.ForeignKeyConstraint> 和 <xref:System.Data.UniqueConstraint>。</span><span class="sxs-lookup"><span data-stu-id="112fa-107">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="112fa-108">默认情况下，这两种约束都会自动创建时创建通过添加两个或多个表之间的关系<xref:System.Data.DataRelation>到**数据集**。</span><span class="sxs-lookup"><span data-stu-id="112fa-108">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="112fa-109">但是，可以通过指定禁用此行为**createConstraints** = **false**创建关系时。</span><span class="sxs-lookup"><span data-stu-id="112fa-109">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="112fa-110">ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="112fa-110">ForeignKeyConstraint</span></span>  
 <span data-ttu-id="112fa-111">一个**ForeignKeyConstraint**强制实施有关如何传播更新和删除对相关表的规则。</span><span class="sxs-lookup"><span data-stu-id="112fa-111">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="112fa-112">例如，如果更新或删除一个表中的行中的值和相同的值还可在一个或多个相关表， **ForeignKeyConstraint**确定相关表中会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="112fa-112">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="112fa-113"><xref:System.Data.ForeignKeyConstraint.DeleteRule%2A>并<xref:System.Data.ForeignKeyConstraint.UpdateRule%2A>的属性**ForeignKeyConstraint**定义当用户尝试删除或更新相关表中的行时采取的操作。</span><span class="sxs-lookup"><span data-stu-id="112fa-113">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="112fa-114">下表描述了可用于不同的设置**DeleteRule**并**UpdateRule**的属性**ForeignKeyConstraint**。</span><span class="sxs-lookup"><span data-stu-id="112fa-114">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="112fa-115">规则设置</span><span class="sxs-lookup"><span data-stu-id="112fa-115">Rule setting</span></span>|<span data-ttu-id="112fa-116">描述</span><span class="sxs-lookup"><span data-stu-id="112fa-116">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="112fa-117">**Cascade**</span><span class="sxs-lookup"><span data-stu-id="112fa-117">**Cascade**</span></span>|<span data-ttu-id="112fa-118">删除或更新相关的行。</span><span class="sxs-lookup"><span data-stu-id="112fa-118">Delete or update related rows.</span></span>|  
|<span data-ttu-id="112fa-119">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="112fa-119">**SetNull**</span></span>|<span data-ttu-id="112fa-120">在相关的行中设置值**DBNull**。</span><span class="sxs-lookup"><span data-stu-id="112fa-120">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="112fa-121">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="112fa-121">**SetDefault**</span></span>|<span data-ttu-id="112fa-122">将相关行中的值设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="112fa-122">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="112fa-123">**无**</span><span class="sxs-lookup"><span data-stu-id="112fa-123">**None**</span></span>|<span data-ttu-id="112fa-124">对相关行不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="112fa-124">Take no action on related rows.</span></span> <span data-ttu-id="112fa-125">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="112fa-125">This is the default.</span></span>|  
  
 <span data-ttu-id="112fa-126">一个**ForeignKeyConstraint**可以限制，并传播到更改相关列。</span><span class="sxs-lookup"><span data-stu-id="112fa-126">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="112fa-127">具体取决于对设置的属性**ForeignKeyConstraint**的列，如果**EnforceConstraints**属性**数据集**是**true**，执行对父行的某些操作将导致异常。</span><span class="sxs-lookup"><span data-stu-id="112fa-127">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="112fa-128">例如，如果**DeleteRule**的属性**ForeignKeyConstraint**是**None**，如果有子行不能删除父行。</span><span class="sxs-lookup"><span data-stu-id="112fa-128">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="112fa-129">可以创建一组使用的列之间或单个列之间的外键约束**ForeignKeyConstraint**构造函数。</span><span class="sxs-lookup"><span data-stu-id="112fa-129">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="112fa-130">传递得到**ForeignKeyConstraint**对象传递给**添加**表的方法**约束**属性，它是**ConstraintCollection**.</span><span class="sxs-lookup"><span data-stu-id="112fa-130">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="112fa-131">此外可以将构造函数自变量传递给的几个重载**外**方法**ConstraintCollection**创建**ForeignKeyConstraint**。</span><span class="sxs-lookup"><span data-stu-id="112fa-131">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="112fa-132">创建时**ForeignKeyConstraint**，可以将传递**DeleteRule**并**UpdateRule**值构造函数作为自变量，也可以将它们设置为作为中的属性以下示例 (其中**DeleteRule**值设置为**None**)。</span><span class="sxs-lookup"><span data-stu-id="112fa-132">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
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
  
### <a name="acceptrejectrule"></a><span data-ttu-id="112fa-133">AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="112fa-133">AcceptRejectRule</span></span>  
 <span data-ttu-id="112fa-134">可以使用接受对行的更改**AcceptChanges**方法或已取消使用**RejectChanges**方法**数据集**， **DataTable**，或**DataRow**。</span><span class="sxs-lookup"><span data-stu-id="112fa-134">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="112fa-135">当**数据集**包含**ForeignKeyConstraints**，则调用**AcceptChanges**或者**RejectChanges**方法会强制**AcceptRejectRule**。</span><span class="sxs-lookup"><span data-stu-id="112fa-135">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="112fa-136">**AcceptRejectRule**的属性**ForeignKeyConstraint**确定将采取的操作在子活动时行**AcceptChanges**或**RejectChanges**对父行调用。</span><span class="sxs-lookup"><span data-stu-id="112fa-136">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="112fa-137">下表列出的可用设置**AcceptRejectRule**。</span><span class="sxs-lookup"><span data-stu-id="112fa-137">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="112fa-138">规则设置</span><span class="sxs-lookup"><span data-stu-id="112fa-138">Rule setting</span></span>|<span data-ttu-id="112fa-139">描述</span><span class="sxs-lookup"><span data-stu-id="112fa-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="112fa-140">**Cascade**</span><span class="sxs-lookup"><span data-stu-id="112fa-140">**Cascade**</span></span>|<span data-ttu-id="112fa-141">接受或拒绝对子行的更改。</span><span class="sxs-lookup"><span data-stu-id="112fa-141">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="112fa-142">**无**</span><span class="sxs-lookup"><span data-stu-id="112fa-142">**None**</span></span>|<span data-ttu-id="112fa-143">对子行不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="112fa-143">Take no action on child rows.</span></span> <span data-ttu-id="112fa-144">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="112fa-144">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="112fa-145">示例</span><span class="sxs-lookup"><span data-stu-id="112fa-145">Example</span></span>  
 <span data-ttu-id="112fa-146">下面的示例创建一个 <xref:System.Data.ForeignKeyConstraint>，设置它的一些属性（包括 <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>），并将它添加到 <xref:System.Data.ConstraintCollection> 对象的 <xref:System.Data.DataTable>。</span><span class="sxs-lookup"><span data-stu-id="112fa-146">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="112fa-147">UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="112fa-147">UniqueConstraint</span></span>  
 <span data-ttu-id="112fa-148">**UniqueConstraint**对象，它可以分配到单个列或列中的数组**DataTable**，确保指定的列或列中的所有数据都是唯一每个行。</span><span class="sxs-lookup"><span data-stu-id="112fa-148">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="112fa-149">可以通过创建唯一约束列或一组列**UniqueConstraint**构造函数。</span><span class="sxs-lookup"><span data-stu-id="112fa-149">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="112fa-150">传递得到**UniqueConstraint**对象传递给**添加**表的方法**约束**属性，它是**ConstraintCollection**.</span><span class="sxs-lookup"><span data-stu-id="112fa-150">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="112fa-151">此外可以将构造函数自变量传递给的几个重载**外**方法**ConstraintCollection**创建**UniqueConstraint**。</span><span class="sxs-lookup"><span data-stu-id="112fa-151">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="112fa-152">创建时**UniqueConstraint**对于某一列或列，您可以选择指定的列是否为主键。</span><span class="sxs-lookup"><span data-stu-id="112fa-152">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="112fa-153">此外可以通过设置创建唯一约束的列**Unique**属性的列**true**。</span><span class="sxs-lookup"><span data-stu-id="112fa-153">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="112fa-154">或者，设置**Unique**到单个列的属性**false**删除可能存在的任何唯一约束。</span><span class="sxs-lookup"><span data-stu-id="112fa-154">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="112fa-155">如果将一列或多列定义为表的主键，会自动为一个或多个指定的列创建唯一的约束。</span><span class="sxs-lookup"><span data-stu-id="112fa-155">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="112fa-156">如果您删除某列从**PrimaryKey**的属性**DataTable**，则**UniqueConstraint**中删除。</span><span class="sxs-lookup"><span data-stu-id="112fa-156">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="112fa-157">下面的示例创建**UniqueConstraint**的两列**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="112fa-157">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="112fa-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="112fa-158">See also</span></span>

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [<span data-ttu-id="112fa-159">数据表架构定义</span><span class="sxs-lookup"><span data-stu-id="112fa-159">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="112fa-160">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="112fa-160">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="112fa-161">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="112fa-161">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

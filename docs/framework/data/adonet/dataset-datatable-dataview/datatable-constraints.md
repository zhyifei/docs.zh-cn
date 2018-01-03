---
title: "数据表约束"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3767467024d6c0d0dfbf1be8829d77ba3f7fa439
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="datatable-constraints"></a><span data-ttu-id="d10a1-102">数据表约束</span><span class="sxs-lookup"><span data-stu-id="d10a1-102">DataTable Constraints</span></span>
<span data-ttu-id="d10a1-103">为了维护数据的完整性，可以使用约束来对 <xref:System.Data.DataTable> 中的数据施加限制。</span><span class="sxs-lookup"><span data-stu-id="d10a1-103">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="d10a1-104">约束是应用于某列或相关各列的自动规则，它决定了某行的值以某种方式更改时的操作过程。</span><span class="sxs-lookup"><span data-stu-id="d10a1-104">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="d10a1-105">强制执行约束时`System.Data.DataSet.EnforceConstraints`属性<xref:System.Data.DataSet>是**true**。</span><span class="sxs-lookup"><span data-stu-id="d10a1-105">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="d10a1-106">有关显示如何设置 `EnforceConstraints` 属性的代码示例，请参见 <xref:System.Data.DataSet.EnforceConstraints%2A> 参考主题。</span><span class="sxs-lookup"><span data-stu-id="d10a1-106">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="d10a1-107">ADO.NET 中有两种约束：<xref:System.Data.ForeignKeyConstraint> 和 <xref:System.Data.UniqueConstraint>。</span><span class="sxs-lookup"><span data-stu-id="d10a1-107">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="d10a1-108">默认情况下，这两个约束时将自动创建创建通过添加两个或多个表之间的关系<xref:System.Data.DataRelation>到**数据集**。</span><span class="sxs-lookup"><span data-stu-id="d10a1-108">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="d10a1-109">但是，你可以禁用此行为通过指定**createConstraints** = **false**创建关系时。</span><span class="sxs-lookup"><span data-stu-id="d10a1-109">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="d10a1-110">ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="d10a1-110">ForeignKeyConstraint</span></span>  
 <span data-ttu-id="d10a1-111">A **ForeignKeyConstraint**强制执行有关如何传播更新和删除对相关表的规则。</span><span class="sxs-lookup"><span data-stu-id="d10a1-111">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="d10a1-112">例如，如果一个表的行中的值被更新或删除，并且该相同的值也采用一个或多个相关表， **ForeignKeyConstraint**确定相关表中会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="d10a1-112">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="d10a1-113"><xref:System.Data.ForeignKeyConstraint.DeleteRule%2A>和<xref:System.Data.ForeignKeyConstraint.UpdateRule%2A>属性**ForeignKeyConstraint**定义在用户尝试删除或更新相关表中的行时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d10a1-113">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="d10a1-114">下表描述可用于的不同设置**DeleteRule**和**UpdateRule**属性**ForeignKeyConstraint**。</span><span class="sxs-lookup"><span data-stu-id="d10a1-114">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="d10a1-115">规则设置</span><span class="sxs-lookup"><span data-stu-id="d10a1-115">Rule setting</span></span>|<span data-ttu-id="d10a1-116">描述</span><span class="sxs-lookup"><span data-stu-id="d10a1-116">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="d10a1-117">**级联**</span><span class="sxs-lookup"><span data-stu-id="d10a1-117">**Cascade**</span></span>|<span data-ttu-id="d10a1-118">删除或更新相关的行。</span><span class="sxs-lookup"><span data-stu-id="d10a1-118">Delete or update related rows.</span></span>|  
|<span data-ttu-id="d10a1-119">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="d10a1-119">**SetNull**</span></span>|<span data-ttu-id="d10a1-120">将值设置到相关行中**DBNull**。</span><span class="sxs-lookup"><span data-stu-id="d10a1-120">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="d10a1-121">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="d10a1-121">**SetDefault**</span></span>|<span data-ttu-id="d10a1-122">将相关行中的值设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="d10a1-122">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="d10a1-123">**无**</span><span class="sxs-lookup"><span data-stu-id="d10a1-123">**None**</span></span>|<span data-ttu-id="d10a1-124">对相关行不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="d10a1-124">Take no action on related rows.</span></span> <span data-ttu-id="d10a1-125">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="d10a1-125">This is the default.</span></span>|  
  
 <span data-ttu-id="d10a1-126">A **ForeignKeyConstraint**可以限制，并传播对相关列。</span><span class="sxs-lookup"><span data-stu-id="d10a1-126">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="d10a1-127">具体取决于对设置的属性**ForeignKeyConstraint**列值，如果**EnforceConstraints**属性**数据集**是**true**，执行对父行的某些操作将导致异常。</span><span class="sxs-lookup"><span data-stu-id="d10a1-127">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="d10a1-128">例如，如果**DeleteRule**属性**ForeignKeyConstraint**是**无**，无法删除父行，如果它具有任何子行。</span><span class="sxs-lookup"><span data-stu-id="d10a1-128">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="d10a1-129">你可以创建一组使用的列之间或单个列之间的外键约束**ForeignKeyConstraint**构造函数。</span><span class="sxs-lookup"><span data-stu-id="d10a1-129">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="d10a1-130">传递生成**ForeignKeyConstraint**对象传递给**添加**的表的方法**约束**属性，它是**ConstraintCollection**.</span><span class="sxs-lookup"><span data-stu-id="d10a1-130">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="d10a1-131">此外可以将构造函数自变量传递到几个重载**添加**方法**ConstraintCollection**创建**ForeignKeyConstraint**。</span><span class="sxs-lookup"><span data-stu-id="d10a1-131">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="d10a1-132">在创建时**ForeignKeyConstraint**，可以将传递**DeleteRule**和**UpdateRule**给构造函数的值作为自变量，或你可以将它们设置为作为中的属性以下示例 (其中**DeleteRule**值设置为**无**)。</span><span class="sxs-lookup"><span data-stu-id="d10a1-132">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
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
  
### <a name="acceptrejectrule"></a><span data-ttu-id="d10a1-133">AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="d10a1-133">AcceptRejectRule</span></span>  
 <span data-ttu-id="d10a1-134">可以使用接受对行的更改**AcceptChanges**方法或已取消使用**RejectChanges**方法**数据集**， **DataTable**，或**DataRow**。</span><span class="sxs-lookup"><span data-stu-id="d10a1-134">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="d10a1-135">当**数据集**包含**ForeignKeyConstraints**，则调用**AcceptChanges**或**RejectChanges**方法会强制**AcceptRejectRule**。</span><span class="sxs-lookup"><span data-stu-id="d10a1-135">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="d10a1-136">**AcceptRejectRule**属性**ForeignKeyConstraint**确定对子不会执行哪些操作时行**AcceptChanges**或**RejectChanges**对父行调用。</span><span class="sxs-lookup"><span data-stu-id="d10a1-136">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="d10a1-137">下表列出的可用设置**AcceptRejectRule**。</span><span class="sxs-lookup"><span data-stu-id="d10a1-137">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="d10a1-138">规则设置</span><span class="sxs-lookup"><span data-stu-id="d10a1-138">Rule setting</span></span>|<span data-ttu-id="d10a1-139">描述</span><span class="sxs-lookup"><span data-stu-id="d10a1-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="d10a1-140">**级联**</span><span class="sxs-lookup"><span data-stu-id="d10a1-140">**Cascade**</span></span>|<span data-ttu-id="d10a1-141">接受或拒绝对子行的更改。</span><span class="sxs-lookup"><span data-stu-id="d10a1-141">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="d10a1-142">**无**</span><span class="sxs-lookup"><span data-stu-id="d10a1-142">**None**</span></span>|<span data-ttu-id="d10a1-143">对子行不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="d10a1-143">Take no action on child rows.</span></span> <span data-ttu-id="d10a1-144">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="d10a1-144">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="d10a1-145">示例</span><span class="sxs-lookup"><span data-stu-id="d10a1-145">Example</span></span>  
 <span data-ttu-id="d10a1-146">下面的示例创建一个 <xref:System.Data.ForeignKeyConstraint>，设置它的一些属性（包括 <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>），并将它添加到 <xref:System.Data.ConstraintCollection> 对象的 <xref:System.Data.DataTable>。</span><span class="sxs-lookup"><span data-stu-id="d10a1-146">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="d10a1-147">UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="d10a1-147">UniqueConstraint</span></span>  
 <span data-ttu-id="d10a1-148">**UniqueConstraint**对象，可以对单个列或到数组中的列分配**DataTable**，确保指定的列或列中的所有数据都是唯一每行。</span><span class="sxs-lookup"><span data-stu-id="d10a1-148">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="d10a1-149">你可以通过创建唯一约束列或列数组**UniqueConstraint**构造函数。</span><span class="sxs-lookup"><span data-stu-id="d10a1-149">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="d10a1-150">传递生成**UniqueConstraint**对象传递给**添加**的表的方法**约束**属性，它是**ConstraintCollection**.</span><span class="sxs-lookup"><span data-stu-id="d10a1-150">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="d10a1-151">此外可以将构造函数自变量传递到几个重载**添加**方法**ConstraintCollection**创建**UniqueConstraint**。</span><span class="sxs-lookup"><span data-stu-id="d10a1-151">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="d10a1-152">在创建时**UniqueConstraint**对于某一列或列，你可以选择指定的列是否为主键。</span><span class="sxs-lookup"><span data-stu-id="d10a1-152">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="d10a1-153">你还可以通过设置来创建针对某一列的唯一约束**Unique**到列的属性**true**。</span><span class="sxs-lookup"><span data-stu-id="d10a1-153">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="d10a1-154">或者，设置**Unique**属性的单个列**false**删除可能存在的任何唯一约束。</span><span class="sxs-lookup"><span data-stu-id="d10a1-154">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="d10a1-155">如果将一列或多列定义为表的主键，会自动为一个或多个指定的列创建唯一的约束。</span><span class="sxs-lookup"><span data-stu-id="d10a1-155">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="d10a1-156">如果您删除某列从**PrimaryKey**属性**DataTable**、 **UniqueConstraint**中删除。</span><span class="sxs-lookup"><span data-stu-id="d10a1-156">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="d10a1-157">下面的示例创建**UniqueConstraint**的两列**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="d10a1-157">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d10a1-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="d10a1-158">See Also</span></span>  
 <xref:System.Data.DataRelation>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.ForeignKeyConstraint>  
 <xref:System.Data.UniqueConstraint>  
 [<span data-ttu-id="d10a1-159">数据表架构定义</span><span class="sxs-lookup"><span data-stu-id="d10a1-159">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="d10a1-160">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="d10a1-160">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="d10a1-161">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="d10a1-161">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

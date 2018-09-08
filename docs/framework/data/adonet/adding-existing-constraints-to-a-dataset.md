---
title: 将现有约束添加到数据集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 90aa1e5dceb3cac87d330837496b9dc467dc1876
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44132678"
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="61ddd-102">将现有约束添加到数据集</span><span class="sxs-lookup"><span data-stu-id="61ddd-102">Adding Existing Constraints to a DataSet</span></span>
<span data-ttu-id="61ddd-103">**填充**方法**DataAdapter**填充<xref:System.Data.DataSet>只使用表中的列和行从数据源; 但是约束通常设置数据源，**填充**方法不会添加到此架构信息**数据集**默认情况下。</span><span class="sxs-lookup"><span data-stu-id="61ddd-103">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="61ddd-104">若要填充**数据集**与现有主键约束信息从数据源，可以通过调用**FillSchema**方法**DataAdapter**，或设置**MissingSchemaAction**的属性**DataAdapter**到**AddWithKey**之前调用**填充**。</span><span class="sxs-lookup"><span data-stu-id="61ddd-104">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="61ddd-105">这将确保该主键中的约束**数据集**反映数据源。</span><span class="sxs-lookup"><span data-stu-id="61ddd-105">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="61ddd-106">外键约束信息不包含在内，必须显式创建，如中所示[数据表约束](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)。</span><span class="sxs-lookup"><span data-stu-id="61ddd-106">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="61ddd-107">添加到架构信息**数据集**用数据填充可确保主键约束所含之前<xref:System.Data.DataTable>中的对象**数据集**。</span><span class="sxs-lookup"><span data-stu-id="61ddd-107">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="61ddd-108">因此，当再次调用来填充**数据集**设为主要键列的信息用于匹配与当前行中每个数据源的新行**DataTable**，以及在当前数据使用数据源的数据覆盖表。</span><span class="sxs-lookup"><span data-stu-id="61ddd-108">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="61ddd-109">如果没有架构信息中，从数据源的新行追加到**数据集**，从而导致重复的行。</span><span class="sxs-lookup"><span data-stu-id="61ddd-109">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61ddd-110">如果数据源中的列被标识为自动递增**FillSchema**方法，或**填充**方法替换**MissingSchemaAction**的**AddWithKey**，创建**DataColumn**与**AutoIncrement**属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="61ddd-110">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="61ddd-111">但是，你将需要设置**AutoIncrementStep**并**AutoIncrementSeed**自己的值。</span><span class="sxs-lookup"><span data-stu-id="61ddd-111">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="61ddd-112">有关自动递增列的详细信息，请参阅[创建 AutoIncrement 列](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)。</span><span class="sxs-lookup"><span data-stu-id="61ddd-112">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
 <span data-ttu-id="61ddd-113">使用**FillSchema**或设置**MissingSchemaAction**到**AddWithKey**需要额外的处理，在数据源来确定主键列信息。</span><span class="sxs-lookup"><span data-stu-id="61ddd-113">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="61ddd-114">这一额外的处理可能会降低性能。</span><span class="sxs-lookup"><span data-stu-id="61ddd-114">This additional processing can hinder performance.</span></span> <span data-ttu-id="61ddd-115">如果主键信息在设计时已知，为了实现最佳性能，建议显式指定一个或多个主键列。</span><span class="sxs-lookup"><span data-stu-id="61ddd-115">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="61ddd-116">有关显式设置表的主键信息的信息，请参阅[定义主键](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)。</span><span class="sxs-lookup"><span data-stu-id="61ddd-116">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="61ddd-117">下面的代码示例演示如何将架构信息添加**数据集**使用**FillSchema**。</span><span class="sxs-lookup"><span data-stu-id="61ddd-117">The following code example shows how to add schema information to a **DataSet** using **FillSchema**.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 <span data-ttu-id="61ddd-118">下面的代码示例演示如何将架构信息添加**数据集**使用**MissingSchemaAction.AddWithKey**属性**填充**方法。</span><span class="sxs-lookup"><span data-stu-id="61ddd-118">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="61ddd-119">处理多个结果集</span><span class="sxs-lookup"><span data-stu-id="61ddd-119">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="61ddd-120">如果**DataAdapter**遇到多个结果集返回从**SelectCommand**，它将创建多个表中的**数据集**。</span><span class="sxs-lookup"><span data-stu-id="61ddd-120">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="61ddd-121">这些表提供的从零开始递增的默认名称**表** *N*，从开始**表**而不是"Table0"。</span><span class="sxs-lookup"><span data-stu-id="61ddd-121">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="61ddd-122">如果作为参数传递表名**FillSchema**方法，这些表将会提供的从零开始增量名称**TableName** *N*，从开始**TableName**而不是"TableName0"。</span><span class="sxs-lookup"><span data-stu-id="61ddd-122">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61ddd-123">如果**FillSchema**方法**OleDbDataAdapter**返回多个结果集的命令调用对象时，所返回的架构信息将从第一个结果集。</span><span class="sxs-lookup"><span data-stu-id="61ddd-123">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="61ddd-124">当返回架构信息的多个结果集使用**OleDbDataAdapter**，，则建议您指定**MissingSchemaAction**的**AddWithKey**并获取架构信息时调用**填充**方法。</span><span class="sxs-lookup"><span data-stu-id="61ddd-124">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ddd-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="61ddd-125">See Also</span></span>  
 [<span data-ttu-id="61ddd-126">DataAdapters 和 DataReaders</span><span class="sxs-lookup"><span data-stu-id="61ddd-126">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="61ddd-127">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="61ddd-127">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="61ddd-128">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="61ddd-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="61ddd-129">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="61ddd-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

---
title: DataAdapter 数据表和 DataColumn 映射
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 6380dd0512bd7834f50b87f90f445cb01b7a8b95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151554"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="aae75-102">DataAdapter 数据表和 DataColumn 映射</span><span class="sxs-lookup"><span data-stu-id="aae75-102">DataAdapter DataTable and DataColumn Mappings</span></span>
<span data-ttu-id="aae75-103">**DataAdapter**在其**表映射**属性中包含零个或多个<xref:System.Data.Common.DataTableMapping>对象的集合。</span><span class="sxs-lookup"><span data-stu-id="aae75-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="aae75-104">**DataTableMapping**在从针对数据源的查询返回的数据和 之间提供主映射<xref:System.Data.DataTable>。</span><span class="sxs-lookup"><span data-stu-id="aae75-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="aae75-105">**数据表映射**名称可以代替**数据表**名称传递给**数据适配器**的**填充**方法。</span><span class="sxs-lookup"><span data-stu-id="aae75-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="aae75-106">下面的示例为 **"作者"** 表创建名为 **"作者映射"\*\*\*\*的数据表映射**。</span><span class="sxs-lookup"><span data-stu-id="aae75-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="aae75-107">**DataTable 映射**使您能够在**DataTable**中使用与数据库中不同的列名称。</span><span class="sxs-lookup"><span data-stu-id="aae75-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="aae75-108">**数据适配器**在更新表时使用映射与列匹配。</span><span class="sxs-lookup"><span data-stu-id="aae75-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="aae75-109">如果在调用**DataAdapter**的**填充**或**更新**方法时未指定**表名**或**DataTable 映射**名称，**则数据适配器**将查找名为"表"**的数据表映射**。</span><span class="sxs-lookup"><span data-stu-id="aae75-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="aae75-110">如果**数据表映射**不存在，**则数据表**的**表名称**为"表"。</span><span class="sxs-lookup"><span data-stu-id="aae75-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="aae75-111">您可以通过创建名称为"表"**的数据表映射**来指定默认**数据表映射**。</span><span class="sxs-lookup"><span data-stu-id="aae75-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="aae75-112">以下代码示例创建**DataTable 映射**（从<xref:System.Data.Common>命名空间），并通过将其命名为"表"使其成为指定**DataAdapter**的默认映射。</span><span class="sxs-lookup"><span data-stu-id="aae75-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="aae75-113">然后，该示例将查询结果中的第一个表（**北风**数据库**的客户**表）中的列映射到<xref:System.Data.DataSet>中的**北风客户**表中的一组更用户友好的名称。</span><span class="sxs-lookup"><span data-stu-id="aae75-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="aae75-114">对于未映射的列，将使用数据源中的列名称。</span><span class="sxs-lookup"><span data-stu-id="aae75-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 <span data-ttu-id="aae75-115">在更高级的情况下，您可以决定希望相同的**DataAdapter**支持使用不同的映射加载不同的表。</span><span class="sxs-lookup"><span data-stu-id="aae75-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="aae75-116">为此，只需添加其他**DataTable 映射**对象即可。</span><span class="sxs-lookup"><span data-stu-id="aae75-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="aae75-117">当**填充**方法传递**DataSet**实例和**DataTable 映射**名称时，如果存在具有该名称的映射，则使用该映射;如果使用填充方法。否则，将使用具有该名称**的数据表**。</span><span class="sxs-lookup"><span data-stu-id="aae75-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="aae75-118">以下示例创建一个**数据表映射**，其名称为**客户**，数据**表**名称为**BizTalkSchema**。</span><span class="sxs-lookup"><span data-stu-id="aae75-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="aae75-119">然后，该示例将 SELECT 语句返回的行映射到**BizTalkSchema** **数据表**。</span><span class="sxs-lookup"><span data-stu-id="aae75-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
> <span data-ttu-id="aae75-120">如果没有为列映射提供源列名称或者没有为表映射提供源表名称，则将自动生成默认名称。</span><span class="sxs-lookup"><span data-stu-id="aae75-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="aae75-121">如果未为列映射提供源列，则为列映射指定一个增量默认名称**SourceColumn** *N，* 从**SourceColumn1**开始。</span><span class="sxs-lookup"><span data-stu-id="aae75-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="aae75-122">如果表映射未提供源表名称，则表映射将给出**源表** *N*的增量默认名称，从**SourceTable1**开始。</span><span class="sxs-lookup"><span data-stu-id="aae75-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aae75-123">我们建议您避免为列映射而避免**SourceColumn** *N*的命名约定，或者为表映射保留**SourceTable** *N，* 因为提供的名称可能与**DataTableMapping 集合**中的**列映射集合**或表映射名称中的现有默认列映射名称冲突。</span><span class="sxs-lookup"><span data-stu-id="aae75-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="aae75-124">如果提供的名称已经存在，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="aae75-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="aae75-125">处理多个结果集</span><span class="sxs-lookup"><span data-stu-id="aae75-125">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="aae75-126">如果**SelectCommand**返回多个表，**则填充**将自动生成具有**DataSet**中表的增量值的表名称，从指定的表名称开始，并在表**Name** *N*窗体中继续，从**表Name1**开始。</span><span class="sxs-lookup"><span data-stu-id="aae75-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="aae75-127">可以使用表映射将自动生成的表名称映射到您希望在**DataSet**中为表指定的名称。</span><span class="sxs-lookup"><span data-stu-id="aae75-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="aae75-128">例如，对于返回两个表"**客户**和**订单**"的**SelectCommand，** 发出以下调用**Fill**。</span><span class="sxs-lookup"><span data-stu-id="aae75-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 <span data-ttu-id="aae75-129">在**DataSet**中创建了两个表：**客户**和**客户1**。</span><span class="sxs-lookup"><span data-stu-id="aae75-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="aae75-130">可以使用表映射来确保第二个表名为 **"订单"** 而不是 **"客户1"。**</span><span class="sxs-lookup"><span data-stu-id="aae75-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="aae75-131">为此，将**客户 1**的源表映射到**DataSet**表**订单**，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="aae75-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a><span data-ttu-id="aae75-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aae75-132">See also</span></span>

- [<span data-ttu-id="aae75-133">DataAdapters 和 DataReaders</span><span class="sxs-lookup"><span data-stu-id="aae75-133">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="aae75-134">在 ADO.NET 中检索和修改数据</span><span class="sxs-lookup"><span data-stu-id="aae75-134">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="aae75-135">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="aae75-135">ADO.NET Overview</span></span>](ado-net-overview.md)

---
title: "创建数据表"
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
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 94fa5507d71fef557baadc6ee8979efeee4acf40
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="creating-a-datatable"></a><span data-ttu-id="1c3f6-102">创建数据表</span><span class="sxs-lookup"><span data-stu-id="1c3f6-102">Creating a DataTable</span></span>
<span data-ttu-id="1c3f6-103"><xref:System.Data.DataTable> 表示一个内存内关系数据的表，可以独立创建和使用，也可以由其他 .NET Framework 对象使用，最常见的情况是作为 <xref:System.Data.DataSet> 的成员使用。</span><span class="sxs-lookup"><span data-stu-id="1c3f6-103">A <xref:System.Data.DataTable>, which represents one table of in-memory relational data, can be created and used independently, or can be used by other .NET Framework objects, most commonly as a member of a <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="1c3f6-104">你可以创建**DataTable**对象使用合适的**DataTable**构造函数。</span><span class="sxs-lookup"><span data-stu-id="1c3f6-104">You can create a **DataTable** object by using the appropriate **DataTable** constructor.</span></span> <span data-ttu-id="1c3f6-105">你可以将其添加到**数据集**使用**添加**方法以将其添加到**DataTable**对象的**表**集合。</span><span class="sxs-lookup"><span data-stu-id="1c3f6-105">You can add it to the **DataSet** by using the **Add** method to add it to the **DataTable** object's **Tables** collection.</span></span>  
  
 <span data-ttu-id="1c3f6-106">你还可以创建**DataTable**对象内**数据集**使用**填充**或**FillSchema**方法**DataAdapter**对象，或从预定义或推断 XML 架构使用**ReadXml**， **ReadXmlSchema**，或**InferXmlSchema**方法的**数据集**。</span><span class="sxs-lookup"><span data-stu-id="1c3f6-106">You can also create **DataTable** objects within a **DataSet** by using the **Fill** or **FillSchema** methods of the **DataAdapter** object, or from a predefined or inferred XML schema using the **ReadXml**, **ReadXmlSchema**, or **InferXmlSchema** methods of the **DataSet**.</span></span> <span data-ttu-id="1c3f6-107">请注意，添加之后**DataTable**作为的成员**表**的一个集合**数据集**，不能将其添加到的任何其他表集合**数据集**。</span><span class="sxs-lookup"><span data-stu-id="1c3f6-107">Note that after you have added a **DataTable** as a member of the **Tables** collection of one **DataSet**, you cannot add it to the collection of tables of any other **DataSet**.</span></span>  
  
 <span data-ttu-id="1c3f6-108">当你首次创建**DataTable**，它不具有架构 （即结构）。</span><span class="sxs-lookup"><span data-stu-id="1c3f6-108">When you first create a **DataTable**, it does not have a schema (that is, a structure).</span></span> <span data-ttu-id="1c3f6-109">若要定义表的架构，必须创建并添加<xref:System.Data.DataColumn>对象添加到**列**表的集合。</span><span class="sxs-lookup"><span data-stu-id="1c3f6-109">To define the schema of the table, you must create and add <xref:System.Data.DataColumn> objects to the **Columns** collection of the table.</span></span> <span data-ttu-id="1c3f6-110">此外可以定义主键列对于表，并创建并添加**约束**对象添加到**约束**表的集合。</span><span class="sxs-lookup"><span data-stu-id="1c3f6-110">You can also define a primary key column for the table, and create and add **Constraint** objects to the **Constraints** collection of the table.</span></span> <span data-ttu-id="1c3f6-111">在定义的架构后**DataTable**，您可以通过添加行数据添加到表**DataRow**对象添加到**行**表的集合。</span><span class="sxs-lookup"><span data-stu-id="1c3f6-111">After you have defined the schema for a **DataTable**, you can add rows of data to the table by adding **DataRow** objects to the **Rows** collection of the table.</span></span>  
  
 <span data-ttu-id="1c3f6-112">不要求你提供的值<xref:System.Data.DataTable.TableName%2A>属性在创建时**DataTable**; 你可以在另一个时，指定该属性，或者可以将它保留为空。</span><span class="sxs-lookup"><span data-stu-id="1c3f6-112">You are not required to supply a value for the <xref:System.Data.DataTable.TableName%2A> property when you create a **DataTable**; you can specify the property at another time, or you can leave it empty.</span></span> <span data-ttu-id="1c3f6-113">但是，当你添加不包含的表时，才**TableName**值赋给**数据集**，表将给定表的递增的默认名称*N*，第一页为 Table0"表"。</span><span class="sxs-lookup"><span data-stu-id="1c3f6-113">However, when you add a table without a **TableName** value to a **DataSet**, the table will be given an incremental default name of Table*N*, starting with "Table" for Table0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c3f6-114">我们建议你避免"表*N*"命名约定，如果你提供**TableName**值，因为所提供的名称可能与中的现有默认表名称发生冲突**数据集**.</span><span class="sxs-lookup"><span data-stu-id="1c3f6-114">We recommend that you avoid the "Table*N*" naming convention when you supply a **TableName** value, because the name you supply may conflict with an existing default table name in the **DataSet**.</span></span> <span data-ttu-id="1c3f6-115">如果提供的名称已经存在，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="1c3f6-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="1c3f6-116">下面的示例创建的实例**DataTable**对象并将其分配的名称"Customers。</span><span class="sxs-lookup"><span data-stu-id="1c3f6-116">The following example creates an instance of a **DataTable** object and assigns it the name "Customers."</span></span>  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 <span data-ttu-id="1c3f6-117">下面的示例创建的实例**DataTable**通过将其添加到**表**集合**数据集**。</span><span class="sxs-lookup"><span data-stu-id="1c3f6-117">The following example creates an instance of a **DataTable** by adding it to the **Tables** collection of a **DataSet**.</span></span>  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c3f6-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c3f6-118">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataTableCollection>  
 [<span data-ttu-id="1c3f6-119">数据表</span><span class="sxs-lookup"><span data-stu-id="1c3f6-119">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="1c3f6-120">从 DataAdapter 填充数据集</span><span class="sxs-lookup"><span data-stu-id="1c3f6-120">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [<span data-ttu-id="1c3f6-121">从 XML 加载数据集</span><span class="sxs-lookup"><span data-stu-id="1c3f6-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="1c3f6-122">从 XML 加载数据集构架信息</span><span class="sxs-lookup"><span data-stu-id="1c3f6-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="1c3f6-123">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="1c3f6-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

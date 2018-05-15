---
title: 向数据表添加列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 8ee47ddce273e564673d96d2b2e276b68879373f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="adding-columns-to-a-datatable"></a><span data-ttu-id="43b05-102">向数据表添加列</span><span class="sxs-lookup"><span data-stu-id="43b05-102">Adding Columns to a DataTable</span></span>
<span data-ttu-id="43b05-103">A<xref:System.Data.DataTable>包含一套<xref:System.Data.DataColumn>所引用的对象**列**的表的属性。</span><span class="sxs-lookup"><span data-stu-id="43b05-103">A <xref:System.Data.DataTable> contains a collection of <xref:System.Data.DataColumn> objects referenced by the **Columns** property of the table.</span></span> <span data-ttu-id="43b05-104">这个列的集合与任何约束一起定义表的架构（即结构）。</span><span class="sxs-lookup"><span data-stu-id="43b05-104">This collection of columns, along with any constraints, defines the schema, or structure, of the table.</span></span>  
  
 <span data-ttu-id="43b05-105">你创建**DataColumn**通过使用表中的对象**DataColumn**构造函数，或通过调用**添加**方法**列**属性表，这是<xref:System.Data.DataColumnCollection>。</span><span class="sxs-lookup"><span data-stu-id="43b05-105">You create **DataColumn** objects within a table by using the **DataColumn** constructor, or by calling the **Add** method of the **Columns** property of the table, which is a <xref:System.Data.DataColumnCollection>.</span></span> <span data-ttu-id="43b05-106">**添加**方法将接受可选**ColumnName**， **DataType**，和**表达式**自变量，并创建新**DataColumn**作为集合的成员。</span><span class="sxs-lookup"><span data-stu-id="43b05-106">The **Add** method accepts optional **ColumnName**, **DataType**, and **Expression** arguments and creates a new **DataColumn** as a member of the collection.</span></span> <span data-ttu-id="43b05-107">它还会接受现有**DataColumn**对象并将其添加到集合，并返回对所添加的引用**DataColumn**如果请求。</span><span class="sxs-lookup"><span data-stu-id="43b05-107">It also accepts an existing **DataColumn** object and adds it to the collection, and returns a reference to the added **DataColumn** if requested.</span></span> <span data-ttu-id="43b05-108">因为**DataTable**对象不是特定于任何数据源、 指定的数据类型时使用.NET Framework 类型**DataColumn**。</span><span class="sxs-lookup"><span data-stu-id="43b05-108">Because **DataTable** objects are not specific to any data source, .NET Framework types are used when specifying the data type of a **DataColumn**.</span></span>  
  
 <span data-ttu-id="43b05-109">下面的示例将添加到四个列**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="43b05-109">The following example adds four columns to a **DataTable**.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 <span data-ttu-id="43b05-110">在示例中，请注意，属性**CustID**列设置为不允许**DBNull**值并将值是唯一约束。</span><span class="sxs-lookup"><span data-stu-id="43b05-110">In the example, notice that the properties for the **CustID** column are set to not allow **DBNull** values and to constrain values to be unique.</span></span> <span data-ttu-id="43b05-111">但是，如果你定义**CustID**为主密钥列的表、 列**AllowDBNull**属性将自动设置为**false**和**Unique**属性将自动设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="43b05-111">However, if you define the **CustID** column as the primary key column of the table, the **AllowDBNull** property will automatically be set to **false** and the **Unique** property will automatically be set to **true**.</span></span> <span data-ttu-id="43b05-112">有关详细信息，请参阅[定义主键](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)。</span><span class="sxs-lookup"><span data-stu-id="43b05-112">For more information, see [Defining Primary Keys](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="43b05-113">如果列名称未提供的列，该列会得到递增的默认名称的列*N，* 从"Column1"开始，当它添加到**DataColumnCollection**。</span><span class="sxs-lookup"><span data-stu-id="43b05-113">If a column name is not supplied for a column, the column is given an incremental default name of Column*N,* starting with "Column1", when it is added to the **DataColumnCollection**.</span></span> <span data-ttu-id="43b05-114">我们建议你避免的命名约定"列*N*"时提供的列名，因为提供的名称可能与中的现有默认列名称相冲突**DataColumnCollection**。</span><span class="sxs-lookup"><span data-stu-id="43b05-114">We recommend that you avoid the naming convention of "Column*N*" when you supply a column name, because the name you supply may conflict with an existing default column name in the **DataColumnCollection**.</span></span> <span data-ttu-id="43b05-115">如果提供的名称已经存在，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="43b05-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="43b05-116">如果将 <xref:System.Xml.Linq.XElement> 用作 <xref:System.Data.DataColumn.DataType%2A> 中的 <xref:System.Data.DataColumn> 的 <xref:System.Data.DataTable>，则在读入数据时，XML 序列化将不起作用。</span><span class="sxs-lookup"><span data-stu-id="43b05-116">If you are using <xref:System.Xml.Linq.XElement> as the <xref:System.Data.DataColumn.DataType%2A> of a <xref:System.Data.DataColumn> in the <xref:System.Data.DataTable>, XML serialization will not work when you read in data.</span></span> <span data-ttu-id="43b05-117">例如，如果通过使用 <xref:System.Xml.XmlDocument> 方法来写出 `DataTable.WriteXml`，则在序列化为 XML 时，<xref:System.Xml.Linq.XElement> 中会出现一个额外的父节点。</span><span class="sxs-lookup"><span data-stu-id="43b05-117">For example, if you write out a <xref:System.Xml.XmlDocument> by using the `DataTable.WriteXml` method, upon serialization to XML there is an additional parent node in the <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="43b05-118">若要解决此问题，请使用 <xref:System.Data.SqlTypes.SqlXml> 类型来代替 <xref:System.Xml.Linq.XElement>。</span><span class="sxs-lookup"><span data-stu-id="43b05-118">To work around this problem, use the <xref:System.Data.SqlTypes.SqlXml> type instead of <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="43b05-119">`ReadXml` 和 `WriteXml` 对 <xref:System.Data.SqlTypes.SqlXml> 均能正确使用。</span><span class="sxs-lookup"><span data-stu-id="43b05-119">`ReadXml` and `WriteXml` work correctly with <xref:System.Data.SqlTypes.SqlXml>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b05-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="43b05-120">See Also</span></span>  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataTable>  
 [<span data-ttu-id="43b05-121">数据表架构定义</span><span class="sxs-lookup"><span data-stu-id="43b05-121">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [<span data-ttu-id="43b05-122">数据表</span><span class="sxs-lookup"><span data-stu-id="43b05-122">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="43b05-123">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="43b05-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

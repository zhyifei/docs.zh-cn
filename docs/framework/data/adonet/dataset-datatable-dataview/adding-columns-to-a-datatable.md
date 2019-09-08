---
title: 向数据表添加列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 6e0dcd819dc354e1fd23b244692dff5091142004
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784853"
---
# <a name="adding-columns-to-a-datatable"></a><span data-ttu-id="effa1-102">向数据表添加列</span><span class="sxs-lookup"><span data-stu-id="effa1-102">Adding Columns to a DataTable</span></span>
<span data-ttu-id="effa1-103">包含由表的**Columns**属性引用的对象的<xref:System.Data.DataColumn>集合。 <xref:System.Data.DataTable></span><span class="sxs-lookup"><span data-stu-id="effa1-103">A <xref:System.Data.DataTable> contains a collection of <xref:System.Data.DataColumn> objects referenced by the **Columns** property of the table.</span></span> <span data-ttu-id="effa1-104">这个列的集合与任何约束一起定义表的架构（即结构）。</span><span class="sxs-lookup"><span data-stu-id="effa1-104">This collection of columns, along with any constraints, defines the schema, or structure, of the table.</span></span>  
  
 <span data-ttu-id="effa1-105">您可以使用**DataColumn**构造函数在表中创建**DataColumn**对象，或调用表的**Columns**属性的<xref:System.Data.DataColumnCollection> **Add**方法（即）。</span><span class="sxs-lookup"><span data-stu-id="effa1-105">You create **DataColumn** objects within a table by using the **DataColumn** constructor, or by calling the **Add** method of the **Columns** property of the table, which is a <xref:System.Data.DataColumnCollection>.</span></span> <span data-ttu-id="effa1-106">**Add**方法接受可选的**ColumnName**、 **DataType**和**Expression**参数，并创建新的**DataColumn**作为集合的成员。</span><span class="sxs-lookup"><span data-stu-id="effa1-106">The **Add** method accepts optional **ColumnName**, **DataType**, and **Expression** arguments and creates a new **DataColumn** as a member of the collection.</span></span> <span data-ttu-id="effa1-107">它还接受现有**DataColumn**对象并将其添加到集合中，并返回对添加的**datacolumn**的引用（如果请求）。</span><span class="sxs-lookup"><span data-stu-id="effa1-107">It also accepts an existing **DataColumn** object and adds it to the collection, and returns a reference to the added **DataColumn** if requested.</span></span> <span data-ttu-id="effa1-108">因为**DataTable**对象不特定于任何数据源，所以在指定**DataColumn**的数据类型时，将使用 .NET Framework 类型。</span><span class="sxs-lookup"><span data-stu-id="effa1-108">Because **DataTable** objects are not specific to any data source, .NET Framework types are used when specifying the data type of a **DataColumn**.</span></span>  
  
 <span data-ttu-id="effa1-109">下面的示例将四列添加到**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="effa1-109">The following example adds four columns to a **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="effa1-110">在此示例中，请注意， **CustID**列的属性设置为不允许**DBNull**值并将值限制为唯一。</span><span class="sxs-lookup"><span data-stu-id="effa1-110">In the example, notice that the properties for the **CustID** column are set to not allow **DBNull** values and to constrain values to be unique.</span></span> <span data-ttu-id="effa1-111">但是，如果将**CustID**列定义为表的主键列，则**AllowDBNull**属性将自动设置为**false** ，并且**Unique**属性将自动设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="effa1-111">However, if you define the **CustID** column as the primary key column of the table, the **AllowDBNull** property will automatically be set to **false** and the **Unique** property will automatically be set to **true**.</span></span> <span data-ttu-id="effa1-112">有关详细信息，请参阅[定义主键](defining-primary-keys.md)。</span><span class="sxs-lookup"><span data-stu-id="effa1-112">For more information, see [Defining Primary Keys](defining-primary-keys.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="effa1-113">如果没有为列提供列名称，则在将列添加到**DataColumnCollection**时，将为该列指定递增的默认名称 *（* 以 "Column1" 开头）。</span><span class="sxs-lookup"><span data-stu-id="effa1-113">If a column name is not supplied for a column, the column is given an incremental default name of Column*N,* starting with "Column1", when it is added to the **DataColumnCollection**.</span></span> <span data-ttu-id="effa1-114">建议在提供列名时避免使用 "Column*N*" 命名约定，因为所提供的名称可能与**DataColumnCollection**中现有的默认列名冲突。</span><span class="sxs-lookup"><span data-stu-id="effa1-114">We recommend that you avoid the naming convention of "Column*N*" when you supply a column name, because the name you supply may conflict with an existing default column name in the **DataColumnCollection**.</span></span> <span data-ttu-id="effa1-115">如果提供的名称已经存在，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="effa1-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="effa1-116">如果将 <xref:System.Xml.Linq.XElement> 用作 <xref:System.Data.DataColumn.DataType%2A> 中的 <xref:System.Data.DataColumn> 的 <xref:System.Data.DataTable>，则在读入数据时，XML 序列化将不起作用。</span><span class="sxs-lookup"><span data-stu-id="effa1-116">If you are using <xref:System.Xml.Linq.XElement> as the <xref:System.Data.DataColumn.DataType%2A> of a <xref:System.Data.DataColumn> in the <xref:System.Data.DataTable>, XML serialization will not work when you read in data.</span></span> <span data-ttu-id="effa1-117">例如，如果通过使用 <xref:System.Xml.XmlDocument> 方法来写出 `DataTable.WriteXml`，则在序列化为 XML 时，<xref:System.Xml.Linq.XElement> 中会出现一个额外的父节点。</span><span class="sxs-lookup"><span data-stu-id="effa1-117">For example, if you write out a <xref:System.Xml.XmlDocument> by using the `DataTable.WriteXml` method, upon serialization to XML there is an additional parent node in the <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="effa1-118">若要解决此问题，请使用 <xref:System.Data.SqlTypes.SqlXml> 类型来代替 <xref:System.Xml.Linq.XElement>。</span><span class="sxs-lookup"><span data-stu-id="effa1-118">To work around this problem, use the <xref:System.Data.SqlTypes.SqlXml> type instead of <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="effa1-119">`ReadXml` 和 `WriteXml` 对 <xref:System.Data.SqlTypes.SqlXml> 均能正确使用。</span><span class="sxs-lookup"><span data-stu-id="effa1-119">`ReadXml` and `WriteXml` work correctly with <xref:System.Data.SqlTypes.SqlXml>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="effa1-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="effa1-120">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="effa1-121">数据表架构定义</span><span class="sxs-lookup"><span data-stu-id="effa1-121">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="effa1-122">数据表</span><span class="sxs-lookup"><span data-stu-id="effa1-122">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="effa1-123">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="effa1-123">ADO.NET Overview</span></span>](../ado-net-overview.md)

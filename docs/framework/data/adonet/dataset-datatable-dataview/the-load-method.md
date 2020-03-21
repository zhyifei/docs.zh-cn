---
title: 加载方法
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
ms.openlocfilehash: f1c819333225c22efb85946001a1fc8340d57989
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150722"
---
# <a name="the-load-method"></a><span data-ttu-id="d7432-102">加载方法</span><span class="sxs-lookup"><span data-stu-id="d7432-102">The Load Method</span></span>
<span data-ttu-id="d7432-103">可以使用 <xref:System.Data.DataTable.Load%2A> 方法为 <xref:System.Data.DataTable> 加载数据源中行。</span><span class="sxs-lookup"><span data-stu-id="d7432-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="d7432-104">这是一个重载方法，其最简单的形式是接受单个参数 **，即 DataReader**。</span><span class="sxs-lookup"><span data-stu-id="d7432-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="d7432-105">在此窗体中，它只需使用行加载**DataTable**即可。</span><span class="sxs-lookup"><span data-stu-id="d7432-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="d7432-106">或者，您可以指定**LoadOption**参数来控制将数据添加到**DataTable**中的方式。</span><span class="sxs-lookup"><span data-stu-id="d7432-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="d7432-107">**LoadOption**参数在**DataTable**已包含数据行的情况下特别有用，因为它描述了数据源的传入数据如何与表中已有的数据组合。</span><span class="sxs-lookup"><span data-stu-id="d7432-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="d7432-108">例如，**保留当前值**（默认值）指定在**数据表中**将行标记为 **"已添加**"的情况下，**原始**值或每列将设置为数据源中匹配行的内容。</span><span class="sxs-lookup"><span data-stu-id="d7432-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="d7432-109">"**当前**"值将保留添加行时分配的值，行的**RowState**将设置为 **"已更改**"。</span><span class="sxs-lookup"><span data-stu-id="d7432-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="d7432-110">下表给出了对 <xref:System.Data.LoadOption> 枚举值的简要说明。</span><span class="sxs-lookup"><span data-stu-id="d7432-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="d7432-111">LoadOption 值</span><span class="sxs-lookup"><span data-stu-id="d7432-111">LoadOption value</span></span>|<span data-ttu-id="d7432-112">说明</span><span class="sxs-lookup"><span data-stu-id="d7432-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="d7432-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="d7432-113">**OverwriteRow**</span></span>|<span data-ttu-id="d7432-114">如果传入行具有与**DataTable**中已有的行相同的**主键**值，则每列**的原始**值和**当前**值将替换为传入行中的值，并且**RowState**属性设置为 **"未更改**"。</span><span class="sxs-lookup"><span data-stu-id="d7432-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="d7432-115">**数据表中**不存在的数据源中的行添加的**RowState**值**为"未更改**"。</span><span class="sxs-lookup"><span data-stu-id="d7432-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="d7432-116">此选项实际上刷新**了 DataTable**的内容，以便它与数据源的内容匹配。</span><span class="sxs-lookup"><span data-stu-id="d7432-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="d7432-117">**PreserveCurrentValues（默认值）**</span><span class="sxs-lookup"><span data-stu-id="d7432-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="d7432-118">如果传入行具有与**DataTable**中已有的行相同的**主键**值，则**原始**值将设置为传入行的内容，并且不会更改 **"当前"** 值。</span><span class="sxs-lookup"><span data-stu-id="d7432-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="d7432-119">如果 **"行状态**已**添加**或**修改**"，则将其设置为 **"已修改**"。</span><span class="sxs-lookup"><span data-stu-id="d7432-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="d7432-120">如果**RowState** **已删除**，则保留**为 "已删除**"。</span><span class="sxs-lookup"><span data-stu-id="d7432-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="d7432-121">将添加**DataTable**中不存在的数据源中的行，并将**RowState**设置为 **"未更改**"。</span><span class="sxs-lookup"><span data-stu-id="d7432-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="d7432-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="d7432-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="d7432-123">如果传入行具有与**DataTable**中已有的行相同的**主键**值，则**当前**值将复制到**原始**值，然后将 **"当前**"值设置为传入行的内容。</span><span class="sxs-lookup"><span data-stu-id="d7432-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="d7432-124">如果**已添加** **DataTable**中的**行状态**，则 **"行状态**"将保持**已添加**。</span><span class="sxs-lookup"><span data-stu-id="d7432-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="d7432-125">对于标记为 **"已修改**或删除"**的**行，将**修改\*\*\*\*"行状态**"。</span><span class="sxs-lookup"><span data-stu-id="d7432-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="d7432-126">将添加**DataTable**中不存在的数据源中的行，并将**RowState**设置为 **"已添加**"。</span><span class="sxs-lookup"><span data-stu-id="d7432-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="d7432-127">以下示例使用**Load**方法显示**Northwind**数据库中员工的生日列表。</span><span class="sxs-lookup"><span data-stu-id="d7432-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
```vb  
Private Sub LoadBirthdays(ByVal connectionString As String)  
    ' Assumes that connectionString is a valid connection string  
    ' to the Northwind database on SQL Server.  
    Dim queryString As String = _  
    "SELECT LastName, FirstName, BirthDate " & _  
      " FROM dbo.Employees " & _  
      "ORDER BY BirthDate, LastName, FirstName"  
  
    ' Open and fill a DataSet.
    Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
        queryString, connectionString)  
    Dim employees As New DataSet  
    adapter.Fill(employees, "Employees")  
  
    ' Create a SqlDataReader for use with the Load Method.  
    Dim reader As DataTableReader = employees.GetDataReader()  
  
    ' Create an instance of DataTable and assign the first  
    ' DataTable in the DataSet.Tables collection to it.  
    Dim dataTableEmp As DataTable = employees.Tables(0)  
  
    ' Fill the DataTable with data by calling Load and  
    ' passing the SqlDataReader.  
    dataTableEmp.Load(reader, LoadOption.OverwriteRow)  
  
    ' Loop through the rows collection and display the values  
    ' in the console window.  
    Dim employeeRow As DataRow  
    For Each employeeRow In dataTableEmp.Rows  
        Console.WriteLine("{0:MM\\dd\\yyyy}" & ControlChars.Tab & _  
          "{1}, {2}", _  
          employeeRow("BirthDate"), _  
          employeeRow("LastName"), _  
          employeeRow("FirstName"))  
    Next employeeRow  
  
    ' Keep the window opened to view the contents.  
    Console.ReadLine()  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7432-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7432-128">See also</span></span>

- [<span data-ttu-id="d7432-129">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="d7432-129">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="d7432-130">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="d7432-130">ADO.NET Overview</span></span>](../ado-net-overview.md)

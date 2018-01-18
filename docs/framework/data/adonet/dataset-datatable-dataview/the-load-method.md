---
title: "加载方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
ms.assetid: e22e5812-89c6-41f0-9302-bb899a46dbff
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a54eda8d96468d4506a5f7dafc342fa5ff128c2a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="the-load-method"></a><span data-ttu-id="a32d3-102">加载方法</span><span class="sxs-lookup"><span data-stu-id="a32d3-102">The Load Method</span></span>
<span data-ttu-id="a32d3-103">可以使用 <xref:System.Data.DataTable.Load%2A> 方法为 <xref:System.Data.DataTable> 加载数据源中行。</span><span class="sxs-lookup"><span data-stu-id="a32d3-103">You can use the <xref:System.Data.DataTable.Load%2A> method to load a <xref:System.Data.DataTable> with rows from a data source.</span></span> <span data-ttu-id="a32d3-104">这是重载的方法，其最简单的形式，接受一个参数， **DataReader**。</span><span class="sxs-lookup"><span data-stu-id="a32d3-104">This is an overloaded method which, in its simplest form, accepts a single parameter, a **DataReader**.</span></span> <span data-ttu-id="a32d3-105">在这种形式，它只需加载**DataTable**行。</span><span class="sxs-lookup"><span data-stu-id="a32d3-105">In this form, it simply loads the **DataTable** with rows.</span></span> <span data-ttu-id="a32d3-106">或者，可以指定**LoadOption**参数，用于控制如何将数据添加到**DataTable**。</span><span class="sxs-lookup"><span data-stu-id="a32d3-106">Optionally, you can specify the **LoadOption** parameter to control how data is added to the **DataTable**.</span></span>  
  
 <span data-ttu-id="a32d3-107">**LoadOption**参数会在情况下特别有用其中**DataTable**已包含的数据行，因为它说明了如何传入数据从数据源都将合并的数据已在表中。</span><span class="sxs-lookup"><span data-stu-id="a32d3-107">The **LoadOption** parameter is particularly useful in cases where the **DataTable** already contains rows of data, because it describes how incoming data from the data source will be combined with the data already in the table.</span></span> <span data-ttu-id="a32d3-108">例如， **PreserveCurrentValues** （默认） 指定在其中将行标记为的情况下**Added**中**DataTable**、**原始**值或每个列设置为匹配的行的内容从数据源。</span><span class="sxs-lookup"><span data-stu-id="a32d3-108">For example, **PreserveCurrentValues** (the default) specifies that in cases where a row is marked as **Added** in the **DataTable**, the **Original** value or each column is set to the contents of the matching row from the data source.</span></span> <span data-ttu-id="a32d3-109">**当前**值将保留时添加行，，分配的值与**RowState**的行都将它设置为**Changed**。</span><span class="sxs-lookup"><span data-stu-id="a32d3-109">The **Current** value will retain the values assigned when the row was added, and the **RowState** of the row will be set to **Changed**.</span></span>  
  
 <span data-ttu-id="a32d3-110">下表给出了对 <xref:System.Data.LoadOption> 枚举值的简要说明。</span><span class="sxs-lookup"><span data-stu-id="a32d3-110">The following table gives a short description of the <xref:System.Data.LoadOption> enumeration values.</span></span>  
  
|<span data-ttu-id="a32d3-111">LoadOption 值</span><span class="sxs-lookup"><span data-stu-id="a32d3-111">LoadOption value</span></span>|<span data-ttu-id="a32d3-112">描述</span><span class="sxs-lookup"><span data-stu-id="a32d3-112">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="a32d3-113">**OverwriteRow**</span><span class="sxs-lookup"><span data-stu-id="a32d3-113">**OverwriteRow**</span></span>|<span data-ttu-id="a32d3-114">如果传入行具有相同**PrimaryKey**为已在一行的值**DataTable**、**原始**和**当前**每个值列替换由传入行中的值与**RowState**属性设置为**Unchanged**。</span><span class="sxs-lookup"><span data-stu-id="a32d3-114">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** and **Current** values of each column are replaced with the values in the incoming row, and the **RowState** property is set to **Unchanged**.</span></span><br /><br /> <span data-ttu-id="a32d3-115">从数据源中不存在的行**DataTable**添加与**RowState**值**Unchanged**。</span><span class="sxs-lookup"><span data-stu-id="a32d3-115">Rows from the data source that do not already exist in the **DataTable** are added with a **RowState** value of **Unchanged**.</span></span><br /><br /> <span data-ttu-id="a32d3-116">此选项的作用是刷新的内容**DataTable** ，使其匹配数据源的内容。</span><span class="sxs-lookup"><span data-stu-id="a32d3-116">This option in effect refreshes the contents of the **DataTable** so that it matches the contents of the data source.</span></span>|  
|<span data-ttu-id="a32d3-117">**PreserveCurrentValues (default)**</span><span class="sxs-lookup"><span data-stu-id="a32d3-117">**PreserveCurrentValues (default)**</span></span>|<span data-ttu-id="a32d3-118">如果传入行具有相同**PrimaryKey**为已在一行的值**DataTable**、**原始**值设置为传入行中和的内容**当前**值不会更改。</span><span class="sxs-lookup"><span data-stu-id="a32d3-118">If incoming rows have the same **PrimaryKey** value as a row already in the **DataTable**, the **Original** value is set to the contents of the incoming row, and the **Current** value is not changed.</span></span><br /><br /> <span data-ttu-id="a32d3-119">如果**RowState**是**Added**或**已修改**，设置为**已修改**。</span><span class="sxs-lookup"><span data-stu-id="a32d3-119">If the **RowState** is **Added** or **Modified**, it is set to **Modified**.</span></span><br /><br /> <span data-ttu-id="a32d3-120">如果**RowState**已**已删除**，它就会一直**已删除**。</span><span class="sxs-lookup"><span data-stu-id="a32d3-120">If the **RowState** was **Deleted**, it remains **Deleted**.</span></span><br /><br /> <span data-ttu-id="a32d3-121">从数据源中不存在的行**DataTable**添加，和**RowState**设置为**Unchanged**。</span><span class="sxs-lookup"><span data-stu-id="a32d3-121">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Unchanged**.</span></span>|  
|<span data-ttu-id="a32d3-122">**UpdateCurrentValues**</span><span class="sxs-lookup"><span data-stu-id="a32d3-122">**UpdateCurrentValues**</span></span>|<span data-ttu-id="a32d3-123">如果传入行具有相同**PrimaryKey**为已在一行的值**DataTable**、**当前**值复制到**原始**值，与**当前**然后，将值设置为传入行的内容。</span><span class="sxs-lookup"><span data-stu-id="a32d3-123">If incoming rows have the same **PrimaryKey** value as the row already in the **DataTable**, the **Current** value is copied to the **Original** value, and the **Current** value is then set to the contents of the incoming row.</span></span><br /><br /> <span data-ttu-id="a32d3-124">如果**RowState**中**DataTable**已**Added**、 **RowState**保持**Added**。</span><span class="sxs-lookup"><span data-stu-id="a32d3-124">If the **RowState** in the **DataTable** was **Added**, the **RowState** remains **Added**.</span></span> <span data-ttu-id="a32d3-125">为行标记为**已修改**或**已删除**、 **RowState**是**已修改**。</span><span class="sxs-lookup"><span data-stu-id="a32d3-125">For rows marked as **Modified** or **Deleted**, the **RowState** is **Modified**.</span></span><br /><br /> <span data-ttu-id="a32d3-126">从数据源中不存在的行**DataTable**添加，和**RowState**设置为**Added**。</span><span class="sxs-lookup"><span data-stu-id="a32d3-126">Rows from the data source that do not already exist in the **DataTable** are added, and the **RowState** is set to **Added**.</span></span>|  
  
 <span data-ttu-id="a32d3-127">下面的示例使用**负载**方法以显示中的员工的生日列表**Northwind**数据库。</span><span class="sxs-lookup"><span data-stu-id="a32d3-127">The following sample uses the **Load** method to display a list of birthdays for the employees in the **Northwind** database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a32d3-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="a32d3-128">See Also</span></span>  
 [<span data-ttu-id="a32d3-129">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="a32d3-129">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="a32d3-130">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="a32d3-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: 将数据添加到数据表中
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: 02d7f94259cc56513be404c5539ca7015d5f3533
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151528"
---
# <a name="adding-data-to-a-datatable"></a><span data-ttu-id="de3f8-102">将数据添加到数据表中</span><span class="sxs-lookup"><span data-stu-id="de3f8-102">Adding Data to a DataTable</span></span>
<span data-ttu-id="de3f8-103">在创建 <xref:System.Data.DataTable> 并使用列和约束定义其结构之后，您可以将新的数据行添加到表中。</span><span class="sxs-lookup"><span data-stu-id="de3f8-103">After you create a <xref:System.Data.DataTable> and define its structure using columns and constraints, you can add new rows of data to the table.</span></span> <span data-ttu-id="de3f8-104">要添加新行，可将一个新变量声明为 <xref:System.Data.DataRow> 类型。</span><span class="sxs-lookup"><span data-stu-id="de3f8-104">To add a new row, declare a new variable as type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="de3f8-105">调用<xref:System.Data.DataTable.NewRow%2A>方法时将返回新的**DataRow**对象。</span><span class="sxs-lookup"><span data-stu-id="de3f8-105">A new **DataRow** object is returned when you call the <xref:System.Data.DataTable.NewRow%2A> method.</span></span> <span data-ttu-id="de3f8-106">然后 **，DataTable**基于表的结构（由 定义）创建**DataRow**对象<xref:System.Data.DataColumnCollection>。</span><span class="sxs-lookup"><span data-stu-id="de3f8-106">The **DataTable** then creates the **DataRow** object based on the structure of the table, as defined by the <xref:System.Data.DataColumnCollection>.</span></span>  
  
 <span data-ttu-id="de3f8-107">下面的示例演示如何通过调用**NewRow**方法创建新行。</span><span class="sxs-lookup"><span data-stu-id="de3f8-107">The following example demonstrates how to create a new row by calling the **NewRow** method.</span></span>  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 <span data-ttu-id="de3f8-108">然后您可以使用索引或列名来处理新添加的行，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="de3f8-108">You then can manipulate the newly added row using an index or the column name, as shown in the following example.</span></span>  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 <span data-ttu-id="de3f8-109">将数据插入到新行后 **，Add**方法用于将行添加到 ，<xref:System.Data.DataRowCollection>如下所示。</span><span class="sxs-lookup"><span data-stu-id="de3f8-109">After data is inserted into the new row, the **Add** method is used to add the row to the <xref:System.Data.DataRowCollection>, shown in the following code.</span></span>  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 <span data-ttu-id="de3f8-110">还可以调用**Add**方法，通过传入值数组来添加新行，这些值键入为<xref:System.Object>，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="de3f8-110">You can also call the **Add** method to add a new row by passing in an array of values, typed as <xref:System.Object>, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 <span data-ttu-id="de3f8-111">将值数组（键入为**Object**）传递给**Add**方法会在表中创建一个新行，并将其列值设置到对象数组中的值。</span><span class="sxs-lookup"><span data-stu-id="de3f8-111">Passing an array of values, typed as **Object**, to the **Add** method creates a new row inside the table and sets its column values to the values in the object array.</span></span> <span data-ttu-id="de3f8-112">请注意，数组中的值会根据它们在表中出现的顺序相继与各列匹配。</span><span class="sxs-lookup"><span data-stu-id="de3f8-112">Note that values in the array are matched sequentially to the columns, based on the order in which they appear in the table.</span></span>  
  
 <span data-ttu-id="de3f8-113">下面的示例将 10 行添加到新创建**的客户**表。</span><span class="sxs-lookup"><span data-stu-id="de3f8-113">The following example adds 10 rows to the newly created **Customers** table.</span></span>  
  
```vb  
Dim workRow As DataRow  
Dim i As Integer  
  
For i = 0 To 9  
  workRow = workTable.NewRow()  
  workRow(0) = i  
  workRow(1) = "CustName" & I.ToString()  
  workTable.Rows.Add(workRow)  
Next  
```  
  
```csharp  
DataRow workRow;  
  
for (int i = 0; i <= 9; i++)
{  
  workRow = workTable.NewRow();  
  workRow[0] = i;  
  workRow[1] = "CustName" + i.ToString();  
  workTable.Rows.Add(workRow);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="de3f8-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de3f8-114">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="de3f8-115">操作数据表中的数据</span><span class="sxs-lookup"><span data-stu-id="de3f8-115">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="de3f8-116">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="de3f8-116">ADO.NET Overview</span></span>](../ado-net-overview.md)

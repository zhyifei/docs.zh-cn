---
title: 定义主键
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 3b9e8835c50ea6c1795fc33aa46bac51cd77defc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650595"
---
# <a name="defining-primary-keys"></a><span data-ttu-id="3ab89-102">定义主键</span><span class="sxs-lookup"><span data-stu-id="3ab89-102">Defining Primary Keys</span></span>
<span data-ttu-id="3ab89-103">数据库表通常都有一列或一组列，用于唯一地标识表中的每一行。</span><span class="sxs-lookup"><span data-stu-id="3ab89-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="3ab89-104">这种具有标识作用的列或列组称为主键。</span><span class="sxs-lookup"><span data-stu-id="3ab89-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="3ab89-105">标识单个<xref:System.Data.DataColumn>作为<xref:System.Data.DataTable.PrimaryKey%2A>有关<xref:System.Data.DataTable>，表将自动设置<xref:System.Data.DataColumn.AllowDBNull%2A>到列的属性**false**和<xref:System.Data.DataColumn.Unique%2A>属性设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="3ab89-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="3ab89-106">对于多列主键，仅**AllowDBNull**属性自动设置为**false**。</span><span class="sxs-lookup"><span data-stu-id="3ab89-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="3ab89-107">**PrimaryKey**的属性<xref:System.Data.DataTable>接收作为其值的一个或多个数组**DataColumn**对象，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="3ab89-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="3ab89-108">第一个示例将单独一列定义为主键。</span><span class="sxs-lookup"><span data-stu-id="3ab89-108">The first example defines a single column as the primary key.</span></span>  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 <span data-ttu-id="3ab89-109">下面的示例将两列定义为主键。</span><span class="sxs-lookup"><span data-stu-id="3ab89-109">The following example defines two columns as a primary key.</span></span>  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],   
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ab89-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ab89-110">See also</span></span>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="3ab89-111">数据表架构定义</span><span class="sxs-lookup"><span data-stu-id="3ab89-111">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="3ab89-112">数据表</span><span class="sxs-lookup"><span data-stu-id="3ab89-112">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="3ab89-113">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="3ab89-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

---
title: "更新数据源中的数据"
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
ms.assetid: 55c545e5-dcd5-4323-a5b9-3825c2157462
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3c611e2d7c4c1de17588ba5220124db55bca2764
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="updating-data-in-a-data-source"></a><span data-ttu-id="d42ef-102">更新数据源中的数据</span><span class="sxs-lookup"><span data-stu-id="d42ef-102">Updating Data in a Data Source</span></span>
<span data-ttu-id="d42ef-103">修改数据的 SQL 语句（如 INSERT、UPDATE 或 DELETE）不返回行。</span><span class="sxs-lookup"><span data-stu-id="d42ef-103">SQL statements that modify data (such as INSERT, UPDATE, or DELETE) do not return rows.</span></span> <span data-ttu-id="d42ef-104">同样，许多存储过程执行操作但不返回行。</span><span class="sxs-lookup"><span data-stu-id="d42ef-104">Similarly, many stored procedures perform an action but do not return rows.</span></span> <span data-ttu-id="d42ef-105">若要执行不返回行的命令，创建**命令**使用相应的 SQL 命令的对象和一个**连接**，包括所有必需**参数**。</span><span class="sxs-lookup"><span data-stu-id="d42ef-105">To execute commands that do not return rows, create a **Command** object with the appropriate SQL command and a **Connection**, including any required **Parameters**.</span></span> <span data-ttu-id="d42ef-106">执行该命令与**ExecuteNonQuery**方法**命令**对象。</span><span class="sxs-lookup"><span data-stu-id="d42ef-106">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="d42ef-107">**ExecuteNonQuery**方法返回一个整数，表示的语句或存储的过程执行受影响的行数。</span><span class="sxs-lookup"><span data-stu-id="d42ef-107">The **ExecuteNonQuery** method returns an integer that represents the number of rows affected by the statement or stored procedure that was executed.</span></span> <span data-ttu-id="d42ef-108">如果执行了多个语句，则返回的值为受所有已执行语句影响的记录的总数。</span><span class="sxs-lookup"><span data-stu-id="d42ef-108">If multiple statements are executed, the value returned is the sum of the records affected by all of the statements executed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d42ef-109">示例</span><span class="sxs-lookup"><span data-stu-id="d42ef-109">Example</span></span>  
 <span data-ttu-id="d42ef-110">下面的代码示例执行一个 INSERT 语句，以将一个记录插入数据库使用**ExecuteNonQuery**。</span><span class="sxs-lookup"><span data-stu-id="d42ef-110">The following code example executes an INSERT statement to insert a record into a database using **ExecuteNonQuery**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
connection.Open()  
  
Dim queryString As String = "INSERT INTO Customers " & _  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
Dim recordsAffected As Int32 = command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
string queryString = "INSERT INTO Customers " +  
  "(CustomerID, CompanyName) Values('NWIND', 'Northwind Traders')";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
Int32 recordsAffected = command.ExecuteNonQuery();  
```  
  
 <span data-ttu-id="d42ef-111">下面的代码示例执行中的示例代码所创建的存储的过程[执行编录操作](../../../../docs/framework/data/adonet/performing-catalog-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="d42ef-111">The following code example executes the stored procedure created by the sample code in [Performing Catalog Operations](../../../../docs/framework/data/adonet/performing-catalog-operations.md).</span></span> <span data-ttu-id="d42ef-112">通过存储过程中，会返回任何行因此**ExecuteNonQuery**方法，但使用该存储的过程未接收输入的参数并返回一个输出参数和返回值。</span><span class="sxs-lookup"><span data-stu-id="d42ef-112">No rows are returned by the stored procedure, so the **ExecuteNonQuery** method is used, but the stored procedure does receive an input parameter and returns an output parameter and a return value.</span></span>  
  
 <span data-ttu-id="d42ef-113">有关<xref:System.Data.OleDb.OleDbCommand>对象， **ReturnValue**必须将参数添加到**参数**集合第一个。</span><span class="sxs-lookup"><span data-stu-id="d42ef-113">For the <xref:System.Data.OleDb.OleDbCommand> object, the **ReturnValue** parameter must be added to the **Parameters** collection first.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim command As SqlCommand = _  
   New SqlCommand("InsertCategory" , connection)  
command.CommandType = CommandType.StoredProcedure  
  
Dim parameter As SqlParameter = _  
 command.Parameters.Add("@RowCount", SqlDbType.Int)  
parameter.Direction = ParameterDirection.ReturnValue  
  
parameter = command.Parameters.Add( _  
  "@CategoryName", SqlDbType.NChar, 15)  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int)  
parameter.Direction = ParameterDirection.Output  
  
command.Parameters("@CategoryName").Value = "New Category"  
command.ExecuteNonQuery()  
  
Dim categoryID As Int32 = CInt(command.Parameters("@Identity").Value)  
Dim rowCount As Int32 = CInt(command.Parameters("@RowCount").Value)   
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlCommand command = new SqlCommand("InsertCategory" , connection);  
command.CommandType = CommandType.StoredProcedure;  
  
SqlParameter parameter = command.Parameters.Add(  
  "@RowCount", SqlDbType.Int);  
parameter.Direction = ParameterDirection.ReturnValue;  
  
parameter = command.Parameters.Add(  
  "@CategoryName", SqlDbType.NChar, 15);  
  
parameter = command.Parameters.Add("@Identity", SqlDbType.Int);  
parameter.Direction = ParameterDirection.Output;  
  
command.Parameters["@CategoryName"].Value = "New Category";  
command.ExecuteNonQuery();  
  
Int32 categoryID = (Int32) command.Parameters["@Identity"].Value;  
Int32 rowCount = (Int32) command.Parameters["@RowCount"].Value;  
```  
  
## <a name="see-also"></a><span data-ttu-id="d42ef-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d42ef-114">See Also</span></span>  
 [<span data-ttu-id="d42ef-115">使用命令修改数据</span><span class="sxs-lookup"><span data-stu-id="d42ef-115">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)  
 [<span data-ttu-id="d42ef-116">使用 DataAdapter 更新数据源</span><span class="sxs-lookup"><span data-stu-id="d42ef-116">Updating Data Sources with DataAdapters</span></span>](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [<span data-ttu-id="d42ef-117">命令和参数</span><span class="sxs-lookup"><span data-stu-id="d42ef-117">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="d42ef-118">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="d42ef-118">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

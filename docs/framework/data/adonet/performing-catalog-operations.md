---
title: 执行目录操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: beb5d2db898df1c98662d53190ac1432acc746e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61878214"
---
# <a name="performing-catalog-operations"></a><span data-ttu-id="a82c9-102">执行目录操作</span><span class="sxs-lookup"><span data-stu-id="a82c9-102">Performing Catalog Operations</span></span>
<span data-ttu-id="a82c9-103">若要执行的命令来修改数据库或目录，如 CREATE TABLE 或 CREATE PROCEDURE 语句创建**命令**对象使用相应的 SQL 语句和一个**连接**对象。</span><span class="sxs-lookup"><span data-stu-id="a82c9-103">To execute a command to modify a database or catalog, such as the CREATE TABLE or CREATE PROCEDURE statement, create a **Command** object using the appropriate SQL statements and a **Connection** object.</span></span> <span data-ttu-id="a82c9-104">使用执行命令**ExecuteNonQuery**方法**命令**对象。</span><span class="sxs-lookup"><span data-stu-id="a82c9-104">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="a82c9-105">以下代码示例在 Microsoft SQL Server 数据库中创建一个存储过程。</span><span class="sxs-lookup"><span data-stu-id="a82c9-105">The following code example creates a stored procedure in a Microsoft SQL Server database.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim queryString As String = "CREATE PROCEDURE InsertCategory " & _  
    "@CategoryName nchar(15), " & _  
    "@Identity int OUT " & _  
    "AS " & _  
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " & _  
    "SET @Identity = @@Identity " & _  
    "RETURN @@ROWCOUNT"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
string queryString = "CREATE PROCEDURE InsertCategory  " +   
    "@CategoryName nchar(15), " +  
    "@Identity int OUT " +  
    "AS " +   
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " +   
    "SET @Identity = @@Identity " +  
    "RETURN @@ROWCOUNT";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
command.ExecuteNonQuery();  
```  
  
## <a name="see-also"></a><span data-ttu-id="a82c9-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="a82c9-106">See also</span></span>

- [<span data-ttu-id="a82c9-107">使用命令修改数据</span><span class="sxs-lookup"><span data-stu-id="a82c9-107">Using Commands to Modify Data</span></span>](../../../../docs/framework/data/adonet/using-commands-to-modify-data.md)
- [<span data-ttu-id="a82c9-108">命令和参数</span><span class="sxs-lookup"><span data-stu-id="a82c9-108">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="a82c9-109">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="a82c9-109">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

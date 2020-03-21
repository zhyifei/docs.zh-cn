---
title: 执行目录操作
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: bedeb4e9c510a3feeedc038e9c4cef6c4721e345
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149240"
---
# <a name="performing-catalog-operations"></a><span data-ttu-id="addb4-102">执行目录操作</span><span class="sxs-lookup"><span data-stu-id="addb4-102">Performing Catalog Operations</span></span>
<span data-ttu-id="addb4-103">要执行修改数据库或目录的命令（如创建表或创建过程语句），请使用相应的 SQL 语句和**连接**对象创建**命令**对象。</span><span class="sxs-lookup"><span data-stu-id="addb4-103">To execute a command to modify a database or catalog, such as the CREATE TABLE or CREATE PROCEDURE statement, create a **Command** object using the appropriate SQL statements and a **Connection** object.</span></span> <span data-ttu-id="addb4-104">使用命令对象的**ExecuteNonQuery**方法执行**命令**。</span><span class="sxs-lookup"><span data-stu-id="addb4-104">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="addb4-105">以下代码示例在 Microsoft SQL Server 数据库中创建一个存储过程。</span><span class="sxs-lookup"><span data-stu-id="addb4-105">The following code example creates a stored procedure in a Microsoft SQL Server database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="addb4-106">另请参阅</span><span class="sxs-lookup"><span data-stu-id="addb4-106">See also</span></span>

- [<span data-ttu-id="addb4-107">使用命令修改数据</span><span class="sxs-lookup"><span data-stu-id="addb4-107">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="addb4-108">命令和参数</span><span class="sxs-lookup"><span data-stu-id="addb4-108">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="addb4-109">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="addb4-109">ADO.NET Overview</span></span>](ado-net-overview.md)

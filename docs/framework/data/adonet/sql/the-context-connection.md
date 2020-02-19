---
title: 上下文连接
ms.date: 03/30/2017
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
ms.openlocfilehash: e237bb53c699fd4bf051876a378c31b73a038502
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451806"
---
# <a name="the-context-connection"></a><span data-ttu-id="a6c9c-102">上下文连接</span><span class="sxs-lookup"><span data-stu-id="a6c9c-102">The Context Connection</span></span>
<span data-ttu-id="a6c9c-103">内部数据访问出现问题相当普遍。</span><span class="sxs-lookup"><span data-stu-id="a6c9c-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="a6c9c-104">也就是说，您想要访问的服务器正是正在执行公共语言运行库 (CLR) 存储过程或函数的服务器。</span><span class="sxs-lookup"><span data-stu-id="a6c9c-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="a6c9c-105">一个选择是使用 <xref:System.Data.SqlClient.SqlConnection> 创建一个连接，指定指向本地服务器的连接字符串，然后打开该连接。</span><span class="sxs-lookup"><span data-stu-id="a6c9c-105">One option is to create a connection using <xref:System.Data.SqlClient.SqlConnection>, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="a6c9c-106">这要求指定用于登录的凭据。</span><span class="sxs-lookup"><span data-stu-id="a6c9c-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="a6c9c-107">此连接位于与存储过程或函数不同的数据库会话中，它可以具有不同的 `SET` 选项，位于不同的事务中，并且看不到你的临时表等。</span><span class="sxs-lookup"><span data-stu-id="a6c9c-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="a6c9c-108">如果你的托管存储过程或函数代码正在 SQL Server 进程中执行，原因可能是某人连接到了该服务器并且执行了 SQL 语句以调用它。</span><span class="sxs-lookup"><span data-stu-id="a6c9c-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="a6c9c-109">你可能希望存储过程或函数在该连接的上下文中与其事务、`SET` 选项等一起执行。</span><span class="sxs-lookup"><span data-stu-id="a6c9c-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="a6c9c-110">这称作上下文连接。</span><span class="sxs-lookup"><span data-stu-id="a6c9c-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="a6c9c-111">通过上下文连接，你可以在第一个位置中调用了你的代码的相同上下文中执行 Transact-SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="a6c9c-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="a6c9c-112">有关更多详细信息，请参见您正在使用的 SQL Server 版本的“SQL Server 联机丛书”版本。</span><span class="sxs-lookup"><span data-stu-id="a6c9c-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="a6c9c-113">**SQL Server 文档**</span><span class="sxs-lookup"><span data-stu-id="a6c9c-113">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="a6c9c-114">上下文连接</span><span class="sxs-lookup"><span data-stu-id="a6c9c-114">The Context Connection</span></span>](/sql/relational-databases/clr-integration/data-access/context-connection)  
  
## <a name="see-also"></a><span data-ttu-id="a6c9c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6c9c-115">See also</span></span>

- [<span data-ttu-id="a6c9c-116">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="a6c9c-116">ADO.NET Overview</span></span>](../ado-net-overview.md)

---
title: 在 SQL Server 中使用存储过程管理权限
ms.date: 03/30/2017
ms.assetid: 08fa34e8-2ffa-470d-ba62-e511a5f8558e
ms.openlocfilehash: 2472481156f44b55726243e9d939522e46796070
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361279"
---
# <a name="managing-permissions-with-stored-procedures-in-sql-server"></a><span data-ttu-id="a853b-102">在 SQL Server 中使用存储过程管理权限</span><span class="sxs-lookup"><span data-stu-id="a853b-102">Managing Permissions with Stored Procedures in SQL Server</span></span>
<span data-ttu-id="a853b-103">为数据库创建多道防线的一个方法是使用存储过程或用户定义的函数实现所有数据访问。</span><span class="sxs-lookup"><span data-stu-id="a853b-103">One method of creating multiple lines of defense around your database is to implement all data access using stored procedures or user-defined functions.</span></span> <span data-ttu-id="a853b-104">撤消或拒绝对基础对象（如表）的所有权限，并授予对存储过程的 EXECUTE 权限。</span><span class="sxs-lookup"><span data-stu-id="a853b-104">You revoke or deny all permissions to underlying objects, such as tables, and grant EXECUTE permissions on stored procedures.</span></span> <span data-ttu-id="a853b-105">这会为数据和数据库对象有效创建安全外围防线。</span><span class="sxs-lookup"><span data-stu-id="a853b-105">This effectively creates a security perimeter around your data and database objects.</span></span>  
  
## <a name="stored-procedure-benefits"></a><span data-ttu-id="a853b-106">存储过程的优点</span><span class="sxs-lookup"><span data-stu-id="a853b-106">Stored Procedure Benefits</span></span>  
 <span data-ttu-id="a853b-107">存储过程具有以下优点：</span><span class="sxs-lookup"><span data-stu-id="a853b-107">Stored procedures have the following benefits:</span></span>  
  
-   <span data-ttu-id="a853b-108">可以包装数据逻辑和业务规则，以便用户可以仅通过开发人员和数据库管理员打算使用的方式访问数据和对象。</span><span class="sxs-lookup"><span data-stu-id="a853b-108">Data logic and business rules can be encapsulated so that users can access data and objects only in ways that developers and database administrators intend.</span></span>  
  
-   <span data-ttu-id="a853b-109">验证所有用户输入的参数化存储过程可用于阻止 SQL 注入攻击。</span><span class="sxs-lookup"><span data-stu-id="a853b-109">Parameterized stored procedures that validate all user input can be used to thwart SQL injection attacks.</span></span> <span data-ttu-id="a853b-110">如果使用动态 SQL，请确保将命令参数化，并绝对不能将参数值直接包括在查询字符串中。</span><span class="sxs-lookup"><span data-stu-id="a853b-110">If you use dynamic SQL, be sure to parameterize your commands, and never include parameter values directly into a query string.</span></span>  
  
-   <span data-ttu-id="a853b-111">可禁止即席查询和数据修改。</span><span class="sxs-lookup"><span data-stu-id="a853b-111">Ad hoc queries and data modifications can be disallowed.</span></span> <span data-ttu-id="a853b-112">这样将阻止用户恶意或无意中损坏数据或执行查询，以避免降低服务器或网络的性能。</span><span class="sxs-lookup"><span data-stu-id="a853b-112">This prevents users from maliciously or inadvertently destroying data or executing queries that impair performance on the server or the network.</span></span>  
  
-   <span data-ttu-id="a853b-113">可以在过程代码中处理错误，而无需将错误直接传递给客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="a853b-113">Errors can be handled in procedure code without being passed directly to client applications.</span></span> <span data-ttu-id="a853b-114">这样可防止返回错误消息，以避免其可能有助于探测攻击。</span><span class="sxs-lookup"><span data-stu-id="a853b-114">This prevents error messages from being returned that could aid in a probing attack.</span></span> <span data-ttu-id="a853b-115">在服务器上记录错误并对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="a853b-115">Log errors and handle them on the server.</span></span>  
  
-   <span data-ttu-id="a853b-116">存储过程只能编写一次，可由很多应用程序访问。</span><span class="sxs-lookup"><span data-stu-id="a853b-116">Stored procedures can be written once, and accessed by many applications.</span></span>  
  
-   <span data-ttu-id="a853b-117">客户端应用程序不需要知道有关基础数据结构的任何信息。</span><span class="sxs-lookup"><span data-stu-id="a853b-117">Client applications do not need to know anything about the underlying data structures.</span></span> <span data-ttu-id="a853b-118">只要更改不影响参数列表或返回的数据类型，就可以更改存储过程代码，而无需在客户端应用程序中进行更改。</span><span class="sxs-lookup"><span data-stu-id="a853b-118">Stored procedure code can be changed without requiring changes in client applications as long as the changes do not affect parameter lists or returned data types.</span></span>  
  
-   <span data-ttu-id="a853b-119">存储过程可通过将多个操作组合到一个过程调用中来减少网络通讯。</span><span class="sxs-lookup"><span data-stu-id="a853b-119">Stored procedures can reduce network traffic by combining multiple operations into one procedure call.</span></span>  
  
## <a name="stored-procedure-execution"></a><span data-ttu-id="a853b-120">存储过程的执行</span><span class="sxs-lookup"><span data-stu-id="a853b-120">Stored Procedure Execution</span></span>  
 <span data-ttu-id="a853b-121">存储过程利用所有权链接来提供对数据的访问，这样，用户就不必拥有访问数据库对象的显式权限。</span><span class="sxs-lookup"><span data-stu-id="a853b-121">Stored procedures take advantage of ownership chaining to provide access to data so that users do not need to have explicit permission to access database objects.</span></span> <span data-ttu-id="a853b-122">如果按顺序相互访问的对象由同一个用户所拥有，就会存在所有权链接。</span><span class="sxs-lookup"><span data-stu-id="a853b-122">An ownership chain exists when objects that access each other sequentially are owned by the same user.</span></span> <span data-ttu-id="a853b-123">例如，存储过程可以调用其他存储过程，或者存储过程可访问多个表。</span><span class="sxs-lookup"><span data-stu-id="a853b-123">For example, a stored procedure can call other stored procedures, or a stored procedure can access multiple tables.</span></span> <span data-ttu-id="a853b-124">如果执行链中的所有对象的所有者相同，则 SQL Server 只检查调用方的 EXECUTE 权限，而不检查调用方对其他对象的权限。</span><span class="sxs-lookup"><span data-stu-id="a853b-124">If all objects in the chain of execution have the same owner, then SQL Server only checks the EXECUTE permission for the caller, not the caller's permissions on other objects.</span></span> <span data-ttu-id="a853b-125">因此，只需对存储过程授予 EXECUTE 权限；可以撤消或拒绝对基础表的所有权限。</span><span class="sxs-lookup"><span data-stu-id="a853b-125">Therefore you need to grant only EXECUTE permissions on stored procedures; you can revoke or deny all permissions on the underlying tables.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="a853b-126">最佳做法</span><span class="sxs-lookup"><span data-stu-id="a853b-126">Best Practices</span></span>  
 <span data-ttu-id="a853b-127">仅编写存储过程不足以保证应用程序的安全，</span><span class="sxs-lookup"><span data-stu-id="a853b-127">Simply writing stored procedures isn't enough to adequately secure your application.</span></span> <span data-ttu-id="a853b-128">还应当考虑以下潜在的安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="a853b-128">You should also consider the following potential security holes.</span></span>  
  
-   <span data-ttu-id="a853b-129">为您希望其能够访问数据的数据库角色授予对存储过程的 EXECUTE 权限。</span><span class="sxs-lookup"><span data-stu-id="a853b-129">Grant EXECUTE permissions on the stored procedures for database roles you want to be able to access the data.</span></span>  
  
-   <span data-ttu-id="a853b-130">撤消或拒绝数据库中所有角色和用户（包括 `public` 角色）对基础表的所有权限。</span><span class="sxs-lookup"><span data-stu-id="a853b-130">Revoke or deny all permissions to the underlying tables for all roles and users in the database, including the `public` role.</span></span> <span data-ttu-id="a853b-131">所有用户会从公共角色中继承权限。</span><span class="sxs-lookup"><span data-stu-id="a853b-131">All users inherit permissions from public.</span></span> <span data-ttu-id="a853b-132">因此，拒绝对 `public` 的权限表示只有所有者和 `sysadmin` 成员具有访问权；所有其他用户将无法从其他角色的成员资格继承权限。</span><span class="sxs-lookup"><span data-stu-id="a853b-132">Therefore denying permissions to `public` means that only owners and `sysadmin` members have access; all other users will be unable to inherit permissions from membership in other roles.</span></span>  
  
-   <span data-ttu-id="a853b-133">请不要将用户或角色添加到 `sysadmin` 或 `db_owner` 角色。</span><span class="sxs-lookup"><span data-stu-id="a853b-133">Do not add users or roles to the `sysadmin` or `db_owner` roles.</span></span> <span data-ttu-id="a853b-134">系统管理员和数据库所有者可访问所有数据库对象。</span><span class="sxs-lookup"><span data-stu-id="a853b-134">System administrators and database owners can access all database objects.</span></span>  
  
-   <span data-ttu-id="a853b-135">禁用 `guest` 帐户。</span><span class="sxs-lookup"><span data-stu-id="a853b-135">Disable the `guest` account.</span></span> <span data-ttu-id="a853b-136">这样将阻止匿名用户连接到数据库。</span><span class="sxs-lookup"><span data-stu-id="a853b-136">This will prevent anonymous users from connecting to the database.</span></span> <span data-ttu-id="a853b-137">默认情况下，会在新数据库中禁用来宾帐户。</span><span class="sxs-lookup"><span data-stu-id="a853b-137">The guest account is disabled by default in new databases.</span></span>  
  
-   <span data-ttu-id="a853b-138">实现错误处理和记录错误。</span><span class="sxs-lookup"><span data-stu-id="a853b-138">Implement error handling and log errors.</span></span>  
  
-   <span data-ttu-id="a853b-139">创建用于验证所有用户输入的参数化存储过程。</span><span class="sxs-lookup"><span data-stu-id="a853b-139">Create parameterized stored procedures that validate all user input.</span></span> <span data-ttu-id="a853b-140">将所有用户输入视为不受信任。</span><span class="sxs-lookup"><span data-stu-id="a853b-140">Treat all user input as untrusted.</span></span>  
  
-   <span data-ttu-id="a853b-141">除非绝对必要，否则应避免使用动态 SQL。</span><span class="sxs-lookup"><span data-stu-id="a853b-141">Avoid dynamic SQL unless absolutely necessary.</span></span> <span data-ttu-id="a853b-142">使用 Transact-SQL QUOTENAME() 函数可分隔字符串值，并对输入字符串中的任何分隔符进行转义。</span><span class="sxs-lookup"><span data-stu-id="a853b-142">Use the Transact-SQL QUOTENAME() function to delimit a string value and escape any occurrence of the delimiter in the input string.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="a853b-143">外部资源</span><span class="sxs-lookup"><span data-stu-id="a853b-143">External Resources</span></span>  
 <span data-ttu-id="a853b-144">有关更多信息，请参见以下资源。</span><span class="sxs-lookup"><span data-stu-id="a853b-144">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="a853b-145">资源</span><span class="sxs-lookup"><span data-stu-id="a853b-145">Resource</span></span>|<span data-ttu-id="a853b-146">描述</span><span class="sxs-lookup"><span data-stu-id="a853b-146">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a853b-147">[存储过程](http://msdn.microsoft.com/library/ms190782.aspx)和[SQL 注入](http://go.microsoft.com/fwlink/?LinkId=98234)SQL Server 联机丛书中</span><span class="sxs-lookup"><span data-stu-id="a853b-147">[Stored Procedures](http://msdn.microsoft.com/library/ms190782.aspx) and [SQL Injection](http://go.microsoft.com/fwlink/?LinkId=98234) in SQL Server Books Online</span></span>|<span data-ttu-id="a853b-148">说明如何创建存储过程和 SQL 注入工作原理的主题。</span><span class="sxs-lookup"><span data-stu-id="a853b-148">Topics describe how to create stored procedures and how SQL Injection works.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a853b-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="a853b-149">See Also</span></span>  
 [<span data-ttu-id="a853b-150">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="a853b-150">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="a853b-151">SQL Server 安全性概述</span><span class="sxs-lookup"><span data-stu-id="a853b-151">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="a853b-152">SQL Server 中的应用程序安全性方案</span><span class="sxs-lookup"><span data-stu-id="a853b-152">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="a853b-153">在 SQL Server 中编写安全的动态 SQL</span><span class="sxs-lookup"><span data-stu-id="a853b-153">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [<span data-ttu-id="a853b-154">在 SQL Server 中对存储过程签名</span><span class="sxs-lookup"><span data-stu-id="a853b-154">Signing Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="a853b-155">在 SQL Server 中使用模拟自定义权限</span><span class="sxs-lookup"><span data-stu-id="a853b-155">Customizing Permissions with Impersonation in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 [<span data-ttu-id="a853b-156">使用存储过程修改数据</span><span class="sxs-lookup"><span data-stu-id="a853b-156">Modifying Data with Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 [<span data-ttu-id="a853b-157">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="a853b-157">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

---
title: 在 SQL Server 中使用模拟自定义权限
ms.date: 03/30/2017
ms.assetid: dc733d09-1d6d-4af0-9c4b-8d24504860f1
ms.openlocfilehash: dd7fb4c94c5a0a9bca0cd36b8d76864158072d4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59326965"
---
# <a name="customizing-permissions-with-impersonation-in-sql-server"></a><span data-ttu-id="a3d4c-102">在 SQL Server 中使用模拟自定义权限</span><span class="sxs-lookup"><span data-stu-id="a3d4c-102">Customizing Permissions with Impersonation in SQL Server</span></span>
<span data-ttu-id="a3d4c-103">许多应用程序都使用存储过程来访问数据，依靠所属权链接来限制对基表的访问。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-103">Many applications use stored procedures to access data, relying on ownership chaining to restrict access to base tables.</span></span> <span data-ttu-id="a3d4c-104">您可以授予针对存储过程的 EXECUTE 权限，撤消或拒绝针对基表的权限。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-104">You can grant EXECUTE permissions on stored procedures, revoking or denying permissions on the base tables.</span></span> <span data-ttu-id="a3d4c-105">如果存储过程和表具有相同的所有者，则 SQL Server 不检查调用方的权限。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-105">SQL Server does not check the permissions of the caller if the stored procedure and tables have the same owner.</span></span> <span data-ttu-id="a3d4c-106">但是，如果对象具有不同的所有者或使用动态 SQL，则所属权链接不起作用。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-106">However, ownership chaining doesn't work if objects have different owners or in the case of dynamic SQL.</span></span>  
  
 <span data-ttu-id="a3d4c-107">当调用方对引用的数据库对象没有权限时，您可以在存储过程中使用 EXECUTE AS 子句。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-107">You can use the EXECUTE AS clause in a stored procedure when the caller doesn't have permissions on the referenced database objects.</span></span> <span data-ttu-id="a3d4c-108">EXECUTE AS 子句的作用是将执行上下文切换到代理用户。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-108">The effect of the EXECUTE AS clause is that the execution context is switched to the proxy user.</span></span> <span data-ttu-id="a3d4c-109">所有代码以及任何对嵌套存储过程或触发器的调用均在代理用户的安全上下文下执行。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-109">All code, as well as any calls to nested stored procedures or triggers, executes under the security context of the proxy user.</span></span> <span data-ttu-id="a3d4c-110">只有在执行该过程或发出 REVERT 语句后，执行上下文才会恢复到原始调用方。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-110">Execution context is reverted to the original caller only after execution of the procedure or when a REVERT statement is issued.</span></span>  
  
## <a name="context-switching-with-the-execute-as-statement"></a><span data-ttu-id="a3d4c-111">使用 EXECUTE AS 语句切换上下文</span><span class="sxs-lookup"><span data-stu-id="a3d4c-111">Context Switching with the EXECUTE AS Statement</span></span>  
 <span data-ttu-id="a3d4c-112">使用 Transact-SQL EXECUTE AS 语句可以通过模拟其他登录名或数据库用户来切换一个语句的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-112">The Transact-SQL EXECUTE AS statement allows you to switch the execution context of a statement by impersonating another login or database user.</span></span> <span data-ttu-id="a3d4c-113">这是一种以其他用户身份测试查询和过程的有用技术。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-113">This is a useful technique for testing queries and procedures as another user.</span></span>  
  
```  
EXECUTE AS LOGIN = 'loginName';  
EXECUTE AS USER = 'userName';  
```  
  
 <span data-ttu-id="a3d4c-114">您必须对要模拟的登录名或用户具有 IMPERSONATE 权限。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-114">You must have IMPERSONATE permissions on the login or user you are impersonating.</span></span> <span data-ttu-id="a3d4c-115">所有数据库的 `sysadmin` 及其拥有的数据库中的 `db_owner` 角色成员都隐含具有此权限。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-115">This permission is implied for `sysadmin` for all databases, and `db_owner` role members in databases that they own.</span></span>  
  
## <a name="granting-permissions-with-the-execute-as-clause"></a><span data-ttu-id="a3d4c-116">使用 EXECUTE AS 子句授予权限</span><span class="sxs-lookup"><span data-stu-id="a3d4c-116">Granting Permissions with the EXECUTE AS Clause</span></span>  
 <span data-ttu-id="a3d4c-117">您可以在存储过程、触发器或用户定义函数（内联表值函数除外）的定义头中使用 EXECUTE AS 子句。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-117">You can use the EXECUTE AS clause in the definition header of a stored procedure, trigger, or user-defined function (except for inline table-valued functions).</span></span> <span data-ttu-id="a3d4c-118">这会使过程在 EXECUTE AS 子句中指定的用户名或关键字的上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-118">This causes the procedure to execute in the context of the user name or keyword specified in the EXECUTE AS clause.</span></span> <span data-ttu-id="a3d4c-119">您可以在数据库中创建一个不映射到登录名的代理用户，仅为其授予对过程所访问的对象的必要权限。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-119">You can create a proxy user in the database that is not mapped to a login, granting it only the necessary permissions on the objects accessed by the procedure.</span></span> <span data-ttu-id="a3d4c-120">只有在 EXECUTE AS 子句中指定的代理用户才必须对模块所访问的所有对象具有权限。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-120">Only the proxy user specified in the EXECUTE AS clause must have permissions on all objects accessed by the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3d4c-121">某些操作（如 TRUNCATE TABLE）没有可授予的权限。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-121">Some actions, such as TRUNCATE TABLE, do not have grantable permissions.</span></span> <span data-ttu-id="a3d4c-122">通过在过程中合并该语句并指定具有 ALTER TABLE 权限的代理用户，可以将截断表的权限扩展到仅对过程具有 EXECUTE 权限的调用方。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-122">By incorporating the statement within a procedure and specifying a proxy user who has ALTER TABLE permissions, you can extend the permissions to truncate the table to callers who have only EXECUTE permissions on the procedure.</span></span>  
  
 <span data-ttu-id="a3d4c-123">EXECUTE AS 子句中指定的上下文在过程（包括嵌套的过程和触发器）期间有效。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-123">The context specified in the EXECUTE AS clause is valid for the duration of the procedure, including nested procedures and triggers.</span></span> <span data-ttu-id="a3d4c-124">当执行完成或发出 REVERT 语句时，上下文恢复到调用方。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-124">Context reverts to the caller when execution is complete or the REVERT statement is issued.</span></span>  
  
 <span data-ttu-id="a3d4c-125">在过程中使用 EXECUTE AS 子句包含三个步骤。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-125">There are three steps involved in using the EXECUTE AS clause in a procedure.</span></span>  
  
1. <span data-ttu-id="a3d4c-126">在数据库中创建一个不映射到登录名的代理用户。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-126">Create a proxy user in the database that is not mapped to a login.</span></span> <span data-ttu-id="a3d4c-127">这不是必需的，但它有助于管理权限。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-127">This is not required, but it helps when managing permissions.</span></span>  
  
```  
CREATE USER proxyUser WITHOUT LOGIN  
```  
  
1. <span data-ttu-id="a3d4c-128">授予代理用户必要的权限。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-128">Grant the proxy user the necessary permissions.</span></span>  
  
2. <span data-ttu-id="a3d4c-129">将 EXECUTE AS 子句添加到存储过程或用户定义函数中。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-129">Add the EXECUTE AS clause to the stored procedure or user-defined function.</span></span>  
  
```  
CREATE PROCEDURE [procName] WITH EXECUTE AS 'proxyUser' AS ...  
```  
  
> [!NOTE]
>  <span data-ttu-id="a3d4c-130">要求审核的应用程序可能中断，因为未保留调用方的原始安全上下文。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-130">Applications that require auditing can break because the original security context of the caller is not retained.</span></span> <span data-ttu-id="a3d4c-131">返回当前用户标识的内置函数（如 SESSION_USER、USER 或 USER_NAME）返回与 EXECUTE AS 子句关联的用户，而不是原始调用方。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-131">Built-in functions that return the identity of the current user, such as SESSION_USER, USER, or USER_NAME, return the user associated with the EXECUTE AS clause, not the original caller.</span></span>  
  
### <a name="using-execute-as-with-revert"></a><span data-ttu-id="a3d4c-132">与 REVERT 一起使用 EXECUTE AS</span><span class="sxs-lookup"><span data-stu-id="a3d4c-132">Using EXECUTE AS with REVERT</span></span>  
 <span data-ttu-id="a3d4c-133">可以使用 Transact-SQL REVERT 语句来返回到原始执行上下文。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-133">You can use the Transact-SQL REVERT statement to revert to the original execution context.</span></span>  
  
 <span data-ttu-id="a3d4c-134">可选子句 WITH NO REVERT COOKIE = @variableName，如果将执行上下文切换回调用方允许@variableName变量包含正确的值。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-134">The optional clause, WITH NO REVERT COOKIE = @variableName, allows you switch the execution context back to the caller if the @variableName variable contains the correct value.</span></span> <span data-ttu-id="a3d4c-135">这允许您在使用连接池的环境中将执行上下文切换回调用方。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-135">This allows you to switch the execution context back to the caller in environments where connection pooling is used.</span></span> <span data-ttu-id="a3d4c-136">因为值@variableName才知道调用方的 EXECUTE AS 语句中，调用方可以保证调用应用程序的最终用户无法更改执行上下文。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-136">Because the value of @variableName is known only to the caller of the EXECUTE AS statement, the caller can guarantee that the execution context cannot be changed by the end user that invokes the application.</span></span> <span data-ttu-id="a3d4c-137">当连接关闭时，它将返回到池中。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-137">When the connection is closed, it is returned to the pool.</span></span> <span data-ttu-id="a3d4c-138">有关详细信息连接池在 ADO.NET 中，请参阅[SQL Server 连接池 (ADO.NET)](../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-138">For more information on connection pooling in ADO.NET, see [SQL Server Connection Pooling (ADO.NET)](../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span>  
  
### <a name="specifying-the-execution-context"></a><span data-ttu-id="a3d4c-139">指定执行上下文</span><span class="sxs-lookup"><span data-stu-id="a3d4c-139">Specifying the Execution Context</span></span>  
 <span data-ttu-id="a3d4c-140">除了指定用户外，还可以将 EXECUTE AS 与以下任意关键字一起使用。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-140">In addition to specifying a user, you can also use EXECUTE AS with any of the following keywords.</span></span>  
  
-   <span data-ttu-id="a3d4c-141">CALLER。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-141">CALLER.</span></span> <span data-ttu-id="a3d4c-142">以 CALLER 身份执行是默认设置；如果未指定其他选项，则过程将在调用方的安全上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-142">Executing as CALLER is the default; if no other option is specified, then the procedure executes in the security context of the caller.</span></span>  
  
-   <span data-ttu-id="a3d4c-143">OWNER。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-143">OWNER.</span></span> <span data-ttu-id="a3d4c-144">以 OWNER 身份执行将在过程所有者的上下文中执行过程。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-144">Executing as OWNER executes the procedure in the context of the procedure owner.</span></span> <span data-ttu-id="a3d4c-145">如果过程是在 `dbo` 或数据库所有者拥有的架构中创建的，则此过程将以无限制权限执行。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-145">If the procedure is created in a schema owned by `dbo` or the database owner, the procedure will execute with unrestricted permissions.</span></span>  
  
-   <span data-ttu-id="a3d4c-146">SELF。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-146">SELF.</span></span> <span data-ttu-id="a3d4c-147">以 SELF 身份执行将在存储过程创建者的安全上下文中执行。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-147">Executing as SELF executes in the security context of the creator of the stored procedure.</span></span> <span data-ttu-id="a3d4c-148">这相当于以指定用户的身份执行，这里的指定用户是指创建或改变过程的人。</span><span class="sxs-lookup"><span data-stu-id="a3d4c-148">This is equivalent to executing as a specified user, where the specified user is the person creating or altering the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3d4c-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3d4c-149">See also</span></span>

- [<span data-ttu-id="a3d4c-150">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="a3d4c-150">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [<span data-ttu-id="a3d4c-151">SQL Server 安全性概述</span><span class="sxs-lookup"><span data-stu-id="a3d4c-151">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)
- [<span data-ttu-id="a3d4c-152">SQL Server 中的应用程序安全性方案</span><span class="sxs-lookup"><span data-stu-id="a3d4c-152">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="a3d4c-153">在 SQL Server 中使用存储过程管理权限</span><span class="sxs-lookup"><span data-stu-id="a3d4c-153">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="a3d4c-154">在 SQL Server 中编写安全的动态 SQL</span><span class="sxs-lookup"><span data-stu-id="a3d4c-154">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)
- [<span data-ttu-id="a3d4c-155">在 SQL Server 中对存储过程签名</span><span class="sxs-lookup"><span data-stu-id="a3d4c-155">Signing Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="a3d4c-156">使用存储过程修改数据</span><span class="sxs-lookup"><span data-stu-id="a3d4c-156">Modifying Data with Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)
- [<span data-ttu-id="a3d4c-157">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="a3d4c-157">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

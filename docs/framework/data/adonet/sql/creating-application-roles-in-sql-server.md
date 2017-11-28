---
title: "在 SQL Server 中创建应用程序角色"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27442435-dfb2-4062-8c59-e2960833a638
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 632b25408db8556dd9604f653f975bccbea75e2b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="creating-application-roles-in-sql-server"></a><span data-ttu-id="4e1ce-102">在 SQL Server 中创建应用程序角色</span><span class="sxs-lookup"><span data-stu-id="4e1ce-102">Creating Application Roles in SQL Server</span></span>
<span data-ttu-id="4e1ce-103">应用程序角色可提供对应用程序（而不是数据库角色或用户）分配权限的方法。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-103">Application roles provide a way to assign permissions to an application instead of a database role or user.</span></span> <span data-ttu-id="4e1ce-104">用户可以连接到数据库、激活应用程序角色以及采用授予应用程序的权限。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-104">Users can connect to the database, activate the application role, and assume the permissions granted to the application.</span></span> <span data-ttu-id="4e1ce-105">授予应用程序角色的权限在连接期间有效。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-105">The permissions granted to the application role are in force for the duration of the connection.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4e1ce-106">当客户端应用程序在连接字符串中提供应用程序角色名称和密码时，可激活应用程序角色。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-106">Application roles are activated when a client application supplies an application role name and a password in the connection string.</span></span> <span data-ttu-id="4e1ce-107">因为密码必须存储在客户端计算机上，所以这些角色在二层应用程序上导致一个安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-107">They present a security vulnerability in a two-tier application because the password must be stored on the client computer.</span></span> <span data-ttu-id="4e1ce-108">在三层应用程序中，您可以存储密码，以便其他应用程序用户将无法对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-108">In a three-tier application, you can store the password so that it cannot be accessed by users of the application.</span></span>  
  
## <a name="application-role-features"></a><span data-ttu-id="4e1ce-109">应用程序角色功能</span><span class="sxs-lookup"><span data-stu-id="4e1ce-109">Application Role Features</span></span>  
 <span data-ttu-id="4e1ce-110">应用程序角色具有以下功能：</span><span class="sxs-lookup"><span data-stu-id="4e1ce-110">Application roles have the following features:</span></span>  
  
-   <span data-ttu-id="4e1ce-111">与数据库角色不同，应用程序角色不包含成员。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-111">Unlike database roles, application roles contain no members.</span></span>  
  
-   <span data-ttu-id="4e1ce-112">当客户端应用程序向 `sp_setapprole` 系统存储过程提供应用程序角色名称和密码时，可激活应用程序角色。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-112">Application roles are activated when an application supplies the application role name and a password to the `sp_setapprole` system stored procedure.</span></span>  
  
-   <span data-ttu-id="4e1ce-113">密码必须存储在客户端计算机上，并且在运行时提供；应用程序角色无法从 SQL Server 内激活。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-113">The password must be stored on the client computer and supplied at run time; an application role cannot be activated from inside of SQL Server.</span></span>  
  
-   <span data-ttu-id="4e1ce-114">密码不加密。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-114">The password is not encrypted.</span></span> <span data-ttu-id="4e1ce-115">参数密码作为单向哈希进行存储。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-115">The parameter password is stored as a one-way hash.</span></span>  
  
-   <span data-ttu-id="4e1ce-116">一旦激活，通过应用程序角色获取的权限在连接期间保持有效。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-116">Once activated, permissions acquired through the application role remain in effect for the duration of the connection.</span></span>  
  
-   <span data-ttu-id="4e1ce-117">应用程序角色继承授予 `public` 角色的权限。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-117">The application role inherits permissions granted to the `public` role.</span></span>  
  
-   <span data-ttu-id="4e1ce-118">如果固定服务器角色 `sysadmin` 的成员激活某一应用程序角色，则安全上下文在连接期间切换为应用程序角色的上下文。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-118">If a member of the `sysadmin` fixed server role activates an application role, the security context switches to that of the application role for the duration of the connection.</span></span>  
  
-   <span data-ttu-id="4e1ce-119">如果您在具有应用程序角色的数据库中创建 `guest` 帐户，则不必为该应用程序角色或调用它的任何登录名创建数据库用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-119">If you create a `guest` account in a database that has an application role, you do not need to create a database user account for the application role or for any of the logins that invoke it.</span></span> <span data-ttu-id="4e1ce-120">只有当在另一个数据库中存在 `guest` 帐户时，应用程序才能直接访问另一数据库。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-120">Application roles can directly access another database only if a `guest` account exists in the second database</span></span>  
  
-   <span data-ttu-id="4e1ce-121">返回登录名的内置函数（如 SYSTEM_USER）返回调用应用程序角色的登录名。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-121">Built-in functions that return login names, such as SYSTEM_USER, return the name of the login that invoked the application role.</span></span> <span data-ttu-id="4e1ce-122">返回数据库用户名的内置函数将返回应用程序角色的名称。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-122">Built-in functions that return database user names return the name of the application role.</span></span>  
  
### <a name="the-principle-of-least-privilege"></a><span data-ttu-id="4e1ce-123">最低特权原则</span><span class="sxs-lookup"><span data-stu-id="4e1ce-123">The Principle of Least Privilege</span></span>  
 <span data-ttu-id="4e1ce-124">仅当密码遭泄漏时，应用程序角色才被授予必要的权限。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-124">Application roles should be granted only required permissions in case the password is compromised.</span></span> <span data-ttu-id="4e1ce-125">在使用应用程序角色的任何数据库中，应撤消对 `public` 角色的权限。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-125">Permissions to the `public` role should be revoked in any database using an application role.</span></span> <span data-ttu-id="4e1ce-126">在不希望应用程序角色的调用方具有访问权限的任何数据库中，禁用 `guest` 帐户。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-126">Disable the `guest` account in any database you do not want callers of the application role to have access to.</span></span>  
  
### <a name="application-role-enhancements"></a><span data-ttu-id="4e1ce-127">应用程序角色增强</span><span class="sxs-lookup"><span data-stu-id="4e1ce-127">Application Role Enhancements</span></span>  
 <span data-ttu-id="4e1ce-128">在激活应用程序角色后，可将执行上下文切换回原始调用方，无需禁用连接池。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-128">The execution context can be switched back to the original caller after activating an application role, removing the need to disable connection pooling.</span></span> <span data-ttu-id="4e1ce-129">`sp_setapprole` 过程具有一个创建 Cookie 的新选项，Cookie 包含有关调用方的上下文信息。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-129">The `sp_setapprole` procedure has a new option that creates a cookie, which contains context information about the caller.</span></span> <span data-ttu-id="4e1ce-130">您可以通过调用 `sp_unsetapprole` 过程来还原会话，并向其传递 Cookie。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-130">You can revert the session by calling the `sp_unsetapprole` procedure, passing it the cookie.</span></span>  
  
## <a name="application-role-alternatives"></a><span data-ttu-id="4e1ce-131">应用程序角色替代项</span><span class="sxs-lookup"><span data-stu-id="4e1ce-131">Application Role Alternatives</span></span>  
 <span data-ttu-id="4e1ce-132">应用程序角色依赖于密码的安全性，而密码具有潜在的安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-132">Application roles depend on the security of a password, which presents a potential security vulnerability.</span></span> <span data-ttu-id="4e1ce-133">密码被嵌入应用程序代码或保存在磁盘上就有可能泄露。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-133">Passwords may be exposed by being embedded in application code or saved on disk.</span></span>  
  
 <span data-ttu-id="4e1ce-134">可能需要考虑以下替代方法。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-134">You may want to consider the following alternatives.</span></span>  
  
-   <span data-ttu-id="4e1ce-135">使用通过 EXECUTE AS 语句及其 NO REVERT 和 WITH COOKIE 字句切换的上下文。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-135">Use context switching with the EXECUTE AS statement with its NO REVERT and WITH COOKIE clauses.</span></span> <span data-ttu-id="4e1ce-136">您可以在未映射为登录名的数据库中创建用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-136">You can create a user account in a database that is not mapped to a login.</span></span> <span data-ttu-id="4e1ce-137">然后，向此帐户分配权限。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-137">You then assign permissions to this account.</span></span> <span data-ttu-id="4e1ce-138">对于很少登录的用户使用 EXECUTE AS 比较安全，因为它基于权限，而不基于密码。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-138">Using EXECUTE AS with a login-less user is more secure because it is permission-based, not password-based.</span></span> <span data-ttu-id="4e1ce-139">有关详细信息，请参阅[模拟 SQL Server 中的自定义权限](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-139">For more information, see [Customizing Permissions with Impersonation in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md).</span></span>  
  
-   <span data-ttu-id="4e1ce-140">使用证书对存储过程进行签名，并仅授予执行这些过程的权限。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-140">Sign stored procedures with certificates, granting only permission to execute the procedures.</span></span> <span data-ttu-id="4e1ce-141">有关详细信息，请参阅[签名 SQL Server 中的存储过程](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-141">For more information, see [Signing Stored Procedures in SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="4e1ce-142">外部资源</span><span class="sxs-lookup"><span data-stu-id="4e1ce-142">External Resources</span></span>  
 <span data-ttu-id="4e1ce-143">有关更多信息，请参见以下资源。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-143">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="4e1ce-144">资源</span><span class="sxs-lookup"><span data-stu-id="4e1ce-144">Resource</span></span>|<span data-ttu-id="4e1ce-145">描述</span><span class="sxs-lookup"><span data-stu-id="4e1ce-145">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="4e1ce-146">[应用程序角色](http://msdn.microsoft.com/library/ms190998.aspx)SQL Server 联机丛书中</span><span class="sxs-lookup"><span data-stu-id="4e1ce-146">[Application Roles](http://msdn.microsoft.com/library/ms190998.aspx) in SQL Server Books Online</span></span>|<span data-ttu-id="4e1ce-147">描述如何在 SQL Server 2008 中创建和使用应用程序角色。</span><span class="sxs-lookup"><span data-stu-id="4e1ce-147">Describes how to create and use application roles in SQL Server 2008.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e1ce-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e1ce-148">See Also</span></span>  
 [<span data-ttu-id="4e1ce-149">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="4e1ce-149">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="4e1ce-150">SQL Server 安全性概述</span><span class="sxs-lookup"><span data-stu-id="4e1ce-150">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="4e1ce-151">SQL Server 中的应用程序安全方案</span><span class="sxs-lookup"><span data-stu-id="4e1ce-151">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="4e1ce-152">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="4e1ce-152">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

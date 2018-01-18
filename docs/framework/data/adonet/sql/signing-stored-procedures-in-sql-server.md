---
title: "在 SQL Server 中对存储过程签名"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a3f1ed66ed7caf2272ca27097dc9a838bec7d0ae
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="signing-stored-procedures-in-sql-server"></a><span data-ttu-id="0c98c-102">在 SQL Server 中对存储过程签名</span><span class="sxs-lookup"><span data-stu-id="0c98c-102">Signing Stored Procedures in SQL Server</span></span>
<span data-ttu-id="0c98c-103">您可以使用证书或非对称密钥为存储过程签名。</span><span class="sxs-lookup"><span data-stu-id="0c98c-103">You can sign a stored procedure with a certificate or an asymmetric key.</span></span> <span data-ttu-id="0c98c-104">此设计适用于无法通过所属权链继承权限或所属权链中断的方案，如动态 SQL。</span><span class="sxs-lookup"><span data-stu-id="0c98c-104">This is designed for scenarios when permissions cannot be inherited through ownership chaining or when the ownership chain is broken, such as dynamic SQL.</span></span> <span data-ttu-id="0c98c-105">然后您可以创建一个映射到该证书的用户，对存储过程需要访问的对象授予证书用户权限。</span><span class="sxs-lookup"><span data-stu-id="0c98c-105">You then create a user mapped to the certificate, granting the certificate user permissions on the objects the stored procedure needs to access.</span></span>  
  
 <span data-ttu-id="0c98c-106">在执行存储过程时，SQL Server 会将证书用户的权限与调用方的权限组合在一起。</span><span class="sxs-lookup"><span data-stu-id="0c98c-106">When the stored procedure is executed, SQL Server combines the permissions of the certificate user with those of the caller.</span></span> <span data-ttu-id="0c98c-107">与 EXECUTE AS 子句不同，它不更改过程的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="0c98c-107">Unlike the EXECUTE AS clause, it does not change the execution context of the procedure.</span></span> <span data-ttu-id="0c98c-108">返回登录名和用户名的内置函数会返回调用方的名称，而不是证书用户的名称。</span><span class="sxs-lookup"><span data-stu-id="0c98c-108">Built-in functions that return login and user names return the name of the caller, not the certificate user name.</span></span>  
  
 <span data-ttu-id="0c98c-109">数字签名是用签名人的私钥加密的数据摘要。</span><span class="sxs-lookup"><span data-stu-id="0c98c-109">A digital signature is a data digest encrypted with the private key of the signer.</span></span> <span data-ttu-id="0c98c-110">该私钥可确保数字签名对于其持有者或所有者是唯一的。</span><span class="sxs-lookup"><span data-stu-id="0c98c-110">The private key ensures that the digital signature is unique to its bearer or owner.</span></span> <span data-ttu-id="0c98c-111">您可以为存储过程、函数或触发器签名。</span><span class="sxs-lookup"><span data-stu-id="0c98c-111">You can sign stored procedures, functions, or triggers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c98c-112">您可以在 master 数据库中创建证书以便授予服务器级权限。</span><span class="sxs-lookup"><span data-stu-id="0c98c-112">You can create a certificate in the master database to grant server-level permissions.</span></span>  
  
## <a name="creating-certificates"></a><span data-ttu-id="0c98c-113">创建证书</span><span class="sxs-lookup"><span data-stu-id="0c98c-113">Creating Certificates</span></span>  
 <span data-ttu-id="0c98c-114">当使用证书为存储过程签名时，会使用私钥创建由该存储过程代码的加密哈希组成的数据摘要。</span><span class="sxs-lookup"><span data-stu-id="0c98c-114">When you sign a stored procedure with a certificate, a data digest consisting of the encrypted hash of the stored procedure code is created using the private key.</span></span> <span data-ttu-id="0c98c-115">在运行时，数据摘要将使用公钥解密并与存储过程的哈希值进行比较。</span><span class="sxs-lookup"><span data-stu-id="0c98c-115">At run time, the data digest is decrypted with the public key and compared with the hash value of the stored procedure.</span></span> <span data-ttu-id="0c98c-116">修改存储过程会使哈希值无效，使数字签名不再匹配。</span><span class="sxs-lookup"><span data-stu-id="0c98c-116">Modifying the stored procedure invalidates the hash value so that the digital signature no longer matches.</span></span> <span data-ttu-id="0c98c-117">这可防止无权访问私钥的人更改存储过程代码。</span><span class="sxs-lookup"><span data-stu-id="0c98c-117">This prevents someone who does not have access to the private key from changing the stored procedure code.</span></span> <span data-ttu-id="0c98c-118">因此，每次修改过程时都必须重新为过程签名。</span><span class="sxs-lookup"><span data-stu-id="0c98c-118">Therefore you must re-sign the procedure each time you modify it.</span></span>  
  
 <span data-ttu-id="0c98c-119">为模块签名涉及以下四个步骤：</span><span class="sxs-lookup"><span data-stu-id="0c98c-119">There are four steps involved in signing a module:</span></span>  
  
1.  <span data-ttu-id="0c98c-120">使用 Transact-SQL `CREATE CERTIFICATE [certificateName]` 语句创建一个证书。</span><span class="sxs-lookup"><span data-stu-id="0c98c-120">Create a certificate using the Transact-SQL `CREATE CERTIFICATE [certificateName]` statement.</span></span> <span data-ttu-id="0c98c-121">此语句具有多个用于设置开始日期、结束日期和密码的选项。</span><span class="sxs-lookup"><span data-stu-id="0c98c-121">This statement has several options for setting a start and end date and a password.</span></span> <span data-ttu-id="0c98c-122">默认的到期日期为一年</span><span class="sxs-lookup"><span data-stu-id="0c98c-122">The default expiration date is one year</span></span>  
  
2.  <span data-ttu-id="0c98c-123">使用 Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` 语句创建与该证书关联的数据库用户。</span><span class="sxs-lookup"><span data-stu-id="0c98c-123">Create a database user associated with that certificate using the Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` statement.</span></span> <span data-ttu-id="0c98c-124">此用户仅存在于数据库中，不与登录名关联。</span><span class="sxs-lookup"><span data-stu-id="0c98c-124">This user exists in the database only and is not associated with a login.</span></span>  
  
3.  <span data-ttu-id="0c98c-125">向证书用户授予访问数据库对象所需的权限。</span><span class="sxs-lookup"><span data-stu-id="0c98c-125">Grant the certificate user the required permissions on the database objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c98c-126">证书不能向用户授予已经使用 DENY 语句撤消的权限。</span><span class="sxs-lookup"><span data-stu-id="0c98c-126">A certificate cannot grant permissions to a user that has had permissions revoked using the DENY statement.</span></span> <span data-ttu-id="0c98c-127">DENY 始终优先于 GRANT，以防止调用方继承授予给证书用户的权限。</span><span class="sxs-lookup"><span data-stu-id="0c98c-127">DENY always takes precedence over GRANT, preventing the caller from inheriting permissions granted to the certificate user.</span></span>  
  
1.  <span data-ttu-id="0c98c-128">使用 Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` 语句通过证书为过程签名。</span><span class="sxs-lookup"><span data-stu-id="0c98c-128">Sign the procedure with the certificate using the Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` statement.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="0c98c-129">外部资源</span><span class="sxs-lookup"><span data-stu-id="0c98c-129">External Resources</span></span>  
 <span data-ttu-id="0c98c-130">有关更多信息，请参见以下资源。</span><span class="sxs-lookup"><span data-stu-id="0c98c-130">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="0c98c-131">资源</span><span class="sxs-lookup"><span data-stu-id="0c98c-131">Resource</span></span>|<span data-ttu-id="0c98c-132">描述</span><span class="sxs-lookup"><span data-stu-id="0c98c-132">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="0c98c-133">[模块签名](http://go.microsoft.com/fwlink/?LinkId=98590)SQL Server 联机丛书中</span><span class="sxs-lookup"><span data-stu-id="0c98c-133">[Module Signing](http://go.microsoft.com/fwlink/?LinkId=98590) in SQL Server Books Online</span></span>|<span data-ttu-id="0c98c-134">说明模块签名，提供示例方案和到相关 Transact-SQL 主题的链接。</span><span class="sxs-lookup"><span data-stu-id="0c98c-134">Describes module signing, providing a sample scenario and links to the relevant Transact-SQL topics.</span></span>|  
|<span data-ttu-id="0c98c-135">[使用证书为存储的过程签名](http://msdn.microsoft.com/library/bb283630.aspx)SQL Server 联机丛书中</span><span class="sxs-lookup"><span data-stu-id="0c98c-135">[Signing Stored Procedures with a Certificate](http://msdn.microsoft.com/library/bb283630.aspx) in SQL Server Books Online</span></span>|<span data-ttu-id="0c98c-136">提供有关使用证书为存储过程签名的教程。</span><span class="sxs-lookup"><span data-stu-id="0c98c-136">Provides a tutorial for signing a stored procedure with a certificate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c98c-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c98c-137">See Also</span></span>  
 [<span data-ttu-id="0c98c-138">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="0c98c-138">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="0c98c-139">SQL Server 安全性概述</span><span class="sxs-lookup"><span data-stu-id="0c98c-139">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="0c98c-140">SQL Server 中的应用程序安全性方案</span><span class="sxs-lookup"><span data-stu-id="0c98c-140">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="0c98c-141">在 SQL Server 中使用存储过程管理权限</span><span class="sxs-lookup"><span data-stu-id="0c98c-141">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="0c98c-142">在 SQL Server 中编写安全的动态 SQL</span><span class="sxs-lookup"><span data-stu-id="0c98c-142">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [<span data-ttu-id="0c98c-143">在 SQL Server 中使用模拟自定义权限</span><span class="sxs-lookup"><span data-stu-id="0c98c-143">Customizing Permissions with Impersonation in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 [<span data-ttu-id="0c98c-144">使用存储过程修改数据</span><span class="sxs-lookup"><span data-stu-id="0c98c-144">Modifying Data with Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 [<span data-ttu-id="0c98c-145">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="0c98c-145">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

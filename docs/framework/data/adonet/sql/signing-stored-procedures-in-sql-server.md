---
title: 在 SQL Server 中对存储过程签名
ms.date: 01/05/2018
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
ms.openlocfilehash: 2c2076294c0e06ec411ceb1f5b1238dc3d7eb304
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313913"
---
# <a name="signing-stored-procedures-in-sql-server"></a><span data-ttu-id="e6139-102">在 SQL Server 中对存储过程签名</span><span class="sxs-lookup"><span data-stu-id="e6139-102">Signing Stored Procedures in SQL Server</span></span>
 <span data-ttu-id="e6139-103">数字签名是用签名人的私钥加密的数据摘要。</span><span class="sxs-lookup"><span data-stu-id="e6139-103">A digital signature is a data digest encrypted with the private key of the signer.</span></span> <span data-ttu-id="e6139-104">该私钥可确保数字签名对于其持有者或所有者是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e6139-104">The private key ensures that the digital signature is unique to its bearer or owner.</span></span> <span data-ttu-id="e6139-105">可以注册存储的过程、 （除内联表值函数） 的函数、 触发器和程序集。</span><span class="sxs-lookup"><span data-stu-id="e6139-105">You can sign stored procedures, functions (except for inline table-valued functions), triggers, and assemblies.</span></span>  
  
 <span data-ttu-id="e6139-106">您可以使用证书或非对称密钥为存储过程签名。</span><span class="sxs-lookup"><span data-stu-id="e6139-106">You can sign a stored procedure with a certificate or an asymmetric key.</span></span> <span data-ttu-id="e6139-107">此设计适用于无法通过所属权链继承权限或所属权链中断的方案，如动态 SQL。</span><span class="sxs-lookup"><span data-stu-id="e6139-107">This is designed for scenarios when permissions cannot be inherited through ownership chaining or when the ownership chain is broken, such as dynamic SQL.</span></span> <span data-ttu-id="e6139-108">然后可以创建映射到证书的用户授予针对存储的过程需要访问的对象的用户权限的证书。</span><span class="sxs-lookup"><span data-stu-id="e6139-108">You can then create a user mapped to the certificate, granting the certificate user permissions on the objects the stored procedure needs to access.</span></span>  

 <span data-ttu-id="e6139-109">您可以还创建登录名映射到同一个证书，并授予该登录名，任何所需的服务器级别权限，或将该登录名添加到一个或多个固定的服务器角色。</span><span class="sxs-lookup"><span data-stu-id="e6139-109">You can also create a login mapped to the same certificate, and then grant any necessary server-level permissions to that login, or add the login to one or more of the fixed server roles.</span></span> <span data-ttu-id="e6139-110">这样设计是为了避免在`TRUSTWORTHY`数据库的方案需要更高级别的权限设置。</span><span class="sxs-lookup"><span data-stu-id="e6139-110">This is designed to avoid enabling the `TRUSTWORTHY` database setting for scenarios in which higher level permissions are needed.</span></span>  
  
 <span data-ttu-id="e6139-111">当执行存储的过程时，SQL Server 将与调用方的相结合证书用户和/或登录名的权限。</span><span class="sxs-lookup"><span data-stu-id="e6139-111">When the stored procedure is executed, SQL Server combines the permissions of the certificate user and/or login with those of the caller.</span></span> <span data-ttu-id="e6139-112">与不同`EXECUTE AS`子句，它不会更改该过程的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="e6139-112">Unlike the `EXECUTE AS` clause, it does not change the execution context of the procedure.</span></span> <span data-ttu-id="e6139-113">返回登录名和用户名的内置函数会返回调用方的名称，而不是证书用户的名称。</span><span class="sxs-lookup"><span data-stu-id="e6139-113">Built-in functions that return login and user names return the name of the caller, not the certificate user name.</span></span>  
  
## <a name="creating-certificates"></a><span data-ttu-id="e6139-114">创建证书</span><span class="sxs-lookup"><span data-stu-id="e6139-114">Creating Certificates</span></span>  
 <span data-ttu-id="e6139-115">当你注册的证书或非对称密钥的加密哈希的存储的过程代码，以及执行包含的数据摘要的存储的过程的以用户身份，使用创建的私钥。</span><span class="sxs-lookup"><span data-stu-id="e6139-115">When you sign a stored procedure with a certificate or asymmetric key, a data digest consisting of the encrypted hash of the stored procedure code, along with the execute-as user, is created using the private key.</span></span> <span data-ttu-id="e6139-116">在运行时，数据摘要将使用公钥解密并与存储过程的哈希值进行比较。</span><span class="sxs-lookup"><span data-stu-id="e6139-116">At run time, the data digest is decrypted with the public key and compared with the hash value of the stored procedure.</span></span> <span data-ttu-id="e6139-117">更改 execute-按用户使无效哈希值，因此，数字签名不再匹配。</span><span class="sxs-lookup"><span data-stu-id="e6139-117">Changing the execute-as user invalidates the hash value so that the digital signature no longer matches.</span></span> <span data-ttu-id="e6139-118">修改存储的过程删除签名完全，即，禁止不具有私钥的访问权限更改存储的过程代码的人。</span><span class="sxs-lookup"><span data-stu-id="e6139-118">Modifying the stored procedure drops the signature entirely, which prevents someone who does not have access to the private key from changing the stored procedure code.</span></span> <span data-ttu-id="e6139-119">在任一情况下，您必须重新签名过程每次更改代码或 execute-以用户身份。</span><span class="sxs-lookup"><span data-stu-id="e6139-119">In either case, you must re-sign the procedure each time you change the code or the execute-as user.</span></span>  
  
 <span data-ttu-id="e6139-120">有两个必需的步骤中为模块签名涉及：</span><span class="sxs-lookup"><span data-stu-id="e6139-120">There are two required steps involved in signing a module:</span></span>  
  
1. <span data-ttu-id="e6139-121">使用 Transact-SQL `CREATE CERTIFICATE [certificateName]` 语句创建一个证书。</span><span class="sxs-lookup"><span data-stu-id="e6139-121">Create a certificate using the Transact-SQL `CREATE CERTIFICATE [certificateName]` statement.</span></span> <span data-ttu-id="e6139-122">此语句具有多个用于设置开始日期、结束日期和密码的选项。</span><span class="sxs-lookup"><span data-stu-id="e6139-122">This statement has several options for setting a start and end date and a password.</span></span> <span data-ttu-id="e6139-123">默认的到期日期为一年。</span><span class="sxs-lookup"><span data-stu-id="e6139-123">The default expiration date is one year.</span></span>  
  
1. <span data-ttu-id="e6139-124">使用 Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` 语句通过证书为过程签名。</span><span class="sxs-lookup"><span data-stu-id="e6139-124">Sign the procedure with the certificate using the Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` statement.</span></span>  

<span data-ttu-id="e6139-125">一旦已签名模块，一个或多个主体需要创建才能保存应与证书相关联的其他权限。</span><span class="sxs-lookup"><span data-stu-id="e6139-125">Once the module has been signed, one or more principals needs to be created in order to hold the additional permissions that should be associated with the certificate.</span></span>  

<span data-ttu-id="e6139-126">如果模块所需的其他数据库级权限：</span><span class="sxs-lookup"><span data-stu-id="e6139-126">If the module needs additional database-level permissions:</span></span>  
  
1. <span data-ttu-id="e6139-127">使用 Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` 语句创建与该证书关联的数据库用户。</span><span class="sxs-lookup"><span data-stu-id="e6139-127">Create a database user associated with that certificate using the Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` statement.</span></span> <span data-ttu-id="e6139-128">此用户只在数据库中存在，除非也从该相同的证书创建一个登录名不与登录名相关联。</span><span class="sxs-lookup"><span data-stu-id="e6139-128">This user exists in the database only and is not associated with a login unless a login has also been created from that same certificate.</span></span>  
  
1. <span data-ttu-id="e6139-129">向证书用户授予所需的数据库级权限。</span><span class="sxs-lookup"><span data-stu-id="e6139-129">Grant the certificate user the required database-level permissions.</span></span>  
  
<span data-ttu-id="e6139-130">如果模块所需的其他服务器级权限：</span><span class="sxs-lookup"><span data-stu-id="e6139-130">If the module needs additional server-level permissions:</span></span>  
  
1. <span data-ttu-id="e6139-131">将证书复制到`master`数据库。</span><span class="sxs-lookup"><span data-stu-id="e6139-131">Copy the certificate to the `master` database.</span></span>  
 
1. <span data-ttu-id="e6139-132">创建与使用 Transact SQL 该证书关联的登录名`CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]`语句。</span><span class="sxs-lookup"><span data-stu-id="e6139-132">Create a login associated with that certificate using the Transact-SQL `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` statement.</span></span>  
  
1. <span data-ttu-id="e6139-133">证书登录名授予所需的服务器级别权限。</span><span class="sxs-lookup"><span data-stu-id="e6139-133">Grant the certificate login the required server-level permissions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6139-134">证书不能向用户授予已经使用 DENY 语句撤消的权限。</span><span class="sxs-lookup"><span data-stu-id="e6139-134">A certificate cannot grant permissions to a user that has had permissions revoked using the DENY statement.</span></span> <span data-ttu-id="e6139-135">DENY 始终优先于 GRANT，以防止调用方继承授予给证书用户的权限。</span><span class="sxs-lookup"><span data-stu-id="e6139-135">DENY always takes precedence over GRANT, preventing the caller from inheriting permissions granted to the certificate user.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="e6139-136">外部资源</span><span class="sxs-lookup"><span data-stu-id="e6139-136">External Resources</span></span>  
 <span data-ttu-id="e6139-137">有关更多信息，请参见以下资源。</span><span class="sxs-lookup"><span data-stu-id="e6139-137">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="e6139-138">资源</span><span class="sxs-lookup"><span data-stu-id="e6139-138">Resource</span></span>|<span data-ttu-id="e6139-139">描述</span><span class="sxs-lookup"><span data-stu-id="e6139-139">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e6139-140">[模块签名](https://go.microsoft.com/fwlink/?LinkId=98590)SQL Server 联机丛书中</span><span class="sxs-lookup"><span data-stu-id="e6139-140">[Module Signing](https://go.microsoft.com/fwlink/?LinkId=98590) in SQL Server Books Online</span></span>|<span data-ttu-id="e6139-141">说明模块签名，提供示例方案和到相关 Transact-SQL 主题的链接。</span><span class="sxs-lookup"><span data-stu-id="e6139-141">Describes module signing, providing a sample scenario and links to the relevant Transact-SQL topics.</span></span>|  
|<span data-ttu-id="e6139-142">[使用证书为存储的过程签名](/sql/relational-databases/tutorial-signing-stored-procedures-with-a-certificate)SQL Server 联机丛书中</span><span class="sxs-lookup"><span data-stu-id="e6139-142">[Signing Stored Procedures with a Certificate](/sql/relational-databases/tutorial-signing-stored-procedures-with-a-certificate) in SQL Server Books Online</span></span>|<span data-ttu-id="e6139-143">提供有关使用证书为存储过程签名的教程。</span><span class="sxs-lookup"><span data-stu-id="e6139-143">Provides a tutorial for signing a stored procedure with a certificate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6139-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6139-144">See also</span></span>

- [<span data-ttu-id="e6139-145">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="e6139-145">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [<span data-ttu-id="e6139-146">SQL Server 安全性概述</span><span class="sxs-lookup"><span data-stu-id="e6139-146">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)
- [<span data-ttu-id="e6139-147">SQL Server 中的应用程序安全性方案</span><span class="sxs-lookup"><span data-stu-id="e6139-147">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="e6139-148">在 SQL Server 中使用存储过程管理权限</span><span class="sxs-lookup"><span data-stu-id="e6139-148">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="e6139-149">在 SQL Server 中编写安全的动态 SQL</span><span class="sxs-lookup"><span data-stu-id="e6139-149">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)
- [<span data-ttu-id="e6139-150">在 SQL Server 中使用模拟自定义权限</span><span class="sxs-lookup"><span data-stu-id="e6139-150">Customizing Permissions with Impersonation in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)
- [<span data-ttu-id="e6139-151">使用存储过程修改数据</span><span class="sxs-lookup"><span data-stu-id="e6139-151">Modifying Data with Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)
- [<span data-ttu-id="e6139-152">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="e6139-152">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

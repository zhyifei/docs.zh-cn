---
title: 在 SQL Server 中对存储过程签名
ms.date: 01/05/2018
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
ms.openlocfilehash: 98dfaa6d5293cb1ad85f70be3388fb333daef373
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="signing-stored-procedures-in-sql-server"></a>在 SQL Server 中对存储过程签名
 数字签名是用签名人的私钥加密的数据摘要。 该私钥可确保数字签名对于其持有者或所有者是唯一的。 你可以注册的存储的过程、 （除外内联表值函数） 的函数、 触发器和程序集。  
  
 您可以使用证书或非对称密钥为存储过程签名。 此设计适用于无法通过所属权链继承权限或所属权链中断的方案，如动态 SQL。 然后可以创建一个映射到证书，用户授予对存储的过程需要访问的对象的用户权限的证书。  

 你可以还创建登录名映射到相同的证书，并授予该登录名，任何所需的服务器级权限，或将该登录名添加到一个或多个固定的服务器角色。 此操作旨在避免启用`TRUSTWORTHY`数据库的情况下需要更高级别的权限中的设置。  
  
 当执行存储的过程时，SQL Server 将使用调用方的组合的证书用户和/或登录名的权限。 与不同`EXECUTE AS`子句，它不会更改过程的执行上下文。 返回登录名和用户名的内置函数会返回调用方的名称，而不是证书用户的名称。  
  
## <a name="creating-certificates"></a>创建证书  
 当你注册使用证书或非对称密钥，由存储的过程代码，以及执行的加密哈希组成的数据摘要为存储的过程-以用户身份，使用创建的私钥。 在运行时，数据摘要将使用公钥解密并与存储过程的哈希值进行比较。 更改 execute-如用户失效的哈希值，以便不再与匹配的数字签名。 修改存储的过程会删除签名完全，这可防止无权访问私钥更改存储的过程代码的任何人。 在任一情况下，你必须重新注册过程每次更改代码或 execute-以用户身份。  
  
 有两个必需的步骤中模块签名涉及：  
  
1.  使用 Transact-SQL `CREATE CERTIFICATE [certificateName]` 语句创建一个证书。 此语句具有多个用于设置开始日期、结束日期和密码的选项。 默认的到期日期是一年。  
  
1.  使用 Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` 语句通过证书为过程签名。  

一旦模块进行了签名，一个或多个主体都需要创建以便保存所应与证书相关联的其他权限。  

如果该模块需要其他数据库级别权限：  
  
1.  使用 Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` 语句创建与该证书关联的数据库用户。 此用户仅在数据库中存在，并且除非也从该相同的证书创建一个登录名不与一个登录名相关联。  
  
1.  授予证书用户所需的数据库级别权限。  
  
如果该模块需要其他服务器级别权限：  
  
1.  将复制到证书`master`数据库。  
 
1.  创建与使用 Transact SQL 该证书关联的登录名`CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]`语句。  
  
1.  证书登录名授予所需的服务器级权限。  
  
> [!NOTE]  
>  证书不能向用户授予已经使用 DENY 语句撤消的权限。 DENY 始终优先于 GRANT，以防止调用方继承授予给证书用户的权限。  
  
## <a name="external-resources"></a>外部资源  
 有关更多信息，请参见以下资源。  
  
|资源|描述|  
|--------------|-----------------|  
|[模块签名](http://go.microsoft.com/fwlink/?LinkId=98590)SQL Server 联机丛书中|说明模块签名，提供示例方案和到相关 Transact-SQL 主题的链接。|  
|[使用证书为存储的过程签名](http://msdn.microsoft.com/library/bb283630.aspx)SQL Server 联机丛书中|提供有关使用证书为存储过程签名的教程。|  
  
## <a name="see-also"></a>请参阅  
 [保证 ADO.NET 应用程序的安全](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server 安全性概述](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [SQL Server 中的应用程序安全性方案](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [在 SQL Server 中使用存储过程管理权限](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [在 SQL Server 中编写安全的动态 SQL](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [在 SQL Server 中使用模拟自定义权限](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 [使用存储过程修改数据](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)

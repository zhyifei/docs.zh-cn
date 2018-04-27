---
title: SQL Server 中的身份验证
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
caps.latest.revision: 9
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 1c918df5de4a66c00f6fd9b9dd1719ac05041ce1
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="authentication-in-sql-server"></a>SQL Server 中的身份验证
SQL Server 支持两种身份验证模式，Windows 身份验证模式和混合模式。  
  
-   Windows 身份验证是默认模式（通常称为集成安全），因为此 SQL Server 安全模型与 Windows 高度集成。 信任特定 Windows 用户和组帐户登录 SQL Server。 已经过身份验证的 Windows 用户不必提供附加的凭据。  
  
-   混合模式支持通过 Windows 和 SQL Server 进行的身份验证。 用户名和密码对保留在 SQL Server 中。  
  
> [!IMPORTANT]
>  我们建议尽可能使用 Windows 身份验证。 Windows 身份验证使用一系列加密消息验证 SQL Server 中的用户。 使用 SQL Server 登录时，会通过网络传递 SQL Server 登录名和密码，这样会降低它们的安全性。  
  
 使用 Windows 身份验证，已经登录到 Windows 的用户不必再单独登录到 SQL Server。 下面的 `SqlConnection.ConnectionString` 可指定 Windows 身份验证，而无需用户名或密码。  
  
```  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;  
```  
  
> [!NOTE]
>  登录名与数据库用户名不同。 您必须通过单独的操作将登录或 Windows 组映射到数据库用户或角色。 然后向用户或角色授予访问数据库对象的权限。  
  
## <a name="authentication-scenarios"></a>身份验证方案  
 在下列情形中，Windows 身份验证通常为最佳选择：  
  
-   存在域控制器。  
  
-   应用程序和数据库位于同一台计算机上。  
  
-   要使用的 SQL Server Express 或 LocalDB 的实例。  
  
 SQL Server 登录常常在以下情况中使用：  
  
-   您有工作组。  
  
-   用户从其他不受信任的域进行连接。  
  
-   Internet 应用程序（例如 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)]）。  
  
> [!NOTE]
>  指定 Windows 身份验证不会禁用 SQL Server 登录。 使用 ALTER LOGIN DISABLE[!INCLUDE[tsql](../../../../../includes/tsql-md.md)]语句禁用高特权 SQL Server 登录名。  
  
## <a name="login-types"></a>登录类型  
 SQL Server 支持三种类型的登录名：  
  
-   本地 Windows 用户帐户或受信任的域帐户。 SQL Server 依赖 Windows 来对 Windows 用户帐户进行身份验证。  
  
-   Windows 组。 向 Windows 组授予访问权限会向作为该组的成员的所有 Windows 用户登录授予访问权限。  
  
-   SQL Server 登录。 SQL Server 将用户名和密码的哈希形式都存储在 master 数据库中，使用内部身份验证方法验证尝试的登录。  
  
> [!NOTE]
>  SQL Server 提供了从证书或仅用于代码签名的非对称密钥创建的登录名。 但无法使用这些登录名连接到 SQL Server。  
  
## <a name="mixed-mode-authentication"></a>混合模式身份验证  
 如果您必须使用混合模式身份验证，则必须创建 SQL Server 登录名，将其存储在 SQL Server 中。 然后必须在运行时提供 SQL Server 用户名和密码。  
  
> [!IMPORTANT]
>  SQL Server 使用名为 `sa`（“系统管理员”的缩写）的 SQL Server 登录进行安装。 为 `sa` 登录分配一个强密码，并且不要在应用程序中使用 `sa` 登录。 `sa` 登录名会映射到 `sysadmin` 固定服务器角色，它对整个服务器有不能撤销的管理凭据。 如果攻击者以系统管理员的身份获取了访问权限，则可能造成的危害是无法预计的。 默认情况下，Windows `BUILTIN\Administrators` 组（本地管理员组）的所有成员均为 `sysadmin` 角色的成员，但可以从该角色中移除这些成员。  
  
 SQL Server 运行时提供的 SQL Server 登录名的 Windows 密码策略机制[!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)]或更高版本。 密码复杂性策略通过增加可能密码的数量来阻止强力攻击。 SQL Server 可以将应用中使用的相同复杂性和到期策略[!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)]在 SQL Server 内使用的密码。  
  
> [!IMPORTANT]
>  连接来自用户输入的连接字符串会使您遭受连接字符串注入攻击。 可使用 <xref:System.Data.SqlClient.SqlConnectionStringBuilder> 在运行时创建语法构成有效的连接字符串。 有关详细信息，请参阅[连接字符串生成器](../../../../../docs/framework/data/adonet/connection-string-builders.md)。  
  
## <a name="external-resources"></a>外部资源  
 有关更多信息，请参见以下资源。  
  
|资源|描述|  
|--------------|-----------------|  
|[主体](http://msdn.microsoft.com/library/bb543165.aspx)SQL Server 联机丛书中|描述登录名和 SQL Server 中的其他安全主体。|  
  
## <a name="see-also"></a>请参阅  
 [保证 ADO.NET 应用程序的安全](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server 中的应用程序安全性方案](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [连接到数据源](../../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [连接字符串](../../../../../docs/framework/data/adonet/connection-strings.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)

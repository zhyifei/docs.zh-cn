---
title: 连接字符串语法
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0977aeee-04d1-4cce-bbed-750c77fce06e
caps.latest.revision: 11
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 76d8765be1dc24f4b8c457644595796680c2f2c3
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="connection-string-syntax"></a><span data-ttu-id="da7c2-102">连接字符串语法</span><span class="sxs-lookup"><span data-stu-id="da7c2-102">Connection String Syntax</span></span>
<span data-ttu-id="da7c2-103">每个 .NET Framework 数据提供程序都有一个继承自 `Connection` 的 <xref:System.Data.Common.DbConnection> 对象，以及一个提供程序特定的 <xref:System.Data.Common.DbConnection.ConnectionString%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="da7c2-103">Each .NET Framework data provider has a `Connection` object that inherits from <xref:System.Data.Common.DbConnection> as well as a provider-specific <xref:System.Data.Common.DbConnection.ConnectionString%2A> property.</span></span> <span data-ttu-id="da7c2-104">每个提供程序的特定连接字符串语法记录在其 `ConnectionString` 属性中。</span><span class="sxs-lookup"><span data-stu-id="da7c2-104">The specific connection string syntax for each provider is documented in its `ConnectionString` property.</span></span> <span data-ttu-id="da7c2-105">下表列出了 .NET Framework 中包含的四个数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="da7c2-105">The following table lists the four data providers that are included in the .NET Framework.</span></span>  
  
|<span data-ttu-id="da7c2-106">.NET Framework data provider — .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="da7c2-106">.NET Framework data provider</span></span>|<span data-ttu-id="da7c2-107">描述</span><span class="sxs-lookup"><span data-stu-id="da7c2-107">Description</span></span>|  
|----------------------------------|-----------------|  
|<xref:System.Data.SqlClient>|<span data-ttu-id="da7c2-108">提供 Microsoft SQL Server 的数据访问。</span><span class="sxs-lookup"><span data-stu-id="da7c2-108">Provides data access for Microsoft SQL Server.</span></span> <span data-ttu-id="da7c2-109">有关连接字符串语法的更多信息，请参见 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>。</span><span class="sxs-lookup"><span data-stu-id="da7c2-109">For more information on connection string syntax, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>|  
|<xref:System.Data.OleDb>|<span data-ttu-id="da7c2-110">提供对使用 OLE DB 公开的数据源中的数据的访问。</span><span class="sxs-lookup"><span data-stu-id="da7c2-110">Provides data access for data sources exposed using OLE DB.</span></span> <span data-ttu-id="da7c2-111">有关连接字符串语法的更多信息，请参见 <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>。</span><span class="sxs-lookup"><span data-stu-id="da7c2-111">For more information on connection string syntax, see <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.</span></span>|  
|<xref:System.Data.Odbc>|<span data-ttu-id="da7c2-112">提供对使用 ODBC 公开的数据源中数据的访问。</span><span class="sxs-lookup"><span data-stu-id="da7c2-112">Provides data access for data sources exposed using ODBC.</span></span> <span data-ttu-id="da7c2-113">有关连接字符串语法的更多信息，请参见 <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A>。</span><span class="sxs-lookup"><span data-stu-id="da7c2-113">For more information on connection string syntax, see <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A>.</span></span>|  
|<xref:System.Data.OracleClient>|<span data-ttu-id="da7c2-114">提供对 Oracle 8.1.7 或更高版本中数据的访问。</span><span class="sxs-lookup"><span data-stu-id="da7c2-114">Provides data access for Oracle version 8.1.7 or later.</span></span> <span data-ttu-id="da7c2-115">有关连接字符串语法的更多信息，请参见 <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>。</span><span class="sxs-lookup"><span data-stu-id="da7c2-115">For more information on connection string syntax, see <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>.</span></span>|  
  
## <a name="connection-string-builders"></a><span data-ttu-id="da7c2-116">连接字符串生成器</span><span class="sxs-lookup"><span data-stu-id="da7c2-116">Connection String Builders</span></span>  
 <span data-ttu-id="da7c2-117">ADO.NET 2.0 为 .NET Framework 数据提供程序引入了以下连接字符串生成器。</span><span class="sxs-lookup"><span data-stu-id="da7c2-117">ADO.NET 2.0 introduced the following connection string builders for the .NET Framework data providers.</span></span>  
  
-   <xref:System.Data.SqlClient.SqlConnectionStringBuilder>  
  
-   <xref:System.Data.OleDb.OleDbConnectionStringBuilder>  
  
-   <xref:System.Data.Odbc.OdbcConnectionStringBuilder>  
  
-   <xref:System.Data.OracleClient.OracleConnectionStringBuilder>  
  
 <span data-ttu-id="da7c2-118">连接字符串生成器使你可以在运行时构造具有有效语法的连接字符串，从而不必在代码中手动串联连接字符串值。</span><span class="sxs-lookup"><span data-stu-id="da7c2-118">The connection string builders allow you to construct syntactically valid connection strings at run time, so you do not have to manually concatenate connection string values in your code.</span></span> <span data-ttu-id="da7c2-119">有关详细信息，请参阅[连接字符串生成器](../../../../docs/framework/data/adonet/connection-string-builders.md)。</span><span class="sxs-lookup"><span data-stu-id="da7c2-119">For more information, see [Connection String Builders](../../../../docs/framework/data/adonet/connection-string-builders.md).</span></span>  

## <a name="windows-authentication"></a><span data-ttu-id="da7c2-120">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="da7c2-120">Windows Authentication</span></span>  
 <span data-ttu-id="da7c2-121">我们建议使用 Windows 身份验证 (有时称为*集成安全性*) 连接到支持它的数据源。</span><span class="sxs-lookup"><span data-stu-id="da7c2-121">We recommend using Windows Authentication (sometimes referred to as *integrated security*) to connect to data sources that support it.</span></span> <span data-ttu-id="da7c2-122">连接字符串中使用的语法根据提供程序的不同而不同。</span><span class="sxs-lookup"><span data-stu-id="da7c2-122">The syntax employed in the connection string varies by provider.</span></span> <span data-ttu-id="da7c2-123">下表演示用于 .NET Framework 数据提供程序的 Windows 身份验证语法。</span><span class="sxs-lookup"><span data-stu-id="da7c2-123">The following table shows the Windows Authentication syntax used with the .NET Framework data providers.</span></span>  
  
|<span data-ttu-id="da7c2-124">提供程序</span><span class="sxs-lookup"><span data-stu-id="da7c2-124">Provider</span></span>|<span data-ttu-id="da7c2-125">语法</span><span class="sxs-lookup"><span data-stu-id="da7c2-125">Syntax</span></span>|  
|--------------|------------|  
|`SqlClient`|`Integrated Security=true;`<br /><br /> `-- or --`<br /><br /> `Integrated Security=SSPI;`|  
|`OleDb`|`Integrated Security=SSPI;`|  
|`Odbc`|`Trusted_Connection=yes;`|  
|`OracleClient`|`Integrated Security=yes;`|  
  
> [!NOTE]
>  <span data-ttu-id="da7c2-126">`Integrated Security=true` 用于 `OleDb` 提供程序时会引发异常。</span><span class="sxs-lookup"><span data-stu-id="da7c2-126">`Integrated Security=true` throws an exception when used with the `OleDb` provider.</span></span>  
  
## <a name="sqlclient-connection-strings"></a><span data-ttu-id="da7c2-127">SqlClient 连接字符串</span><span class="sxs-lookup"><span data-stu-id="da7c2-127">SqlClient Connection Strings</span></span>  
<span data-ttu-id="da7c2-128"><xref:System.Data.SqlClient.SqlConnection> 连接字符串的语法记录在 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> 属性中。</span><span class="sxs-lookup"><span data-stu-id="da7c2-128">The syntax for a <xref:System.Data.SqlClient.SqlConnection> connection string is documented in the <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="da7c2-129">您可以使用 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> 属性来获取或设置 SQL Server 数据库的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="da7c2-129">You can use the <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property to get or set a connection string for a SQL Server database.</span></span> <span data-ttu-id="da7c2-130">如果您需要连接到早期版本的 SQL Server，则必须使用适用于 OleDb 的 .NET Framework 数据提供程序 (<xref:System.Data.OleDb>)。</span><span class="sxs-lookup"><span data-stu-id="da7c2-130">If you need to connect to an earlier version of SQL Server, you must use the .NET Framework Data Provider for OleDb (<xref:System.Data.OleDb>).</span></span> <span data-ttu-id="da7c2-131">大多数连接字符串关键字还会在 <xref:System.Data.SqlClient.SqlConnectionStringBuilder> 中映射为属性。</span><span class="sxs-lookup"><span data-stu-id="da7c2-131">Most connection string keywords also map to properties in the <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="da7c2-132">默认设置`Persist Security Info`关键字是`false`。</span><span class="sxs-lookup"><span data-stu-id="da7c2-132">The default setting for the `Persist Security Info` keyword is `false`.</span></span> <span data-ttu-id="da7c2-133">如果将其设置为 `true` 或 `yes`，则允许在打开连接后通过连接获取安全敏感信息（包括用户 ID 和密码）。</span><span class="sxs-lookup"><span data-stu-id="da7c2-133">Setting it to `true` or `yes` allows security-sensitive information, including the user ID and password, to be obtained from the connection after the connection has been opened.</span></span> <span data-ttu-id="da7c2-134">保留`Persist Security Info`设置为`false`以确保不受信任的源没有访问敏感的连接字符串信息。</span><span class="sxs-lookup"><span data-stu-id="da7c2-134">Keep `Persist Security Info` set to `false` to ensure that an untrusted source does not have access to sensitive connection string information.</span></span>  

### <a name="windows-authentication-with-sqlclient"></a><span data-ttu-id="da7c2-135">使用 SqlClient 的 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="da7c2-135">Windows authentication with SqlClient</span></span> 
 <span data-ttu-id="da7c2-136">每个以下形式的语法使用 Windows 身份验证连接到**AdventureWorks**的本地服务器上的数据库。</span><span class="sxs-lookup"><span data-stu-id="da7c2-136">Each of the following forms of syntax uses Windows Authentication to connect to the **AdventureWorks** database on a local server.</span></span>  
  
```  
"Persist Security Info=False;Integrated Security=true;  
    Initial Catalog=AdventureWorks;Server=MSSQL1"  
"Persist Security Info=False;Integrated Security=SSPI;  
    database=AdventureWorks;server=(local)"  
"Persist Security Info=False;Trusted_Connection=True;  
    database=AdventureWorks;server=(local)"  
```  
  
### <a name="sql-server-authentication-with-sqlclient"></a><span data-ttu-id="da7c2-137">使用 SqlClient 的 SQL Server 身份验证</span><span class="sxs-lookup"><span data-stu-id="da7c2-137">SQL Server authentication with SqlClient</span></span>   
 <span data-ttu-id="da7c2-138">Windows 身份验证是用于连接到 SQL Server 的首选方法。</span><span class="sxs-lookup"><span data-stu-id="da7c2-138">Windows Authentication is preferred for connecting to SQL Server.</span></span> <span data-ttu-id="da7c2-139">但是，如果需要 SQL Server 身份验证，请使用下列语法来指定用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="da7c2-139">However, if SQL Server Authentication is required, use the following syntax to specify a user name and password.</span></span> <span data-ttu-id="da7c2-140">在此示例中，星号用来表示有效用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="da7c2-140">In this example, asterisks are used to represent a valid user name and password.</span></span>  
  
```  
"Persist Security Info=False;User ID=*****;Password=*****;Initial Catalog=AdventureWorks;Server=MySqlServer"  
```  

<span data-ttu-id="da7c2-141">当你连接到 Azure SQL 数据库或 Azure SQL 数据仓库，并提供格式中的登录名`user@servername`，请确保`servername`于此登录中的值与提供的值匹配`Server=`。</span><span class="sxs-lookup"><span data-stu-id="da7c2-141">When you connect to Azure SQL Database or to Azure SQL Data Warehouse and provide a login in the format `user@servername`, make sure that the `servername` value in the login matches the value provided for `Server=`.</span></span>

> [!NOTE]
>  <span data-ttu-id="da7c2-142">Windows 身份验证优先于 SQL Server 登录。</span><span class="sxs-lookup"><span data-stu-id="da7c2-142">Windows authentication takes precedence over SQL Server logins.</span></span> <span data-ttu-id="da7c2-143">如果您同时指定 Integrated Security=true 以及用户名和密码，将忽略用户名和密码，而使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="da7c2-143">If you specify both Integrated Security=true as well as a user name and password, the user name and password will be ignored and Windows authentication will be used.</span></span>  

### <a name="connect-to-a-named-instance-of-sql-server"></a><span data-ttu-id="da7c2-144">连接到 SQL Server 的命名实例</span><span class="sxs-lookup"><span data-stu-id="da7c2-144">Connect to a named instance of SQL Server</span></span>
<span data-ttu-id="da7c2-145">若要连接到 SQL Server 的命名实例，使用*服务器名称 \ 实例名称*语法。</span><span class="sxs-lookup"><span data-stu-id="da7c2-145">To connect to a named instance of SQL Server, use the *server name\instance name* syntax.</span></span>  
  
```  
Data Source=MySqlServer\MSSQL1;"  
```  
 
<span data-ttu-id="da7c2-146">在生成连接字符串时，您还可以将 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A> 的 `SqlConnectionStringBuilder` 属性设置为实例名。</span><span class="sxs-lookup"><span data-stu-id="da7c2-146">You can also set the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A> property of the `SqlConnectionStringBuilder` to the instance name when building a connection string.</span></span> <span data-ttu-id="da7c2-147"><xref:System.Data.SqlClient.SqlConnection.DataSource%2A> 对象的 <xref:System.Data.SqlClient.SqlConnection> 属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="da7c2-147">The <xref:System.Data.SqlClient.SqlConnection.DataSource%2A> property of a <xref:System.Data.SqlClient.SqlConnection> object is read-only.</span></span>  
  
### <a name="type-system-version-changes"></a><span data-ttu-id="da7c2-148">类型系统版本更改</span><span class="sxs-lookup"><span data-stu-id="da7c2-148">Type System Version Changes</span></span>  
 <span data-ttu-id="da7c2-149">`Type System Version` 中的 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> 关键字指定 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 类型的客户端表示形式。</span><span class="sxs-lookup"><span data-stu-id="da7c2-149">The `Type System Version` keyword in a <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> specifies the client-side representation of [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] types.</span></span> <span data-ttu-id="da7c2-150">有关 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> 关键字的更多信息，请参见 `Type System Version`。</span><span class="sxs-lookup"><span data-stu-id="da7c2-150">See <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> for more information about the `Type System Version` keyword.</span></span>  
  
## <a name="connecting-and-attaching-to-sql-server-express-user-instances"></a><span data-ttu-id="da7c2-151">连接并附加到 SQL Server Express 用户实例</span><span class="sxs-lookup"><span data-stu-id="da7c2-151">Connecting and Attaching to SQL Server Express User Instances</span></span>  
 <span data-ttu-id="da7c2-152">用户实例是 SQL Server Express 中的一个功能。</span><span class="sxs-lookup"><span data-stu-id="da7c2-152">User instances are a feature in SQL Server Express.</span></span> <span data-ttu-id="da7c2-153">它们允许以最低权限的本地 Windows 帐户运行的用户附加并运行 SQL Server 数据库，而无需具有管理权限。</span><span class="sxs-lookup"><span data-stu-id="da7c2-153">They allow a user running on a least-privileged local Windows account to attach and run a SQL Server database without requiring administrative privileges.</span></span> <span data-ttu-id="da7c2-154">使用用户 Windows 凭据执行用户实例，而不是作为服务执行用户实例。</span><span class="sxs-lookup"><span data-stu-id="da7c2-154">A user instance executes with the user's Windows credentials, not as a service.</span></span>  
  
 <span data-ttu-id="da7c2-155">使用用户实例的详细信息，请参阅[SQL Server Express 用户实例](../../../../docs/framework/data/adonet/sql/sql-server-express-user-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="da7c2-155">For more information on working with user instances, see [SQL Server Express User Instances](../../../../docs/framework/data/adonet/sql/sql-server-express-user-instances.md).</span></span>  
  
## <a name="using-trustservercertificate"></a><span data-ttu-id="da7c2-156">使用 TrustServerCertificate</span><span class="sxs-lookup"><span data-stu-id="da7c2-156">Using TrustServerCertificate</span></span>  
 <span data-ttu-id="da7c2-157">`TrustServerCertificate` 关键字仅在连接到具有有效证书的 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 实例时有效。</span><span class="sxs-lookup"><span data-stu-id="da7c2-157">The `TrustServerCertificate` keyword is valid only when connecting to a [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] instance with a valid certificate.</span></span> <span data-ttu-id="da7c2-158">当 `TrustServerCertificate` 设置为 `true` 时，传输层将使用 SSL 来加密通道并跳过证书链以验证信任。</span><span class="sxs-lookup"><span data-stu-id="da7c2-158">When `TrustServerCertificate` is set to `true`, the transport layer will use SSL to encrypt the channel and bypass walking the certificate chain to validate trust.</span></span>  
  
```  
"TrustServerCertificate=true;"   
```  
  
> [!NOTE]
>  <span data-ttu-id="da7c2-159">如果 `TrustServerCertificate` 设置为 `true` 并已启动加密，将使用对服务器指定的加密级别，即使 `Encrypt` 在连接字符串中被设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="da7c2-159">If `TrustServerCertificate` is set to `true` and encryption is turned on, the encryption level specified on the server will be used even if `Encrypt` is set to `false` in the connection string.</span></span> <span data-ttu-id="da7c2-160">否则连接将会失败。</span><span class="sxs-lookup"><span data-stu-id="da7c2-160">The connection will fail otherwise.</span></span>  
  
### <a name="enabling-encryption"></a><span data-ttu-id="da7c2-161">启用加密</span><span class="sxs-lookup"><span data-stu-id="da7c2-161">Enabling Encryption</span></span>  
 <span data-ttu-id="da7c2-162">若要启用加密证书不设置后在服务器上，**强制协议加密**和**信任服务器证书**选项必须设置在 SQL Server 配置管理器中。</span><span class="sxs-lookup"><span data-stu-id="da7c2-162">To enable encryption when a certificate has not been provisioned on the server, the **Force Protocol Encryption** and the **Trust Server Certificate** options must be set in SQL Server Configuration Manager.</span></span> <span data-ttu-id="da7c2-163">在此情况下，如果未向服务器提供可验证的证书，加密将使用未经验证的自签名服务器证书。</span><span class="sxs-lookup"><span data-stu-id="da7c2-163">In this case, encryption will use a self-signed server certificate without validation if no verifiable certificate has been provisioned on the server.</span></span>  
  
 <span data-ttu-id="da7c2-164">应用程序设置无法降低在 SQL Server 中配置的安全级别，但可以增强安全级别。</span><span class="sxs-lookup"><span data-stu-id="da7c2-164">Application settings cannot reduce the level of security configured in SQL Server, but can optionally strengthen it.</span></span> <span data-ttu-id="da7c2-165">应用程序可以通过设置请求加密`TrustServerCertificate`和`Encrypt`关键字`true`，从而保证，加密进行，即使尚未设置服务器证书和**强制协议加密**尚未配置客户端。</span><span class="sxs-lookup"><span data-stu-id="da7c2-165">An application can request encryption by setting the `TrustServerCertificate` and `Encrypt` keywords to `true`, guaranteeing that encryption takes place even when a server certificate has not been provisioned and **Force Protocol Encryption** has not been configured for the client.</span></span> <span data-ttu-id="da7c2-166">但是，如果未在客户端配置中启用 `TrustServerCertificate`，则仍需要提供服务器证书。</span><span class="sxs-lookup"><span data-stu-id="da7c2-166">However, if `TrustServerCertificate` is not enabled in the client configuration, a provisioned server certificate is still required.</span></span>  
  
 <span data-ttu-id="da7c2-167">下表描述了各种情况。</span><span class="sxs-lookup"><span data-stu-id="da7c2-167">The following table describes all cases.</span></span>  
  
|<span data-ttu-id="da7c2-168">“强制协议加密”客户端设置</span><span class="sxs-lookup"><span data-stu-id="da7c2-168">Force Protocol Encryption client setting</span></span>|<span data-ttu-id="da7c2-169">“信任服务器证书”客户端设置</span><span class="sxs-lookup"><span data-stu-id="da7c2-169">Trust Server Certificate client setting</span></span>|<span data-ttu-id="da7c2-170">“密加/使用数据加密”连接字符串/属性</span><span class="sxs-lookup"><span data-stu-id="da7c2-170">Encrypt/Use Encryption for Data connection string/attribute</span></span>|<span data-ttu-id="da7c2-171">“信任服务器证书”连接字符串/特性</span><span class="sxs-lookup"><span data-stu-id="da7c2-171">Trust Server Certificate connection string/attribute</span></span>|<span data-ttu-id="da7c2-172">结果</span><span class="sxs-lookup"><span data-stu-id="da7c2-172">Result</span></span>|  
|----------------------------------------------|---------------------------------------------|-------------------------------------------------------------------|-----------------------------------------------------------|------------|  
|<span data-ttu-id="da7c2-173">No</span><span class="sxs-lookup"><span data-stu-id="da7c2-173">No</span></span>|<span data-ttu-id="da7c2-174">不可用</span><span class="sxs-lookup"><span data-stu-id="da7c2-174">N/A</span></span>|<span data-ttu-id="da7c2-175">否（默认值）</span><span class="sxs-lookup"><span data-stu-id="da7c2-175">No (default)</span></span>|<span data-ttu-id="da7c2-176">忽略</span><span class="sxs-lookup"><span data-stu-id="da7c2-176">Ignored</span></span>|<span data-ttu-id="da7c2-177">不加密。</span><span class="sxs-lookup"><span data-stu-id="da7c2-177">No encryption occurs.</span></span>|  
|<span data-ttu-id="da7c2-178">No</span><span class="sxs-lookup"><span data-stu-id="da7c2-178">No</span></span>|<span data-ttu-id="da7c2-179">不可用</span><span class="sxs-lookup"><span data-stu-id="da7c2-179">N/A</span></span>|<span data-ttu-id="da7c2-180">是</span><span class="sxs-lookup"><span data-stu-id="da7c2-180">Yes</span></span>|<span data-ttu-id="da7c2-181">否（默认值）</span><span class="sxs-lookup"><span data-stu-id="da7c2-181">No (default)</span></span>|<span data-ttu-id="da7c2-182">只有在具有可验证的服务器证书的情况下才能进行加密，否则连接尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="da7c2-182">Encryption occurs only if there is a verifiable server certificate, otherwise the connection attempt fails.</span></span>|  
|<span data-ttu-id="da7c2-183">No</span><span class="sxs-lookup"><span data-stu-id="da7c2-183">No</span></span>|<span data-ttu-id="da7c2-184">不可用</span><span class="sxs-lookup"><span data-stu-id="da7c2-184">N/A</span></span>|<span data-ttu-id="da7c2-185">是</span><span class="sxs-lookup"><span data-stu-id="da7c2-185">Yes</span></span>|<span data-ttu-id="da7c2-186">是</span><span class="sxs-lookup"><span data-stu-id="da7c2-186">Yes</span></span>|<span data-ttu-id="da7c2-187">只有在具有可验证的服务器证书的情况下才能进行加密，否则连接尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="da7c2-187">Encryption occurs only if there is a verifiable server certificate, otherwise the connection attempt fails.</span></span>|  
|<span data-ttu-id="da7c2-188">是</span><span class="sxs-lookup"><span data-stu-id="da7c2-188">Yes</span></span>|<span data-ttu-id="da7c2-189">No</span><span class="sxs-lookup"><span data-stu-id="da7c2-189">No</span></span>|<span data-ttu-id="da7c2-190">忽略</span><span class="sxs-lookup"><span data-stu-id="da7c2-190">Ignored</span></span>|<span data-ttu-id="da7c2-191">忽略</span><span class="sxs-lookup"><span data-stu-id="da7c2-191">Ignored</span></span>|<span data-ttu-id="da7c2-192">只有在具有可验证的服务器证书的情况下才能进行加密，否则连接尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="da7c2-192">Encryption occurs only if there is a verifiable server certificate, otherwise the connection attempt fails.</span></span>|  
|<span data-ttu-id="da7c2-193">是</span><span class="sxs-lookup"><span data-stu-id="da7c2-193">Yes</span></span>|<span data-ttu-id="da7c2-194">是</span><span class="sxs-lookup"><span data-stu-id="da7c2-194">Yes</span></span>|<span data-ttu-id="da7c2-195">否（默认值）</span><span class="sxs-lookup"><span data-stu-id="da7c2-195">No (default)</span></span>|<span data-ttu-id="da7c2-196">忽略</span><span class="sxs-lookup"><span data-stu-id="da7c2-196">Ignored</span></span>|<span data-ttu-id="da7c2-197">只有在具有可验证的服务器证书的情况下才能进行加密，否则连接尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="da7c2-197">Encryption occurs only if there is a verifiable server certificate, otherwise the connection attempt fails.</span></span>|  
|<span data-ttu-id="da7c2-198">是</span><span class="sxs-lookup"><span data-stu-id="da7c2-198">Yes</span></span>|<span data-ttu-id="da7c2-199">是</span><span class="sxs-lookup"><span data-stu-id="da7c2-199">Yes</span></span>|<span data-ttu-id="da7c2-200">是</span><span class="sxs-lookup"><span data-stu-id="da7c2-200">Yes</span></span>|<span data-ttu-id="da7c2-201">否（默认值）</span><span class="sxs-lookup"><span data-stu-id="da7c2-201">No (default)</span></span>|<span data-ttu-id="da7c2-202">只有在具有可验证的服务器证书的情况下才能进行加密，否则连接尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="da7c2-202">Encryption occurs only if there is a verifiable server certificate, otherwise the connection attempt fails.</span></span>|  
|<span data-ttu-id="da7c2-203">是</span><span class="sxs-lookup"><span data-stu-id="da7c2-203">Yes</span></span>|<span data-ttu-id="da7c2-204">是</span><span class="sxs-lookup"><span data-stu-id="da7c2-204">Yes</span></span>|<span data-ttu-id="da7c2-205">是</span><span class="sxs-lookup"><span data-stu-id="da7c2-205">Yes</span></span>|<span data-ttu-id="da7c2-206">是</span><span class="sxs-lookup"><span data-stu-id="da7c2-206">Yes</span></span>|<span data-ttu-id="da7c2-207">只有在具有可验证的服务器证书的情况下才能进行加密，否则连接尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="da7c2-207">Encryption occurs only if there is a verifiable server certificate, otherwise the connection attempt fails.</span></span>|  
  
 <span data-ttu-id="da7c2-208">有关详细信息，请参阅[使用未经验证的加密](http://go.microsoft.com/fwlink/?LinkId=120500)SQL Server 联机丛书中。</span><span class="sxs-lookup"><span data-stu-id="da7c2-208">For more information, see [Using Encryption Without Validation](http://go.microsoft.com/fwlink/?LinkId=120500) in SQL Server Books Online.</span></span>  
  
## <a name="oledb-connection-strings"></a><span data-ttu-id="da7c2-209">OleDb 连接字符串</span><span class="sxs-lookup"><span data-stu-id="da7c2-209">OleDb Connection Strings</span></span>  
 <span data-ttu-id="da7c2-210">通过 <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> 的 <xref:System.Data.OleDb.OleDbConnection> 属性，您可以获取或设置 OLE DB 数据源（如 Microsoft Access）的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="da7c2-210">The <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> property of a <xref:System.Data.OleDb.OleDbConnection> allows you to get or set a connection string for an OLE DB data source, such as Microsoft Access.</span></span> <span data-ttu-id="da7c2-211">也可以使用 `OleDb` 类在运行时创建一个 <xref:System.Data.OleDb.OleDbConnectionStringBuilder> 连接字符串。</span><span class="sxs-lookup"><span data-stu-id="da7c2-211">You can also create an `OleDb` connection string at run time by using the <xref:System.Data.OleDb.OleDbConnectionStringBuilder> class.</span></span>  
  
### <a name="oledb-connection-string-syntax"></a><span data-ttu-id="da7c2-212">OleDb 连接字符串语法</span><span class="sxs-lookup"><span data-stu-id="da7c2-212">OleDb Connection String Syntax</span></span>  
 <span data-ttu-id="da7c2-213">必须为 <xref:System.Data.OleDb.OleDbConnection> 连接字符串指定提供程序名称。</span><span class="sxs-lookup"><span data-stu-id="da7c2-213">You must specify a provider name for an <xref:System.Data.OleDb.OleDbConnection> connection string.</span></span> <span data-ttu-id="da7c2-214">下列连接字符串使用 Jet 提供程序连接到 Microsoft Access 数据库。</span><span class="sxs-lookup"><span data-stu-id="da7c2-214">The following connection string connects to a Microsoft Access database using the Jet provider.</span></span> <span data-ttu-id="da7c2-215">请注意，如果数据库未受到保护（默认值），可选择 `UserID` 和 `Password` 关键字。</span><span class="sxs-lookup"><span data-stu-id="da7c2-215">Note that the `UserID` and `Password` keywords are optional if the database is unsecured (the default).</span></span>  
  
```  
Provider=Microsoft.Jet.OLEDB.4.0; Data Source=d:\Northwind.mdb;User ID=Admin;Password=;   
```  
  
 <span data-ttu-id="da7c2-216">如果使用用户级安全保护 Jet 数据库，则必须提供工作组信息文件 (.mdw) 的位置。</span><span class="sxs-lookup"><span data-stu-id="da7c2-216">If the Jet database is secured using user-level security, you must provide the location of the workgroup information file (.mdw).</span></span> <span data-ttu-id="da7c2-217">工作组信息文件用于验证连接字符串中显示的凭据。</span><span class="sxs-lookup"><span data-stu-id="da7c2-217">The workgroup information file is used to validate the credentials presented in the connection string.</span></span>  
  
```  
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=d:\Northwind.mdb;Jet OLEDB:System Database=d:\NorthwindSystem.mdw;User ID=*****;Password=*****;  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="da7c2-218">可以提供的连接信息**OleDbConnection**在通用数据链接 (UDL) 文件; 但是，应避免这样做。</span><span class="sxs-lookup"><span data-stu-id="da7c2-218">It is possible to supply connection information for an **OleDbConnection** in a Universal Data Link (UDL) file; however you should avoid doing so.</span></span> <span data-ttu-id="da7c2-219">UDL 文件未加密，会以明文形式公开连接字符串信息。</span><span class="sxs-lookup"><span data-stu-id="da7c2-219">UDL files are not encrypted, and expose connection string information in clear text.</span></span> <span data-ttu-id="da7c2-220">因为 UDL 文件对您的应用程序来说是一个基于文件的外部资源，所以无法使用 .NET Framework 保护该文件。</span><span class="sxs-lookup"><span data-stu-id="da7c2-220">Because a UDL file is an external file-based resource to your application, it cannot be secured using the .NET Framework.</span></span> <span data-ttu-id="da7c2-221">不支持 UDL 文件**SqlClient**。</span><span class="sxs-lookup"><span data-stu-id="da7c2-221">UDL files are not supported for **SqlClient**.</span></span>  
  
### <a name="using-datadirectory-to-connect-to-accessjet"></a><span data-ttu-id="da7c2-222">使用 DataDirectory 连接到 Access/Jet</span><span class="sxs-lookup"><span data-stu-id="da7c2-222">Using DataDirectory to Connect to Access/Jet</span></span>  
 <span data-ttu-id="da7c2-223">`DataDirectory` 不是 `SqlClient` 独占的。</span><span class="sxs-lookup"><span data-stu-id="da7c2-223">`DataDirectory` is not exclusive to `SqlClient`.</span></span> <span data-ttu-id="da7c2-224">它还可以用于 <xref:System.Data.OleDb> 和 <xref:System.Data.Odbc> .NET 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="da7c2-224">It can also be used with the <xref:System.Data.OleDb> and <xref:System.Data.Odbc> .NET data providers.</span></span> <span data-ttu-id="da7c2-225">下面的 <xref:System.Data.OleDb.OleDbConnection> 字符串示例演示连接到应用程序 app_data 文件夹中的 Northwind.mdb 所需的语法。</span><span class="sxs-lookup"><span data-stu-id="da7c2-225">The following sample <xref:System.Data.OleDb.OleDbConnection> string demonstrates the syntax required to connect to the Northwind.mdb located in the application's app_data folder.</span></span> <span data-ttu-id="da7c2-226">系统数据库 (System.mdw) 也存储在该位置。</span><span class="sxs-lookup"><span data-stu-id="da7c2-226">The system database (System.mdw) is also stored in that location.</span></span>  
  
```  
"Provider=Microsoft.Jet.OLEDB.4.0;  
Data Source=|DataDirectory|\Northwind.mdb;  
Jet OLEDB:System Database=|DataDirectory|\System.mdw;"  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="da7c2-227">如果 Access/Jet 数据库未受到保护，则不需要在连接字符串中指定系统数据库的位置。</span><span class="sxs-lookup"><span data-stu-id="da7c2-227">Specifying the location of the system database in the connection string is not required if the Access/Jet database is unsecured.</span></span> <span data-ttu-id="da7c2-228">默认情况下安全性为关，所有用户可作为内置管理员用户使用空白密码进行连接。</span><span class="sxs-lookup"><span data-stu-id="da7c2-228">Security is off by default, with all users connecting as the built-in Admin user with a blank password.</span></span> <span data-ttu-id="da7c2-229">即使在正确实现用户级安全时，Jet 数据库仍很容易受到攻击。</span><span class="sxs-lookup"><span data-stu-id="da7c2-229">Even when user-level security is correctly implemented, a Jet database remains vulnerable to attack.</span></span> <span data-ttu-id="da7c2-230">由于 Access/Jet 数据库的基于文件的安全性架构存在固有弱点，因此不建议在 Access/Jet 数据库中存储敏感信息。</span><span class="sxs-lookup"><span data-stu-id="da7c2-230">Therefore, storing sensitive information in an Access/Jet database is not recommended because of the inherent weakness of its file-based security scheme.</span></span>  
  
### <a name="connecting-to-excel"></a><span data-ttu-id="da7c2-231">连接到 Excel</span><span class="sxs-lookup"><span data-stu-id="da7c2-231">Connecting to Excel</span></span>  
 <span data-ttu-id="da7c2-232">Microsoft Jet 提供程序用于连接到 Excel 工作簿。</span><span class="sxs-lookup"><span data-stu-id="da7c2-232">The Microsoft Jet provider is used to connect to an Excel workbook.</span></span> <span data-ttu-id="da7c2-233">下列连接字符串中的 `Extended Properties` 关键字会设置特定于 Excel 的属性。</span><span class="sxs-lookup"><span data-stu-id="da7c2-233">In the following connection string, the `Extended Properties` keyword sets properties that are specific to Excel.</span></span> <span data-ttu-id="da7c2-234">“HDR=Yes;”指示第一行包含列名称，但不包含数据；“IMEX=1;”指示驱动程序始终将“intermixed”数据列作为文本进行读取。</span><span class="sxs-lookup"><span data-stu-id="da7c2-234">"HDR=Yes;" indicates that the first row contains column names, not data, and "IMEX=1;" tells the driver to always read "intermixed" data columns as text.</span></span>  
  
```  
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=D:\MyExcel.xls;Extended Properties=""Excel 8.0;HDR=Yes;IMEX=1""  
```  
  
 <span data-ttu-id="da7c2-235">请注意，`Extended Properties` 所需的双引号字符还必须包含在双引号中。</span><span class="sxs-lookup"><span data-stu-id="da7c2-235">Note that the double quotation character required for the `Extended Properties` must also be enclosed in double quotation marks.</span></span>  
  
### <a name="data-shape-provider-connection-string-syntax"></a><span data-ttu-id="da7c2-236">Data Shape 提供程序连接字符串语法</span><span class="sxs-lookup"><span data-stu-id="da7c2-236">Data Shape Provider Connection String Syntax</span></span>  
 <span data-ttu-id="da7c2-237">在使用 Microsoft Data Shape 提供程序时，请同时使用 `Provider` 和 `Data Provider` 关键字。</span><span class="sxs-lookup"><span data-stu-id="da7c2-237">Use both the `Provider` and the `Data Provider` keywords when using the Microsoft Data Shape provider.</span></span> <span data-ttu-id="da7c2-238">下面的示例使用 Shape 提供程序连接到 SQL Server 的本地实例。</span><span class="sxs-lookup"><span data-stu-id="da7c2-238">The following example uses the Shape provider to connect to a local instance of SQL Server.</span></span>  
  
```  
"Provider=MSDataShape;Data Provider=SQLOLEDB;Data Source=(local);Initial Catalog=pubs;Integrated Security=SSPI;"   
```  
  
## <a name="odbc-connection-strings"></a><span data-ttu-id="da7c2-239">Odbc 连接字符串</span><span class="sxs-lookup"><span data-stu-id="da7c2-239">Odbc Connection Strings</span></span>  
 <span data-ttu-id="da7c2-240"><xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A> 的 <xref:System.Data.Odbc.OdbcConnection> 属性允许您获取或设置 OLE DB 数据源的连接字符串或。</span><span class="sxs-lookup"><span data-stu-id="da7c2-240">The <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A> property of a <xref:System.Data.Odbc.OdbcConnection> allows you to get or set a connection string for an OLE DB data source.</span></span> <span data-ttu-id="da7c2-241"><xref:System.Data.Odbc.OdbcConnectionStringBuilder> 也支持 Odbc 连接字符串。</span><span class="sxs-lookup"><span data-stu-id="da7c2-241">Odbc connection strings are also supported by the <xref:System.Data.Odbc.OdbcConnectionStringBuilder>.</span></span>  
  
 <span data-ttu-id="da7c2-242">下列连接字符串使用 Microsoft 文本驱动程序。</span><span class="sxs-lookup"><span data-stu-id="da7c2-242">The following connection string uses the Microsoft Text Driver.</span></span>  
  
```  
Driver={Microsoft Text Driver (*.txt; *.csv)};DBQ=d:\bin  
```  
  
### <a name="using-datadirectory-to-connect-to-visual-foxpro"></a><span data-ttu-id="da7c2-243">使用 DataDirectory 连接到 Visual FoxPro</span><span class="sxs-lookup"><span data-stu-id="da7c2-243">Using DataDirectory to Connect to Visual FoxPro</span></span>  
 <span data-ttu-id="da7c2-244">下面的 <xref:System.Data.Odbc.OdbcConnection> 连接字符串示例演示如何使用 `DataDirectory` 连接到 Microsoft Visual FoxPro 文件。</span><span class="sxs-lookup"><span data-stu-id="da7c2-244">The following <xref:System.Data.Odbc.OdbcConnection> connection string sample demonstrates using `DataDirectory` to connect to a Microsoft Visual FoxPro file.</span></span>  
  
```  
"Driver={Microsoft Visual FoxPro Driver};  
SourceDB=|DataDirectory|\MyData.DBC;SourceType=DBC;"  
```  
  
## <a name="oracle-connection-strings"></a><span data-ttu-id="da7c2-245">Oracle 连接字符串</span><span class="sxs-lookup"><span data-stu-id="da7c2-245">Oracle Connection Strings</span></span>  
 <span data-ttu-id="da7c2-246"><xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A> 的 <xref:System.Data.OracleClient.OracleConnection> 属性允许您获取或设置 OLE DB 数据源的连接字符串或。</span><span class="sxs-lookup"><span data-stu-id="da7c2-246">The <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A> property of a <xref:System.Data.OracleClient.OracleConnection> allows you to get or set a connection string for an OLE DB data source.</span></span> <span data-ttu-id="da7c2-247"><xref:System.Data.OracleClient.OracleConnectionStringBuilder> 也支持 Oracle 连接字符串。</span><span class="sxs-lookup"><span data-stu-id="da7c2-247">Oracle connection strings are also supported by the <xref:System.Data.OracleClient.OracleConnectionStringBuilder> .</span></span>  
  
```  
Data Source=Oracle9i;User ID=*****;Password=*****;  
```  
  
 <span data-ttu-id="da7c2-248">有关 ODBC 连接字符串语法的更多信息，请参见 <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>。</span><span class="sxs-lookup"><span data-stu-id="da7c2-248">For more information on ODBC connection string syntax, see <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da7c2-249">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da7c2-249">See Also</span></span>  
 [<span data-ttu-id="da7c2-250">连接字符串</span><span class="sxs-lookup"><span data-stu-id="da7c2-250">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="da7c2-251">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="da7c2-251">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="da7c2-252">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="da7c2-252">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

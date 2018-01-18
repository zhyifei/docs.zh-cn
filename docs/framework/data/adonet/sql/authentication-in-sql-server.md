---
title: "SQL Server 中的身份验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
caps.latest.revision: "9"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: fa9a23f00e7ce3b52c2ff64c8b22e1b4b8727b97
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="authentication-in-sql-server"></a><span data-ttu-id="86353-102">SQL Server 中的身份验证</span><span class="sxs-lookup"><span data-stu-id="86353-102">Authentication in SQL Server</span></span>
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="86353-103"> 支持两种身份验证模式，即 Windows 身份验证模式和混合模式。</span><span class="sxs-lookup"><span data-stu-id="86353-103"> supports two authentication modes, Windows authentication mode and mixed mode.</span></span>  
  
-   <span data-ttu-id="86353-104">Windows 身份验证是默认模式（通常称为集成安全），因为此 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 安全模型与 Windows 紧密集成。</span><span class="sxs-lookup"><span data-stu-id="86353-104">Windows authentication is the default, and is often referred to as integrated security because this [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] security model is tightly integrated with Windows.</span></span> <span data-ttu-id="86353-105">信任特定 Windows 用户和组帐户登录 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="86353-105">Specific Windows user and group accounts are trusted to log in to SQL Server.</span></span> <span data-ttu-id="86353-106">已经过身份验证的 Windows 用户不必提供附加的凭据。</span><span class="sxs-lookup"><span data-stu-id="86353-106">Windows users who have already been authenticated do not have to present additional credentials.</span></span>  
  
-   <span data-ttu-id="86353-107">混合模式支持由 Windows 和 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="86353-107">Mixed mode supports authentication both by Windows and by [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="86353-108">用户名和密码保留在 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 内。</span><span class="sxs-lookup"><span data-stu-id="86353-108">User name and password pairs are maintained within [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="86353-109">我们建议尽可能使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="86353-109">We recommend using Windows authentication wherever possible.</span></span> <span data-ttu-id="86353-110">Windows 身份验证使用一系列加密消息来验证 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 中的用户。</span><span class="sxs-lookup"><span data-stu-id="86353-110">Windows authentication uses a series of encrypted messages to authenticate users in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="86353-111">使用 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 登录时，将跨网络传递 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 登录名和密码，这样会降低它们的安全性。</span><span class="sxs-lookup"><span data-stu-id="86353-111">When [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] logins are used, [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] login names and passwords are passed across the network, which makes them less secure.</span></span>  
  
 <span data-ttu-id="86353-112">使用 Windows 身份验证时，用户已登录到 Windows，无需另外登录到 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="86353-112">With Windows authentication, users are already logged onto Windows and do not have to log on separately to [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="86353-113">下面的 `SqlConnection.ConnectionString` 可指定 Windows 身份验证，而无需用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="86353-113">The following `SqlConnection.ConnectionString` specifies Windows authentication without requiring the a user name or password.</span></span>  
  
```  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;  
```  
  
> [!NOTE]
>  <span data-ttu-id="86353-114">登录名与数据库用户名不同。</span><span class="sxs-lookup"><span data-stu-id="86353-114">Logins are distinct from database users.</span></span> <span data-ttu-id="86353-115">您必须通过单独的操作将登录或 Windows 组映射到数据库用户或角色。</span><span class="sxs-lookup"><span data-stu-id="86353-115">You must map logins or Windows groups to database users or roles in a separate operation.</span></span> <span data-ttu-id="86353-116">然后向用户或角色授予访问数据库对象的权限。</span><span class="sxs-lookup"><span data-stu-id="86353-116">You then grant permissions to users or roles to access database objects.</span></span>  
  
## <a name="authentication-scenarios"></a><span data-ttu-id="86353-117">身份验证方案</span><span class="sxs-lookup"><span data-stu-id="86353-117">Authentication Scenarios</span></span>  
 <span data-ttu-id="86353-118">在下列情形中，Windows 身份验证通常为最佳选择：</span><span class="sxs-lookup"><span data-stu-id="86353-118">Windows authentication is usually the best choice in the following situations:</span></span>  
  
-   <span data-ttu-id="86353-119">存在域控制器。</span><span class="sxs-lookup"><span data-stu-id="86353-119">There is a domain controller.</span></span>  
  
-   <span data-ttu-id="86353-120">应用程序和数据库位于同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="86353-120">The application and the database are on the same computer.</span></span>  
  
-   <span data-ttu-id="86353-121">您正在使用 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express 或 LocalDB 的实例。</span><span class="sxs-lookup"><span data-stu-id="86353-121">You are using an instance of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express or LocalDB.</span></span>  
  
 <span data-ttu-id="86353-122">SQL Server 登录常常在以下情况中使用：</span><span class="sxs-lookup"><span data-stu-id="86353-122">SQL Server logins are often used in the following situations:</span></span>  
  
-   <span data-ttu-id="86353-123">您有工作组。</span><span class="sxs-lookup"><span data-stu-id="86353-123">If you have a workgroup.</span></span>  
  
-   <span data-ttu-id="86353-124">用户从其他不受信任的域进行连接。</span><span class="sxs-lookup"><span data-stu-id="86353-124">Users connect from different, non-trusted domains.</span></span>  
  
-   <span data-ttu-id="86353-125">Internet 应用程序（例如 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)]）。</span><span class="sxs-lookup"><span data-stu-id="86353-125">Internet applications, such as [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86353-126">指定 Windows 身份验证不会禁用 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 登录。</span><span class="sxs-lookup"><span data-stu-id="86353-126">Specifying Windows authentication does not disable [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="86353-127">使用 ALTER LOGIN DISABLE [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 语句可禁用具有高级权限的 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 登录。</span><span class="sxs-lookup"><span data-stu-id="86353-127">Use the ALTER LOGIN DISABLE [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statement to disable highly-privileged [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] logins.</span></span>  
  
## <a name="login-types"></a><span data-ttu-id="86353-128">登录类型</span><span class="sxs-lookup"><span data-stu-id="86353-128">Login Types</span></span>  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="86353-129"> 支持三种登录类型：</span><span class="sxs-lookup"><span data-stu-id="86353-129"> supports three types of logins:</span></span>  
  
-   <span data-ttu-id="86353-130">本地 Windows 用户帐户或受信任的域帐户。</span><span class="sxs-lookup"><span data-stu-id="86353-130">A local Windows user account or trusted domain account.</span></span> [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="86353-131"> 依靠 Windows 来对 Windows 用户帐户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="86353-131"> relies on Windows to authenticate the Windows user accounts.</span></span>  
  
-   <span data-ttu-id="86353-132">Windows 组。</span><span class="sxs-lookup"><span data-stu-id="86353-132">Windows group.</span></span> <span data-ttu-id="86353-133">向 Windows 组授予访问权限会向作为该组的成员的所有 Windows 用户登录授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="86353-133">Granting access to a Windows group grants access to all Windows user logins that are members of the group.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="86353-134"> 登录。</span><span class="sxs-lookup"><span data-stu-id="86353-134"> login.</span></span> [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="86353-135"> 将用户名和密码的哈希都存储在 master 数据库中，使用内部身份验证方法来验证登录尝试。</span><span class="sxs-lookup"><span data-stu-id="86353-135"> stores both the username and a hash of the password in the master database, by using internal authentication methods to verify login attempts.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="86353-136"> 提供了从证书或非对称密钥创建的登录名，仅用于代码签名。</span><span class="sxs-lookup"><span data-stu-id="86353-136"> provides logins created from certificates or asymmetric keys that are used only for code signing.</span></span> <span data-ttu-id="86353-137">这些登录名不能用于连接到 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="86353-137">They cannot be used to connect to [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="mixed-mode-authentication"></a><span data-ttu-id="86353-138">混合模式身份验证</span><span class="sxs-lookup"><span data-stu-id="86353-138">Mixed Mode Authentication</span></span>  
 <span data-ttu-id="86353-139">如果您必须使用混合模式身份验证，则必须创建 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 登录名，这些登录名存储在 SQL Server 中。</span><span class="sxs-lookup"><span data-stu-id="86353-139">If you must use mixed mode authentication, you must create [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] logins, which are stored in SQL Server.</span></span> <span data-ttu-id="86353-140">然后，您必须在运行时提供 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="86353-140">You then have to supply the [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] user name and password at run time.</span></span>  
  
> [!IMPORTANT]
>  [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="86353-141"> 使用名为 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]（“system administrator”的缩写）的 `sa` 登录名进行安装。</span><span class="sxs-lookup"><span data-stu-id="86353-141"> installs with a [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] login named `sa` (an abbreviation of "system administrator").</span></span> <span data-ttu-id="86353-142">为 `sa` 登录分配一个强密码，并且不要在应用程序中使用 `sa` 登录。</span><span class="sxs-lookup"><span data-stu-id="86353-142">Assign a strong password to the `sa` login and do not use the `sa` login in your application.</span></span> <span data-ttu-id="86353-143">`sa` 登录名会映射到 `sysadmin` 固定服务器角色，它对整个服务器有不能撤销的管理凭据。</span><span class="sxs-lookup"><span data-stu-id="86353-143">The `sa` login maps to the `sysadmin` fixed server role, which has irrevocable administrative credentials on the whole server.</span></span> <span data-ttu-id="86353-144">如果攻击者以系统管理员的身份获取了访问权限，则可能造成的危害是无法预计的。</span><span class="sxs-lookup"><span data-stu-id="86353-144">There are no limits to the potential damage if an attacker gains access as a system administrator.</span></span> <span data-ttu-id="86353-145">默认情况下，Windows `BUILTIN\Administrators` 组（本地管理员组）的所有成员均为 `sysadmin` 角色的成员，但可以从该角色中移除这些成员。</span><span class="sxs-lookup"><span data-stu-id="86353-145">All members of the Windows `BUILTIN\Administrators` group (the local administrator's group) are members of the `sysadmin` role by default, but can be removed from that role.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="86353-146"> 提供了在 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 或更高版本上运行时 [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] 登录的 Windows 密码策略机制。</span><span class="sxs-lookup"><span data-stu-id="86353-146"> provides Windows password policy mechanisms for [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] logins when it is running on [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] or later versions.</span></span> <span data-ttu-id="86353-147">密码复杂性策略通过增加可能密码的数量来阻止强力攻击。</span><span class="sxs-lookup"><span data-stu-id="86353-147">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="86353-148"> 可将 [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] 中使用的相同复杂性和到期策略应用于 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 中使用的密码。</span><span class="sxs-lookup"><span data-stu-id="86353-148"> can apply the same complexity and expiration policies used in [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] to passwords used inside [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="86353-149">连接来自用户输入的连接字符串会使您遭受连接字符串注入攻击。</span><span class="sxs-lookup"><span data-stu-id="86353-149">Concatenating connection strings from user input can leave you vulnerable to a connection string injection attack.</span></span> <span data-ttu-id="86353-150">可使用 <xref:System.Data.SqlClient.SqlConnectionStringBuilder> 在运行时创建语法构成有效的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="86353-150">Use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="86353-151">有关详细信息，请参阅[连接字符串生成器](../../../../../docs/framework/data/adonet/connection-string-builders.md)。</span><span class="sxs-lookup"><span data-stu-id="86353-151">For more information, see [Connection String Builders](../../../../../docs/framework/data/adonet/connection-string-builders.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="86353-152">外部资源</span><span class="sxs-lookup"><span data-stu-id="86353-152">External Resources</span></span>  
 <span data-ttu-id="86353-153">有关更多信息，请参见以下资源。</span><span class="sxs-lookup"><span data-stu-id="86353-153">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="86353-154">资源</span><span class="sxs-lookup"><span data-stu-id="86353-154">Resource</span></span>|<span data-ttu-id="86353-155">描述</span><span class="sxs-lookup"><span data-stu-id="86353-155">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="86353-156">[主体](http://msdn.microsoft.com/library/bb543165.aspx)中[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]联机丛书</span><span class="sxs-lookup"><span data-stu-id="86353-156">[Principals](http://msdn.microsoft.com/library/bb543165.aspx) in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online</span></span>|<span data-ttu-id="86353-157">介绍了 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 中的登录名和其他安全主体。</span><span class="sxs-lookup"><span data-stu-id="86353-157">Describes logins and other security principals in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86353-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="86353-158">See Also</span></span>  
 [<span data-ttu-id="86353-159">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="86353-159">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="86353-160">SQL Server 中的应用程序安全性方案</span><span class="sxs-lookup"><span data-stu-id="86353-160">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="86353-161">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="86353-161">Connecting to a Data Source</span></span>](../../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="86353-162">连接字符串</span><span class="sxs-lookup"><span data-stu-id="86353-162">Connection Strings</span></span>](../../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="86353-163">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="86353-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

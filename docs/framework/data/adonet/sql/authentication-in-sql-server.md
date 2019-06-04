---
title: SQL Server 中的身份验证
ms.date: 05/22/2018
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
ms.openlocfilehash: 5809a75dbadffbd2528f6882aa586aecd3232408
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490096"
---
# <a name="authentication-in-sql-server"></a><span data-ttu-id="ddb54-102">SQL Server 中的身份验证</span><span class="sxs-lookup"><span data-stu-id="ddb54-102">Authentication in SQL Server</span></span>
<span data-ttu-id="ddb54-103">SQL Server 支持两种身份验证模式，Windows 身份验证模式和混合模式。</span><span class="sxs-lookup"><span data-stu-id="ddb54-103">SQL Server supports two authentication modes, Windows authentication mode and mixed mode.</span></span>  
  
- <span data-ttu-id="ddb54-104">Windows 身份验证是默认模式（通常称为集成安全），因为此 SQL Server 安全模型与 Windows 高度集成。</span><span class="sxs-lookup"><span data-stu-id="ddb54-104">Windows authentication is the default, and is often referred to as integrated security because this SQL Server security model is tightly integrated with Windows.</span></span> <span data-ttu-id="ddb54-105">信任特定 Windows 用户和组帐户登录 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="ddb54-105">Specific Windows user and group accounts are trusted to log in to SQL Server.</span></span> <span data-ttu-id="ddb54-106">已经过身份验证的 Windows 用户不必提供附加的凭据。</span><span class="sxs-lookup"><span data-stu-id="ddb54-106">Windows users who have already been authenticated do not have to present additional credentials.</span></span>  
  
- <span data-ttu-id="ddb54-107">混合模式支持通过 Windows 和 SQL Server 进行的身份验证。</span><span class="sxs-lookup"><span data-stu-id="ddb54-107">Mixed mode supports authentication both by Windows and by SQL Server.</span></span> <span data-ttu-id="ddb54-108">用户名和密码对保留在 SQL Server 中。</span><span class="sxs-lookup"><span data-stu-id="ddb54-108">User name and password pairs are maintained within SQL Server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ddb54-109">我们建议尽可能使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="ddb54-109">We recommend using Windows authentication wherever possible.</span></span> <span data-ttu-id="ddb54-110">Windows 身份验证使用一系列加密消息验证 SQL Server 中的用户。</span><span class="sxs-lookup"><span data-stu-id="ddb54-110">Windows authentication uses a series of encrypted messages to authenticate users in SQL Server.</span></span> <span data-ttu-id="ddb54-111">当使用 SQL Server 登录名时，SQL Server 登录名和加密的密码传递通过网络，这使它们不太安全。</span><span class="sxs-lookup"><span data-stu-id="ddb54-111">When SQL Server logins are used, SQL Server login names and encrypted passwords are passed across the network, which makes them less secure.</span></span>  
  
 <span data-ttu-id="ddb54-112">使用 Windows 身份验证，已经登录到 Windows 的用户不必再单独登录到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="ddb54-112">With Windows authentication, users are already logged onto Windows and do not have to log on separately to SQL Server.</span></span> <span data-ttu-id="ddb54-113">以下`SqlConnection.ConnectionString`指定 Windows 身份验证，而无需用户提供用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="ddb54-113">The following `SqlConnection.ConnectionString` specifies Windows authentication without requiring users to provide a user name or password.</span></span>  
  
```  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;  
```  
  
> [!NOTE]
>  <span data-ttu-id="ddb54-114">登录名与数据库用户名不同。</span><span class="sxs-lookup"><span data-stu-id="ddb54-114">Logins are distinct from database users.</span></span> <span data-ttu-id="ddb54-115">您必须通过单独的操作将登录或 Windows 组映射到数据库用户或角色。</span><span class="sxs-lookup"><span data-stu-id="ddb54-115">You must map logins or Windows groups to database users or roles in a separate operation.</span></span> <span data-ttu-id="ddb54-116">然后向用户或角色授予访问数据库对象的权限。</span><span class="sxs-lookup"><span data-stu-id="ddb54-116">You then grant permissions to users or roles to access database objects.</span></span>  
  
## <a name="authentication-scenarios"></a><span data-ttu-id="ddb54-117">身份验证方案</span><span class="sxs-lookup"><span data-stu-id="ddb54-117">Authentication Scenarios</span></span>  
 <span data-ttu-id="ddb54-118">在下列情形中，Windows 身份验证通常为最佳选择：</span><span class="sxs-lookup"><span data-stu-id="ddb54-118">Windows authentication is usually the best choice in the following situations:</span></span>  
  
- <span data-ttu-id="ddb54-119">存在域控制器。</span><span class="sxs-lookup"><span data-stu-id="ddb54-119">There is a domain controller.</span></span>  
  
- <span data-ttu-id="ddb54-120">应用程序和数据库位于同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="ddb54-120">The application and the database are on the same computer.</span></span>  
  
- <span data-ttu-id="ddb54-121">使用 SQL Server Express 或 LocalDB 的实例。</span><span class="sxs-lookup"><span data-stu-id="ddb54-121">You are using an instance of SQL Server Express or LocalDB.</span></span>  
  
 <span data-ttu-id="ddb54-122">SQL Server 登录常常在以下情况中使用：</span><span class="sxs-lookup"><span data-stu-id="ddb54-122">SQL Server logins are often used in the following situations:</span></span>  
  
- <span data-ttu-id="ddb54-123">您有工作组。</span><span class="sxs-lookup"><span data-stu-id="ddb54-123">If you have a workgroup.</span></span>  
  
- <span data-ttu-id="ddb54-124">用户从其他不受信任的域进行连接。</span><span class="sxs-lookup"><span data-stu-id="ddb54-124">Users connect from different, non-trusted domains.</span></span>  
  
- <span data-ttu-id="ddb54-125">Internet 应用程序，如 ASP.NET。</span><span class="sxs-lookup"><span data-stu-id="ddb54-125">Internet applications, such as ASP.NET.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddb54-126">指定 Windows 身份验证不会禁用 SQL Server 登录。</span><span class="sxs-lookup"><span data-stu-id="ddb54-126">Specifying Windows authentication does not disable SQL Server logins.</span></span> <span data-ttu-id="ddb54-127">使用 ALTER LOGIN DISABLE Transact-SQL 语句会禁用具有高特权的 SQL Server 登录。</span><span class="sxs-lookup"><span data-stu-id="ddb54-127">Use the ALTER LOGIN DISABLE Transact-SQL statement to disable highly-privileged SQL Server logins.</span></span>  
  
## <a name="login-types"></a><span data-ttu-id="ddb54-128">登录类型</span><span class="sxs-lookup"><span data-stu-id="ddb54-128">Login Types</span></span>  
 <span data-ttu-id="ddb54-129">SQL Server 支持三种类型的登录名：</span><span class="sxs-lookup"><span data-stu-id="ddb54-129">SQL Server supports three types of logins:</span></span>  
  
- <span data-ttu-id="ddb54-130">本地 Windows 用户帐户或受信任的域帐户。</span><span class="sxs-lookup"><span data-stu-id="ddb54-130">A local Windows user account or trusted domain account.</span></span> <span data-ttu-id="ddb54-131">SQL Server 依赖 Windows 来对 Windows 用户帐户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ddb54-131">SQL Server relies on Windows to authenticate the Windows user accounts.</span></span>  
  
- <span data-ttu-id="ddb54-132">Windows 组。</span><span class="sxs-lookup"><span data-stu-id="ddb54-132">Windows group.</span></span> <span data-ttu-id="ddb54-133">向 Windows 组授予访问权限会向作为该组的成员的所有 Windows 用户登录授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="ddb54-133">Granting access to a Windows group grants access to all Windows user logins that are members of the group.</span></span>  
  
- <span data-ttu-id="ddb54-134">SQL Server 登录。</span><span class="sxs-lookup"><span data-stu-id="ddb54-134">SQL Server login.</span></span> <span data-ttu-id="ddb54-135">SQL Server 将用户名和密码的哈希形式都存储在 master 数据库中，使用内部身份验证方法验证尝试的登录。</span><span class="sxs-lookup"><span data-stu-id="ddb54-135">SQL Server stores both the username and a hash of the password in the master database, by using internal authentication methods to verify login attempts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddb54-136">SQL Server 提供从证书或仅用于代码签名的非对称密钥创建的登录名。</span><span class="sxs-lookup"><span data-stu-id="ddb54-136">SQL Server provides logins created from certificates or asymmetric keys that are used only for code signing.</span></span> <span data-ttu-id="ddb54-137">但无法使用这些登录名连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="ddb54-137">They cannot be used to connect to SQL Server.</span></span>  
  
## <a name="mixed-mode-authentication"></a><span data-ttu-id="ddb54-138">混合模式身份验证</span><span class="sxs-lookup"><span data-stu-id="ddb54-138">Mixed Mode Authentication</span></span>  
 <span data-ttu-id="ddb54-139">如果您必须使用混合模式身份验证，则必须创建 SQL Server 登录名，将其存储在 SQL Server 中。</span><span class="sxs-lookup"><span data-stu-id="ddb54-139">If you must use mixed mode authentication, you must create SQL Server logins, which are stored in SQL Server.</span></span> <span data-ttu-id="ddb54-140">然后必须在运行时提供 SQL Server 用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="ddb54-140">You then have to supply the SQL Server user name and password at run time.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ddb54-141">SQL Server 使用名为 `sa`（“系统管理员”的缩写）的 SQL Server 登录进行安装。</span><span class="sxs-lookup"><span data-stu-id="ddb54-141">SQL Server installs with a SQL Server login named `sa` (an abbreviation of "system administrator").</span></span> <span data-ttu-id="ddb54-142">为 `sa` 登录分配一个强密码，并且不要在应用程序中使用 `sa` 登录。</span><span class="sxs-lookup"><span data-stu-id="ddb54-142">Assign a strong password to the `sa` login and do not use the `sa` login in your application.</span></span> <span data-ttu-id="ddb54-143">`sa` 登录名会映射到 `sysadmin` 固定服务器角色，它对整个服务器有不能撤销的管理凭据。</span><span class="sxs-lookup"><span data-stu-id="ddb54-143">The `sa` login maps to the `sysadmin` fixed server role, which has irrevocable administrative credentials on the whole server.</span></span> <span data-ttu-id="ddb54-144">如果攻击者以系统管理员的身份获取了访问权限，则可能造成的危害是无法预计的。</span><span class="sxs-lookup"><span data-stu-id="ddb54-144">There are no limits to the potential damage if an attacker gains access as a system administrator.</span></span> <span data-ttu-id="ddb54-145">默认情况下，Windows `BUILTIN\Administrators` 组（本地管理员组）的所有成员均为 `sysadmin` 角色的成员，但可以从该角色中移除这些成员。</span><span class="sxs-lookup"><span data-stu-id="ddb54-145">All members of the Windows `BUILTIN\Administrators` group (the local administrator's group) are members of the `sysadmin` role by default, but can be removed from that role.</span></span>  
  
 <span data-ttu-id="ddb54-146">SQL Server 上运行时提供 SQL Server 登录名的 Windows 密码策略机制[!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)]或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ddb54-146">SQL Server provides Windows password policy mechanisms for SQL Server logins when it is running on [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] or later versions.</span></span> <span data-ttu-id="ddb54-147">密码复杂性策略通过增加可能密码的数量来阻止强力攻击。</span><span class="sxs-lookup"><span data-stu-id="ddb54-147">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="ddb54-148">SQL Server 可以应用中使用的相同复杂性和到期策略[!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)]到 SQL Server 中使用的密码。</span><span class="sxs-lookup"><span data-stu-id="ddb54-148">SQL Server can apply the same complexity and expiration policies used in [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] to passwords used inside SQL Server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ddb54-149">连接来自用户输入的连接字符串会使您遭受连接字符串注入攻击。</span><span class="sxs-lookup"><span data-stu-id="ddb54-149">Concatenating connection strings from user input can leave you vulnerable to a connection string injection attack.</span></span> <span data-ttu-id="ddb54-150">可使用 <xref:System.Data.SqlClient.SqlConnectionStringBuilder> 在运行时创建语法构成有效的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="ddb54-150">Use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="ddb54-151">有关详细信息，请参阅[连接字符串生成器](../../../../../docs/framework/data/adonet/connection-string-builders.md)。</span><span class="sxs-lookup"><span data-stu-id="ddb54-151">For more information, see [Connection String Builders](../../../../../docs/framework/data/adonet/connection-string-builders.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="ddb54-152">外部资源</span><span class="sxs-lookup"><span data-stu-id="ddb54-152">External Resources</span></span>  
 <span data-ttu-id="ddb54-153">有关更多信息，请参见以下资源。</span><span class="sxs-lookup"><span data-stu-id="ddb54-153">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="ddb54-154">资源</span><span class="sxs-lookup"><span data-stu-id="ddb54-154">Resource</span></span>|<span data-ttu-id="ddb54-155">描述</span><span class="sxs-lookup"><span data-stu-id="ddb54-155">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="ddb54-156">主体</span><span class="sxs-lookup"><span data-stu-id="ddb54-156">Principals</span></span>](/sql/relational-databases/security/authentication-access/principals-database-engine)|<span data-ttu-id="ddb54-157">描述登录和其他 SQL Server 中的安全主体。</span><span class="sxs-lookup"><span data-stu-id="ddb54-157">Describes logins and other security principals in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ddb54-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddb54-158">See also</span></span>

- [<span data-ttu-id="ddb54-159">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="ddb54-159">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [<span data-ttu-id="ddb54-160">SQL Server 中的应用程序安全性方案</span><span class="sxs-lookup"><span data-stu-id="ddb54-160">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="ddb54-161">连接到数据源</span><span class="sxs-lookup"><span data-stu-id="ddb54-161">Connecting to a Data Source</span></span>](../../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)
- [<span data-ttu-id="ddb54-162">连接字符串</span><span class="sxs-lookup"><span data-stu-id="ddb54-162">Connection Strings</span></span>](../../../../../docs/framework/data/adonet/connection-strings.md)
- [<span data-ttu-id="ddb54-163">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="ddb54-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

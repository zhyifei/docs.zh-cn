---
title: "LINQ to SQL 中的安全性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d49787f7-414e-4c71-aa33-80a5895536b1
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0ee361c27bd14f0266b2b86f315f9c091e049c12
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="security-in-linq-to-sql"></a><span data-ttu-id="fbf32-102">LINQ to SQL 中的安全性</span><span class="sxs-lookup"><span data-stu-id="fbf32-102">Security in LINQ to SQL</span></span>
<span data-ttu-id="fbf32-103">连接到数据库时始终都存在安全风险。</span><span class="sxs-lookup"><span data-stu-id="fbf32-103">Security risks are always present when you connect to a database.</span></span> <span data-ttu-id="fbf32-104">尽管 LINQ to SQL 可能包括一些使用 SQL Server 中的数据的新方法，但它并没有提供任何附加安全机制。</span><span class="sxs-lookup"><span data-stu-id="fbf32-104">Although LINQ to SQL may include some new ways to work with data in SQL Server, it does not provide any additional security mechanisms.</span></span>  
  
## <a name="access-control-and-authentication"></a><span data-ttu-id="fbf32-105">访问控制和身份验证</span><span class="sxs-lookup"><span data-stu-id="fbf32-105">Access Control and Authentication</span></span>  
 <span data-ttu-id="fbf32-106">LINQ to SQL 没有自己的用户模型或身份验证机制。</span><span class="sxs-lookup"><span data-stu-id="fbf32-106">LINQ to SQL does not have its own user model or authentication mechanisms.</span></span> <span data-ttu-id="fbf32-107">使用 SQL Server 安全性可控制对映射到对象模型的数据库、数据库表、视图和存储过程的访问。</span><span class="sxs-lookup"><span data-stu-id="fbf32-107">Use SQL Server Security to control access to the database, database tables, views, and stored procedures that are mapped to your object model.</span></span> <span data-ttu-id="fbf32-108">授予用户所需的最低访问权限并要求对用户身份验证使用强密码。</span><span class="sxs-lookup"><span data-stu-id="fbf32-108">Grant the minimally required access to users and require strong passwords for user authentication.</span></span>  
  
## <a name="mapping-and-schema-information"></a><span data-ttu-id="fbf32-109">映射和架构信息</span><span class="sxs-lookup"><span data-stu-id="fbf32-109">Mapping and Schema Information</span></span>  
 <span data-ttu-id="fbf32-110">对象模型或外部映射文件中的 SQL-CLR 类型映射和数据库架构信息可供访问文件系统中的这些文件的所有用户使用。</span><span class="sxs-lookup"><span data-stu-id="fbf32-110">SQL-CLR type mapping and database schema information in your object model or external mapping file is available for all with access to those files in the file system.</span></span> <span data-ttu-id="fbf32-111">假设架构信息将供可访问对象模型或外部映射文件的所有用户使用。若要防止对架构信息进行更大范围的访问，请使用文件安全机制保护源文件和映射文件。</span><span class="sxs-lookup"><span data-stu-id="fbf32-111">Assume that schema information will be available to all who can access the object model or external mapping file.To prevent more widespread access to schema information, use file security mechanisms to secure source files and mapping files.</span></span>  
  
## <a name="connection-strings"></a><span data-ttu-id="fbf32-112">连接字符串</span><span class="sxs-lookup"><span data-stu-id="fbf32-112">Connection Strings</span></span>  
 <span data-ttu-id="fbf32-113">应尽可能避免在连接字符串中使用密码。</span><span class="sxs-lookup"><span data-stu-id="fbf32-113">Using passwords in connection strings should be avoided whenever possible.</span></span> <span data-ttu-id="fbf32-114">连接字符串不仅会在自己的权限方面带来安全风险，而且在使用对象关系设计器或 SQLMetal 命令行工具时，连接字符串还可能会以明文形式添加到对象模型或外部映射文件。</span><span class="sxs-lookup"><span data-stu-id="fbf32-114">Not only is a connection string a security risk in its own right, but the connection string may also be added in clear text to the object model or external mapping file when using the Object Relational Designer or SQLMetal command-line tool.</span></span> <span data-ttu-id="fbf32-115">可通过文件系统访问对象模型或外部映射文件的任何用户都可以查看连接密码（如果该密码包含在连接字符串中）。</span><span class="sxs-lookup"><span data-stu-id="fbf32-115">Anyone with access to the object model or external mapping file via the file system could see the connection password (if it is included in the connection string).</span></span>  
  
 <span data-ttu-id="fbf32-116">为了尽可能降低此类风险，请使用集成安全性与 [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] 建立可信连接。</span><span class="sxs-lookup"><span data-stu-id="fbf32-116">To minimize such risks, use integrated security to make a trusted connection with [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fbf32-117">通过使用这种方法，您无需将密码存储在连接字符串中。</span><span class="sxs-lookup"><span data-stu-id="fbf32-117">By using this approach, you do not have to store a password in the connection string.</span></span> <span data-ttu-id="fbf32-118">有关详细信息，请参阅[SQL Server 安全性](../../../../../../docs/framework/data/adonet/sql/sql-server-security.md)。</span><span class="sxs-lookup"><span data-stu-id="fbf32-118">For more information, see [SQL Server Security](../../../../../../docs/framework/data/adonet/sql/sql-server-security.md).</span></span>  
  
 <span data-ttu-id="fbf32-119">如果缺少集成安全性，则连接字符串中将需要明文密码。</span><span class="sxs-lookup"><span data-stu-id="fbf32-119">In the absence of integrated security, a clear-text password will be needed in the connection string.</span></span> <span data-ttu-id="fbf32-120">帮助保护连接字符串的最佳方法如下（按风险升序排列）：</span><span class="sxs-lookup"><span data-stu-id="fbf32-120">The best way to help secure your connection string, in increasing order of risk, is as follows:</span></span>  
  
-   <span data-ttu-id="fbf32-121">使用集成安全性。</span><span class="sxs-lookup"><span data-stu-id="fbf32-121">Use integrated security.</span></span>  
  
-   <span data-ttu-id="fbf32-122">通过密码保护连接字符串并尽可能减少连接字符串的传递。</span><span class="sxs-lookup"><span data-stu-id="fbf32-122">Secure connection strings with passwords and minimize passing around connection strings.</span></span>  
  
-   <span data-ttu-id="fbf32-123">使用 <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> 类来替代连接字符串，因为它可以限制公开的持续时间。</span><span class="sxs-lookup"><span data-stu-id="fbf32-123">Use a <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> class instead of a connection string since it limits the duration of exposure.</span></span> <span data-ttu-id="fbf32-124">可使用 <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> 来实例化 LINQ to SQL <xref:System.Data.SqlClient.SqlConnection> 类。</span><span class="sxs-lookup"><span data-stu-id="fbf32-124">The LINQ to SQL <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> class can be instantiated using a <xref:System.Data.SqlClient.SqlConnection>.</span></span>  
  
-   <span data-ttu-id="fbf32-125">最大程度地减少所有连接字符串的生存期和接触点。</span><span class="sxs-lookup"><span data-stu-id="fbf32-125">Minimize lifetimes and touch points for all connection strings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf32-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="fbf32-126">See Also</span></span>  
 [<span data-ttu-id="fbf32-127">背景信息</span><span class="sxs-lookup"><span data-stu-id="fbf32-127">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="fbf32-128">常见问题</span><span class="sxs-lookup"><span data-stu-id="fbf32-128">Frequently Asked Questions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/frequently-asked-questions.md)

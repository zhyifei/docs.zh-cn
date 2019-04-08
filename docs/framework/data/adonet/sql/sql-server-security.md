---
title: SQL Server 安全性
ms.date: 03/30/2017
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
ms.openlocfilehash: 4aa4feadb6305f8a0ea6f99c2add780d6fca95cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080748"
---
# <a name="sql-server-security"></a><span data-ttu-id="5884c-102">SQL Server 安全性</span><span class="sxs-lookup"><span data-stu-id="5884c-102">SQL Server Security</span></span>
<span data-ttu-id="5884c-103">SQL Server 具有多个支持创建安全数据库应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="5884c-103">SQL Server has many features that support creating secure database applications.</span></span>  
  
 <span data-ttu-id="5884c-104">不管您要使用哪个版本的 SQL Server，一般性的安全注意事项（如数据盗窃和蓄意破坏）都适用。</span><span class="sxs-lookup"><span data-stu-id="5884c-104">Common security considerations, such as data theft or vandalism, apply regardless of the version of SQL Server you are using.</span></span> <span data-ttu-id="5884c-105">数据完整性也应视为安全问题。</span><span class="sxs-lookup"><span data-stu-id="5884c-105">Data integrity should also be considered as a security issue.</span></span> <span data-ttu-id="5884c-106">如果数据不加保护，则在允许对数据执行临时操作并且数据被有意或无意修改（添加错误的值或完全删除）的情况下，数据可能会变得毫无价值。</span><span class="sxs-lookup"><span data-stu-id="5884c-106">If data is not protected, it is possible that it could become worthless if ad hoc data manipulation is permitted and the data is inadvertently or maliciously modified with incorrect values or deleted entirely.</span></span> <span data-ttu-id="5884c-107">此外，通常还有一些必须遵守的法定要求，如正确存储机密信息。</span><span class="sxs-lookup"><span data-stu-id="5884c-107">In addition, there are often legal requirements that must be adhered to, such as the correct storage of confidential information.</span></span> <span data-ttu-id="5884c-108">完全禁止存储某些类型的个人数据，具体取决于特定司法范围内适用的法律。</span><span class="sxs-lookup"><span data-stu-id="5884c-108">Storing some kinds of personal data is proscribed entirely, depending on the laws that apply in a particular jurisdiction.</span></span>  
  
 <span data-ttu-id="5884c-109">和每个版本的 Windows 一样，每个版本的 SQL Server 都具有不同的安全功能，版本越高，功能越强。</span><span class="sxs-lookup"><span data-stu-id="5884c-109">Each version of SQL Server has different security features, as does each version of Windows, with later versions having enhanced functionality over earlier ones.</span></span> <span data-ttu-id="5884c-110">必须了解的是，安全功能本身不能保证数据库应用程序的安全。</span><span class="sxs-lookup"><span data-stu-id="5884c-110">It is important to understand that security features alone cannot guarantee a secure database application.</span></span> <span data-ttu-id="5884c-111">每个数据库应用程序都具有独特的要求、执行环境、部署模型、物理位置和用户人群。</span><span class="sxs-lookup"><span data-stu-id="5884c-111">Each database application is unique in its requirements, execution environment, deployment model, physical location, and user population.</span></span> <span data-ttu-id="5884c-112">范围限于本地的一些应用程序可能只需要最低的安全性，而其他本地应用程序或通过 Internet 部署的应用程序可能需要严格的安全措施和实时监控和评估。</span><span class="sxs-lookup"><span data-stu-id="5884c-112">Some applications that are local in scope may need only minimal security whereas other local applications or applications deployed over the Internet may require stringent security measures and ongoing monitoring and evaluation.</span></span>  
  
 <span data-ttu-id="5884c-113">SQL Server 数据库应用程序的安全要求应该在设计时加以考虑，而不应事后考虑。</span><span class="sxs-lookup"><span data-stu-id="5884c-113">The security requirements of a SQL Server database application should be considered at design time, not as an afterthought.</span></span> <span data-ttu-id="5884c-114">在开发周期的初期评估危胁可以减轻检测到漏洞时造成的潜在损害。</span><span class="sxs-lookup"><span data-stu-id="5884c-114">Evaluating threats early in the development cycle gives you the opportunity to mitigate potential damage wherever a vulnerability is detected.</span></span>  
  
 <span data-ttu-id="5884c-115">即使应用程序的初始设计非常可靠，但随着系统的发展，仍可能会出现新的危胁。</span><span class="sxs-lookup"><span data-stu-id="5884c-115">Even if the initial design of an application is sound, new threats may emerge as the system evolves.</span></span> <span data-ttu-id="5884c-116">通过在数据库周围构建多道防线，可以最大程度地减轻安全侵犯事件所造成的损害。</span><span class="sxs-lookup"><span data-stu-id="5884c-116">By creating multiple lines of defense around your database, you can minimize the damage inflicted by a security breach.</span></span> <span data-ttu-id="5884c-117">第一道防线是通过仅授予完全必要的权限而不授予更多权限来减小攻击面。</span><span class="sxs-lookup"><span data-stu-id="5884c-117">Your first line of defense is to reduce the attack surface area by never to granting more permissions than are absolutely necessary.</span></span>  
  
 <span data-ttu-id="5884c-118">本节中的主题简要说明 SQL Server 中与开发人员相关的安全功能，并提供到 SQL Server 联机丛书中相关主题和提供更详细说明的其他资源的链接。</span><span class="sxs-lookup"><span data-stu-id="5884c-118">The topics in this section briefly describe the security features in SQL Server that are relevant for developers, with links to relevant topics in SQL Server Books Online and other resources that provide more detailed coverage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5884c-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="5884c-119">In This Section</span></span>  
 [<span data-ttu-id="5884c-120">SQL Server 安全性概述</span><span class="sxs-lookup"><span data-stu-id="5884c-120">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 <span data-ttu-id="5884c-121">说明 SQL Server 的体系结构和安全功能。</span><span class="sxs-lookup"><span data-stu-id="5884c-121">Describes the architecture and security features of SQL Server.</span></span>  
  
 [<span data-ttu-id="5884c-122">SQL Server 中的应用程序安全性方案</span><span class="sxs-lookup"><span data-stu-id="5884c-122">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 <span data-ttu-id="5884c-123">包含论述 ADO.NET 和 SQL Server 应用程序各种应用程序安全方案的主题。</span><span class="sxs-lookup"><span data-stu-id="5884c-123">Contains topics discussing various application security scenarios for ADO.NET and SQL Server applications.</span></span>  
  
 [<span data-ttu-id="5884c-124">SQL Server Express 安全性</span><span class="sxs-lookup"><span data-stu-id="5884c-124">SQL Server Express Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-express-security.md)  
 <span data-ttu-id="5884c-125">介绍有关 SQL Server Express 的安全注意事项。</span><span class="sxs-lookup"><span data-stu-id="5884c-125">Describes security considerations for SQL Server Express.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5884c-126">相关章节</span><span class="sxs-lookup"><span data-stu-id="5884c-126">Related Sections</span></span>  
[<span data-ttu-id="5884c-127">SQL Server 数据库引擎和 Azure SQL 数据库安全中心</span><span class="sxs-lookup"><span data-stu-id="5884c-127">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](/sql/relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database)  
<span data-ttu-id="5884c-128">介绍 SQL Server 和 Azure SQL 数据库的安全注意事项。</span><span class="sxs-lookup"><span data-stu-id="5884c-128">Describes security considerations for SQL Server and Azure SQL Database.</span></span>

[<span data-ttu-id="5884c-129">有关安装 SQL Server 的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="5884c-129">Security Considerations for a SQL Server Installation</span></span>](/sql/sql-server/install/security-considerations-for-a-sql-server-installation)  
<span data-ttu-id="5884c-130">说明安装 SQL Server 之前需要考虑的安全问题。</span><span class="sxs-lookup"><span data-stu-id="5884c-130">Describes security concerns to consider before installing SQL Server.</span></span>

## <a name="see-also"></a><span data-ttu-id="5884c-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="5884c-131">See also</span></span>

- [<span data-ttu-id="5884c-132">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="5884c-132">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [<span data-ttu-id="5884c-133">SQL Server 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5884c-133">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)

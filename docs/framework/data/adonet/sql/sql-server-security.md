---
title: "SQL Server 安全性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4f41a794916c63672ca0c844f086629f77b90aa0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-security"></a><span data-ttu-id="94018-102">SQL Server 安全性</span><span class="sxs-lookup"><span data-stu-id="94018-102">SQL Server Security</span></span>
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="94018-103"> 具有许多支持创建安全数据库应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="94018-103"> has many features that support creating secure database applications.</span></span>  
  
 <span data-ttu-id="94018-104">无论您要使用哪个版本的 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]，通用安全注意事项（如数据盗窃和蓄意破坏）都适用。</span><span class="sxs-lookup"><span data-stu-id="94018-104">Common security considerations, such as data theft or vandalism, apply regardless of the version of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] you are using.</span></span> <span data-ttu-id="94018-105">数据完整性也应视为安全问题。</span><span class="sxs-lookup"><span data-stu-id="94018-105">Data integrity should also be considered as a security issue.</span></span> <span data-ttu-id="94018-106">如果数据不加保护，则在允许对数据执行临时操作并且数据被有意或无意修改（添加错误的值或完全删除）的情况下，数据可能会变得毫无价值。</span><span class="sxs-lookup"><span data-stu-id="94018-106">If data is not protected, it is possible that it could become worthless if ad hoc data manipulation is permitted and the data is inadvertently or maliciously modified with incorrect values or deleted entirely.</span></span> <span data-ttu-id="94018-107">此外，通常还有一些必须遵守的法定要求，如正确存储机密信息。</span><span class="sxs-lookup"><span data-stu-id="94018-107">In addition, there are often legal requirements that must be adhered to, such as the correct storage of confidential information.</span></span> <span data-ttu-id="94018-108">完全禁止存储某些类型的个人数据，具体取决于特定司法范围内适用的法律。</span><span class="sxs-lookup"><span data-stu-id="94018-108">Storing some kinds of personal data is proscribed entirely, depending on the laws that apply in a particular jurisdiction.</span></span>  
  
 <span data-ttu-id="94018-109">与每个版本的 Windows 一样，每个版本的 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 都具有不同的安全功能，版本越高，功能越强。</span><span class="sxs-lookup"><span data-stu-id="94018-109">Each version of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] has different security features, as does each version of Windows, with later versions having enhanced functionality over earlier ones.</span></span> <span data-ttu-id="94018-110">必须了解的是，安全功能本身不能保证数据库应用程序的安全。</span><span class="sxs-lookup"><span data-stu-id="94018-110">It is important to understand that security features alone cannot guarantee a secure database application.</span></span> <span data-ttu-id="94018-111">每个数据库应用程序都具有独特的要求、执行环境、部署模型、物理位置和用户人群。</span><span class="sxs-lookup"><span data-stu-id="94018-111">Each database application is unique in its requirements, execution environment, deployment model, physical location, and user population.</span></span> <span data-ttu-id="94018-112">范围限于本地的一些应用程序可能只需要最低的安全性，而其他本地应用程序或通过 Internet 部署的应用程序可能需要严格的安全措施和实时监控和评估。</span><span class="sxs-lookup"><span data-stu-id="94018-112">Some applications that are local in scope may need only minimal security whereas other local applications or applications deployed over the Internet may require stringent security measures and ongoing monitoring and evaluation.</span></span>  
  
 <span data-ttu-id="94018-113">[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 数据库应用程序的安全要求应该在设计时就加以考虑，而不应事后再考虑。</span><span class="sxs-lookup"><span data-stu-id="94018-113">The security requirements of a [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] database application should be considered at design time, not as an afterthought.</span></span> <span data-ttu-id="94018-114">在开发周期的初期评估危胁可以减轻检测到漏洞时造成的潜在损害。</span><span class="sxs-lookup"><span data-stu-id="94018-114">Evaluating threats early in the development cycle gives you the opportunity to mitigate potential damage wherever a vulnerability is detected.</span></span>  
  
 <span data-ttu-id="94018-115">即使应用程序的初始设计非常可靠，但随着系统的发展，仍可能会出现新的危胁。</span><span class="sxs-lookup"><span data-stu-id="94018-115">Even if the initial design of an application is sound, new threats may emerge as the system evolves.</span></span> <span data-ttu-id="94018-116">通过在数据库周围构建多道防线，可以最大程度地减轻安全侵犯事件所造成的损害。</span><span class="sxs-lookup"><span data-stu-id="94018-116">By creating multiple lines of defense around your database, you can minimize the damage inflicted by a security breach.</span></span> <span data-ttu-id="94018-117">第一道防线是通过仅授予完全必要的权限而不授予更多权限来减小攻击面。</span><span class="sxs-lookup"><span data-stu-id="94018-117">Your first line of defense is to reduce the attack surface area by never to granting more permissions than are absolutely necessary.</span></span>  
  
 <span data-ttu-id="94018-118">本节中的主题简要说明了 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 中开发人员相关的安全功能，并提供了到 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 联机丛书中的相关主题以及提供更详细说明的其他资源的链接。</span><span class="sxs-lookup"><span data-stu-id="94018-118">The topics in this section briefly describe the security features in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] that are relevant for developers, with links to relevant topics in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online and other resources that provide more detailed coverage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94018-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="94018-119">In This Section</span></span>  
 [<span data-ttu-id="94018-120">SQL Server 安全性概述</span><span class="sxs-lookup"><span data-stu-id="94018-120">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 <span data-ttu-id="94018-121">说明了 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 的体系结构和安全功能。</span><span class="sxs-lookup"><span data-stu-id="94018-121">Describes the architecture and security features of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="94018-122">SQL Server 中的应用程序安全方案</span><span class="sxs-lookup"><span data-stu-id="94018-122">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 <span data-ttu-id="94018-123">包含对 ADO.NET 和 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 应用程序的各种应用程序安全方案进行讨论的主题。</span><span class="sxs-lookup"><span data-stu-id="94018-123">Contains topics discussing various application security scenarios for ADO.NET and [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] applications.</span></span>  
  
 [<span data-ttu-id="94018-124">SQL Server Express 安全性</span><span class="sxs-lookup"><span data-stu-id="94018-124">SQL Server Express Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-express-security.md)  
 <span data-ttu-id="94018-125">说明了 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express 的安全注意事项。</span><span class="sxs-lookup"><span data-stu-id="94018-125">Describes security considerations for [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="94018-126">相关章节</span><span class="sxs-lookup"><span data-stu-id="94018-126">Related Sections</span></span>  
 <span data-ttu-id="94018-127">[安全和保护 （数据库引擎）](http://msdn2.microsoft.com/library/bb510589\(SQL.100\).aspx.)</span><span class="sxs-lookup"><span data-stu-id="94018-127">[Security and Protection (Database Engine)](http://msdn2.microsoft.com/library/bb510589\(SQL.100\).aspx.)</span></span>  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="94018-128"> 联机丛书安全性主题。</span><span class="sxs-lookup"><span data-stu-id="94018-128"> Books Online security topics.</span></span>  
  
 [<span data-ttu-id="94018-129">SQL Server 的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="94018-129">Security Considerations for SQL Server</span></span>](http://go.microsoft.com/fwlink/?LinkId=98587)  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="94018-130"> 联机丛书安全性主题。</span><span class="sxs-lookup"><span data-stu-id="94018-130"> Books Online security topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94018-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94018-131">See Also</span></span>  
 [<span data-ttu-id="94018-132">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="94018-132">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="94018-133">SQL Server 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="94018-133">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="94018-134">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="94018-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)

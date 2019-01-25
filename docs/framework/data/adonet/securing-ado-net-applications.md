---
title: 保证 ADO.NET 应用程序的安全
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: 935d963ed19175518191006c2cc367f88d69e2aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585362"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="72ed3-102">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="72ed3-102">Securing ADO.NET Applications</span></span>
<span data-ttu-id="72ed3-103">编写安全 ADO.NET 应用程序不仅仅是避免常见的编码缺陷（如不验证用户输入）。</span><span class="sxs-lookup"><span data-stu-id="72ed3-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="72ed3-104">访问数据的应用程序具有许多潜在的故障点，攻击者可以利用这些故障点来检索、操作或损坏敏感数据。</span><span class="sxs-lookup"><span data-stu-id="72ed3-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="72ed3-105">因此，了解安全性的各个方面（从应用程序设计阶段期间的威胁建模过程到应用程序的最终部署和不断的维护）非常重要。</span><span class="sxs-lookup"><span data-stu-id="72ed3-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
 <span data-ttu-id="72ed3-106">.NET Framework 提供了很多有用的类、服务和工具，以用于保证数据库应用程序的安全和对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="72ed3-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="72ed3-107">公共语言运行库 (CLR) 提供了供代码在其中运行的类型安全环境，以及用于进一步限制托管代码权限的代码访问安全性 (CAS)。</span><span class="sxs-lookup"><span data-stu-id="72ed3-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="72ed3-108">遵循安全数据访问编码惯例可降低由潜在攻击者造成的损坏。</span><span class="sxs-lookup"><span data-stu-id="72ed3-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
 <span data-ttu-id="72ed3-109">编写安全代码不会阻止在使用非托管资源（如数据库）时自己造成的安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="72ed3-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="72ed3-110">多数服务器数据库（如 SQL Server）拥有其各自的安全系统，正确实现这些安全系统可增强安全性。</span><span class="sxs-lookup"><span data-stu-id="72ed3-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="72ed3-111">但是，即使是具有可靠安全系统的数据源，如果未适当配置，也可能受到攻击。</span><span class="sxs-lookup"><span data-stu-id="72ed3-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="72ed3-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="72ed3-112">In This Section</span></span>  
 [<span data-ttu-id="72ed3-113">安全性概述</span><span class="sxs-lookup"><span data-stu-id="72ed3-113">Security Overview</span></span>](../../../../docs/framework/data/adonet/security-overview.md)  
 <span data-ttu-id="72ed3-114">提供对设计安全 ADO.NET 应用程序的建议。</span><span class="sxs-lookup"><span data-stu-id="72ed3-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="72ed3-115">安全数据访问</span><span class="sxs-lookup"><span data-stu-id="72ed3-115">Secure Data Access</span></span>](../../../../docs/framework/data/adonet/secure-data-access.md)  
 <span data-ttu-id="72ed3-116">描述如何使用受保护数据源中的数据。</span><span class="sxs-lookup"><span data-stu-id="72ed3-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="72ed3-117">保证客户端应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="72ed3-117">Secure Client Applications</span></span>](../../../../docs/framework/data/adonet/secure-client-applications.md)  
 <span data-ttu-id="72ed3-118">描述客户端应用程序的安全注意事项。</span><span class="sxs-lookup"><span data-stu-id="72ed3-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="72ed3-119">代码访问安全性和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="72ed3-119">Code Access Security and ADO.NET</span></span>](../../../../docs/framework/data/adonet/code-access-security.md)  
 <span data-ttu-id="72ed3-120">描述 CAS 如何帮助保护 ADO.NET 代码，</span><span class="sxs-lookup"><span data-stu-id="72ed3-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="72ed3-121">还讨论如何使用部分信任。</span><span class="sxs-lookup"><span data-stu-id="72ed3-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="72ed3-122">隐私和数据安全性</span><span class="sxs-lookup"><span data-stu-id="72ed3-122">Privacy and Data Security</span></span>](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 <span data-ttu-id="72ed3-123">描述 ADO.NET 应用程序的加密选项。</span><span class="sxs-lookup"><span data-stu-id="72ed3-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="72ed3-124">相关章节</span><span class="sxs-lookup"><span data-stu-id="72ed3-124">Related Sections</span></span>  
 [<span data-ttu-id="72ed3-125">SQL Server 安全性</span><span class="sxs-lookup"><span data-stu-id="72ed3-125">SQL Server Security</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="72ed3-126">描述从开发人员角度来讲的 SQL Server 安全功能。</span><span class="sxs-lookup"><span data-stu-id="72ed3-126">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="72ed3-127">安全注意事项</span><span class="sxs-lookup"><span data-stu-id="72ed3-127">Security Considerations</span></span>](../../../../docs/framework/data/adonet/ef/security-considerations.md)  
 <span data-ttu-id="72ed3-128">描述实体框架应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="72ed3-128">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="72ed3-129">安全性</span><span class="sxs-lookup"><span data-stu-id="72ed3-129">Security</span></span>](../../../../docs/standard/security/index.md)  
 <span data-ttu-id="72ed3-130">包含描述 .NET 中各个安全方面的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="72ed3-130">Contains links to topics describing all aspects of security in .NET.</span></span>  
  
 [<span data-ttu-id="72ed3-131">安全性工具</span><span class="sxs-lookup"><span data-stu-id="72ed3-131">Security Tools</span></span>](https://msdn.microsoft.com/library/2a3eb98a-2de6-4fba-b41c-01a74d354c11)  
 <span data-ttu-id="72ed3-132">用于保证安全策略的安全和对其进行管理的 .NET Framework 工具。</span><span class="sxs-lookup"><span data-stu-id="72ed3-132">.NET Framework tools for securing and administering security policy.</span></span>  
  
 [<span data-ttu-id="72ed3-133">创建安全应用程序的资源</span><span class="sxs-lookup"><span data-stu-id="72ed3-133">Resources for Creating Secure Applications</span></span>](https://msdn.microsoft.com/library/0ebf5f69-76f2-498a-a2df-83cf3443e132)  
 <span data-ttu-id="72ed3-134">提供用于创建安全应用程序的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="72ed3-134">Provides links to topics for creating secure applications.</span></span>  
  
 [<span data-ttu-id="72ed3-135">安全性参考书目</span><span class="sxs-lookup"><span data-stu-id="72ed3-135">Security Bibliography</span></span>](/visualstudio/ide/security-bibliography)  
 <span data-ttu-id="72ed3-136">提供联机和印刷资料中提供的外部资源的链接。</span><span class="sxs-lookup"><span data-stu-id="72ed3-136">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72ed3-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="72ed3-137">See also</span></span>
- [<span data-ttu-id="72ed3-138">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="72ed3-138">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
- [<span data-ttu-id="72ed3-139">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="72ed3-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

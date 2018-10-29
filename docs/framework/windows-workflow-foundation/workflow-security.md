---
title: 工作流安全性
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], workflow security
ms.assetid: d712a566-f435-44c0-b8c0-49298e84b114
ms.openlocfilehash: 2979f8e50b7fc0d0fab419a89e708517fd271be8
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199196"
---
# <a name="workflow-security"></a><span data-ttu-id="8a51d-102">工作流安全性</span><span class="sxs-lookup"><span data-stu-id="8a51d-102">Workflow Security</span></span>
<span data-ttu-id="8a51d-103">Windows Workflow Foundation (WF) 与多个不同的技术，如 Microsoft SQL Server 和 Windows Communication Foundation (WCF) 集成。</span><span class="sxs-lookup"><span data-stu-id="8a51d-103">Windows Workflow Foundation (WF) is integrated with several different technologies, such as Microsoft SQL Server and Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="8a51d-104">如果操作不当，采用这些技术可能会给工作流带来安全问题。</span><span class="sxs-lookup"><span data-stu-id="8a51d-104">Interacting with these technologies may introduce security issues into your workflow if done improperly.</span></span>

## <a name="persistence-security-concerns"></a><span data-ttu-id="8a51d-105">持久性安全问题</span><span class="sxs-lookup"><span data-stu-id="8a51d-105">Persistence Security Concerns</span></span>

1.  <span data-ttu-id="8a51d-106">使用 <xref:System.Activities.Statements.Delay> 活动和持久性的工作流需要由服务重新激活。</span><span class="sxs-lookup"><span data-stu-id="8a51d-106">Workflows that use a <xref:System.Activities.Statements.Delay> activity and persistence need to be reactivated by a service.</span></span> <span data-ttu-id="8a51d-107">Windows AppFabric 使用工作流管理服务 (WMS) 重新激活计时器已过期的工作流。</span><span class="sxs-lookup"><span data-stu-id="8a51d-107">Windows AppFabric uses the Workflow Management Service (WMS) to reactivate workflows with expired timers.</span></span> <span data-ttu-id="8a51d-108">WMS 创建 <xref:System.ServiceModel.WorkflowServiceHost> 来承载重新激活的工作流。</span><span class="sxs-lookup"><span data-stu-id="8a51d-108">WMS creates a <xref:System.ServiceModel.WorkflowServiceHost> to host the reactivated workflow.</span></span> <span data-ttu-id="8a51d-109">如果 WMS 服务停止，则持久化的工作流在其计时器过期时将不会重新激活。</span><span class="sxs-lookup"><span data-stu-id="8a51d-109">If the WMS service is stopped, persisted workflows will not be reactivated when their timers expire.</span></span>

2.  <span data-ttu-id="8a51d-110">对持久性实例化的访问应当防止应用程序域外的恶意实体。</span><span class="sxs-lookup"><span data-stu-id="8a51d-110">Access to durable instancing should be protected against malicious entities external to the application domain.</span></span> <span data-ttu-id="8a51d-111">此外，开发人员应确保恶意代码不能在与持久性实例化代码相同的应用程序域中执行。</span><span class="sxs-lookup"><span data-stu-id="8a51d-111">In addition, developers should ensure that malicious code can't be executed in the same application domain as the durable instancing code.</span></span>

3.  <span data-ttu-id="8a51d-112">不应使用提升的（管理员）权限来运行持久性实例化。</span><span class="sxs-lookup"><span data-stu-id="8a51d-112">Durable instancing should not be run with elevated (Administrator) permissions.</span></span>

4.  <span data-ttu-id="8a51d-113">要在应用程序域的外部处理的数据应受到保护。</span><span class="sxs-lookup"><span data-stu-id="8a51d-113">Data being processed outside the application domain should be protected.</span></span>

5.  <span data-ttu-id="8a51d-114">需要安全隔离的应用程序不应共享架构抽象的同一实例。</span><span class="sxs-lookup"><span data-stu-id="8a51d-114">Applications that require security isolation should not share the same instance of the schema abstraction.</span></span> <span data-ttu-id="8a51d-115">此类应用程序应使用不同的存储提供程序，或者使用配置为使用不同存储实例化的存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="8a51d-115">Such applications should use different store providers, or store providers configured to use different store instantiations.</span></span>

## <a name="sql-server-security-concerns"></a><span data-ttu-id="8a51d-116">SQL Server 安全问题</span><span class="sxs-lookup"><span data-stu-id="8a51d-116">SQL Server Security Concerns</span></span>

-   <span data-ttu-id="8a51d-117">使用大量子活动、位置、书签、宿主扩展或作用域时，或使用负载很大的书签时，可能会耗尽内存，或在持久化过程中分配过多的数据库空间。</span><span class="sxs-lookup"><span data-stu-id="8a51d-117">When large numbers of child activities, locations, bookmarks, host extensions, or scopes are used, or when bookmarks with very large payloads are used, memory can be exhausted, or undue amounts of database space can be allocated during persistence.</span></span> <span data-ttu-id="8a51d-118">可使用对象级和数据级的安全措施来缓解该问题。</span><span class="sxs-lookup"><span data-stu-id="8a51d-118">This can be mitigated by using object-level and database-level security.</span></span>

-   <span data-ttu-id="8a51d-119">使用 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 时，必须保护实例存储区的安全。</span><span class="sxs-lookup"><span data-stu-id="8a51d-119">When using <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, the instance store must be secured.</span></span> <span data-ttu-id="8a51d-120">有关详细信息，请参阅[SQL Server 最佳实践](https://go.microsoft.com/fwlink/?LinkId=164972)。</span><span class="sxs-lookup"><span data-stu-id="8a51d-120">For more information, see [SQL Server Best Practices](https://go.microsoft.com/fwlink/?LinkId=164972).</span></span>

-   <span data-ttu-id="8a51d-121">应为实例存储区中的敏感数据加密。</span><span class="sxs-lookup"><span data-stu-id="8a51d-121">Sensitive data in the instance store should be encrypted.</span></span> <span data-ttu-id="8a51d-122">有关详细信息，请参阅[SQL 安全性加密](https://go.microsoft.com/fwlink/?LinkId=164976)。</span><span class="sxs-lookup"><span data-stu-id="8a51d-122">For more information, see [SQL Security Encryption](https://go.microsoft.com/fwlink/?LinkId=164976).</span></span>

-   <span data-ttu-id="8a51d-123">因为数据库连接字符串通常包含在配置文件中，所以，Windows 级别的安全性 (ACL) 应该用于确保配置文件（通常是 Web.Config）是安全的，并且登录名和密码信息不包含在连接字符串中。</span><span class="sxs-lookup"><span data-stu-id="8a51d-123">Since the database connection string is often included in a configuration file, windows-level security (ACL) should be used to ensure that the configuration file (Web.Config usually) is secure, and that login and password information are not included in the connection string.</span></span> <span data-ttu-id="8a51d-124">应改为在数据库和 Web 服务器之间使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="8a51d-124">Windows authentication should be used between the database and the web server instead.</span></span>

## <a name="considerations-for-workflowservicehost"></a><span data-ttu-id="8a51d-125">WorkflowServiceHost 的注意事项</span><span class="sxs-lookup"><span data-stu-id="8a51d-125">Considerations for WorkflowServiceHost</span></span>

-   <span data-ttu-id="8a51d-126">应保护工作流中使用的 Windows Communication Foundation (WCF) 终结点。</span><span class="sxs-lookup"><span data-stu-id="8a51d-126">Windows Communication Foundation (WCF) endpoints used in workflows should be secured.</span></span> <span data-ttu-id="8a51d-127">有关详细信息，请参阅[WCF 安全性概述](https://go.microsoft.com/fwlink/?LinkID=164975)。</span><span class="sxs-lookup"><span data-stu-id="8a51d-127">For more information, see [WCF Security Overview](https://go.microsoft.com/fwlink/?LinkID=164975).</span></span>

-   <span data-ttu-id="8a51d-128">宿主级授权可以使用 <xref:System.ServiceModel.ServiceAuthorizationManager> 来实现。</span><span class="sxs-lookup"><span data-stu-id="8a51d-128">Host-level authorization can be implemented by using <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span> <span data-ttu-id="8a51d-129">请参阅[如何： 创建自定义授权管理器服务的](https://go.microsoft.com/fwlink/?LinkId=192228)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="8a51d-129">See [How To: Create a Custom Authorization Manager for a Service](https://go.microsoft.com/fwlink/?LinkId=192228) for details.</span></span>

-   <span data-ttu-id="8a51d-130">也可通过访问 OperationContext 从工作流内提供传入消息的 ServiceSecurityContext。</span><span class="sxs-lookup"><span data-stu-id="8a51d-130">The ServiceSecurityContext for the incoming message is also available from within workflow by accessing OperationContext.</span></span>

## <a name="wf-security-pack-ctp"></a><span data-ttu-id="8a51d-131">WF Security Pack CTP</span><span class="sxs-lookup"><span data-stu-id="8a51d-131">WF Security Pack CTP</span></span>
 <span data-ttu-id="8a51d-132">Microsoft WF Security Pack CTP 1 是一组活动和根据其实现的第一个社区技术预览 (CTP) 版本[Windows Workflow Foundation](https://msdn.microsoft.com/netframework/aa663328.aspx)中[.NET Framework 4](https://msdn.microsoft.com/netframework/default.aspx) (WF4），并[Windows Identity Foundation (WIF)](https://msdn.microsoft.com/security/aa570351.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8a51d-132">The Microsoft WF Security Pack CTP 1 is the first community technology preview (CTP) release of a set of activities and their implementation based on [Windows Workflow Foundation](https://msdn.microsoft.com/netframework/aa663328.aspx)in [.NET Framework 4](https://msdn.microsoft.com/netframework/default.aspx) (WF 4) and the [Windows Identity Foundation (WIF)](https://msdn.microsoft.com/security/aa570351.aspx).</span></span>  <span data-ttu-id="8a51d-133">Microsoft WF Security Pack CTP 1 包含活动及其设计器，阐释如何使用工作流轻松地实现各种与安全相关的方案，包括：</span><span class="sxs-lookup"><span data-stu-id="8a51d-133">The Microsoft WF Security Pack CTP 1 contains both activities and their designers which illustrate how to easily enable various security-related scenarios using workflow, including:</span></span>

1.  <span data-ttu-id="8a51d-134">在工作流中模拟客户端标识</span><span class="sxs-lookup"><span data-stu-id="8a51d-134">Impersonating a client identity in the workflow</span></span>

2.  <span data-ttu-id="8a51d-135">工作流中授权，例如 PrincipalPermission 和声明的验证</span><span class="sxs-lookup"><span data-stu-id="8a51d-135">In-workflow authorization, such as PrincipalPermission and validation of Claims</span></span>

3.  <span data-ttu-id="8a51d-136">使用在工作流中指定的 ClientCredentials 的经过身份验证的消息传递，例如从安全令牌服务 (STS) 检索的用户名/密码或令牌。</span><span class="sxs-lookup"><span data-stu-id="8a51d-136">Authenticated messaging using ClientCredentials specified in the workflow, such as username/password or a token retrieved from a Security Token Service (STS)</span></span>

4.  <span data-ttu-id="8a51d-137">使用 WS-Trust ActAs 将客户端安全令牌流动到后端服务（基于声明的委托）</span><span class="sxs-lookup"><span data-stu-id="8a51d-137">Flowing a client security token to a back-end service (claims-based delegation) using WS-Trust ActAs</span></span>

<span data-ttu-id="8a51d-138">有关详细信息以及下载 WF Security Pack CTP，请参阅： [WF Security Pack CTP](https://wf.codeplex.com/releases/view/48114)</span><span class="sxs-lookup"><span data-stu-id="8a51d-138">For more information and to download the WF Security Pack CTP, see: [WF Security Pack CTP](https://wf.codeplex.com/releases/view/48114)</span></span>
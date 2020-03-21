---
title: 如何：审核 Windows Communication Foundation 安全事件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], auditing events
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
ms.openlocfilehash: 62d26b24b5d46427c1871fccf48b063c45781beb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185113"
---
# <a name="how-to-audit-windows-communication-foundation-security-events"></a><span data-ttu-id="7949a-102">如何：审核 Windows Communication Foundation 安全事件</span><span class="sxs-lookup"><span data-stu-id="7949a-102">How to: Audit Windows Communication Foundation Security Events</span></span>
<span data-ttu-id="7949a-103">Windows 通信基础 （WCF） 允许您将安全事件记录到 Windows 事件日志，可以使用 Windows 事件查看器查看该日志。</span><span class="sxs-lookup"><span data-stu-id="7949a-103">Windows Communication Foundation (WCF) allows you to log security events to the Windows event log, which can be viewed using the Windows Event Viewer.</span></span> <span data-ttu-id="7949a-104">本主题说明如何设置应用程序以使其记录安全事件。</span><span class="sxs-lookup"><span data-stu-id="7949a-104">This topic explains how to set up an application so that it logs security events.</span></span> <span data-ttu-id="7949a-105">有关 WCF 审核的详细信息，请参阅[审核](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)。</span><span class="sxs-lookup"><span data-stu-id="7949a-105">For more information about WCF auditing, see [Auditing](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).</span></span>  
  
### <a name="to-audit-security-events-in-code"></a><span data-ttu-id="7949a-106">通过代码审核安全事件</span><span class="sxs-lookup"><span data-stu-id="7949a-106">To audit security events in code</span></span>  
  
1. <span data-ttu-id="7949a-107">指定审核日志位置。</span><span class="sxs-lookup"><span data-stu-id="7949a-107">Specify the audit log location.</span></span> <span data-ttu-id="7949a-108">为此，请将 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> 类的 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> 属性设置为 <xref:System.ServiceModel.AuditLogLocation> 枚举值之一，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="7949a-108">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> property of the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> class to one of the <xref:System.ServiceModel.AuditLogLocation> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     <span data-ttu-id="7949a-109">枚<xref:System.ServiceModel.AuditLogLocation>举有三个值： `Application`、`Security`或`Default`。</span><span class="sxs-lookup"><span data-stu-id="7949a-109">The <xref:System.ServiceModel.AuditLogLocation> enumeration has three values: `Application`, `Security`, or `Default`.</span></span> <span data-ttu-id="7949a-110">该值指定在事件查看器中可见的日志之一：安全日志或应用程序日志。</span><span class="sxs-lookup"><span data-stu-id="7949a-110">The value specifies one of the logs visible in the Event Viewer, either the Security log or the Application log.</span></span> <span data-ttu-id="7949a-111">如果您使用 `Default` 值，则实际的日志将取决于运行应用程序的操作系统。</span><span class="sxs-lookup"><span data-stu-id="7949a-111">If you use the `Default` value, the actual log will depend on the operating system the application is running on.</span></span> <span data-ttu-id="7949a-112">如果启用审核，但未指定日志位置，则对于支持写入安全日志的平台，默认值为 `Security` 日志；对于其他平台，则写入 `Application` 日志。</span><span class="sxs-lookup"><span data-stu-id="7949a-112">If auditing is enabled and the log location is not specified, the default is the `Security` log for platforms that support writing to the Security log; otherwise, it will write to the `Application` log.</span></span> <span data-ttu-id="7949a-113">默认情况下，只有 Windows 服务器 2003 和 Windows Vista 支持写入安全日志。</span><span class="sxs-lookup"><span data-stu-id="7949a-113">Only Windows Server 2003 and Windows Vista support writing to the Security log by default.</span></span>  
  
2. <span data-ttu-id="7949a-114">设置要审核的事件的类型。</span><span class="sxs-lookup"><span data-stu-id="7949a-114">Set up the types of events to audit.</span></span> <span data-ttu-id="7949a-115">您可以同时审核服务级事件或消息级授权事件。</span><span class="sxs-lookup"><span data-stu-id="7949a-115">You can simultaneously audit service-level events or message-level authorization events.</span></span> <span data-ttu-id="7949a-116">为此，请将 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> 属性或 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> 属性设置为 <xref:System.ServiceModel.AuditLevel> 枚举值之一，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="7949a-116">To do this, set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> property or the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> property to one of the <xref:System.ServiceModel.AuditLevel> enumeration values, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3. <span data-ttu-id="7949a-117">指定是向应用程序隐匿还是公开日志审核失败事件。</span><span class="sxs-lookup"><span data-stu-id="7949a-117">Specify whether to suppress or expose failures to the application regarding log audit events.</span></span> <span data-ttu-id="7949a-118">将 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> 属性设置为 `true` 或 `false`，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="7949a-118">Set the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to either `true` or `false`, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     <span data-ttu-id="7949a-119">默认 `SuppressAuditFailure` 属性为 `true`，因此审核失败不会影响应用程序。</span><span class="sxs-lookup"><span data-stu-id="7949a-119">The default `SuppressAuditFailure` property is `true`, so that the failure to audit does not affect the application.</span></span> <span data-ttu-id="7949a-120">否则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="7949a-120">Otherwise, an exception is thrown.</span></span> <span data-ttu-id="7949a-121">对于任何成功的审核，都将写入详细跟踪。</span><span class="sxs-lookup"><span data-stu-id="7949a-121">For any successful audit, a verbose trace is written.</span></span> <span data-ttu-id="7949a-122">对于任何失败的审核，都将在错误级别写入跟踪。</span><span class="sxs-lookup"><span data-stu-id="7949a-122">For any failure to audit, the trace is written at the Error level.</span></span>  
  
4. <span data-ttu-id="7949a-123">从在 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> 的说明中找到的行为集合中移除现有 <xref:System.ServiceModel.ServiceHost>。</span><span class="sxs-lookup"><span data-stu-id="7949a-123">Delete the existing <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> from the collection of behaviors found in the description of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="7949a-124">该行为集合通过 <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 属性来访问，而该属性又通过 <xref:System.ServiceModel.ServiceHostBase.Description%2A> 属性来访问。</span><span class="sxs-lookup"><span data-stu-id="7949a-124">The behavior collection is accessed by the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property, which in turn is accessed from the <xref:System.ServiceModel.ServiceHostBase.Description%2A> property.</span></span> <span data-ttu-id="7949a-125">然后，向同一集合中添加新的 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="7949a-125">Then add the new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to the same collection, as shown in the following code.</span></span>  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### <a name="to-set-up-auditing-in-configuration"></a><span data-ttu-id="7949a-126">通过配置方式设置审核</span><span class="sxs-lookup"><span data-stu-id="7949a-126">To set up auditing in configuration</span></span>  
  
1. <span data-ttu-id="7949a-127">要在配置中设置审核，>元素向 Web.config 文件>部分[\<的行为](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)添加[\<行为](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)元素。</span><span class="sxs-lookup"><span data-stu-id="7949a-127">To set up auditing in configuration, add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) section of the web.config file.</span></span> <span data-ttu-id="7949a-128">然后添加[\<服务安全审核>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)元素并设置各种属性，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="7949a-128">Then add a [\<serviceSecurityAudit>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) element and set the various attributes, as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
       <behavior name="myAuditBehavior">  
          <serviceSecurityAudit auditLogLocation="Application"  
                suppressAuditFailure="false"
                serviceAuthorizationAuditLevel="None"
                messageAuthenticationAuditLevel="SuccessOrFailure" />  
          </behavior>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="7949a-129">您必须为服务指定行为，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="7949a-129">You must specify the behavior for the service, as shown in the following example.</span></span>  
  
    ```xml  
    <services>  
        <service type="WCS.Samples.Service.Echo"
        behaviorConfiguration=" myAuditBehavior">  
           <endpoint address=""  
                    binding="wsHttpBinding"  
                    bindingConfiguration="CertificateDefault"
                    contract="WCS.Samples.Service.IEcho" />  
        </service>  
    </services>  
    ```  
  
## <a name="example"></a><span data-ttu-id="7949a-130">示例</span><span class="sxs-lookup"><span data-stu-id="7949a-130">Example</span></span>  
 <span data-ttu-id="7949a-131">下面的代码创建 <xref:System.ServiceModel.ServiceHost> 类的一个实例，然后向其行为集合添加一个新的 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>。</span><span class="sxs-lookup"><span data-stu-id="7949a-131">The following code creates an instance of the <xref:System.ServiceModel.ServiceHost> class and adds a new <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to its collection of behaviors.</span></span>  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="7949a-132">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="7949a-132">.NET Framework Security</span></span>  
 <span data-ttu-id="7949a-133">将 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> 属性设置为 `true`，就会隐匿任何生成安全审核失败（如果设置为 `false`，则会引发异常）。</span><span class="sxs-lookup"><span data-stu-id="7949a-133">Setting the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> property to `true`, suppresses any failure to generate security audits (if set to `false`, an exception is thrown).</span></span> <span data-ttu-id="7949a-134">但是，如果启用以下 Windows**本地安全设置**属性，则生成审核事件失败将导致 Windows 立即关闭：</span><span class="sxs-lookup"><span data-stu-id="7949a-134">However, if you enable the following Windows **Local Security Setting** property, a failure to generate audit events will cause Windows to shut down immediately:</span></span>  
  
 <span data-ttu-id="7949a-135">**审核：如果无法记录安全审核则立即关闭系统**</span><span class="sxs-lookup"><span data-stu-id="7949a-135">**Audit: Shut down system immediately if unable to log security audits**</span></span>  
  
 <span data-ttu-id="7949a-136">要设置该属性，打开 **"本地安全设置"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="7949a-136">To set the property, open the **Local Security Settings** dialog box.</span></span> <span data-ttu-id="7949a-137">在 **"安全设置"** 下，单击 **"本地策略**"。</span><span class="sxs-lookup"><span data-stu-id="7949a-137">Under **Security Settings**, click **Local Policies**.</span></span> <span data-ttu-id="7949a-138">然后单击 **"安全选项**"。</span><span class="sxs-lookup"><span data-stu-id="7949a-138">Then click **Security Options**.</span></span>  
  
 <span data-ttu-id="7949a-139">如果属性<xref:System.ServiceModel.AuditLogLocation>设置为，<xref:System.ServiceModel.AuditLogLocation.Security>并且未在**本地安全策略**中设置**审核对象访问**，则审核事件将不会写入安全日志。</span><span class="sxs-lookup"><span data-stu-id="7949a-139">If the <xref:System.ServiceModel.AuditLogLocation> property is set to <xref:System.ServiceModel.AuditLogLocation.Security> and **Audit Object Access** is not set in the **Local Security Policy**, audit events will not be written to the Security log.</span></span> <span data-ttu-id="7949a-140">请注意，虽然不返回任何失败记录，但审核项不会写入安全日志。</span><span class="sxs-lookup"><span data-stu-id="7949a-140">Note that no failure is returned, but audit entries are not written to the Security log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7949a-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7949a-141">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- <xref:System.ServiceModel.AuditLogLocation>
- [<span data-ttu-id="7949a-142">审计</span><span class="sxs-lookup"><span data-stu-id="7949a-142">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)

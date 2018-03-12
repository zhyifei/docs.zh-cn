---
title: '&lt;serviceSecurityAudit&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 25355acfd7bc82ccff33f68a690f3f02d1235438
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="ltservicesecurityauditgt"></a><span data-ttu-id="c585e-102">&lt;serviceSecurityAudit&gt;</span><span class="sxs-lookup"><span data-stu-id="c585e-102">&lt;serviceSecurityAudit&gt;</span></span>
<span data-ttu-id="c585e-103">指定用于在服务操作过程中启用安全事件审核的设置。</span><span class="sxs-lookup"><span data-stu-id="c585e-103">Specifies settings that enable auditing of security events during service operations.</span></span>  
  
 <span data-ttu-id="c585e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c585e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c585e-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c585e-105">\<behaviors></span></span>  
<span data-ttu-id="c585e-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c585e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c585e-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c585e-107">\<behavior></span></span>  
<span data-ttu-id="c585e-108">\<serviceSecurityAudit></span><span class="sxs-lookup"><span data-stu-id="c585e-108">\<serviceSecurityAudit></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c585e-109">语法</span><span class="sxs-lookup"><span data-stu-id="c585e-109">Syntax</span></span>  
  
```xml  
<serviceSecurityAudit   
   auditLogLocation="Default/Application/Security"  
   messageAuthenticationAuditLevel= None/Success/Failure/SuccessOrFailure"   serviceAuthorizationAuditLevel="None/Success/Failure/SuccessOrFailure"  
   suppressAuditFailure="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c585e-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c585e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c585e-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c585e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c585e-112">特性</span><span class="sxs-lookup"><span data-stu-id="c585e-112">Attributes</span></span>  
  
|<span data-ttu-id="c585e-113">特性</span><span class="sxs-lookup"><span data-stu-id="c585e-113">Attribute</span></span>|<span data-ttu-id="c585e-114">描述</span><span class="sxs-lookup"><span data-stu-id="c585e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c585e-115">auditLogLocation</span><span class="sxs-lookup"><span data-stu-id="c585e-115">auditLogLocation</span></span>|<span data-ttu-id="c585e-116">指定审核日志的位置。</span><span class="sxs-lookup"><span data-stu-id="c585e-116">Specifies the location of the audit log.</span></span> <span data-ttu-id="c585e-117">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="c585e-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c585e-118">默认： 安全事件写入到应用程序日志在 Windows XP 中，和事件日志在 Windows Server 2003 和 Windows Vista。</span><span class="sxs-lookup"><span data-stu-id="c585e-118">-   Default: Security events are written to the application log on Windows XP, and to the Event Log on Windows Server 2003 and Windows Vista.</span></span><br /><span data-ttu-id="c585e-119">应用程序： 审核事件写入到应用程序事件日志中。</span><span class="sxs-lookup"><span data-stu-id="c585e-119">-   Application: Audit events are written to the Application Event Log.</span></span><br /><span data-ttu-id="c585e-120">安全性： 审核事件写入安全事件日志。</span><span class="sxs-lookup"><span data-stu-id="c585e-120">-   Security: Audit events are written to the Security Event Log.</span></span><br /><br /> <span data-ttu-id="c585e-121">默认值为 Default。</span><span class="sxs-lookup"><span data-stu-id="c585e-121">The default value is Default.</span></span> <span data-ttu-id="c585e-122">有关详细信息，请参阅<xref:System.ServiceModel.AuditLogLocation>。</span><span class="sxs-lookup"><span data-stu-id="c585e-122">For more information, see <xref:System.ServiceModel.AuditLogLocation>.</span></span>|  
|<span data-ttu-id="c585e-123">suppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="c585e-123">suppressAuditFailure</span></span>|<span data-ttu-id="c585e-124">一个布尔值，指定取消显示审核日志写入失败的行为。</span><span class="sxs-lookup"><span data-stu-id="c585e-124">A Boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span><br /><br /> <span data-ttu-id="c585e-125">应将对审核日志的写入错误通知给应用程序。</span><span class="sxs-lookup"><span data-stu-id="c585e-125">Applications should be notified for failures of writing to the audit log.</span></span> <span data-ttu-id="c585e-126">如果应用程序并不用于处理审核错误，则应使用此属性取消显示审核日志写入失败。</span><span class="sxs-lookup"><span data-stu-id="c585e-126">If your application is not designed to handle audit failures, you should use this attribute to suppress failures in writing to the audit log.</span></span><br /><br /> <span data-ttu-id="c585e-127">如果此属性为 `true`，则因尝试写入审核事件而导致的异常（OutOfMemoryException、StackOverFlowException、ThreadAbortException 和 ArgumentException 除外）将由系统进行处理并且不会传播到应用程序。</span><span class="sxs-lookup"><span data-stu-id="c585e-127">If this attribute is `true`, exceptions other than OutOfMemoryException, StackOverFlowException, ThreadAbortException, and ArgumentException that result from attempts to write audit events are handled by the system, and are not propagated to the application.</span></span> <span data-ttu-id="c585e-128">如果此属性为 `false`，则因尝试写入审核事件而导致的所有异常都将向上传递给应用程序。</span><span class="sxs-lookup"><span data-stu-id="c585e-128">If this attribute is `false`, all exceptions that result from attempts to write audit events are passed up to the application.</span></span><br /><br /> <span data-ttu-id="c585e-129">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="c585e-129">The default is `true`.</span></span>|  
|<span data-ttu-id="c585e-130">serviceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="c585e-130">serviceAuthorizationAuditLevel</span></span>|<span data-ttu-id="c585e-131">指定审核日志中记录的授权事件的类型。</span><span class="sxs-lookup"><span data-stu-id="c585e-131">Specifies the types of authorization events that are recorded in the audit log.</span></span> <span data-ttu-id="c585e-132">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="c585e-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c585e-133">-None： 没有的服务授权事件执行审核。</span><span class="sxs-lookup"><span data-stu-id="c585e-133">-   None: No auditing of service authorization events is performed.</span></span><br /><span data-ttu-id="c585e-134">-Success： 只成功的服务授权审核事件。</span><span class="sxs-lookup"><span data-stu-id="c585e-134">-   Success: Only successful service authorization events are audited.</span></span><br /><span data-ttu-id="c585e-135">故障： 只失败服务授权审核事件。</span><span class="sxs-lookup"><span data-stu-id="c585e-135">-   Failure: Only failure service authorization events are audited.</span></span><br /><span data-ttu-id="c585e-136">-SuccessOrFailure： 同时成功和失败服务授权事件进行审核。</span><span class="sxs-lookup"><span data-stu-id="c585e-136">-   SuccessOrFailure: Both success and failure service authorization events are audited.</span></span><br /><br /> <span data-ttu-id="c585e-137">默认值为 None。</span><span class="sxs-lookup"><span data-stu-id="c585e-137">The default value is None.</span></span> <span data-ttu-id="c585e-138">有关详细信息，请参阅<xref:System.ServiceModel.AuditLevel>。</span><span class="sxs-lookup"><span data-stu-id="c585e-138">For more information, see <xref:System.ServiceModel.AuditLevel>.</span></span>|  
|<span data-ttu-id="c585e-139">messageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="c585e-139">messageAuthenticationAuditLevel</span></span>|<span data-ttu-id="c585e-140">指定所记录的消息身份验证审核事件的类型。</span><span class="sxs-lookup"><span data-stu-id="c585e-140">Specifies the type of message authentication audit events logged.</span></span> <span data-ttu-id="c585e-141">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="c585e-141">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c585e-142">-None： 不生成审核事件。</span><span class="sxs-lookup"><span data-stu-id="c585e-142">-   None: No audit events are generated.</span></span><br /><span data-ttu-id="c585e-143">-Success： 记录仅成功的安全 （完全验证，包括消息签名验证、 密码和令牌验证） 事件。</span><span class="sxs-lookup"><span data-stu-id="c585e-143">-   Success: Only successful security (full validation including message signature validation, cipher, and token validation) events are logged.</span></span><br /><span data-ttu-id="c585e-144">记录故障： 仅失败的事件。</span><span class="sxs-lookup"><span data-stu-id="c585e-144">-   Failure: Only failure events are logged.</span></span><br /><span data-ttu-id="c585e-145">-SuccessOrFailure： 同时记录成功和失败的事件。</span><span class="sxs-lookup"><span data-stu-id="c585e-145">-   SuccessOrFailure: Both success and failure events are logged.</span></span><br /><br /> <span data-ttu-id="c585e-146">默认值为 None。</span><span class="sxs-lookup"><span data-stu-id="c585e-146">The default value is None.</span></span> <span data-ttu-id="c585e-147">有关详细信息，请参阅<xref:System.ServiceModel.AuditLevel>。</span><span class="sxs-lookup"><span data-stu-id="c585e-147">For more information, see <xref:System.ServiceModel.AuditLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c585e-148">子元素</span><span class="sxs-lookup"><span data-stu-id="c585e-148">Child Elements</span></span>  
 <span data-ttu-id="c585e-149">无。</span><span class="sxs-lookup"><span data-stu-id="c585e-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c585e-150">父元素</span><span class="sxs-lookup"><span data-stu-id="c585e-150">Parent Elements</span></span>  
  
|<span data-ttu-id="c585e-151">元素</span><span class="sxs-lookup"><span data-stu-id="c585e-151">Element</span></span>|<span data-ttu-id="c585e-152">描述</span><span class="sxs-lookup"><span data-stu-id="c585e-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c585e-153">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c585e-153">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="c585e-154">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="c585e-154">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c585e-155">备注</span><span class="sxs-lookup"><span data-stu-id="c585e-155">Remarks</span></span>  
 <span data-ttu-id="c585e-156">此配置元素用于审核 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 身份验证事件。</span><span class="sxs-lookup"><span data-stu-id="c585e-156">This configuraton element is used to audit [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] authentication events.</span></span> <span data-ttu-id="c585e-157">当启用了审核时，可对成功或失败的身份验证尝试（或这两者）进行审核。</span><span class="sxs-lookup"><span data-stu-id="c585e-157">When auditing is enabled, either successful or failed authentication attempts (or both) can be audited.</span></span> <span data-ttu-id="c585e-158">事件会写入到三个事件日志之一：操作系统版本的应用程序日志、安全日志或默认日志。</span><span class="sxs-lookup"><span data-stu-id="c585e-158">The events are written to one of three event logs: application, security, or the default log for the operating system version.</span></span> <span data-ttu-id="c585e-159">可以使用 Windows 事件查看器查看所有事件日志。</span><span class="sxs-lookup"><span data-stu-id="c585e-159">The event logs can all be viewed using the Windows Event viewer.</span></span>  
  
 <span data-ttu-id="c585e-160">使用此配置元素的详细示例，请参阅[服务审核行为](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="c585e-160">For a detailed example of using this configuration element, see [Service Auditing Behavior](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md).</span></span>  
  
 <span data-ttu-id="c585e-161">默认情况下，可在 Windows XP 上的应用程序日志中查看审核事件；而在 Windows Server 2003 和 Windows Vista 上，可在安全日志中查看审核事件。</span><span class="sxs-lookup"><span data-stu-id="c585e-161">By default, on Windows XP the audit events can be seen in the Application Log; while on Windows Server 2003 and Windows Vista, the audit events can be seen in the Security Log.</span></span> <span data-ttu-id="c585e-162">通过将 `auditLogLocation` 属性设置为“Application”或“Security”，可以指定审核事件的位置。</span><span class="sxs-lookup"><span data-stu-id="c585e-162">The location of audit events can be specified by setting the `auditLogLocation` attribute to 'Application' or 'Security'.</span></span> <span data-ttu-id="c585e-163">有关详细信息，请参阅[如何： 审核安全事件](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)。</span><span class="sxs-lookup"><span data-stu-id="c585e-163">For more information, see [How to: Audit Security Events](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).</span></span> <span data-ttu-id="c585e-164">如果在安全日志中写入事件，则应该针对“Success”和“Failure”设置“LocalSecurityPolicy”->“启用对象访问”。</span><span class="sxs-lookup"><span data-stu-id="c585e-164">If the events are written in the Security Log, the LocalSecurityPolicy-> Enable Object Access should be set for "Success" and "Failure".</span></span>  
  
 <span data-ttu-id="c585e-165">在查看事件日志时，审核事件的来源为“ServiceModel Audit 3.0.0.0”。</span><span class="sxs-lookup"><span data-stu-id="c585e-165">When looking at the event log, the source of the audit events is "ServiceModel Audit 3.0.0.0".</span></span> <span data-ttu-id="c585e-166">消息身份验证审核记录的类别为“MessageAuthentication”，而服务授权审核记录的类别为“ServiceAuthorization”。</span><span class="sxs-lookup"><span data-stu-id="c585e-166">Message authentication audit records have a category of "MessageAuthentication" while service authorization audit records have a category of 'ServiceAuthorization'.</span></span>  
  
 <span data-ttu-id="c585e-167">消息身份验证审核事件包含消息是否被篡改、消息是否已过期以及客户端是否可以向服务进行身份验证等信息。</span><span class="sxs-lookup"><span data-stu-id="c585e-167">Message authentication audit events cover whether the message was tampered with, whether the message has expired and whether the client can authenticate to the service.</span></span> <span data-ttu-id="c585e-168">这些事件还提供了有关身份验证是成功还是失败（以及客户端标识）的信息和有关消息所发送到的终结点（以及与消息关联的操作）的信息。</span><span class="sxs-lookup"><span data-stu-id="c585e-168">They provide information about whether the authentication succeeded or failed along with the identity of the client and the endpoint the message was sent to along with the action associated with the message.</span></span>  
  
 <span data-ttu-id="c585e-169">服务授权审核事件包含服务授权管理器所做出的授权决定。</span><span class="sxs-lookup"><span data-stu-id="c585e-169">Service authorization audit events cover the authorization decision made by a service authorization manager.</span></span> <span data-ttu-id="c585e-170">它们提供有关授权是成功还是信息或失败以及客户端的标识，终结点消息发送到消息、 从生成的授权上下文的标识符关联的操作传入的消息并做出访问决定的授权管理器的类型。</span><span class="sxs-lookup"><span data-stu-id="c585e-170">They provide information about whether authorization succeeded or failed along with the identity of the client, the endpoint the message was sent to, the action associated with the message, the identifier of the authorization context that was generated from the incoming message and the type of the authorization manager that made the access decision.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c585e-171">示例</span><span class="sxs-lookup"><span data-stu-id="c585e-171">Example</span></span>  
  
```xml  
<system.serviceModel>  
   <serviceBehaviors>  
      <behavior name="NewBehavior">  
         <serviceSecurityAudit auditLogLocation="Application"   
             suppressAuditFailure="true"  
             serviceAuthorizationAuditLevel="Success"   
             messageAuthenticationAuditLevel="Success" />  
      </behavior>  
   </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c585e-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="c585e-172">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>  
 [<span data-ttu-id="c585e-173">安全行为</span><span class="sxs-lookup"><span data-stu-id="c585e-173">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="c585e-174">审核</span><span class="sxs-lookup"><span data-stu-id="c585e-174">Auditing</span></span>](../../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [<span data-ttu-id="c585e-175">如何：审核安全事件</span><span class="sxs-lookup"><span data-stu-id="c585e-175">How to: Audit Security Events</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)  
 [<span data-ttu-id="c585e-176">服务审核行为</span><span class="sxs-lookup"><span data-stu-id="c585e-176">Service Auditing Behavior</span></span>](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)

---
title: '&lt;serviceSecurityAudit&gt;'
ms.date: 03/30/2017
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 293cd3118ace2e073933e4c124664c775902e7d8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32751176"
---
# <a name="ltservicesecurityauditgt"></a><span data-ttu-id="4ed74-102">&lt;serviceSecurityAudit&gt;</span><span class="sxs-lookup"><span data-stu-id="4ed74-102">&lt;serviceSecurityAudit&gt;</span></span>
<span data-ttu-id="4ed74-103">指定用于在服务操作过程中启用安全事件审核的设置。</span><span class="sxs-lookup"><span data-stu-id="4ed74-103">Specifies settings that enable auditing of security events during service operations.</span></span>  
  
 <span data-ttu-id="4ed74-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4ed74-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4ed74-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="4ed74-105">\<behaviors></span></span>  
<span data-ttu-id="4ed74-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4ed74-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="4ed74-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="4ed74-107">\<behavior></span></span>  
<span data-ttu-id="4ed74-108">\<serviceSecurityAudit></span><span class="sxs-lookup"><span data-stu-id="4ed74-108">\<serviceSecurityAudit></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ed74-109">语法</span><span class="sxs-lookup"><span data-stu-id="4ed74-109">Syntax</span></span>  
  
```xml  
<serviceSecurityAudit   
   auditLogLocation="Default/Application/Security"  
   messageAuthenticationAuditLevel= None/Success/Failure/SuccessOrFailure"   serviceAuthorizationAuditLevel="None/Success/Failure/SuccessOrFailure"  
   suppressAuditFailure="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ed74-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4ed74-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4ed74-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4ed74-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ed74-112">特性</span><span class="sxs-lookup"><span data-stu-id="4ed74-112">Attributes</span></span>  
  
|<span data-ttu-id="4ed74-113">特性</span><span class="sxs-lookup"><span data-stu-id="4ed74-113">Attribute</span></span>|<span data-ttu-id="4ed74-114">描述</span><span class="sxs-lookup"><span data-stu-id="4ed74-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ed74-115">auditLogLocation</span><span class="sxs-lookup"><span data-stu-id="4ed74-115">auditLogLocation</span></span>|<span data-ttu-id="4ed74-116">指定审核日志的位置。</span><span class="sxs-lookup"><span data-stu-id="4ed74-116">Specifies the location of the audit log.</span></span> <span data-ttu-id="4ed74-117">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="4ed74-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4ed74-118">默认： 安全事件写入到应用程序日志在 Windows XP 中，和事件日志在 Windows Server 2003 和 Windows Vista。</span><span class="sxs-lookup"><span data-stu-id="4ed74-118">-   Default: Security events are written to the application log on Windows XP, and to the Event Log on Windows Server 2003 and Windows Vista.</span></span><br /><span data-ttu-id="4ed74-119">应用程序： 审核事件写入到应用程序事件日志中。</span><span class="sxs-lookup"><span data-stu-id="4ed74-119">-   Application: Audit events are written to the Application Event Log.</span></span><br /><span data-ttu-id="4ed74-120">安全性： 审核事件写入安全事件日志。</span><span class="sxs-lookup"><span data-stu-id="4ed74-120">-   Security: Audit events are written to the Security Event Log.</span></span><br /><br /> <span data-ttu-id="4ed74-121">默认值为 Default。</span><span class="sxs-lookup"><span data-stu-id="4ed74-121">The default value is Default.</span></span> <span data-ttu-id="4ed74-122">有关详细信息，请参阅<xref:System.ServiceModel.AuditLogLocation>。</span><span class="sxs-lookup"><span data-stu-id="4ed74-122">For more information, see <xref:System.ServiceModel.AuditLogLocation>.</span></span>|  
|<span data-ttu-id="4ed74-123">suppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="4ed74-123">suppressAuditFailure</span></span>|<span data-ttu-id="4ed74-124">一个布尔值，指定取消显示审核日志写入失败的行为。</span><span class="sxs-lookup"><span data-stu-id="4ed74-124">A Boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span><br /><br /> <span data-ttu-id="4ed74-125">应将对审核日志的写入错误通知给应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ed74-125">Applications should be notified for failures of writing to the audit log.</span></span> <span data-ttu-id="4ed74-126">如果应用程序并不用于处理审核错误，则应使用此属性取消显示审核日志写入失败。</span><span class="sxs-lookup"><span data-stu-id="4ed74-126">If your application is not designed to handle audit failures, you should use this attribute to suppress failures in writing to the audit log.</span></span><br /><br /> <span data-ttu-id="4ed74-127">如果此属性为 `true`，则因尝试写入审核事件而导致的异常（OutOfMemoryException、StackOverFlowException、ThreadAbortException 和 ArgumentException 除外）将由系统进行处理并且不会传播到应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ed74-127">If this attribute is `true`, exceptions other than OutOfMemoryException, StackOverFlowException, ThreadAbortException, and ArgumentException that result from attempts to write audit events are handled by the system, and are not propagated to the application.</span></span> <span data-ttu-id="4ed74-128">如果此属性为 `false`，则因尝试写入审核事件而导致的所有异常都将向上传递给应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ed74-128">If this attribute is `false`, all exceptions that result from attempts to write audit events are passed up to the application.</span></span><br /><br /> <span data-ttu-id="4ed74-129">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="4ed74-129">The default is `true`.</span></span>|  
|<span data-ttu-id="4ed74-130">serviceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="4ed74-130">serviceAuthorizationAuditLevel</span></span>|<span data-ttu-id="4ed74-131">指定审核日志中记录的授权事件的类型。</span><span class="sxs-lookup"><span data-stu-id="4ed74-131">Specifies the types of authorization events that are recorded in the audit log.</span></span> <span data-ttu-id="4ed74-132">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="4ed74-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4ed74-133">-None： 没有的服务授权事件执行审核。</span><span class="sxs-lookup"><span data-stu-id="4ed74-133">-   None: No auditing of service authorization events is performed.</span></span><br /><span data-ttu-id="4ed74-134">-Success： 只成功的服务授权审核事件。</span><span class="sxs-lookup"><span data-stu-id="4ed74-134">-   Success: Only successful service authorization events are audited.</span></span><br /><span data-ttu-id="4ed74-135">故障： 只失败服务授权审核事件。</span><span class="sxs-lookup"><span data-stu-id="4ed74-135">-   Failure: Only failure service authorization events are audited.</span></span><br /><span data-ttu-id="4ed74-136">-SuccessOrFailure： 同时成功和失败服务授权事件进行审核。</span><span class="sxs-lookup"><span data-stu-id="4ed74-136">-   SuccessOrFailure: Both success and failure service authorization events are audited.</span></span><br /><br /> <span data-ttu-id="4ed74-137">默认值为 None。</span><span class="sxs-lookup"><span data-stu-id="4ed74-137">The default value is None.</span></span> <span data-ttu-id="4ed74-138">有关详细信息，请参阅<xref:System.ServiceModel.AuditLevel>。</span><span class="sxs-lookup"><span data-stu-id="4ed74-138">For more information, see <xref:System.ServiceModel.AuditLevel>.</span></span>|  
|<span data-ttu-id="4ed74-139">messageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="4ed74-139">messageAuthenticationAuditLevel</span></span>|<span data-ttu-id="4ed74-140">指定所记录的消息身份验证审核事件的类型。</span><span class="sxs-lookup"><span data-stu-id="4ed74-140">Specifies the type of message authentication audit events logged.</span></span> <span data-ttu-id="4ed74-141">包括以下有效值：</span><span class="sxs-lookup"><span data-stu-id="4ed74-141">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4ed74-142">-None： 不生成审核事件。</span><span class="sxs-lookup"><span data-stu-id="4ed74-142">-   None: No audit events are generated.</span></span><br /><span data-ttu-id="4ed74-143">-Success： 记录仅成功的安全 （完全验证，包括消息签名验证、 密码和令牌验证） 事件。</span><span class="sxs-lookup"><span data-stu-id="4ed74-143">-   Success: Only successful security (full validation including message signature validation, cipher, and token validation) events are logged.</span></span><br /><span data-ttu-id="4ed74-144">记录故障： 仅失败的事件。</span><span class="sxs-lookup"><span data-stu-id="4ed74-144">-   Failure: Only failure events are logged.</span></span><br /><span data-ttu-id="4ed74-145">-SuccessOrFailure： 同时记录成功和失败的事件。</span><span class="sxs-lookup"><span data-stu-id="4ed74-145">-   SuccessOrFailure: Both success and failure events are logged.</span></span><br /><br /> <span data-ttu-id="4ed74-146">默认值为 None。</span><span class="sxs-lookup"><span data-stu-id="4ed74-146">The default value is None.</span></span> <span data-ttu-id="4ed74-147">有关详细信息，请参阅<xref:System.ServiceModel.AuditLevel>。</span><span class="sxs-lookup"><span data-stu-id="4ed74-147">For more information, see <xref:System.ServiceModel.AuditLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ed74-148">子元素</span><span class="sxs-lookup"><span data-stu-id="4ed74-148">Child Elements</span></span>  
 <span data-ttu-id="4ed74-149">无。</span><span class="sxs-lookup"><span data-stu-id="4ed74-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ed74-150">父元素</span><span class="sxs-lookup"><span data-stu-id="4ed74-150">Parent Elements</span></span>  
  
|<span data-ttu-id="4ed74-151">元素</span><span class="sxs-lookup"><span data-stu-id="4ed74-151">Element</span></span>|<span data-ttu-id="4ed74-152">描述</span><span class="sxs-lookup"><span data-stu-id="4ed74-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ed74-153">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="4ed74-153">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="4ed74-154">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="4ed74-154">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ed74-155">备注</span><span class="sxs-lookup"><span data-stu-id="4ed74-155">Remarks</span></span>  
 <span data-ttu-id="4ed74-156">此配置元素用于审核 Windows Communication Foundation (WCF) 身份验证事件。</span><span class="sxs-lookup"><span data-stu-id="4ed74-156">This configuraton element is used to audit Windows Communication Foundation (WCF) authentication events.</span></span> <span data-ttu-id="4ed74-157">当启用了审核时，可对成功或失败的身份验证尝试（或这两者）进行审核。</span><span class="sxs-lookup"><span data-stu-id="4ed74-157">When auditing is enabled, either successful or failed authentication attempts (or both) can be audited.</span></span> <span data-ttu-id="4ed74-158">事件会写入到三个事件日志之一：操作系统版本的应用程序日志、安全日志或默认日志。</span><span class="sxs-lookup"><span data-stu-id="4ed74-158">The events are written to one of three event logs: application, security, or the default log for the operating system version.</span></span> <span data-ttu-id="4ed74-159">可以使用 Windows 事件查看器查看所有事件日志。</span><span class="sxs-lookup"><span data-stu-id="4ed74-159">The event logs can all be viewed using the Windows Event viewer.</span></span>  
  
 <span data-ttu-id="4ed74-160">使用此配置元素的详细示例，请参阅[服务审核行为](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="4ed74-160">For a detailed example of using this configuration element, see [Service Auditing Behavior](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md).</span></span>  
  
 <span data-ttu-id="4ed74-161">默认情况下，可在 Windows XP 上的应用程序日志中查看审核事件；而在 Windows Server 2003 和 Windows Vista 上，可在安全日志中查看审核事件。</span><span class="sxs-lookup"><span data-stu-id="4ed74-161">By default, on Windows XP the audit events can be seen in the Application Log; while on Windows Server 2003 and Windows Vista, the audit events can be seen in the Security Log.</span></span> <span data-ttu-id="4ed74-162">通过将 `auditLogLocation` 属性设置为“Application”或“Security”，可以指定审核事件的位置。</span><span class="sxs-lookup"><span data-stu-id="4ed74-162">The location of audit events can be specified by setting the `auditLogLocation` attribute to 'Application' or 'Security'.</span></span> <span data-ttu-id="4ed74-163">有关详细信息，请参阅[如何： 审核安全事件](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)。</span><span class="sxs-lookup"><span data-stu-id="4ed74-163">For more information, see [How to: Audit Security Events](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).</span></span> <span data-ttu-id="4ed74-164">如果在安全日志中写入事件，则应该针对“Success”和“Failure”设置“LocalSecurityPolicy”->“启用对象访问”。</span><span class="sxs-lookup"><span data-stu-id="4ed74-164">If the events are written in the Security Log, the LocalSecurityPolicy-> Enable Object Access should be set for "Success" and "Failure".</span></span>  
  
 <span data-ttu-id="4ed74-165">在查看事件日志时，审核事件的来源为“ServiceModel Audit 3.0.0.0”。</span><span class="sxs-lookup"><span data-stu-id="4ed74-165">When looking at the event log, the source of the audit events is "ServiceModel Audit 3.0.0.0".</span></span> <span data-ttu-id="4ed74-166">消息身份验证审核记录的类别为“MessageAuthentication”，而服务授权审核记录的类别为“ServiceAuthorization”。</span><span class="sxs-lookup"><span data-stu-id="4ed74-166">Message authentication audit records have a category of "MessageAuthentication" while service authorization audit records have a category of 'ServiceAuthorization'.</span></span>  
  
 <span data-ttu-id="4ed74-167">消息身份验证审核事件包含消息是否被篡改、消息是否已过期以及客户端是否可以向服务进行身份验证等信息。</span><span class="sxs-lookup"><span data-stu-id="4ed74-167">Message authentication audit events cover whether the message was tampered with, whether the message has expired and whether the client can authenticate to the service.</span></span> <span data-ttu-id="4ed74-168">这些事件还提供了有关身份验证是成功还是失败（以及客户端标识）的信息和有关消息所发送到的终结点（以及与消息关联的操作）的信息。</span><span class="sxs-lookup"><span data-stu-id="4ed74-168">They provide information about whether the authentication succeeded or failed along with the identity of the client and the endpoint the message was sent to along with the action associated with the message.</span></span>  
  
 <span data-ttu-id="4ed74-169">服务授权审核事件包含服务授权管理器所做出的授权决定。</span><span class="sxs-lookup"><span data-stu-id="4ed74-169">Service authorization audit events cover the authorization decision made by a service authorization manager.</span></span> <span data-ttu-id="4ed74-170">它们提供有关授权是成功还是信息或失败以及客户端的标识，终结点消息发送到消息、 从生成的授权上下文的标识符关联的操作传入的消息并做出访问决定的授权管理器的类型。</span><span class="sxs-lookup"><span data-stu-id="4ed74-170">They provide information about whether authorization succeeded or failed along with the identity of the client, the endpoint the message was sent to, the action associated with the message, the identifier of the authorization context that was generated from the incoming message and the type of the authorization manager that made the access decision.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ed74-171">示例</span><span class="sxs-lookup"><span data-stu-id="4ed74-171">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4ed74-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ed74-172">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>  
 [<span data-ttu-id="4ed74-173">安全行为</span><span class="sxs-lookup"><span data-stu-id="4ed74-173">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="4ed74-174">审核</span><span class="sxs-lookup"><span data-stu-id="4ed74-174">Auditing</span></span>](../../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [<span data-ttu-id="4ed74-175">如何：审核安全事件</span><span class="sxs-lookup"><span data-stu-id="4ed74-175">How to: Audit Security Events</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)  
 [<span data-ttu-id="4ed74-176">服务审核行为</span><span class="sxs-lookup"><span data-stu-id="4ed74-176">Service Auditing Behavior</span></span>](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)

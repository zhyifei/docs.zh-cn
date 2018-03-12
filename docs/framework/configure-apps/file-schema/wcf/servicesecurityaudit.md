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
# <a name="ltservicesecurityauditgt"></a>&lt;serviceSecurityAudit&gt;
指定用于在服务操作过程中启用安全事件审核的设置。  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceSecurityAudit>  
  
## <a name="syntax"></a>语法  
  
```xml  
<serviceSecurityAudit   
   auditLogLocation="Default/Application/Security"  
   messageAuthenticationAuditLevel= None/Success/Failure/SuccessOrFailure"   serviceAuthorizationAuditLevel="None/Success/Failure/SuccessOrFailure"  
   suppressAuditFailure="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|auditLogLocation|指定审核日志的位置。 包括以下有效值：<br /><br /> 默认： 安全事件写入到应用程序日志在 Windows XP 中，和事件日志在 Windows Server 2003 和 Windows Vista。<br />应用程序： 审核事件写入到应用程序事件日志中。<br />安全性： 审核事件写入安全事件日志。<br /><br /> 默认值为 Default。 有关详细信息，请参阅<xref:System.ServiceModel.AuditLogLocation>。|  
|suppressAuditFailure|一个布尔值，指定取消显示审核日志写入失败的行为。<br /><br /> 应将对审核日志的写入错误通知给应用程序。 如果应用程序并不用于处理审核错误，则应使用此属性取消显示审核日志写入失败。<br /><br /> 如果此属性为 `true`，则因尝试写入审核事件而导致的异常（OutOfMemoryException、StackOverFlowException、ThreadAbortException 和 ArgumentException 除外）将由系统进行处理并且不会传播到应用程序。 如果此属性为 `false`，则因尝试写入审核事件而导致的所有异常都将向上传递给应用程序。<br /><br /> 默认值为 `true`。|  
|serviceAuthorizationAuditLevel|指定审核日志中记录的授权事件的类型。 包括以下有效值：<br /><br /> -None： 没有的服务授权事件执行审核。<br />-Success： 只成功的服务授权审核事件。<br />故障： 只失败服务授权审核事件。<br />-SuccessOrFailure： 同时成功和失败服务授权事件进行审核。<br /><br /> 默认值为 None。 有关详细信息，请参阅<xref:System.ServiceModel.AuditLevel>。|  
|messageAuthenticationAuditLevel|指定所记录的消息身份验证审核事件的类型。 包括以下有效值：<br /><br /> -None： 不生成审核事件。<br />-Success： 记录仅成功的安全 （完全验证，包括消息签名验证、 密码和令牌验证） 事件。<br />记录故障： 仅失败的事件。<br />-SuccessOrFailure： 同时记录成功和失败的事件。<br /><br /> 默认值为 None。 有关详细信息，请参阅<xref:System.ServiceModel.AuditLevel>。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|指定行为元素。|  
  
## <a name="remarks"></a>备注  
 此配置元素用于审核 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 身份验证事件。 当启用了审核时，可对成功或失败的身份验证尝试（或这两者）进行审核。 事件会写入到三个事件日志之一：操作系统版本的应用程序日志、安全日志或默认日志。 可以使用 Windows 事件查看器查看所有事件日志。  
  
 使用此配置元素的详细示例，请参阅[服务审核行为](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)。  
  
 默认情况下，可在 Windows XP 上的应用程序日志中查看审核事件；而在 Windows Server 2003 和 Windows Vista 上，可在安全日志中查看审核事件。 通过将 `auditLogLocation` 属性设置为“Application”或“Security”，可以指定审核事件的位置。 有关详细信息，请参阅[如何： 审核安全事件](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)。 如果在安全日志中写入事件，则应该针对“Success”和“Failure”设置“LocalSecurityPolicy”->“启用对象访问”。  
  
 在查看事件日志时，审核事件的来源为“ServiceModel Audit 3.0.0.0”。 消息身份验证审核记录的类别为“MessageAuthentication”，而服务授权审核记录的类别为“ServiceAuthorization”。  
  
 消息身份验证审核事件包含消息是否被篡改、消息是否已过期以及客户端是否可以向服务进行身份验证等信息。 这些事件还提供了有关身份验证是成功还是失败（以及客户端标识）的信息和有关消息所发送到的终结点（以及与消息关联的操作）的信息。  
  
 服务授权审核事件包含服务授权管理器所做出的授权决定。 它们提供有关授权是成功还是信息或失败以及客户端的标识，终结点消息发送到消息、 从生成的授权上下文的标识符关联的操作传入的消息并做出访问决定的授权管理器的类型。  
  
## <a name="example"></a>示例  
  
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
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>  
 [安全行为](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [审核](../../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [如何：审核安全事件](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)  
 [服务审核行为](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)

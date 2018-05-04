---
title: '&lt;authorizationPolicies&gt;'
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 8e1bc702db899c4b0b3ee539fdc89cdda6c4cf10
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltauthorizationpoliciesgt"></a>&lt;authorizationPolicies&gt;
本配置节包含可使用 `add` 关键字添加的授权策略类型的集合。 每个授权类型都包含一个所需的 `policyType` 属性，此属性是一个字符串。 该属性指定一个授权策略，可以将一组输入声明转换为另一组声明。 可以根据该授权策略来授予或拒绝访问控制。 授权策略的工作原理的详细信息，请参阅<xref:System.IdentityModel.Policy.IAuthorizationPolicy>和[授权策略](../../../../../docs/framework/wcf/samples/authorization-policy.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 [授予对服务操作的权限](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [如何：为服务创建自定义授权管理器](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)  
 [授权策略](../../../../../docs/framework/wcf/samples/authorization-policy.md)

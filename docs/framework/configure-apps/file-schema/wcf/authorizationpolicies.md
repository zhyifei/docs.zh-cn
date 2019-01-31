---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: d8ca43a7b633d7d19dd37ceb0ff64075931b6c5c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254754"
---
# <a name="authorizationpolicies"></a><span data-ttu-id="a8496-101">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="a8496-101">\<authorizationPolicies></span></span>
<span data-ttu-id="a8496-102">本配置节包含可使用 `add` 关键字添加的授权策略类型的集合。</span><span class="sxs-lookup"><span data-stu-id="a8496-102">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="a8496-103">每个授权类型都包含一个所需的 `policyType` 属性，此属性是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="a8496-103">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="a8496-104">该属性指定一个授权策略，可以将一组输入声明转换为另一组声明。</span><span class="sxs-lookup"><span data-stu-id="a8496-104">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="a8496-105">可以根据该授权策略来授予或拒绝访问控制。</span><span class="sxs-lookup"><span data-stu-id="a8496-105">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="a8496-106">授权策略的工作原理的详细信息，请参阅<xref:System.IdentityModel.Policy.IAuthorizationPolicy>并[授权策略](../../../../../docs/framework/wcf/samples/authorization-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="a8496-106">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8496-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8496-107">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="a8496-108">授予对服务操作的权限</span><span class="sxs-lookup"><span data-stu-id="a8496-108">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="a8496-109">如何：创建自定义授权管理器服务</span><span class="sxs-lookup"><span data-stu-id="a8496-109">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="a8496-110">\<add></span><span class="sxs-lookup"><span data-stu-id="a8496-110">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [<span data-ttu-id="a8496-111">授权策略</span><span class="sxs-lookup"><span data-stu-id="a8496-111">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)

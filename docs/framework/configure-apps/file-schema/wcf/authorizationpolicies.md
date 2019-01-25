---
title: '&lt;authorizationPolicies&gt;'
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 7648c221a61efb99b4dc486f9b4d121439632c63
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54519549"
---
# <a name="ltauthorizationpoliciesgt"></a><span data-ttu-id="5ae11-102">&lt;authorizationPolicies&gt;</span><span class="sxs-lookup"><span data-stu-id="5ae11-102">&lt;authorizationPolicies&gt;</span></span>
<span data-ttu-id="5ae11-103">本配置节包含可使用 `add` 关键字添加的授权策略类型的集合。</span><span class="sxs-lookup"><span data-stu-id="5ae11-103">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="5ae11-104">每个授权类型都包含一个所需的 `policyType` 属性，此属性是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="5ae11-104">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="5ae11-105">该属性指定一个授权策略，可以将一组输入声明转换为另一组声明。</span><span class="sxs-lookup"><span data-stu-id="5ae11-105">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="5ae11-106">可以根据该授权策略来授予或拒绝访问控制。</span><span class="sxs-lookup"><span data-stu-id="5ae11-106">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="5ae11-107">授权策略的工作原理的详细信息，请参阅<xref:System.IdentityModel.Policy.IAuthorizationPolicy>并[授权策略](../../../../../docs/framework/wcf/samples/authorization-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="5ae11-107">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae11-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ae11-108">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="5ae11-109">授予对服务操作的权限</span><span class="sxs-lookup"><span data-stu-id="5ae11-109">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="5ae11-110">如何：创建自定义授权管理器服务</span><span class="sxs-lookup"><span data-stu-id="5ae11-110">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="5ae11-111">\<add></span><span class="sxs-lookup"><span data-stu-id="5ae11-111">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [<span data-ttu-id="5ae11-112">授权策略</span><span class="sxs-lookup"><span data-stu-id="5ae11-112">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)

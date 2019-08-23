---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 38d123a53b344ff1e4d781115093d0d1de5ae679
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926465"
---
# <a name="authorizationpolicies"></a><span data-ttu-id="bc30b-101">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="bc30b-101">\<authorizationPolicies></span></span>
<span data-ttu-id="bc30b-102">本配置节包含可使用 `add` 关键字添加的授权策略类型的集合。</span><span class="sxs-lookup"><span data-stu-id="bc30b-102">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="bc30b-103">每个授权类型都包含一个所需的 `policyType` 属性，此属性是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="bc30b-103">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="bc30b-104">该属性指定一个授权策略，可以将一组输入声明转换为另一组声明。</span><span class="sxs-lookup"><span data-stu-id="bc30b-104">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="bc30b-105">可以根据该授权策略来授予或拒绝访问控制。</span><span class="sxs-lookup"><span data-stu-id="bc30b-105">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="bc30b-106">有关授权策略工作方式的详细信息, 请参阅<xref:System.IdentityModel.Policy.IAuthorizationPolicy>和[授权策略](../../../wcf/samples/authorization-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="bc30b-106">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc30b-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc30b-107">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="bc30b-108">授予对服务操作的权限</span><span class="sxs-lookup"><span data-stu-id="bc30b-108">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="bc30b-109">如何：为服务创建自定义授权管理器</span><span class="sxs-lookup"><span data-stu-id="bc30b-109">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="bc30b-110">\<add></span><span class="sxs-lookup"><span data-stu-id="bc30b-110">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="bc30b-111">授权策略</span><span class="sxs-lookup"><span data-stu-id="bc30b-111">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)

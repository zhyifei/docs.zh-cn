---
title: '&lt;authorizationPolicies&gt; 的 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 008f465134860141293776130ebd75cd39120f5e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltauthorizationpoliciesgt"></a><span data-ttu-id="36431-102">&lt;authorizationPolicies&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="36431-102">&lt;add&gt; of &lt;authorizationPolicies&gt;</span></span>
<span data-ttu-id="36431-103">指定声明转换的授权策略。</span><span class="sxs-lookup"><span data-stu-id="36431-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="36431-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="36431-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="36431-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="36431-105">\<behaviors></span></span>  
<span data-ttu-id="36431-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="36431-106">\<behavior></span></span>  
<span data-ttu-id="36431-107">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="36431-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="36431-108">\<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="36431-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="36431-109">\<add></span><span class="sxs-lookup"><span data-stu-id="36431-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36431-110">语法</span><span class="sxs-lookup"><span data-stu-id="36431-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>  
   <add policyType="String" />  
</authorizationPolicies>  
```  
  
## <a name="type"></a><span data-ttu-id="36431-111">类型</span><span class="sxs-lookup"><span data-stu-id="36431-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36431-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="36431-112">Attributes and Elements</span></span>  
 <span data-ttu-id="36431-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="36431-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36431-114">特性</span><span class="sxs-lookup"><span data-stu-id="36431-114">Attributes</span></span>  
  
|<span data-ttu-id="36431-115">特性</span><span class="sxs-lookup"><span data-stu-id="36431-115">Attribute</span></span>|<span data-ttu-id="36431-116">描述</span><span class="sxs-lookup"><span data-stu-id="36431-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="36431-117">必需的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="36431-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="36431-118">Windows Communication Foundation (WCF) 的访问控制模型支持预配的作为类型的授权策略集。</span><span class="sxs-lookup"><span data-stu-id="36431-118">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="36431-119">此属性指定一个授权策略，使得可以将一组输入声明转换为另一组声明。</span><span class="sxs-lookup"><span data-stu-id="36431-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="36431-120">可以根据该授权策略来授予或拒绝访问控制。</span><span class="sxs-lookup"><span data-stu-id="36431-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36431-121">子元素</span><span class="sxs-lookup"><span data-stu-id="36431-121">Child Elements</span></span>  
 <span data-ttu-id="36431-122">无。</span><span class="sxs-lookup"><span data-stu-id="36431-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="36431-123">父元素</span><span class="sxs-lookup"><span data-stu-id="36431-123">Parent Elements</span></span>  
  
|<span data-ttu-id="36431-124">元素</span><span class="sxs-lookup"><span data-stu-id="36431-124">Element</span></span>|<span data-ttu-id="36431-125">描述</span><span class="sxs-lookup"><span data-stu-id="36431-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36431-126">\<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="36431-126">\<authorizationPolicies></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|<span data-ttu-id="36431-127">指定一个授权策略类型集合。</span><span class="sxs-lookup"><span data-stu-id="36431-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36431-128">备注</span><span class="sxs-lookup"><span data-stu-id="36431-128">Remarks</span></span>  
 <span data-ttu-id="36431-129">每个授权类型都包含一个所需的 `policyType` 属性，此属性是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="36431-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="36431-130">该属性指定一个授权策略，可以将一组输入声明转换为另一组声明。</span><span class="sxs-lookup"><span data-stu-id="36431-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="36431-131">可以根据该授权策略来授予或拒绝访问控制。</span><span class="sxs-lookup"><span data-stu-id="36431-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="36431-132">授权策略的工作原理的详细信息，请参阅<xref:System.IdentityModel.Policy.IAuthorizationPolicy>和[授权策略](../../../../../docs/framework/wcf/samples/authorization-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="36431-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36431-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="36431-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 [<span data-ttu-id="36431-134">授予对服务操作的权限</span><span class="sxs-lookup"><span data-stu-id="36431-134">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="36431-135">如何：为服务创建自定义授权管理器</span><span class="sxs-lookup"><span data-stu-id="36431-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="36431-136">\<add></span><span class="sxs-lookup"><span data-stu-id="36431-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)  
 [<span data-ttu-id="36431-137">授权策略</span><span class="sxs-lookup"><span data-stu-id="36431-137">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)

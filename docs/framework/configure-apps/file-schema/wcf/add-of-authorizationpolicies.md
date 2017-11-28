---
title: "&lt;authorizationPolicies&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d835d96c89e8b292fc2c038794aa4056fda3a095
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltauthorizationpoliciesgt"></a><span data-ttu-id="2f510-102">&lt;authorizationPolicies&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="2f510-102">&lt;add&gt; of &lt;authorizationPolicies&gt;</span></span>
<span data-ttu-id="2f510-103">指定声明转换的授权策略。</span><span class="sxs-lookup"><span data-stu-id="2f510-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="2f510-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2f510-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2f510-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="2f510-105">\<behaviors></span></span>  
<span data-ttu-id="2f510-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="2f510-106">\<behavior></span></span>  
<span data-ttu-id="2f510-107">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="2f510-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="2f510-108">\<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="2f510-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="2f510-109">\<add></span><span class="sxs-lookup"><span data-stu-id="2f510-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f510-110">语法</span><span class="sxs-lookup"><span data-stu-id="2f510-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>  
   <add policyType="String" />  
</authorizationPolicies>  
```  
  
## <a name="type"></a><span data-ttu-id="2f510-111">类型</span><span class="sxs-lookup"><span data-stu-id="2f510-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f510-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2f510-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2f510-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2f510-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f510-114">特性</span><span class="sxs-lookup"><span data-stu-id="2f510-114">Attributes</span></span>  
  
|<span data-ttu-id="2f510-115">特性</span><span class="sxs-lookup"><span data-stu-id="2f510-115">Attribute</span></span>|<span data-ttu-id="2f510-116">描述</span><span class="sxs-lookup"><span data-stu-id="2f510-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="2f510-117">必需的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="2f510-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="2f510-118">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 访问控制模型支持以类型的形式提供一组授权策略。</span><span class="sxs-lookup"><span data-stu-id="2f510-118">The [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="2f510-119">此属性指定一个授权策略，使得可以将一组输入声明转换为另一组声明。</span><span class="sxs-lookup"><span data-stu-id="2f510-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="2f510-120">可以根据该授权策略来授予或拒绝访问控制。</span><span class="sxs-lookup"><span data-stu-id="2f510-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f510-121">子元素</span><span class="sxs-lookup"><span data-stu-id="2f510-121">Child Elements</span></span>  
 <span data-ttu-id="2f510-122">无。</span><span class="sxs-lookup"><span data-stu-id="2f510-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2f510-123">父元素</span><span class="sxs-lookup"><span data-stu-id="2f510-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2f510-124">元素</span><span class="sxs-lookup"><span data-stu-id="2f510-124">Element</span></span>|<span data-ttu-id="2f510-125">描述</span><span class="sxs-lookup"><span data-stu-id="2f510-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f510-126">\<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="2f510-126">\<authorizationPolicies></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|<span data-ttu-id="2f510-127">指定一个授权策略类型集合。</span><span class="sxs-lookup"><span data-stu-id="2f510-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f510-128">备注</span><span class="sxs-lookup"><span data-stu-id="2f510-128">Remarks</span></span>  
 <span data-ttu-id="2f510-129">每个授权类型都包含一个所需的 `policyType` 属性，此属性是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="2f510-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="2f510-130">该属性指定一个授权策略，可以将一组输入声明转换为另一组声明。</span><span class="sxs-lookup"><span data-stu-id="2f510-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="2f510-131">可以根据该授权策略来授予或拒绝访问控制。</span><span class="sxs-lookup"><span data-stu-id="2f510-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="2f510-132">授权策略的工作原理的详细信息，请参阅<xref:System.IdentityModel.Policy.IAuthorizationPolicy>和[授权策略](../../../../../docs/framework/wcf/samples/authorization-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="2f510-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f510-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f510-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 [<span data-ttu-id="2f510-134">授予对服务操作访问权限</span><span class="sxs-lookup"><span data-stu-id="2f510-134">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="2f510-135">如何： 创建自定义授权管理器服务</span><span class="sxs-lookup"><span data-stu-id="2f510-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="2f510-136">\<add></span><span class="sxs-lookup"><span data-stu-id="2f510-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)  
 [<span data-ttu-id="2f510-137">授权策略</span><span class="sxs-lookup"><span data-stu-id="2f510-137">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)

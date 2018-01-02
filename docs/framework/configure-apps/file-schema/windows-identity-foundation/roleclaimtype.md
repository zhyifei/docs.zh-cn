---
title: '&lt;roleClaimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: eb46585561ca8a2ab7c69f09d073d38bc1b60646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="a2932-102">&lt;roleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="a2932-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="a2932-103">指定的集合中定义的角色类型声明的声明类型<xref:System.Security.Claims.ClaimsIdentity>返回的对象<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>令牌处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="a2932-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="a2932-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="a2932-104">\<system.identityModel></span></span>  
<span data-ttu-id="a2932-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a2932-105">\<identityConfiguration></span></span>  
<span data-ttu-id="a2932-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="a2932-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="a2932-107">\<add></span><span class="sxs-lookup"><span data-stu-id="a2932-107">\<add></span></span>  
<span data-ttu-id="a2932-108">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="a2932-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="a2932-109">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="a2932-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2932-110">语法</span><span class="sxs-lookup"><span data-stu-id="a2932-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2932-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a2932-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a2932-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a2932-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2932-113">特性</span><span class="sxs-lookup"><span data-stu-id="a2932-113">Attributes</span></span>  
  
|<span data-ttu-id="a2932-114">特性</span><span class="sxs-lookup"><span data-stu-id="a2932-114">Attribute</span></span>|<span data-ttu-id="a2932-115">描述</span><span class="sxs-lookup"><span data-stu-id="a2932-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a2932-116">值</span><span class="sxs-lookup"><span data-stu-id="a2932-116">value</span></span>|<span data-ttu-id="a2932-117">一个字符串，指定表示要用于此角色声明类型的声明的声明类型的 URI。</span><span class="sxs-lookup"><span data-stu-id="a2932-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2932-118">子元素</span><span class="sxs-lookup"><span data-stu-id="a2932-118">Child Elements</span></span>  
 <span data-ttu-id="a2932-119">无</span><span class="sxs-lookup"><span data-stu-id="a2932-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2932-120">父元素</span><span class="sxs-lookup"><span data-stu-id="a2932-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a2932-121">元素</span><span class="sxs-lookup"><span data-stu-id="a2932-121">Element</span></span>|<span data-ttu-id="a2932-122">描述</span><span class="sxs-lookup"><span data-stu-id="a2932-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a2932-123">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="a2932-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="a2932-124">提供有关配置<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>类，<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类或这些类之一的派生的类。</span><span class="sxs-lookup"><span data-stu-id="a2932-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2932-125">备注</span><span class="sxs-lookup"><span data-stu-id="a2932-125">Remarks</span></span>  
 <span data-ttu-id="a2932-126">`<roleClaimType>`元素集<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>属性时<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>从配置初始化对象。</span><span class="sxs-lookup"><span data-stu-id="a2932-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2932-127">示例</span><span class="sxs-lookup"><span data-stu-id="a2932-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2932-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2932-128">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>

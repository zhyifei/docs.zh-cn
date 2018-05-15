---
title: '&lt;roleClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 909df1bd6054d9737f91c30c3c6b2d68b932281c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="3dd87-102">&lt;roleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="3dd87-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="3dd87-103">指定的集合中定义的角色类型声明的声明类型<xref:System.Security.Claims.ClaimsIdentity>返回的对象<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>令牌处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="3dd87-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="3dd87-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3dd87-104">\<system.identityModel></span></span>  
<span data-ttu-id="3dd87-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3dd87-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3dd87-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3dd87-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3dd87-107">\<add></span><span class="sxs-lookup"><span data-stu-id="3dd87-107">\<add></span></span>  
<span data-ttu-id="3dd87-108">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="3dd87-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="3dd87-109">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="3dd87-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dd87-110">语法</span><span class="sxs-lookup"><span data-stu-id="3dd87-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3dd87-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3dd87-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3dd87-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3dd87-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3dd87-113">特性</span><span class="sxs-lookup"><span data-stu-id="3dd87-113">Attributes</span></span>  
  
|<span data-ttu-id="3dd87-114">特性</span><span class="sxs-lookup"><span data-stu-id="3dd87-114">Attribute</span></span>|<span data-ttu-id="3dd87-115">描述</span><span class="sxs-lookup"><span data-stu-id="3dd87-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3dd87-116">值</span><span class="sxs-lookup"><span data-stu-id="3dd87-116">value</span></span>|<span data-ttu-id="3dd87-117">一个字符串，指定表示要用于此角色声明类型的声明的声明类型的 URI。</span><span class="sxs-lookup"><span data-stu-id="3dd87-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3dd87-118">子元素</span><span class="sxs-lookup"><span data-stu-id="3dd87-118">Child Elements</span></span>  
 <span data-ttu-id="3dd87-119">无</span><span class="sxs-lookup"><span data-stu-id="3dd87-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3dd87-120">父元素</span><span class="sxs-lookup"><span data-stu-id="3dd87-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3dd87-121">元素</span><span class="sxs-lookup"><span data-stu-id="3dd87-121">Element</span></span>|<span data-ttu-id="3dd87-122">描述</span><span class="sxs-lookup"><span data-stu-id="3dd87-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3dd87-123">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="3dd87-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="3dd87-124">提供有关配置<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>类，<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类或这些类之一的派生的类。</span><span class="sxs-lookup"><span data-stu-id="3dd87-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dd87-125">备注</span><span class="sxs-lookup"><span data-stu-id="3dd87-125">Remarks</span></span>  
 <span data-ttu-id="3dd87-126">`<roleClaimType>`元素集<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>属性时<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>从配置初始化对象。</span><span class="sxs-lookup"><span data-stu-id="3dd87-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dd87-127">示例</span><span class="sxs-lookup"><span data-stu-id="3dd87-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3dd87-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="3dd87-128">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>

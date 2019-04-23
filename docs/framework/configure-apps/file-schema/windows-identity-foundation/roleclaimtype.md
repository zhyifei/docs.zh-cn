---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 8c7b7c9b42ac72b878aed4e12298dc3655f1e707
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115591"
---
# <a name="roleclaimtype"></a><span data-ttu-id="95018-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="95018-101">\<roleClaimType></span></span>
<span data-ttu-id="95018-102">指定的集合中定义的角色类型声明的声明类型<xref:System.Security.Claims.ClaimsIdentity>返回的对象<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>令牌处理程序的方法。</span><span class="sxs-lookup"><span data-stu-id="95018-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="95018-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="95018-103">\<system.identityModel></span></span>  
<span data-ttu-id="95018-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="95018-104">\<identityConfiguration></span></span>  
<span data-ttu-id="95018-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="95018-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="95018-106">\<add></span><span class="sxs-lookup"><span data-stu-id="95018-106">\<add></span></span>  
<span data-ttu-id="95018-107">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="95018-107">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="95018-108">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="95018-108">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95018-109">语法</span><span class="sxs-lookup"><span data-stu-id="95018-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95018-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="95018-110">Attributes and Elements</span></span>  
 <span data-ttu-id="95018-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="95018-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95018-112">特性</span><span class="sxs-lookup"><span data-stu-id="95018-112">Attributes</span></span>  
  
|<span data-ttu-id="95018-113">特性</span><span class="sxs-lookup"><span data-stu-id="95018-113">Attribute</span></span>|<span data-ttu-id="95018-114">描述</span><span class="sxs-lookup"><span data-stu-id="95018-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95018-115">值</span><span class="sxs-lookup"><span data-stu-id="95018-115">value</span></span>|<span data-ttu-id="95018-116">一个字符串，指定表示要用于角色声明类型的声明的声明类型的 URI。</span><span class="sxs-lookup"><span data-stu-id="95018-116">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95018-117">子元素</span><span class="sxs-lookup"><span data-stu-id="95018-117">Child Elements</span></span>  
 <span data-ttu-id="95018-118">None</span><span class="sxs-lookup"><span data-stu-id="95018-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="95018-119">父元素</span><span class="sxs-lookup"><span data-stu-id="95018-119">Parent Elements</span></span>  
  
|<span data-ttu-id="95018-120">元素</span><span class="sxs-lookup"><span data-stu-id="95018-120">Element</span></span>|<span data-ttu-id="95018-121">描述</span><span class="sxs-lookup"><span data-stu-id="95018-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95018-122">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="95018-122">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="95018-123">提供用于配置<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>类，<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类或这些类的任何一个的派生的类。</span><span class="sxs-lookup"><span data-stu-id="95018-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95018-124">备注</span><span class="sxs-lookup"><span data-stu-id="95018-124">Remarks</span></span>  
 <span data-ttu-id="95018-125">`<roleClaimType>`元素集<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>属性时<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>从配置初始化对象。</span><span class="sxs-lookup"><span data-stu-id="95018-125">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95018-126">示例</span><span class="sxs-lookup"><span data-stu-id="95018-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="95018-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="95018-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>

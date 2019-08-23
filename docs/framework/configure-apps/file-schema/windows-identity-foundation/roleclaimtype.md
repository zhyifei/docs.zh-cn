---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0ce2e06ee895d09de193bac1fe7038e71794dda4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942544"
---
# <a name="roleclaimtype"></a><span data-ttu-id="28b8a-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="28b8a-101">\<roleClaimType></span></span>
<span data-ttu-id="28b8a-102">指定声明类型, 该声明类型定义<xref:System.Security.Claims.ClaimsIdentity> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>由标记处理程序的方法返回的对象集合中的角色类型声明。</span><span class="sxs-lookup"><span data-stu-id="28b8a-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="28b8a-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="28b8a-103">\<system.identityModel></span></span>  
<span data-ttu-id="28b8a-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="28b8a-104">\<identityConfiguration></span></span>  
<span data-ttu-id="28b8a-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="28b8a-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="28b8a-106">\<add></span><span class="sxs-lookup"><span data-stu-id="28b8a-106">\<add></span></span>  
<span data-ttu-id="28b8a-107">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="28b8a-107">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="28b8a-108">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="28b8a-108">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28b8a-109">语法</span><span class="sxs-lookup"><span data-stu-id="28b8a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28b8a-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="28b8a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="28b8a-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="28b8a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28b8a-112">特性</span><span class="sxs-lookup"><span data-stu-id="28b8a-112">Attributes</span></span>  
  
|<span data-ttu-id="28b8a-113">特性</span><span class="sxs-lookup"><span data-stu-id="28b8a-113">Attribute</span></span>|<span data-ttu-id="28b8a-114">描述</span><span class="sxs-lookup"><span data-stu-id="28b8a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="28b8a-115">值</span><span class="sxs-lookup"><span data-stu-id="28b8a-115">value</span></span>|<span data-ttu-id="28b8a-116">一个字符串, 指定表示要用于角色声明类型的声明的声明类型的 URI。</span><span class="sxs-lookup"><span data-stu-id="28b8a-116">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28b8a-117">子元素</span><span class="sxs-lookup"><span data-stu-id="28b8a-117">Child Elements</span></span>  
 <span data-ttu-id="28b8a-118">无</span><span class="sxs-lookup"><span data-stu-id="28b8a-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28b8a-119">父元素</span><span class="sxs-lookup"><span data-stu-id="28b8a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="28b8a-120">元素</span><span class="sxs-lookup"><span data-stu-id="28b8a-120">Element</span></span>|<span data-ttu-id="28b8a-121">描述</span><span class="sxs-lookup"><span data-stu-id="28b8a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28b8a-122">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="28b8a-122">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="28b8a-123">为<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 类<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 、类或其中任何一个类的派生类提供配置。</span><span class="sxs-lookup"><span data-stu-id="28b8a-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28b8a-124">备注</span><span class="sxs-lookup"><span data-stu-id="28b8a-124">Remarks</span></span>  
 <span data-ttu-id="28b8a-125">从`<roleClaimType>`配置中初始化<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>对象时, 元素设置属性。</span><span class="sxs-lookup"><span data-stu-id="28b8a-125">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28b8a-126">示例</span><span class="sxs-lookup"><span data-stu-id="28b8a-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="28b8a-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="28b8a-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>

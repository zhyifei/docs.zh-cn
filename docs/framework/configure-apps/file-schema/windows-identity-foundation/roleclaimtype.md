---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0f651377346b1f14a4226128cd5cf7059543adca
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251916"
---
# <a name="roleclaimtype"></a><span data-ttu-id="fadd8-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="fadd8-101">\<roleClaimType></span></span>
<span data-ttu-id="fadd8-102">指定声明类型，该声明类型定义<xref:System.Security.Claims.ClaimsIdentity> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>由标记处理程序的方法返回的对象集合中的角色类型声明。</span><span class="sxs-lookup"><span data-stu-id="fadd8-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
<span data-ttu-id="fadd8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fadd8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fadd8-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="fadd8-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="fadd8-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="fadd8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="fadd8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="fadd8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="fadd8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<添加 >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="fadd8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="fadd8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<samlSecurityTokenRequirement >** ](samlsecuritytokenrequirement.md)</span><span class="sxs-lookup"><span data-stu-id="fadd8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)</span></span>\
<span data-ttu-id="fadd8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<roleClaimType >**</span><span class="sxs-lookup"><span data-stu-id="fadd8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fadd8-110">语法</span><span class="sxs-lookup"><span data-stu-id="fadd8-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fadd8-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fadd8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fadd8-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fadd8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fadd8-113">特性</span><span class="sxs-lookup"><span data-stu-id="fadd8-113">Attributes</span></span>  
  
|<span data-ttu-id="fadd8-114">特性</span><span class="sxs-lookup"><span data-stu-id="fadd8-114">Attribute</span></span>|<span data-ttu-id="fadd8-115">描述</span><span class="sxs-lookup"><span data-stu-id="fadd8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fadd8-116">值</span><span class="sxs-lookup"><span data-stu-id="fadd8-116">value</span></span>|<span data-ttu-id="fadd8-117">一个字符串，指定表示要用于角色声明类型的声明的声明类型的 URI。</span><span class="sxs-lookup"><span data-stu-id="fadd8-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fadd8-118">子元素</span><span class="sxs-lookup"><span data-stu-id="fadd8-118">Child Elements</span></span>  
 <span data-ttu-id="fadd8-119">无</span><span class="sxs-lookup"><span data-stu-id="fadd8-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fadd8-120">父元素</span><span class="sxs-lookup"><span data-stu-id="fadd8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="fadd8-121">元素</span><span class="sxs-lookup"><span data-stu-id="fadd8-121">Element</span></span>|<span data-ttu-id="fadd8-122">描述</span><span class="sxs-lookup"><span data-stu-id="fadd8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fadd8-123">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="fadd8-123">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="fadd8-124">为<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 类<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 、类或其中任何一个类的派生类提供配置。</span><span class="sxs-lookup"><span data-stu-id="fadd8-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fadd8-125">备注</span><span class="sxs-lookup"><span data-stu-id="fadd8-125">Remarks</span></span>  
 <span data-ttu-id="fadd8-126">从`<roleClaimType>`配置中初始化<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>对象时，元素设置属性。</span><span class="sxs-lookup"><span data-stu-id="fadd8-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fadd8-127">示例</span><span class="sxs-lookup"><span data-stu-id="fadd8-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fadd8-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="fadd8-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>

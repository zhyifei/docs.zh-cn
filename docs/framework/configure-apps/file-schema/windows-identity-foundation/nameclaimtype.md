---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 47366c5bb2bd9228268fce3ae6e1fb5ad457dab1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942619"
---
# <a name="nameclaimtype"></a><span data-ttu-id="4b735-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="4b735-101">\<nameClaimType></span></span>
<span data-ttu-id="4b735-102">设置指定<xref:System.Security.Principal.IIdentity.Name%2A>属性的声明类型。</span><span class="sxs-lookup"><span data-stu-id="4b735-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="4b735-103">声明类型用于<xref:System.Security.Claims.Claim>在此标记处理程序的<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>方法返回的<xref:System.Security.Claims.ClaimsIdentity>对象集合中搜索。</span><span class="sxs-lookup"><span data-stu-id="4b735-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="4b735-104">然后, 将匹配声明的值设置为从此标记处理程序生成<xref:System.Security.Principal.IIdentity>的的名称。</span><span class="sxs-lookup"><span data-stu-id="4b735-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="4b735-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="4b735-105">\<system.identityModel></span></span>  
<span data-ttu-id="4b735-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="4b735-106">\<identityConfiguration></span></span>  
<span data-ttu-id="4b735-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="4b735-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="4b735-108">\<add></span><span class="sxs-lookup"><span data-stu-id="4b735-108">\<add></span></span>  
<span data-ttu-id="4b735-109">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="4b735-109">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="4b735-110">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="4b735-110">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b735-111">语法</span><span class="sxs-lookup"><span data-stu-id="4b735-111">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b735-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4b735-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4b735-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4b735-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b735-114">特性</span><span class="sxs-lookup"><span data-stu-id="4b735-114">Attributes</span></span>  
  
|<span data-ttu-id="4b735-115">特性</span><span class="sxs-lookup"><span data-stu-id="4b735-115">Attribute</span></span>|<span data-ttu-id="4b735-116">描述</span><span class="sxs-lookup"><span data-stu-id="4b735-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b735-117">值</span><span class="sxs-lookup"><span data-stu-id="4b735-117">value</span></span>|<span data-ttu-id="4b735-118">一个字符串, 指定表示要<xref:System.Security.Principal.IIdentity.Name%2A>用于属性的声明的声明类型的 URI。</span><span class="sxs-lookup"><span data-stu-id="4b735-118">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="4b735-119">必需。</span><span class="sxs-lookup"><span data-stu-id="4b735-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b735-120">子元素</span><span class="sxs-lookup"><span data-stu-id="4b735-120">Child Elements</span></span>  
 <span data-ttu-id="4b735-121">无</span><span class="sxs-lookup"><span data-stu-id="4b735-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4b735-122">父元素</span><span class="sxs-lookup"><span data-stu-id="4b735-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4b735-123">元素</span><span class="sxs-lookup"><span data-stu-id="4b735-123">Element</span></span>|<span data-ttu-id="4b735-124">描述</span><span class="sxs-lookup"><span data-stu-id="4b735-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b735-125">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="4b735-125">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="4b735-126">为<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 类<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 、类或其中任何一个类的派生类提供配置。</span><span class="sxs-lookup"><span data-stu-id="4b735-126">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b735-127">备注</span><span class="sxs-lookup"><span data-stu-id="4b735-127">Remarks</span></span>  
 <span data-ttu-id="4b735-128">从`<nameClaimType>`配置中初始化<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>对象时, 元素设置属性。</span><span class="sxs-lookup"><span data-stu-id="4b735-128">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b735-129">示例</span><span class="sxs-lookup"><span data-stu-id="4b735-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b735-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b735-130">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>

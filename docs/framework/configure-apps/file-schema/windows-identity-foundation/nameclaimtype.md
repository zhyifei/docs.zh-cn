---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4bf8ad2f70499edfc72dd9fcd9a5d8a0aafbbc66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251942"
---
# <a name="nameclaimtype"></a><span data-ttu-id="de6e1-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="de6e1-101">\<nameClaimType></span></span>
<span data-ttu-id="de6e1-102">设置指定<xref:System.Security.Principal.IIdentity.Name%2A>属性的声明类型。</span><span class="sxs-lookup"><span data-stu-id="de6e1-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="de6e1-103">声明类型用于<xref:System.Security.Claims.Claim>在此标记处理程序的<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>方法返回的<xref:System.Security.Claims.ClaimsIdentity>对象集合中搜索。</span><span class="sxs-lookup"><span data-stu-id="de6e1-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="de6e1-104">然后，将匹配声明的值设置为从此标记处理程序生成<xref:System.Security.Principal.IIdentity>的的名称。</span><span class="sxs-lookup"><span data-stu-id="de6e1-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
<span data-ttu-id="de6e1-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="de6e1-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="de6e1-106">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="de6e1-106">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="de6e1-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="de6e1-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="de6e1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="de6e1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="de6e1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<添加 >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="de6e1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="de6e1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<samlSecurityTokenRequirement >** ](samlsecuritytokenrequirement.md)</span><span class="sxs-lookup"><span data-stu-id="de6e1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)</span></span>\
<span data-ttu-id="de6e1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<nameClaimType >**</span><span class="sxs-lookup"><span data-stu-id="de6e1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de6e1-112">语法</span><span class="sxs-lookup"><span data-stu-id="de6e1-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de6e1-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="de6e1-113">Attributes and Elements</span></span>  
 <span data-ttu-id="de6e1-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="de6e1-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de6e1-115">特性</span><span class="sxs-lookup"><span data-stu-id="de6e1-115">Attributes</span></span>  
  
|<span data-ttu-id="de6e1-116">特性</span><span class="sxs-lookup"><span data-stu-id="de6e1-116">Attribute</span></span>|<span data-ttu-id="de6e1-117">描述</span><span class="sxs-lookup"><span data-stu-id="de6e1-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de6e1-118">值</span><span class="sxs-lookup"><span data-stu-id="de6e1-118">value</span></span>|<span data-ttu-id="de6e1-119">一个字符串，指定表示要<xref:System.Security.Principal.IIdentity.Name%2A>用于属性的声明的声明类型的 URI。</span><span class="sxs-lookup"><span data-stu-id="de6e1-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="de6e1-120">必需。</span><span class="sxs-lookup"><span data-stu-id="de6e1-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de6e1-121">子元素</span><span class="sxs-lookup"><span data-stu-id="de6e1-121">Child Elements</span></span>  
 <span data-ttu-id="de6e1-122">无</span><span class="sxs-lookup"><span data-stu-id="de6e1-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de6e1-123">父元素</span><span class="sxs-lookup"><span data-stu-id="de6e1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="de6e1-124">元素</span><span class="sxs-lookup"><span data-stu-id="de6e1-124">Element</span></span>|<span data-ttu-id="de6e1-125">描述</span><span class="sxs-lookup"><span data-stu-id="de6e1-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de6e1-126">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="de6e1-126">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="de6e1-127">为<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 类<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 、类或其中任何一个类的派生类提供配置。</span><span class="sxs-lookup"><span data-stu-id="de6e1-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de6e1-128">备注</span><span class="sxs-lookup"><span data-stu-id="de6e1-128">Remarks</span></span>  
 <span data-ttu-id="de6e1-129">从`<nameClaimType>`配置中初始化<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>对象时，元素设置属性。</span><span class="sxs-lookup"><span data-stu-id="de6e1-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de6e1-130">示例</span><span class="sxs-lookup"><span data-stu-id="de6e1-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de6e1-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="de6e1-131">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>

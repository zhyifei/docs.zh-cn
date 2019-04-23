---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 5202e162a7eb5fc4e36d6a6c0a2c18af48872a69
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130320"
---
# <a name="nameclaimtype"></a><span data-ttu-id="77405-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="77405-101">\<nameClaimType></span></span>
<span data-ttu-id="77405-102">设置指定的声明类型<xref:System.Security.Principal.IIdentity.Name%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="77405-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="77405-103">声明类型用于搜索<xref:System.Security.Claims.Claim>中的集合<xref:System.Security.Claims.ClaimsIdentity>返回的对象<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>此令牌处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="77405-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="77405-104">然后，将匹配声明的值设置为的名称<xref:System.Security.Principal.IIdentity>生成的此令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="77405-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="77405-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="77405-105">\<system.identityModel></span></span>  
<span data-ttu-id="77405-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="77405-106">\<identityConfiguration></span></span>  
<span data-ttu-id="77405-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="77405-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="77405-108">\<add></span><span class="sxs-lookup"><span data-stu-id="77405-108">\<add></span></span>  
<span data-ttu-id="77405-109">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="77405-109">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="77405-110">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="77405-110">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77405-111">语法</span><span class="sxs-lookup"><span data-stu-id="77405-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77405-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="77405-112">Attributes and Elements</span></span>  
 <span data-ttu-id="77405-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="77405-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77405-114">特性</span><span class="sxs-lookup"><span data-stu-id="77405-114">Attributes</span></span>  
  
|<span data-ttu-id="77405-115">特性</span><span class="sxs-lookup"><span data-stu-id="77405-115">Attribute</span></span>|<span data-ttu-id="77405-116">描述</span><span class="sxs-lookup"><span data-stu-id="77405-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="77405-117">值</span><span class="sxs-lookup"><span data-stu-id="77405-117">value</span></span>|<span data-ttu-id="77405-118">一个字符串，指定表示要使用的声明的声明类型的 URI<xref:System.Security.Principal.IIdentity.Name%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="77405-118">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="77405-119">必需。</span><span class="sxs-lookup"><span data-stu-id="77405-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="77405-120">子元素</span><span class="sxs-lookup"><span data-stu-id="77405-120">Child Elements</span></span>  
 <span data-ttu-id="77405-121">None</span><span class="sxs-lookup"><span data-stu-id="77405-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77405-122">父元素</span><span class="sxs-lookup"><span data-stu-id="77405-122">Parent Elements</span></span>  
  
|<span data-ttu-id="77405-123">元素</span><span class="sxs-lookup"><span data-stu-id="77405-123">Element</span></span>|<span data-ttu-id="77405-124">描述</span><span class="sxs-lookup"><span data-stu-id="77405-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="77405-125">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="77405-125">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="77405-126">提供用于配置<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>类，<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>类或这些类的任何一个的派生的类。</span><span class="sxs-lookup"><span data-stu-id="77405-126">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77405-127">备注</span><span class="sxs-lookup"><span data-stu-id="77405-127">Remarks</span></span>  
 <span data-ttu-id="77405-128">`<nameClaimType>`元素集<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>属性时<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>从配置初始化对象。</span><span class="sxs-lookup"><span data-stu-id="77405-128">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77405-129">示例</span><span class="sxs-lookup"><span data-stu-id="77405-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="77405-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="77405-130">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>

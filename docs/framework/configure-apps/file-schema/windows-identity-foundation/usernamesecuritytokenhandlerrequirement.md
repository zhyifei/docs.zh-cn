---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 5863c01e97e7f5fb6fe07c43174c0d6cb7a0a25d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251737"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="4a9db-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="4a9db-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="4a9db-102">提供<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>类或派生类的配置。</span><span class="sxs-lookup"><span data-stu-id="4a9db-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="4a9db-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4a9db-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4a9db-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="4a9db-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="4a9db-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="4a9db-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="4a9db-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="4a9db-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="4a9db-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<添加 >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="4a9db-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="4a9db-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<userNameSecurityTokenHandlerRequirement >**</span><span class="sxs-lookup"><span data-stu-id="4a9db-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a9db-109">语法</span><span class="sxs-lookup"><span data-stu-id="4a9db-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a9db-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4a9db-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4a9db-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4a9db-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a9db-112">特性</span><span class="sxs-lookup"><span data-stu-id="4a9db-112">Attributes</span></span>  
  
|<span data-ttu-id="4a9db-113">特性</span><span class="sxs-lookup"><span data-stu-id="4a9db-113">Attribute</span></span>|<span data-ttu-id="4a9db-114">描述</span><span class="sxs-lookup"><span data-stu-id="4a9db-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a9db-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="4a9db-115">membershipProviderName</span></span>|<span data-ttu-id="4a9db-116"><xref:System.Web.Security.MembershipProvider>指定应该由安全令牌处理程序使用的。</span><span class="sxs-lookup"><span data-stu-id="4a9db-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a9db-117">子元素</span><span class="sxs-lookup"><span data-stu-id="4a9db-117">Child Elements</span></span>  
 <span data-ttu-id="4a9db-118">无</span><span class="sxs-lookup"><span data-stu-id="4a9db-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a9db-119">父元素</span><span class="sxs-lookup"><span data-stu-id="4a9db-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4a9db-120">元素</span><span class="sxs-lookup"><span data-stu-id="4a9db-120">Element</span></span>|<span data-ttu-id="4a9db-121">描述</span><span class="sxs-lookup"><span data-stu-id="4a9db-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a9db-122">\<add></span><span class="sxs-lookup"><span data-stu-id="4a9db-122">\<add></span></span>](add.md)|<span data-ttu-id="4a9db-123">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="4a9db-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a9db-124">备注</span><span class="sxs-lookup"><span data-stu-id="4a9db-124">Remarks</span></span>  
 <span data-ttu-id="4a9db-125">从`<userNameSecurityTokenHandlerRequirement>`配置中初始化<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>对象时，元素设置属性。</span><span class="sxs-lookup"><span data-stu-id="4a9db-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a9db-126">示例</span><span class="sxs-lookup"><span data-stu-id="4a9db-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```

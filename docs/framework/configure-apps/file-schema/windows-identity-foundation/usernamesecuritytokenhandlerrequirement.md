---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 5d725cc0d16457f2bdfb404baf4758e3431ce6b7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756652"
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a><span data-ttu-id="3c2a1-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="3c2a1-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="3c2a1-103">提供有关配置<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="3c2a1-103">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="3c2a1-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3c2a1-104">\<system.identityModel></span></span>  
<span data-ttu-id="3c2a1-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3c2a1-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3c2a1-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3c2a1-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3c2a1-107">\<add></span><span class="sxs-lookup"><span data-stu-id="3c2a1-107">\<add></span></span>  
<span data-ttu-id="3c2a1-108">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="3c2a1-108">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c2a1-109">语法</span><span class="sxs-lookup"><span data-stu-id="3c2a1-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c2a1-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3c2a1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3c2a1-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3c2a1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c2a1-112">特性</span><span class="sxs-lookup"><span data-stu-id="3c2a1-112">Attributes</span></span>  
  
|<span data-ttu-id="3c2a1-113">特性</span><span class="sxs-lookup"><span data-stu-id="3c2a1-113">Attribute</span></span>|<span data-ttu-id="3c2a1-114">描述</span><span class="sxs-lookup"><span data-stu-id="3c2a1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c2a1-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="3c2a1-115">membershipProviderName</span></span>|<span data-ttu-id="3c2a1-116">指定<xref:System.Web.Security.MembershipProvider>，应由安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="3c2a1-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c2a1-117">子元素</span><span class="sxs-lookup"><span data-stu-id="3c2a1-117">Child Elements</span></span>  
 <span data-ttu-id="3c2a1-118">无</span><span class="sxs-lookup"><span data-stu-id="3c2a1-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c2a1-119">父元素</span><span class="sxs-lookup"><span data-stu-id="3c2a1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3c2a1-120">元素</span><span class="sxs-lookup"><span data-stu-id="3c2a1-120">Element</span></span>|<span data-ttu-id="3c2a1-121">描述</span><span class="sxs-lookup"><span data-stu-id="3c2a1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c2a1-122">\<add></span><span class="sxs-lookup"><span data-stu-id="3c2a1-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="3c2a1-123">将指定的安全令牌处理程序添加到令牌处理程序集合中。</span><span class="sxs-lookup"><span data-stu-id="3c2a1-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c2a1-124">备注</span><span class="sxs-lookup"><span data-stu-id="3c2a1-124">Remarks</span></span>  
 <span data-ttu-id="3c2a1-125">`<userNameSecurityTokenHandlerRequirement>`元素集<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A>属性时<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>从配置初始化对象。</span><span class="sxs-lookup"><span data-stu-id="3c2a1-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c2a1-126">示例</span><span class="sxs-lookup"><span data-stu-id="3c2a1-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```

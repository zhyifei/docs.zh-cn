---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: fed8964e03b80e365fdc5eafd45b4fc372a6e352
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944254"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="16452-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="16452-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="16452-102">提供<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>类或派生类的配置。</span><span class="sxs-lookup"><span data-stu-id="16452-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="16452-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="16452-103">\<system.identityModel></span></span>  
<span data-ttu-id="16452-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="16452-104">\<identityConfiguration></span></span>  
<span data-ttu-id="16452-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="16452-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="16452-106">\<add></span><span class="sxs-lookup"><span data-stu-id="16452-106">\<add></span></span>  
<span data-ttu-id="16452-107">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="16452-107">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16452-108">语法</span><span class="sxs-lookup"><span data-stu-id="16452-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16452-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="16452-109">Attributes and Elements</span></span>  
 <span data-ttu-id="16452-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="16452-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16452-111">特性</span><span class="sxs-lookup"><span data-stu-id="16452-111">Attributes</span></span>  
  
|<span data-ttu-id="16452-112">特性</span><span class="sxs-lookup"><span data-stu-id="16452-112">Attribute</span></span>|<span data-ttu-id="16452-113">描述</span><span class="sxs-lookup"><span data-stu-id="16452-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="16452-114">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="16452-114">membershipProviderName</span></span>|<span data-ttu-id="16452-115"><xref:System.Web.Security.MembershipProvider>指定应该由安全令牌处理程序使用的。</span><span class="sxs-lookup"><span data-stu-id="16452-115">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16452-116">子元素</span><span class="sxs-lookup"><span data-stu-id="16452-116">Child Elements</span></span>  
 <span data-ttu-id="16452-117">无</span><span class="sxs-lookup"><span data-stu-id="16452-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16452-118">父元素</span><span class="sxs-lookup"><span data-stu-id="16452-118">Parent Elements</span></span>  
  
|<span data-ttu-id="16452-119">元素</span><span class="sxs-lookup"><span data-stu-id="16452-119">Element</span></span>|<span data-ttu-id="16452-120">描述</span><span class="sxs-lookup"><span data-stu-id="16452-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16452-121">\<add></span><span class="sxs-lookup"><span data-stu-id="16452-121">\<add></span></span>](add.md)|<span data-ttu-id="16452-122">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="16452-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16452-123">备注</span><span class="sxs-lookup"><span data-stu-id="16452-123">Remarks</span></span>  
 <span data-ttu-id="16452-124">从`<userNameSecurityTokenHandlerRequirement>`配置中初始化<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>对象时, 元素设置属性。</span><span class="sxs-lookup"><span data-stu-id="16452-124">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16452-125">示例</span><span class="sxs-lookup"><span data-stu-id="16452-125">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```

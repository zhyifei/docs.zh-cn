---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 18769794da8528f085c567264827db5aa6b214f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790450"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="64795-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="64795-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="64795-102">提供配置<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="64795-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="64795-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="64795-103">\<system.identityModel></span></span>  
<span data-ttu-id="64795-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="64795-104">\<identityConfiguration></span></span>  
<span data-ttu-id="64795-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="64795-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="64795-106">\<add></span><span class="sxs-lookup"><span data-stu-id="64795-106">\<add></span></span>  
<span data-ttu-id="64795-107">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="64795-107">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64795-108">语法</span><span class="sxs-lookup"><span data-stu-id="64795-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64795-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="64795-109">Attributes and Elements</span></span>  
 <span data-ttu-id="64795-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="64795-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64795-111">特性</span><span class="sxs-lookup"><span data-stu-id="64795-111">Attributes</span></span>  
  
|<span data-ttu-id="64795-112">特性</span><span class="sxs-lookup"><span data-stu-id="64795-112">Attribute</span></span>|<span data-ttu-id="64795-113">描述</span><span class="sxs-lookup"><span data-stu-id="64795-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="64795-114">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="64795-114">membershipProviderName</span></span>|<span data-ttu-id="64795-115">指定<xref:System.Web.Security.MembershipProvider>，应由安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="64795-115">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64795-116">子元素</span><span class="sxs-lookup"><span data-stu-id="64795-116">Child Elements</span></span>  
 <span data-ttu-id="64795-117">None</span><span class="sxs-lookup"><span data-stu-id="64795-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64795-118">父元素</span><span class="sxs-lookup"><span data-stu-id="64795-118">Parent Elements</span></span>  
  
|<span data-ttu-id="64795-119">元素</span><span class="sxs-lookup"><span data-stu-id="64795-119">Element</span></span>|<span data-ttu-id="64795-120">描述</span><span class="sxs-lookup"><span data-stu-id="64795-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64795-121">\<add></span><span class="sxs-lookup"><span data-stu-id="64795-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="64795-122">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="64795-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64795-123">备注</span><span class="sxs-lookup"><span data-stu-id="64795-123">Remarks</span></span>  
 <span data-ttu-id="64795-124">`<userNameSecurityTokenHandlerRequirement>`元素集<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A>属性时<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>从配置初始化对象。</span><span class="sxs-lookup"><span data-stu-id="64795-124">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64795-125">示例</span><span class="sxs-lookup"><span data-stu-id="64795-125">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```

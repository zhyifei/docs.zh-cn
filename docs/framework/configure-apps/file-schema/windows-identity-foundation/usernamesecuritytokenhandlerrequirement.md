---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 4ffe9764eb730be4859fb66ae2f0cc845c9404e8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a><span data-ttu-id="d6035-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="d6035-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="d6035-103">提供有关配置<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="d6035-103">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="d6035-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="d6035-104">\<system.identityModel></span></span>  
<span data-ttu-id="d6035-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d6035-105">\<identityConfiguration></span></span>  
<span data-ttu-id="d6035-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="d6035-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d6035-107">\<add></span><span class="sxs-lookup"><span data-stu-id="d6035-107">\<add></span></span>  
<span data-ttu-id="d6035-108">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="d6035-108">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6035-109">语法</span><span class="sxs-lookup"><span data-stu-id="d6035-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d6035-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d6035-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d6035-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d6035-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d6035-112">特性</span><span class="sxs-lookup"><span data-stu-id="d6035-112">Attributes</span></span>  
  
|<span data-ttu-id="d6035-113">特性</span><span class="sxs-lookup"><span data-stu-id="d6035-113">Attribute</span></span>|<span data-ttu-id="d6035-114">描述</span><span class="sxs-lookup"><span data-stu-id="d6035-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d6035-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="d6035-115">membershipProviderName</span></span>|<span data-ttu-id="d6035-116">指定<xref:System.Web.Security.MembershipProvider>，应由安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="d6035-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d6035-117">子元素</span><span class="sxs-lookup"><span data-stu-id="d6035-117">Child Elements</span></span>  
 <span data-ttu-id="d6035-118">无</span><span class="sxs-lookup"><span data-stu-id="d6035-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d6035-119">父元素</span><span class="sxs-lookup"><span data-stu-id="d6035-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d6035-120">元素</span><span class="sxs-lookup"><span data-stu-id="d6035-120">Element</span></span>|<span data-ttu-id="d6035-121">说明</span><span class="sxs-lookup"><span data-stu-id="d6035-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d6035-122">\<add></span><span class="sxs-lookup"><span data-stu-id="d6035-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="d6035-123">将指定的安全令牌处理程序添加到令牌处理程序集合中。</span><span class="sxs-lookup"><span data-stu-id="d6035-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6035-124">备注</span><span class="sxs-lookup"><span data-stu-id="d6035-124">Remarks</span></span>  
 <span data-ttu-id="d6035-125">`<userNameSecurityTokenHandlerRequirement>`元素集<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A>属性时<xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>从配置初始化对象。</span><span class="sxs-lookup"><span data-stu-id="d6035-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6035-126">示例</span><span class="sxs-lookup"><span data-stu-id="d6035-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```

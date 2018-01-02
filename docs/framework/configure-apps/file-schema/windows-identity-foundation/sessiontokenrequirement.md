---
title: '&lt;sessionTokenRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 5a141dd83cb7ef1271906871097eb68da174d22f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsessiontokenrequirementgt"></a><span data-ttu-id="811c1-102">&lt;sessionTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="811c1-102">&lt;sessionTokenRequirement&gt;</span></span>
<span data-ttu-id="811c1-103">提供有关配置<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="811c1-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="811c1-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="811c1-104">\<system.identityModel></span></span>  
<span data-ttu-id="811c1-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="811c1-105">\<identityConfiguration></span></span>  
<span data-ttu-id="811c1-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="811c1-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="811c1-107">\<add></span><span class="sxs-lookup"><span data-stu-id="811c1-107">\<add></span></span>  
<span data-ttu-id="811c1-108">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="811c1-108">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="811c1-109">语法</span><span class="sxs-lookup"><span data-stu-id="811c1-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="811c1-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="811c1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="811c1-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="811c1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="811c1-112">特性</span><span class="sxs-lookup"><span data-stu-id="811c1-112">Attributes</span></span>  
  
|<span data-ttu-id="811c1-113">特性</span><span class="sxs-lookup"><span data-stu-id="811c1-113">Attribute</span></span>|<span data-ttu-id="811c1-114">描述</span><span class="sxs-lookup"><span data-stu-id="811c1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="811c1-115">Lifetime — 生存期</span><span class="sxs-lookup"><span data-stu-id="811c1-115">lifetime</span></span>|<span data-ttu-id="811c1-116">指定的会话令牌的生存期。</span><span class="sxs-lookup"><span data-stu-id="811c1-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="811c1-117">子元素</span><span class="sxs-lookup"><span data-stu-id="811c1-117">Child Elements</span></span>  
 <span data-ttu-id="811c1-118">无</span><span class="sxs-lookup"><span data-stu-id="811c1-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="811c1-119">父元素</span><span class="sxs-lookup"><span data-stu-id="811c1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="811c1-120">元素</span><span class="sxs-lookup"><span data-stu-id="811c1-120">Element</span></span>|<span data-ttu-id="811c1-121">描述</span><span class="sxs-lookup"><span data-stu-id="811c1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="811c1-122">\<add></span><span class="sxs-lookup"><span data-stu-id="811c1-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="811c1-123">将指定的安全令牌处理程序添加到令牌处理程序集合中。</span><span class="sxs-lookup"><span data-stu-id="811c1-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="811c1-124">示例</span><span class="sxs-lookup"><span data-stu-id="811c1-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```

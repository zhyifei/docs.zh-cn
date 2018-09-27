---
title: '&lt;sessionTokenRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 4d5d2348f04ace7596a3a513c5106ea612dc17b7
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47236882"
---
# <a name="ltsessiontokenrequirementgt"></a><span data-ttu-id="b495e-102">&lt;sessionTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="b495e-102">&lt;sessionTokenRequirement&gt;</span></span>
<span data-ttu-id="b495e-103">提供配置<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="b495e-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="b495e-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b495e-104">\<system.identityModel></span></span>  
<span data-ttu-id="b495e-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b495e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b495e-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b495e-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b495e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="b495e-107">\<add></span></span>  
<span data-ttu-id="b495e-108">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="b495e-108">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b495e-109">语法</span><span class="sxs-lookup"><span data-stu-id="b495e-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b495e-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b495e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b495e-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b495e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b495e-112">特性</span><span class="sxs-lookup"><span data-stu-id="b495e-112">Attributes</span></span>  
  
|<span data-ttu-id="b495e-113">特性</span><span class="sxs-lookup"><span data-stu-id="b495e-113">Attribute</span></span>|<span data-ttu-id="b495e-114">描述</span><span class="sxs-lookup"><span data-stu-id="b495e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b495e-115">Lifetime — 生存期</span><span class="sxs-lookup"><span data-stu-id="b495e-115">lifetime</span></span>|<span data-ttu-id="b495e-116">指定的会话令牌的生存期。</span><span class="sxs-lookup"><span data-stu-id="b495e-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b495e-117">子元素</span><span class="sxs-lookup"><span data-stu-id="b495e-117">Child Elements</span></span>  
 <span data-ttu-id="b495e-118">无</span><span class="sxs-lookup"><span data-stu-id="b495e-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b495e-119">父元素</span><span class="sxs-lookup"><span data-stu-id="b495e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b495e-120">元素</span><span class="sxs-lookup"><span data-stu-id="b495e-120">Element</span></span>|<span data-ttu-id="b495e-121">描述</span><span class="sxs-lookup"><span data-stu-id="b495e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b495e-122">\<add></span><span class="sxs-lookup"><span data-stu-id="b495e-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="b495e-123">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="b495e-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b495e-124">示例</span><span class="sxs-lookup"><span data-stu-id="b495e-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```

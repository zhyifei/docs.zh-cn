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
ms.openlocfilehash: 8b729f588d2195992b231661f7bb718240141fdd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltsessiontokenrequirementgt"></a><span data-ttu-id="45038-102">&lt;sessionTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="45038-102">&lt;sessionTokenRequirement&gt;</span></span>
<span data-ttu-id="45038-103">提供有关配置<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="45038-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="45038-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="45038-104">\<system.identityModel></span></span>  
<span data-ttu-id="45038-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="45038-105">\<identityConfiguration></span></span>  
<span data-ttu-id="45038-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="45038-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="45038-107">\<add></span><span class="sxs-lookup"><span data-stu-id="45038-107">\<add></span></span>  
<span data-ttu-id="45038-108">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="45038-108">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45038-109">语法</span><span class="sxs-lookup"><span data-stu-id="45038-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45038-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="45038-110">Attributes and Elements</span></span>  
 <span data-ttu-id="45038-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="45038-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45038-112">特性</span><span class="sxs-lookup"><span data-stu-id="45038-112">Attributes</span></span>  
  
|<span data-ttu-id="45038-113">特性</span><span class="sxs-lookup"><span data-stu-id="45038-113">Attribute</span></span>|<span data-ttu-id="45038-114">描述</span><span class="sxs-lookup"><span data-stu-id="45038-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="45038-115">Lifetime — 生存期</span><span class="sxs-lookup"><span data-stu-id="45038-115">lifetime</span></span>|<span data-ttu-id="45038-116">指定的会话令牌的生存期。</span><span class="sxs-lookup"><span data-stu-id="45038-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="45038-117">子元素</span><span class="sxs-lookup"><span data-stu-id="45038-117">Child Elements</span></span>  
 <span data-ttu-id="45038-118">无</span><span class="sxs-lookup"><span data-stu-id="45038-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="45038-119">父元素</span><span class="sxs-lookup"><span data-stu-id="45038-119">Parent Elements</span></span>  
  
|<span data-ttu-id="45038-120">元素</span><span class="sxs-lookup"><span data-stu-id="45038-120">Element</span></span>|<span data-ttu-id="45038-121">说明</span><span class="sxs-lookup"><span data-stu-id="45038-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45038-122">\<add></span><span class="sxs-lookup"><span data-stu-id="45038-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="45038-123">将指定的安全令牌处理程序添加到令牌处理程序集合中。</span><span class="sxs-lookup"><span data-stu-id="45038-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="45038-124">示例</span><span class="sxs-lookup"><span data-stu-id="45038-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```

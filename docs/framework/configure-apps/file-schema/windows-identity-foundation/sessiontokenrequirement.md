---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 254d34149892abeaf31b9227f7567eb0a66ec0b6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943666"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="2e38a-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="2e38a-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="2e38a-102">提供<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>类或派生类的配置。</span><span class="sxs-lookup"><span data-stu-id="2e38a-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="2e38a-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="2e38a-103">\<system.identityModel></span></span>  
<span data-ttu-id="2e38a-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="2e38a-104">\<identityConfiguration></span></span>  
<span data-ttu-id="2e38a-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="2e38a-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="2e38a-106">\<add></span><span class="sxs-lookup"><span data-stu-id="2e38a-106">\<add></span></span>  
<span data-ttu-id="2e38a-107">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="2e38a-107">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e38a-108">语法</span><span class="sxs-lookup"><span data-stu-id="2e38a-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e38a-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2e38a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2e38a-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2e38a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e38a-111">特性</span><span class="sxs-lookup"><span data-stu-id="2e38a-111">Attributes</span></span>  
  
|<span data-ttu-id="2e38a-112">特性</span><span class="sxs-lookup"><span data-stu-id="2e38a-112">Attribute</span></span>|<span data-ttu-id="2e38a-113">描述</span><span class="sxs-lookup"><span data-stu-id="2e38a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e38a-114">Lifetime — 生存期</span><span class="sxs-lookup"><span data-stu-id="2e38a-114">lifetime</span></span>|<span data-ttu-id="2e38a-115">指定会话令牌的生存期。</span><span class="sxs-lookup"><span data-stu-id="2e38a-115">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e38a-116">子元素</span><span class="sxs-lookup"><span data-stu-id="2e38a-116">Child Elements</span></span>  
 <span data-ttu-id="2e38a-117">无</span><span class="sxs-lookup"><span data-stu-id="2e38a-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e38a-118">父元素</span><span class="sxs-lookup"><span data-stu-id="2e38a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="2e38a-119">元素</span><span class="sxs-lookup"><span data-stu-id="2e38a-119">Element</span></span>|<span data-ttu-id="2e38a-120">描述</span><span class="sxs-lookup"><span data-stu-id="2e38a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e38a-121">\<add></span><span class="sxs-lookup"><span data-stu-id="2e38a-121">\<add></span></span>](add.md)|<span data-ttu-id="2e38a-122">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="2e38a-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2e38a-123">示例</span><span class="sxs-lookup"><span data-stu-id="2e38a-123">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```

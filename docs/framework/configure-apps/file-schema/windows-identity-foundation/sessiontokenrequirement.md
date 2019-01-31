---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 0c575e02862884e8f7ecf062138c36fe731f8e19
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271897"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="7d7fe-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="7d7fe-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="7d7fe-102">提供配置<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>类或派生的类。</span><span class="sxs-lookup"><span data-stu-id="7d7fe-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="7d7fe-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="7d7fe-103">\<system.identityModel></span></span>  
<span data-ttu-id="7d7fe-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="7d7fe-104">\<identityConfiguration></span></span>  
<span data-ttu-id="7d7fe-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="7d7fe-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="7d7fe-106">\<add></span><span class="sxs-lookup"><span data-stu-id="7d7fe-106">\<add></span></span>  
<span data-ttu-id="7d7fe-107">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="7d7fe-107">\<sessionTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d7fe-108">语法</span><span class="sxs-lookup"><span data-stu-id="7d7fe-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d7fe-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7d7fe-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7d7fe-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7d7fe-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d7fe-111">特性</span><span class="sxs-lookup"><span data-stu-id="7d7fe-111">Attributes</span></span>  
  
|<span data-ttu-id="7d7fe-112">特性</span><span class="sxs-lookup"><span data-stu-id="7d7fe-112">Attribute</span></span>|<span data-ttu-id="7d7fe-113">描述</span><span class="sxs-lookup"><span data-stu-id="7d7fe-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d7fe-114">Lifetime — 生存期</span><span class="sxs-lookup"><span data-stu-id="7d7fe-114">lifetime</span></span>|<span data-ttu-id="7d7fe-115">指定的会话令牌的生存期。</span><span class="sxs-lookup"><span data-stu-id="7d7fe-115">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d7fe-116">子元素</span><span class="sxs-lookup"><span data-stu-id="7d7fe-116">Child Elements</span></span>  
 <span data-ttu-id="7d7fe-117">无</span><span class="sxs-lookup"><span data-stu-id="7d7fe-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d7fe-118">父元素</span><span class="sxs-lookup"><span data-stu-id="7d7fe-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7d7fe-119">元素</span><span class="sxs-lookup"><span data-stu-id="7d7fe-119">Element</span></span>|<span data-ttu-id="7d7fe-120">描述</span><span class="sxs-lookup"><span data-stu-id="7d7fe-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d7fe-121">\<add></span><span class="sxs-lookup"><span data-stu-id="7d7fe-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="7d7fe-122">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="7d7fe-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7d7fe-123">示例</span><span class="sxs-lookup"><span data-stu-id="7d7fe-123">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```

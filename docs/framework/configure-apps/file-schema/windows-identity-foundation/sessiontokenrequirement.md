---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 968c48df9e92a1dfbfb6e248b06cf4f97cece8b4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251815"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="fa4da-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="fa4da-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="fa4da-102">提供<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>类或派生类的配置。</span><span class="sxs-lookup"><span data-stu-id="fa4da-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="fa4da-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa4da-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fa4da-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="fa4da-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="fa4da-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="fa4da-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="fa4da-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="fa4da-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="fa4da-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<添加 >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="fa4da-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="fa4da-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<sessionTokenRequirement >**</span><span class="sxs-lookup"><span data-stu-id="fa4da-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa4da-109">语法</span><span class="sxs-lookup"><span data-stu-id="fa4da-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa4da-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fa4da-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fa4da-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fa4da-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa4da-112">特性</span><span class="sxs-lookup"><span data-stu-id="fa4da-112">Attributes</span></span>  
  
|<span data-ttu-id="fa4da-113">特性</span><span class="sxs-lookup"><span data-stu-id="fa4da-113">Attribute</span></span>|<span data-ttu-id="fa4da-114">描述</span><span class="sxs-lookup"><span data-stu-id="fa4da-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa4da-115">Lifetime — 生存期</span><span class="sxs-lookup"><span data-stu-id="fa4da-115">lifetime</span></span>|<span data-ttu-id="fa4da-116">指定会话令牌的生存期。</span><span class="sxs-lookup"><span data-stu-id="fa4da-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa4da-117">子元素</span><span class="sxs-lookup"><span data-stu-id="fa4da-117">Child Elements</span></span>  
 <span data-ttu-id="fa4da-118">无</span><span class="sxs-lookup"><span data-stu-id="fa4da-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa4da-119">父元素</span><span class="sxs-lookup"><span data-stu-id="fa4da-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fa4da-120">元素</span><span class="sxs-lookup"><span data-stu-id="fa4da-120">Element</span></span>|<span data-ttu-id="fa4da-121">描述</span><span class="sxs-lookup"><span data-stu-id="fa4da-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa4da-122">\<add></span><span class="sxs-lookup"><span data-stu-id="fa4da-122">\<add></span></span>](add.md)|<span data-ttu-id="fa4da-123">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="fa4da-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fa4da-124">示例</span><span class="sxs-lookup"><span data-stu-id="fa4da-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```

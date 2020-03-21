---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: ade55a5b26826633faf2e7ef7598a4071d613bbc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152536"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="c8885-101">\<会话令牌要求></span><span class="sxs-lookup"><span data-stu-id="c8885-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="c8885-102">提供类或派生<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>类的配置。</span><span class="sxs-lookup"><span data-stu-id="c8885-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="c8885-103">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8885-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c8885-104">&nbsp;&nbsp;[**\<系统.身份模型>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="c8885-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="c8885-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份配置>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c8885-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="c8885-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<安全令牌处理程序>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="c8885-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="c8885-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<添加>**](add.md)</span><span class="sxs-lookup"><span data-stu-id="c8885-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="c8885-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<会话令牌要求>**</span><span class="sxs-lookup"><span data-stu-id="c8885-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8885-109">语法</span><span class="sxs-lookup"><span data-stu-id="c8885-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8885-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c8885-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c8885-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c8885-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8885-112">属性</span><span class="sxs-lookup"><span data-stu-id="c8885-112">Attributes</span></span>  
  
|<span data-ttu-id="c8885-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="c8885-113">Attribute</span></span>|<span data-ttu-id="c8885-114">说明</span><span class="sxs-lookup"><span data-stu-id="c8885-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8885-115">lifetime</span><span class="sxs-lookup"><span data-stu-id="c8885-115">lifetime</span></span>|<span data-ttu-id="c8885-116">指定会话令牌的生存期。</span><span class="sxs-lookup"><span data-stu-id="c8885-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8885-117">子元素</span><span class="sxs-lookup"><span data-stu-id="c8885-117">Child Elements</span></span>  
 <span data-ttu-id="c8885-118">无</span><span class="sxs-lookup"><span data-stu-id="c8885-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8885-119">父元素</span><span class="sxs-lookup"><span data-stu-id="c8885-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c8885-120">元素</span><span class="sxs-lookup"><span data-stu-id="c8885-120">Element</span></span>|<span data-ttu-id="c8885-121">说明</span><span class="sxs-lookup"><span data-stu-id="c8885-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8885-122">\<添加></span><span class="sxs-lookup"><span data-stu-id="c8885-122">\<add></span></span>](add.md)|<span data-ttu-id="c8885-123">将指定的安全令牌处理程序添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="c8885-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c8885-124">示例</span><span class="sxs-lookup"><span data-stu-id="c8885-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```

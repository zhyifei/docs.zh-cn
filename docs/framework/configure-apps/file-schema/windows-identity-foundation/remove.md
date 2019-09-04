---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: cfdfbb3aabde253ad17b221801b20c1ac9a45c2d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251927"
---
# <a name="remove"></a><span data-ttu-id="347e4-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="347e4-101">\<remove></span></span>
<span data-ttu-id="347e4-102">从标记处理程序集合中删除指定的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="347e4-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
<span data-ttu-id="347e4-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="347e4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="347e4-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="347e4-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="347e4-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="347e4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="347e4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="347e4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="347e4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<删除 >**</span><span class="sxs-lookup"><span data-stu-id="347e4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="347e4-108">语法</span><span class="sxs-lookup"><span data-stu-id="347e4-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <remove type=xs:string >  
      </remove>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="347e4-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="347e4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="347e4-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="347e4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="347e4-111">特性</span><span class="sxs-lookup"><span data-stu-id="347e4-111">Attributes</span></span>  
  
|<span data-ttu-id="347e4-112">特性</span><span class="sxs-lookup"><span data-stu-id="347e4-112">Attribute</span></span>|<span data-ttu-id="347e4-113">描述</span><span class="sxs-lookup"><span data-stu-id="347e4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="347e4-114">type</span><span class="sxs-lookup"><span data-stu-id="347e4-114">type</span></span>|<span data-ttu-id="347e4-115">要移除的令牌处理程序的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="347e4-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="347e4-116">有关如何指定`type`属性的详细信息，请参阅[自定义类型引用](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)。</span><span class="sxs-lookup"><span data-stu-id="347e4-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="347e4-117">必需。</span><span class="sxs-lookup"><span data-stu-id="347e4-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="347e4-118">子元素</span><span class="sxs-lookup"><span data-stu-id="347e4-118">Child Elements</span></span>  
 <span data-ttu-id="347e4-119">无</span><span class="sxs-lookup"><span data-stu-id="347e4-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="347e4-120">父元素</span><span class="sxs-lookup"><span data-stu-id="347e4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="347e4-121">元素</span><span class="sxs-lookup"><span data-stu-id="347e4-121">Element</span></span>|<span data-ttu-id="347e4-122">描述</span><span class="sxs-lookup"><span data-stu-id="347e4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="347e4-123">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="347e4-123">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="347e4-124">指定注册到终结点的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="347e4-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="347e4-125">示例</span><span class="sxs-lookup"><span data-stu-id="347e4-125">Example</span></span>  
 <span data-ttu-id="347e4-126">下面的 XML 演示如何使用`<add>`和`<remove>`元素将默认会话标记处理程序替换为自定义会话标记处理程序。</span><span class="sxs-lookup"><span data-stu-id="347e4-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="347e4-127">XML 是从`ClaimsAwareWebFarm`示例获取的。</span><span class="sxs-lookup"><span data-stu-id="347e4-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

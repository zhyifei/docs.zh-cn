---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 11aeed0277fc13cbd9a65232311bd575a4a81ff7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942573"
---
# <a name="remove"></a><span data-ttu-id="e3923-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="e3923-101">\<remove></span></span>
<span data-ttu-id="e3923-102">从标记处理程序集合中删除指定的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3923-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="e3923-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="e3923-103">\<system.identityModel></span></span>  
<span data-ttu-id="e3923-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e3923-104">\<identityConfiguration></span></span>  
<span data-ttu-id="e3923-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="e3923-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e3923-106">\<remove></span><span class="sxs-lookup"><span data-stu-id="e3923-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3923-107">语法</span><span class="sxs-lookup"><span data-stu-id="e3923-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3923-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e3923-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e3923-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e3923-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3923-110">特性</span><span class="sxs-lookup"><span data-stu-id="e3923-110">Attributes</span></span>  
  
|<span data-ttu-id="e3923-111">特性</span><span class="sxs-lookup"><span data-stu-id="e3923-111">Attribute</span></span>|<span data-ttu-id="e3923-112">描述</span><span class="sxs-lookup"><span data-stu-id="e3923-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e3923-113">type</span><span class="sxs-lookup"><span data-stu-id="e3923-113">type</span></span>|<span data-ttu-id="e3923-114">要移除的令牌处理程序的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="e3923-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="e3923-115">有关如何指定`type`属性的详细信息, 请参阅[自定义类型引用](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)。</span><span class="sxs-lookup"><span data-stu-id="e3923-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="e3923-116">必需。</span><span class="sxs-lookup"><span data-stu-id="e3923-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e3923-117">子元素</span><span class="sxs-lookup"><span data-stu-id="e3923-117">Child Elements</span></span>  
 <span data-ttu-id="e3923-118">无</span><span class="sxs-lookup"><span data-stu-id="e3923-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e3923-119">父元素</span><span class="sxs-lookup"><span data-stu-id="e3923-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e3923-120">元素</span><span class="sxs-lookup"><span data-stu-id="e3923-120">Element</span></span>|<span data-ttu-id="e3923-121">描述</span><span class="sxs-lookup"><span data-stu-id="e3923-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3923-122">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="e3923-122">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="e3923-123">指定注册到终结点的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="e3923-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e3923-124">示例</span><span class="sxs-lookup"><span data-stu-id="e3923-124">Example</span></span>  
 <span data-ttu-id="e3923-125">下面的 XML 演示如何使用`<add>`和`<remove>`元素将默认会话标记处理程序替换为自定义会话标记处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3923-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="e3923-126">XML 是从`ClaimsAwareWebFarm`示例获取的。</span><span class="sxs-lookup"><span data-stu-id="e3923-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

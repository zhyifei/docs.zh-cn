---
title: '&lt;remove&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: fb62bbe8b52032708dddd62dd895e61ba8c1c5e9
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="ltremovegt"></a><span data-ttu-id="72fe6-102">&lt;remove&gt;</span><span class="sxs-lookup"><span data-stu-id="72fe6-102">&lt;remove&gt;</span></span>
<span data-ttu-id="72fe6-103">从标记处理程序集合中移除指定的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="72fe6-103">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="72fe6-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="72fe6-104">\<system.identityModel></span></span>  
<span data-ttu-id="72fe6-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="72fe6-105">\<identityConfiguration></span></span>  
<span data-ttu-id="72fe6-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="72fe6-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="72fe6-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="72fe6-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72fe6-108">语法</span><span class="sxs-lookup"><span data-stu-id="72fe6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72fe6-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="72fe6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="72fe6-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="72fe6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72fe6-111">特性</span><span class="sxs-lookup"><span data-stu-id="72fe6-111">Attributes</span></span>  
  
|<span data-ttu-id="72fe6-112">特性</span><span class="sxs-lookup"><span data-stu-id="72fe6-112">Attribute</span></span>|<span data-ttu-id="72fe6-113">描述</span><span class="sxs-lookup"><span data-stu-id="72fe6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="72fe6-114">类型</span><span class="sxs-lookup"><span data-stu-id="72fe6-114">type</span></span>|<span data-ttu-id="72fe6-115">要删除的令牌处理程序的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="72fe6-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="72fe6-116">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24)。</span><span class="sxs-lookup"><span data-stu-id="72fe6-116">For more information about how to specify the `type` attribute, see [Custom Type References](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span> <span data-ttu-id="72fe6-117">必须的。</span><span class="sxs-lookup"><span data-stu-id="72fe6-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72fe6-118">子元素</span><span class="sxs-lookup"><span data-stu-id="72fe6-118">Child Elements</span></span>  
 <span data-ttu-id="72fe6-119">无</span><span class="sxs-lookup"><span data-stu-id="72fe6-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72fe6-120">父元素</span><span class="sxs-lookup"><span data-stu-id="72fe6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="72fe6-121">元素</span><span class="sxs-lookup"><span data-stu-id="72fe6-121">Element</span></span>|<span data-ttu-id="72fe6-122">描述</span><span class="sxs-lookup"><span data-stu-id="72fe6-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72fe6-123">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="72fe6-123">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="72fe6-124">指定与终结点注册的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="72fe6-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="72fe6-125">示例</span><span class="sxs-lookup"><span data-stu-id="72fe6-125">Example</span></span>  
 <span data-ttu-id="72fe6-126">下面的 XML 演示如何使用`<add>`和`<remove>`元素使用的自定义会话令牌处理程序替换默认会话令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="72fe6-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="72fe6-127">XML 取自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="72fe6-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

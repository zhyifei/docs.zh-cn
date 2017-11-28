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
ms.openlocfilehash: 0c8fd5a9a5c4d6007ff0f67132b97b0aa5d98256
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltremovegt"></a><span data-ttu-id="02e65-102">&lt;remove&gt;</span><span class="sxs-lookup"><span data-stu-id="02e65-102">&lt;remove&gt;</span></span>
<span data-ttu-id="02e65-103">从标记处理程序集合中移除指定的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="02e65-103">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="02e65-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="02e65-104">\<system.identityModel></span></span>  
<span data-ttu-id="02e65-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="02e65-105">\<identityConfiguration></span></span>  
<span data-ttu-id="02e65-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="02e65-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="02e65-107">\<删除 ></span><span class="sxs-lookup"><span data-stu-id="02e65-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02e65-108">语法</span><span class="sxs-lookup"><span data-stu-id="02e65-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02e65-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="02e65-109">Attributes and Elements</span></span>  
 <span data-ttu-id="02e65-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="02e65-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02e65-111">特性</span><span class="sxs-lookup"><span data-stu-id="02e65-111">Attributes</span></span>  
  
|<span data-ttu-id="02e65-112">特性</span><span class="sxs-lookup"><span data-stu-id="02e65-112">Attribute</span></span>|<span data-ttu-id="02e65-113">描述</span><span class="sxs-lookup"><span data-stu-id="02e65-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02e65-114">类型</span><span class="sxs-lookup"><span data-stu-id="02e65-114">type</span></span>|<span data-ttu-id="02e65-115">要删除的令牌处理程序的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="02e65-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="02e65-116">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](http://msdn.microsoft.com/en-us/7286d2e3-c63d-49fd-abdc-ce2705f22c24)。</span><span class="sxs-lookup"><span data-stu-id="02e65-116">For more information about how to specify the `type` attribute, see [Custom Type References](http://msdn.microsoft.com/en-us/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span> <span data-ttu-id="02e65-117">必需。</span><span class="sxs-lookup"><span data-stu-id="02e65-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02e65-118">子元素</span><span class="sxs-lookup"><span data-stu-id="02e65-118">Child Elements</span></span>  
 <span data-ttu-id="02e65-119">无</span><span class="sxs-lookup"><span data-stu-id="02e65-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02e65-120">父元素</span><span class="sxs-lookup"><span data-stu-id="02e65-120">Parent Elements</span></span>  
  
|<span data-ttu-id="02e65-121">元素</span><span class="sxs-lookup"><span data-stu-id="02e65-121">Element</span></span>|<span data-ttu-id="02e65-122">描述</span><span class="sxs-lookup"><span data-stu-id="02e65-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02e65-123">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="02e65-123">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="02e65-124">指定与终结点注册的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="02e65-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="02e65-125">示例</span><span class="sxs-lookup"><span data-stu-id="02e65-125">Example</span></span>  
 <span data-ttu-id="02e65-126">下面的 XML 演示如何使用`<add>`和`<remove>`元素使用的自定义会话令牌处理程序替换默认会话令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="02e65-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="02e65-127">XML 取自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="02e65-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

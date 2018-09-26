---
title: '&lt;remove&gt;'
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 410fef1a43f9202d56c4957b1162c53ee056ae3f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47198717"
---
# <a name="ltremovegt"></a><span data-ttu-id="b03c6-102">&lt;remove&gt;</span><span class="sxs-lookup"><span data-stu-id="b03c6-102">&lt;remove&gt;</span></span>
<span data-ttu-id="b03c6-103">从令牌处理程序集合中移除指定的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="b03c6-103">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="b03c6-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b03c6-104">\<system.identityModel></span></span>  
<span data-ttu-id="b03c6-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b03c6-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b03c6-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b03c6-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b03c6-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="b03c6-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b03c6-108">语法</span><span class="sxs-lookup"><span data-stu-id="b03c6-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b03c6-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b03c6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b03c6-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b03c6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b03c6-111">特性</span><span class="sxs-lookup"><span data-stu-id="b03c6-111">Attributes</span></span>  
  
|<span data-ttu-id="b03c6-112">特性</span><span class="sxs-lookup"><span data-stu-id="b03c6-112">Attribute</span></span>|<span data-ttu-id="b03c6-113">描述</span><span class="sxs-lookup"><span data-stu-id="b03c6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b03c6-114">类型</span><span class="sxs-lookup"><span data-stu-id="b03c6-114">type</span></span>|<span data-ttu-id="b03c6-115">要删除的令牌处理程序的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="b03c6-115">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="b03c6-116">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24)。</span><span class="sxs-lookup"><span data-stu-id="b03c6-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span> <span data-ttu-id="b03c6-117">必须的。</span><span class="sxs-lookup"><span data-stu-id="b03c6-117">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b03c6-118">子元素</span><span class="sxs-lookup"><span data-stu-id="b03c6-118">Child Elements</span></span>  
 <span data-ttu-id="b03c6-119">无</span><span class="sxs-lookup"><span data-stu-id="b03c6-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b03c6-120">父元素</span><span class="sxs-lookup"><span data-stu-id="b03c6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b03c6-121">元素</span><span class="sxs-lookup"><span data-stu-id="b03c6-121">Element</span></span>|<span data-ttu-id="b03c6-122">描述</span><span class="sxs-lookup"><span data-stu-id="b03c6-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b03c6-123">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b03c6-123">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="b03c6-124">指定与该终结点注册的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="b03c6-124">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b03c6-125">示例</span><span class="sxs-lookup"><span data-stu-id="b03c6-125">Example</span></span>  
 <span data-ttu-id="b03c6-126">下面的 XML 演示如何使用`<add>`和`<remove>`元素使用的自定义会话令牌处理程序替换默认会话标记处理程序。</span><span class="sxs-lookup"><span data-stu-id="b03c6-126">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="b03c6-127">XML 来自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="b03c6-127">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

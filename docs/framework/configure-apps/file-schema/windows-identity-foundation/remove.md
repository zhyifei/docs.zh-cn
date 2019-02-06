---
title: <remove>
ms.date: 03/30/2017
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
author: BrucePerlerMS
ms.openlocfilehash: 17c4d4289cf90b66d52986c054d4807ecff2b3d8
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758412"
---
# <a name="remove"></a><span data-ttu-id="a30fd-101">\<remove></span><span class="sxs-lookup"><span data-stu-id="a30fd-101">\<remove></span></span>
<span data-ttu-id="a30fd-102">从令牌处理程序集合中移除指定的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="a30fd-102">Removes the specified security token handler from the token handler collection.</span></span>  
  
 <span data-ttu-id="a30fd-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="a30fd-103">\<system.identityModel></span></span>  
<span data-ttu-id="a30fd-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a30fd-104">\<identityConfiguration></span></span>  
<span data-ttu-id="a30fd-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="a30fd-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="a30fd-106">\<remove></span><span class="sxs-lookup"><span data-stu-id="a30fd-106">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a30fd-107">语法</span><span class="sxs-lookup"><span data-stu-id="a30fd-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a30fd-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a30fd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a30fd-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a30fd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a30fd-110">特性</span><span class="sxs-lookup"><span data-stu-id="a30fd-110">Attributes</span></span>  
  
|<span data-ttu-id="a30fd-111">特性</span><span class="sxs-lookup"><span data-stu-id="a30fd-111">Attribute</span></span>|<span data-ttu-id="a30fd-112">描述</span><span class="sxs-lookup"><span data-stu-id="a30fd-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a30fd-113">类型</span><span class="sxs-lookup"><span data-stu-id="a30fd-113">type</span></span>|<span data-ttu-id="a30fd-114">要删除的令牌处理程序的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="a30fd-114">The CLR type name of the token handler to be removed.</span></span> <span data-ttu-id="a30fd-115">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references)。</span><span class="sxs-lookup"><span data-stu-id="a30fd-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span> <span data-ttu-id="a30fd-116">必需。</span><span class="sxs-lookup"><span data-stu-id="a30fd-116">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a30fd-117">子元素</span><span class="sxs-lookup"><span data-stu-id="a30fd-117">Child Elements</span></span>  
 <span data-ttu-id="a30fd-118">无</span><span class="sxs-lookup"><span data-stu-id="a30fd-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a30fd-119">父元素</span><span class="sxs-lookup"><span data-stu-id="a30fd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a30fd-120">元素</span><span class="sxs-lookup"><span data-stu-id="a30fd-120">Element</span></span>|<span data-ttu-id="a30fd-121">描述</span><span class="sxs-lookup"><span data-stu-id="a30fd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a30fd-122">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="a30fd-122">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="a30fd-123">指定与该终结点注册的安全令牌处理程序的集合。</span><span class="sxs-lookup"><span data-stu-id="a30fd-123">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a30fd-124">示例</span><span class="sxs-lookup"><span data-stu-id="a30fd-124">Example</span></span>  
 <span data-ttu-id="a30fd-125">下面的 XML 演示如何使用`<add>`和`<remove>`元素使用的自定义会话令牌处理程序替换默认会话标记处理程序。</span><span class="sxs-lookup"><span data-stu-id="a30fd-125">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="a30fd-126">XML 来自`ClaimsAwareWebFarm`示例。</span><span class="sxs-lookup"><span data-stu-id="a30fd-126">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```

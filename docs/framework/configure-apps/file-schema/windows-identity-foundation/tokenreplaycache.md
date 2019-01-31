---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: dfa6c0d84582d55595f00f149adfdcaa9d554d6b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271943"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="f1464-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="f1464-101">\<tokenReplayCache></span></span>
<span data-ttu-id="f1464-102">使用的服务或安全令牌处理程序集合注册的标记重播缓存。</span><span class="sxs-lookup"><span data-stu-id="f1464-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="f1464-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="f1464-103">\<system.identityModel></span></span>  
<span data-ttu-id="f1464-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="f1464-104">\<identityConfiguration></span></span>  
<span data-ttu-id="f1464-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="f1464-105">\<caches></span></span>  
<span data-ttu-id="f1464-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="f1464-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1464-107">语法</span><span class="sxs-lookup"><span data-stu-id="f1464-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1464-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f1464-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f1464-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f1464-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1464-110">特性</span><span class="sxs-lookup"><span data-stu-id="f1464-110">Attributes</span></span>  
  
|<span data-ttu-id="f1464-111">特性</span><span class="sxs-lookup"><span data-stu-id="f1464-111">Attribute</span></span>|<span data-ttu-id="f1464-112">描述</span><span class="sxs-lookup"><span data-stu-id="f1464-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1464-113">类型</span><span class="sxs-lookup"><span data-stu-id="f1464-113">type</span></span>|<span data-ttu-id="f1464-114">从派生的类型的<xref:System.IdentityModel.Tokens.TokenReplayCache>类。</span><span class="sxs-lookup"><span data-stu-id="f1464-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="f1464-115">详细了解如何指定自定义`type`，请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="f1464-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="f1464-116">子元素</span><span class="sxs-lookup"><span data-stu-id="f1464-116">Child Elements</span></span>  
 <span data-ttu-id="f1464-117">无</span><span class="sxs-lookup"><span data-stu-id="f1464-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f1464-118">父元素</span><span class="sxs-lookup"><span data-stu-id="f1464-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f1464-119">元素</span><span class="sxs-lookup"><span data-stu-id="f1464-119">Element</span></span>|<span data-ttu-id="f1464-120">描述</span><span class="sxs-lookup"><span data-stu-id="f1464-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1464-121">\<caches></span><span class="sxs-lookup"><span data-stu-id="f1464-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="f1464-122">注册服务或安全令牌处理程序集合使用的缓存。</span><span class="sxs-lookup"><span data-stu-id="f1464-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1464-123">备注</span><span class="sxs-lookup"><span data-stu-id="f1464-123">Remarks</span></span>  
 <span data-ttu-id="f1464-124">令牌重放缓存用于检测重播的标记。</span><span class="sxs-lookup"><span data-stu-id="f1464-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="f1464-125">通过启用令牌重放检测[ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)元素，它还指定令牌的最大到期时间。</span><span class="sxs-lookup"><span data-stu-id="f1464-125">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1464-126">示例</span><span class="sxs-lookup"><span data-stu-id="f1464-126">Example</span></span>  
 <span data-ttu-id="f1464-127">以下 XML 显示了用于检测重播的标记的自定义缓存配置。</span><span class="sxs-lookup"><span data-stu-id="f1464-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1464-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1464-128">See also</span></span>
- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="f1464-129">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="f1464-129">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)

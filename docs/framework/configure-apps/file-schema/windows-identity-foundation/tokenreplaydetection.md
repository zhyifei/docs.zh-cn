---
title: '&lt;tokenReplayDetection&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: f95d200f74621a40d2987acf68bc554df8d17ab6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="lttokenreplaydetectiongt"></a><span data-ttu-id="a5792-102">&lt;tokenReplayDetection&gt;</span><span class="sxs-lookup"><span data-stu-id="a5792-102">&lt;tokenReplayDetection&gt;</span></span>
<span data-ttu-id="a5792-103">启用令牌重放检测并指定令牌的过期时间。</span><span class="sxs-lookup"><span data-stu-id="a5792-103">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="a5792-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="a5792-104">\<system.identityModel></span></span>  
<span data-ttu-id="a5792-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a5792-105">\<identityConfiguration></span></span>  
<span data-ttu-id="a5792-106">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="a5792-106">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5792-107">语法</span><span class="sxs-lookup"><span data-stu-id="a5792-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="a5792-108">类型</span><span class="sxs-lookup"><span data-stu-id="a5792-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5792-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a5792-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a5792-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a5792-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5792-111">特性</span><span class="sxs-lookup"><span data-stu-id="a5792-111">Attributes</span></span>  
  
|<span data-ttu-id="a5792-112">特性</span><span class="sxs-lookup"><span data-stu-id="a5792-112">Attribute</span></span>|<span data-ttu-id="a5792-113">描述</span><span class="sxs-lookup"><span data-stu-id="a5792-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a5792-114">enabled</span><span class="sxs-lookup"><span data-stu-id="a5792-114">enabled</span></span>|<span data-ttu-id="a5792-115">一个值，指定是否启用令牌重放检测;"true"若要启用令牌重放检测。</span><span class="sxs-lookup"><span data-stu-id="a5792-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="a5792-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="a5792-116">expirationPeriod</span></span>|<span data-ttu-id="a5792-117">A <xref:System.TimeSpan> ，它指定的最大项被视为过期并从缓存中删除之前的时间量。</span><span class="sxs-lookup"><span data-stu-id="a5792-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="a5792-118">有关如何指定详细信息<xref:System.TimeSpan>值，请参阅[Timespan 值](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a5792-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5792-119">子元素</span><span class="sxs-lookup"><span data-stu-id="a5792-119">Child Elements</span></span>  
 <span data-ttu-id="a5792-120">无</span><span class="sxs-lookup"><span data-stu-id="a5792-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5792-121">父元素</span><span class="sxs-lookup"><span data-stu-id="a5792-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a5792-122">元素</span><span class="sxs-lookup"><span data-stu-id="a5792-122">Element</span></span>|<span data-ttu-id="a5792-123">描述</span><span class="sxs-lookup"><span data-stu-id="a5792-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5792-124">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a5792-124">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="a5792-125">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="a5792-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="a5792-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a5792-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="a5792-127">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="a5792-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5792-128">备注</span><span class="sxs-lookup"><span data-stu-id="a5792-128">Remarks</span></span>  
 <span data-ttu-id="a5792-129">A`<tokenReplayDetection>`可以在服务级别下指定元素`<identityConfiguration>`元素或下位于安全令牌处理程序集合级别`<securityTokenHandlerConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="a5792-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="a5792-130">令牌处理程序集合上的设置会覆盖在服务上指定。</span><span class="sxs-lookup"><span data-stu-id="a5792-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="a5792-131">指定的令牌重放缓存类型[ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)元素。</span><span class="sxs-lookup"><span data-stu-id="a5792-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>

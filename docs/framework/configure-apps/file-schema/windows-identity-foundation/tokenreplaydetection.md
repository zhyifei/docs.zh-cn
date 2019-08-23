---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 2e2159a73ca79fc362a8138eea95dbd173dafb11
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944294"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="3d7bd-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="3d7bd-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="3d7bd-102">启用令牌重播检测并指定令牌的过期时间。</span><span class="sxs-lookup"><span data-stu-id="3d7bd-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="3d7bd-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3d7bd-103">\<system.identityModel></span></span>  
<span data-ttu-id="3d7bd-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3d7bd-104">\<identityConfiguration></span></span>  
<span data-ttu-id="3d7bd-105">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="3d7bd-105">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d7bd-106">语法</span><span class="sxs-lookup"><span data-stu-id="3d7bd-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="3d7bd-107">类型</span><span class="sxs-lookup"><span data-stu-id="3d7bd-107">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d7bd-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3d7bd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3d7bd-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3d7bd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d7bd-110">特性</span><span class="sxs-lookup"><span data-stu-id="3d7bd-110">Attributes</span></span>  
  
|<span data-ttu-id="3d7bd-111">特性</span><span class="sxs-lookup"><span data-stu-id="3d7bd-111">Attribute</span></span>|<span data-ttu-id="3d7bd-112">描述</span><span class="sxs-lookup"><span data-stu-id="3d7bd-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3d7bd-113">enabled</span><span class="sxs-lookup"><span data-stu-id="3d7bd-113">enabled</span></span>|<span data-ttu-id="3d7bd-114">一个值, 该值指定是否启用令牌重放检测;"true" 表示启用令牌重播检测。</span><span class="sxs-lookup"><span data-stu-id="3d7bd-114">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="3d7bd-115">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="3d7bd-115">expirationPeriod</span></span>|<span data-ttu-id="3d7bd-116">一个<xref:System.TimeSpan> , 指定项目被视为过期并从缓存中删除之前的最大时间量。</span><span class="sxs-lookup"><span data-stu-id="3d7bd-116">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="3d7bd-117">有关如何指定<xref:System.TimeSpan>值的详细信息, 请参阅[Timespan 值](../windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="3d7bd-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d7bd-118">子元素</span><span class="sxs-lookup"><span data-stu-id="3d7bd-118">Child Elements</span></span>  
 <span data-ttu-id="3d7bd-119">无</span><span class="sxs-lookup"><span data-stu-id="3d7bd-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d7bd-120">父元素</span><span class="sxs-lookup"><span data-stu-id="3d7bd-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3d7bd-121">元素</span><span class="sxs-lookup"><span data-stu-id="3d7bd-121">Element</span></span>|<span data-ttu-id="3d7bd-122">描述</span><span class="sxs-lookup"><span data-stu-id="3d7bd-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d7bd-123">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3d7bd-123">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="3d7bd-124">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="3d7bd-124">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="3d7bd-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="3d7bd-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="3d7bd-126">为安全标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="3d7bd-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d7bd-127">备注</span><span class="sxs-lookup"><span data-stu-id="3d7bd-127">Remarks</span></span>  
 <span data-ttu-id="3d7bd-128">可以在元素`<identityConfiguration>`下的服务级别指定元素, 或在`<securityTokenHandlerConfiguration>`元素下的安全令牌处理程序集合级别指定元素。`<tokenReplayDetection>`</span><span class="sxs-lookup"><span data-stu-id="3d7bd-128">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="3d7bd-129">标记处理程序集合上的设置将重写服务上指定的设置。</span><span class="sxs-lookup"><span data-stu-id="3d7bd-129">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="3d7bd-130">令牌重播缓存的类型由[ \<tokenReplayCache >](tokenreplaycache.md)元素指定。</span><span class="sxs-lookup"><span data-stu-id="3d7bd-130">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>

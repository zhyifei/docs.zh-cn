---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a4454042e1d97fb3cc2d6f2735104dadda6e7b5a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251773"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="a450b-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="a450b-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="a450b-102">启用令牌重播检测并指定令牌的过期时间。</span><span class="sxs-lookup"><span data-stu-id="a450b-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
<span data-ttu-id="a450b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a450b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a450b-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="a450b-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="a450b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="a450b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="a450b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<tokenReplayDetection >**</span><span class="sxs-lookup"><span data-stu-id="a450b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a450b-107">语法</span><span class="sxs-lookup"><span data-stu-id="a450b-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="a450b-108">类型</span><span class="sxs-lookup"><span data-stu-id="a450b-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a450b-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a450b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a450b-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a450b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a450b-111">特性</span><span class="sxs-lookup"><span data-stu-id="a450b-111">Attributes</span></span>  
  
|<span data-ttu-id="a450b-112">特性</span><span class="sxs-lookup"><span data-stu-id="a450b-112">Attribute</span></span>|<span data-ttu-id="a450b-113">描述</span><span class="sxs-lookup"><span data-stu-id="a450b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a450b-114">enabled</span><span class="sxs-lookup"><span data-stu-id="a450b-114">enabled</span></span>|<span data-ttu-id="a450b-115">一个值，该值指定是否启用令牌重放检测;"true" 表示启用令牌重播检测。</span><span class="sxs-lookup"><span data-stu-id="a450b-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="a450b-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="a450b-116">expirationPeriod</span></span>|<span data-ttu-id="a450b-117">一个<xref:System.TimeSpan> ，指定项目被视为过期并从缓存中删除之前的最大时间量。</span><span class="sxs-lookup"><span data-stu-id="a450b-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="a450b-118">有关如何指定<xref:System.TimeSpan>值的详细信息，请参阅[Timespan 值](../windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a450b-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a450b-119">子元素</span><span class="sxs-lookup"><span data-stu-id="a450b-119">Child Elements</span></span>  
 <span data-ttu-id="a450b-120">无</span><span class="sxs-lookup"><span data-stu-id="a450b-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a450b-121">父元素</span><span class="sxs-lookup"><span data-stu-id="a450b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a450b-122">元素</span><span class="sxs-lookup"><span data-stu-id="a450b-122">Element</span></span>|<span data-ttu-id="a450b-123">描述</span><span class="sxs-lookup"><span data-stu-id="a450b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a450b-124">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a450b-124">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="a450b-125">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="a450b-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="a450b-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="a450b-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="a450b-127">为安全标记处理程序的集合提供配置。</span><span class="sxs-lookup"><span data-stu-id="a450b-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a450b-128">备注</span><span class="sxs-lookup"><span data-stu-id="a450b-128">Remarks</span></span>  
 <span data-ttu-id="a450b-129">可以在元素`<identityConfiguration>`下的服务级别指定元素，或在`<securityTokenHandlerConfiguration>`元素下的安全令牌处理程序集合级别指定元素。`<tokenReplayDetection>`</span><span class="sxs-lookup"><span data-stu-id="a450b-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="a450b-130">标记处理程序集合上的设置将重写服务上指定的设置。</span><span class="sxs-lookup"><span data-stu-id="a450b-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="a450b-131">令牌重播缓存的类型由[ \<tokenReplayCache >](tokenreplaycache.md)元素指定。</span><span class="sxs-lookup"><span data-stu-id="a450b-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>

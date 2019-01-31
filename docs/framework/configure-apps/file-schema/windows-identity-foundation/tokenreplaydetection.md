---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 4deeb1d84f2621adb7ff1b649a505138b6856ec1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283070"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="5beea-101">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="5beea-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="5beea-102">启用令牌重放检测并指定令牌的到期时间。</span><span class="sxs-lookup"><span data-stu-id="5beea-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="5beea-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="5beea-103">\<system.identityModel></span></span>  
<span data-ttu-id="5beea-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5beea-104">\<identityConfiguration></span></span>  
<span data-ttu-id="5beea-105">\<tokenReplayDetection></span><span class="sxs-lookup"><span data-stu-id="5beea-105">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5beea-106">语法</span><span class="sxs-lookup"><span data-stu-id="5beea-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="5beea-107">类型</span><span class="sxs-lookup"><span data-stu-id="5beea-107">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5beea-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5beea-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5beea-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5beea-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5beea-110">特性</span><span class="sxs-lookup"><span data-stu-id="5beea-110">Attributes</span></span>  
  
|<span data-ttu-id="5beea-111">特性</span><span class="sxs-lookup"><span data-stu-id="5beea-111">Attribute</span></span>|<span data-ttu-id="5beea-112">描述</span><span class="sxs-lookup"><span data-stu-id="5beea-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5beea-113">enabled</span><span class="sxs-lookup"><span data-stu-id="5beea-113">enabled</span></span>|<span data-ttu-id="5beea-114">一个值，指定是否启用令牌重放检测;"true"以启用令牌重放检测。</span><span class="sxs-lookup"><span data-stu-id="5beea-114">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="5beea-115">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="5beea-115">expirationPeriod</span></span>|<span data-ttu-id="5beea-116">一个<xref:System.TimeSpan>指定最大的前一个项目被认为过期并从缓存中删除的时间量。</span><span class="sxs-lookup"><span data-stu-id="5beea-116">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="5beea-117">有关如何指定详细信息<xref:System.TimeSpan>值，请参阅[Timespan 值](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5beea-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5beea-118">子元素</span><span class="sxs-lookup"><span data-stu-id="5beea-118">Child Elements</span></span>  
 <span data-ttu-id="5beea-119">无</span><span class="sxs-lookup"><span data-stu-id="5beea-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5beea-120">父元素</span><span class="sxs-lookup"><span data-stu-id="5beea-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5beea-121">元素</span><span class="sxs-lookup"><span data-stu-id="5beea-121">Element</span></span>|<span data-ttu-id="5beea-122">描述</span><span class="sxs-lookup"><span data-stu-id="5beea-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5beea-123">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5beea-123">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="5beea-124">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="5beea-124">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="5beea-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="5beea-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="5beea-126">提供配置集合的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="5beea-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5beea-127">备注</span><span class="sxs-lookup"><span data-stu-id="5beea-127">Remarks</span></span>  
 <span data-ttu-id="5beea-128">一个`<tokenReplayDetection>`可以在服务级别下指定元素`<identityConfiguration>`元素下的安全令牌处理程序集合级别上或`<securityTokenHandlerConfiguration>`元素。</span><span class="sxs-lookup"><span data-stu-id="5beea-128">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="5beea-129">标记处理程序集合上的设置将覆盖在服务上指定的。</span><span class="sxs-lookup"><span data-stu-id="5beea-129">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="5beea-130">通过指定的标记重播缓存类型[ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)元素。</span><span class="sxs-lookup"><span data-stu-id="5beea-130">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>

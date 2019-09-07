---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 7c4d9ae29ca1e543217d444e05a661b48e2cbb62
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400066"
---
# <a name="persistenceprovider"></a><span data-ttu-id="91912-101">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="91912-101">\<persistenceProvider></span></span>
<span data-ttu-id="91912-102">指定要使用的持久性提供程序实现的类型以及用于持久性操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="91912-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
<span data-ttu-id="91912-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="91912-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="91912-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="91912-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="91912-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="91912-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="91912-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="91912-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="91912-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="91912-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="91912-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<persistenceProvider >**</span><span class="sxs-lookup"><span data-stu-id="91912-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91912-109">语法</span><span class="sxs-lookup"><span data-stu-id="91912-109">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91912-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="91912-110">Attributes and Elements</span></span>  
 <span data-ttu-id="91912-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="91912-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91912-112">特性</span><span class="sxs-lookup"><span data-stu-id="91912-112">Attributes</span></span>  
  
|<span data-ttu-id="91912-113">特性</span><span class="sxs-lookup"><span data-stu-id="91912-113">Attribute</span></span>|<span data-ttu-id="91912-114">描述</span><span class="sxs-lookup"><span data-stu-id="91912-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="91912-115">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="91912-115">persistenceOperationTimeout</span></span>|<span data-ttu-id="91912-116">一个 <xref:System.TimeSpan> 值，指定用于持久性操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="91912-116">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="91912-117">默认值为 "00:00:30"。</span><span class="sxs-lookup"><span data-stu-id="91912-117">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="91912-118">type</span><span class="sxs-lookup"><span data-stu-id="91912-118">type</span></span>|<span data-ttu-id="91912-119">一个字符串，指定要使用的永久性提供程序工厂的类型。</span><span class="sxs-lookup"><span data-stu-id="91912-119">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91912-120">子元素</span><span class="sxs-lookup"><span data-stu-id="91912-120">Child Elements</span></span>  
 <span data-ttu-id="91912-121">无。</span><span class="sxs-lookup"><span data-stu-id="91912-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91912-122">父元素</span><span class="sxs-lookup"><span data-stu-id="91912-122">Parent Elements</span></span>  
  
|<span data-ttu-id="91912-123">元素</span><span class="sxs-lookup"><span data-stu-id="91912-123">Element</span></span>|<span data-ttu-id="91912-124">描述</span><span class="sxs-lookup"><span data-stu-id="91912-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91912-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="91912-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="91912-126">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="91912-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91912-127">备注</span><span class="sxs-lookup"><span data-stu-id="91912-127">Remarks</span></span>  
 <span data-ttu-id="91912-128">此元素指定要用于序列化 WCF 服务的状态的永久性提供程序。</span><span class="sxs-lookup"><span data-stu-id="91912-128">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="91912-129">它应该与 `wsHttpContextBinding` 一起使用，后者在 HTTP 头中传递状态信息。</span><span class="sxs-lookup"><span data-stu-id="91912-129">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91912-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="91912-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>

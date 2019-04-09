---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: dc8dea0ddd1ea074c08952e3e2ebfef2d12f7183
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099282"
---
# <a name="persistenceprovider"></a><span data-ttu-id="240e2-101">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="240e2-101">\<persistenceProvider></span></span>
<span data-ttu-id="240e2-102">指定要使用的持久性提供程序实现的类型以及用于持久性操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="240e2-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="240e2-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="240e2-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="240e2-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="240e2-104">\<behaviors></span></span>  
<span data-ttu-id="240e2-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="240e2-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="240e2-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="240e2-106">\<behavior></span></span>  
<span data-ttu-id="240e2-107">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="240e2-107">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="240e2-108">语法</span><span class="sxs-lookup"><span data-stu-id="240e2-108">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="240e2-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="240e2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="240e2-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="240e2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="240e2-111">特性</span><span class="sxs-lookup"><span data-stu-id="240e2-111">Attributes</span></span>  
  
|<span data-ttu-id="240e2-112">特性</span><span class="sxs-lookup"><span data-stu-id="240e2-112">Attribute</span></span>|<span data-ttu-id="240e2-113">描述</span><span class="sxs-lookup"><span data-stu-id="240e2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="240e2-114">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="240e2-114">persistenceOperationTimeout</span></span>|<span data-ttu-id="240e2-115">一个 <xref:System.TimeSpan> 值，指定用于持久性操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="240e2-115">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="240e2-116">默认值是"00: 00:30"。</span><span class="sxs-lookup"><span data-stu-id="240e2-116">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="240e2-117">类型</span><span class="sxs-lookup"><span data-stu-id="240e2-117">type</span></span>|<span data-ttu-id="240e2-118">一个字符串，指定要使用的永久性提供程序工厂的类型。</span><span class="sxs-lookup"><span data-stu-id="240e2-118">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="240e2-119">子元素</span><span class="sxs-lookup"><span data-stu-id="240e2-119">Child Elements</span></span>  
 <span data-ttu-id="240e2-120">无。</span><span class="sxs-lookup"><span data-stu-id="240e2-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="240e2-121">父元素</span><span class="sxs-lookup"><span data-stu-id="240e2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="240e2-122">元素</span><span class="sxs-lookup"><span data-stu-id="240e2-122">Element</span></span>|<span data-ttu-id="240e2-123">描述</span><span class="sxs-lookup"><span data-stu-id="240e2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="240e2-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="240e2-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="240e2-125">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="240e2-125">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="240e2-126">备注</span><span class="sxs-lookup"><span data-stu-id="240e2-126">Remarks</span></span>  
 <span data-ttu-id="240e2-127">此元素指定要用于序列化 WCF 服务的状态的永久性提供程序。</span><span class="sxs-lookup"><span data-stu-id="240e2-127">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="240e2-128">它应该与 `wsHttpContextBinding` 一起使用，后者在 HTTP 头中传递状态信息。</span><span class="sxs-lookup"><span data-stu-id="240e2-128">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="240e2-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="240e2-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>

---
title: '&lt;callbackDebug&gt;'
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 5bd2356c3bb798e948341cb3c4ba504ac886ed44
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145076"
---
# <a name="ltcallbackdebuggt"></a><span data-ttu-id="44c9e-102">&lt;callbackDebug&gt;</span><span class="sxs-lookup"><span data-stu-id="44c9e-102">&lt;callbackDebug&gt;</span></span>
<span data-ttu-id="44c9e-103">指定服务调试 Windows Communication Foundation (WCF) 回调对象。</span><span class="sxs-lookup"><span data-stu-id="44c9e-103">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="44c9e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="44c9e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="44c9e-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="44c9e-105">\<behaviors></span></span>  
<span data-ttu-id="44c9e-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="44c9e-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="44c9e-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="44c9e-107">\<behavior></span></span>  
<span data-ttu-id="44c9e-108">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="44c9e-108">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44c9e-109">语法</span><span class="sxs-lookup"><span data-stu-id="44c9e-109">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="44c9e-110">类型</span><span class="sxs-lookup"><span data-stu-id="44c9e-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44c9e-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="44c9e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="44c9e-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="44c9e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44c9e-113">特性</span><span class="sxs-lookup"><span data-stu-id="44c9e-113">Attributes</span></span>  
  
|<span data-ttu-id="44c9e-114">特性</span><span class="sxs-lookup"><span data-stu-id="44c9e-114">Attribute</span></span>|<span data-ttu-id="44c9e-115">描述</span><span class="sxs-lookup"><span data-stu-id="44c9e-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="44c9e-116">一个值，指定客户端回调对象是否向服务返回 SOAP 错误中的托管异常信息。</span><span class="sxs-lookup"><span data-stu-id="44c9e-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="44c9e-117">如果以编程方式将此属性设置为 `true`，则可以将客户端回调对象中的托管异常信息回流到服务，以便进行调试。</span><span class="sxs-lookup"><span data-stu-id="44c9e-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="44c9e-118">注意：向客户端返回托管异常信息可能具有安全风险。</span><span class="sxs-lookup"><span data-stu-id="44c9e-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="44c9e-119">这是因为，异常详细信息公开了有关内部服务实现的信息，这些信息可能被未经授权的客户端使用。</span><span class="sxs-lookup"><span data-stu-id="44c9e-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44c9e-120">子元素</span><span class="sxs-lookup"><span data-stu-id="44c9e-120">Child Elements</span></span>  
 <span data-ttu-id="44c9e-121">无。</span><span class="sxs-lookup"><span data-stu-id="44c9e-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44c9e-122">父元素</span><span class="sxs-lookup"><span data-stu-id="44c9e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="44c9e-123">元素</span><span class="sxs-lookup"><span data-stu-id="44c9e-123">Element</span></span>|<span data-ttu-id="44c9e-124">描述</span><span class="sxs-lookup"><span data-stu-id="44c9e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44c9e-125">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="44c9e-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="44c9e-126">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="44c9e-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44c9e-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="44c9e-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>  
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>

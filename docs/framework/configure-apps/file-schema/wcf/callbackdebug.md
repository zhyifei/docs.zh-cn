---
title: '&lt;callbackDebug&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 93b89787795cb58644b79ae4795e7a036741e138
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltcallbackdebuggt"></a><span data-ttu-id="07fde-102">&lt;callbackDebug&gt;</span><span class="sxs-lookup"><span data-stu-id="07fde-102">&lt;callbackDebug&gt;</span></span>
<span data-ttu-id="07fde-103">指定 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 回调对象的服务调试。</span><span class="sxs-lookup"><span data-stu-id="07fde-103">Specifies service debugging for a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] callback object.</span></span>  
  
 <span data-ttu-id="07fde-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="07fde-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="07fde-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="07fde-105">\<behaviors></span></span>  
<span data-ttu-id="07fde-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="07fde-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="07fde-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="07fde-107">\<behavior></span></span>  
<span data-ttu-id="07fde-108">\<callbackDebug ></span><span class="sxs-lookup"><span data-stu-id="07fde-108">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07fde-109">语法</span><span class="sxs-lookup"><span data-stu-id="07fde-109">Syntax</span></span>  
  
```xml  
<callbackDebug  includeExceptionDetailInFaults="Boolean" />  
```  
  
## <a name="type"></a><span data-ttu-id="07fde-110">类型</span><span class="sxs-lookup"><span data-stu-id="07fde-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07fde-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="07fde-111">Attributes and Elements</span></span>  
 <span data-ttu-id="07fde-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="07fde-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07fde-113">特性</span><span class="sxs-lookup"><span data-stu-id="07fde-113">Attributes</span></span>  
  
|<span data-ttu-id="07fde-114">特性</span><span class="sxs-lookup"><span data-stu-id="07fde-114">Attribute</span></span>|<span data-ttu-id="07fde-115">描述</span><span class="sxs-lookup"><span data-stu-id="07fde-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="07fde-116">一个值，指定客户端回调对象是否向服务返回 SOAP 错误中的托管异常信息。</span><span class="sxs-lookup"><span data-stu-id="07fde-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="07fde-117">如果以编程方式将此属性设置为 `true`，则可以将客户端回调对象中的托管异常信息回流到服务，以便进行调试。</span><span class="sxs-lookup"><span data-stu-id="07fde-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="07fde-118">**注意：**返回托管的异常信息返回给客户端可能会带来安全风险。</span><span class="sxs-lookup"><span data-stu-id="07fde-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="07fde-119">这是因为，异常详细信息公开了有关内部服务实现的信息，这些信息可能被未经授权的客户端使用。</span><span class="sxs-lookup"><span data-stu-id="07fde-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07fde-120">子元素</span><span class="sxs-lookup"><span data-stu-id="07fde-120">Child Elements</span></span>  
 <span data-ttu-id="07fde-121">无。</span><span class="sxs-lookup"><span data-stu-id="07fde-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07fde-122">父元素</span><span class="sxs-lookup"><span data-stu-id="07fde-122">Parent Elements</span></span>  
  
|<span data-ttu-id="07fde-123">元素</span><span class="sxs-lookup"><span data-stu-id="07fde-123">Element</span></span>|<span data-ttu-id="07fde-124">描述</span><span class="sxs-lookup"><span data-stu-id="07fde-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07fde-125">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="07fde-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="07fde-126">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="07fde-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07fde-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07fde-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>  
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>

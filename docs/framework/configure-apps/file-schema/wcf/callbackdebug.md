---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 62ce1bc179c7215d4988e4c6bda08025c3d3e5de
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286307"
---
# <a name="callbackdebug"></a><span data-ttu-id="0dcda-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="0dcda-101">\<callbackDebug></span></span>
<span data-ttu-id="0dcda-102">指定服务调试 Windows Communication Foundation (WCF) 回调对象。</span><span class="sxs-lookup"><span data-stu-id="0dcda-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="0dcda-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0dcda-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0dcda-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0dcda-104">\<behaviors></span></span>  
<span data-ttu-id="0dcda-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="0dcda-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="0dcda-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0dcda-106">\<behavior></span></span>  
<span data-ttu-id="0dcda-107">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="0dcda-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dcda-108">语法</span><span class="sxs-lookup"><span data-stu-id="0dcda-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="0dcda-109">类型</span><span class="sxs-lookup"><span data-stu-id="0dcda-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0dcda-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0dcda-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0dcda-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0dcda-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0dcda-112">特性</span><span class="sxs-lookup"><span data-stu-id="0dcda-112">Attributes</span></span>  
  
|<span data-ttu-id="0dcda-113">特性</span><span class="sxs-lookup"><span data-stu-id="0dcda-113">Attribute</span></span>|<span data-ttu-id="0dcda-114">描述</span><span class="sxs-lookup"><span data-stu-id="0dcda-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="0dcda-115">一个值，指定客户端回调对象是否向服务返回 SOAP 错误中的托管异常信息。</span><span class="sxs-lookup"><span data-stu-id="0dcda-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="0dcda-116">如果以编程方式将此属性设置为 `true`，则可以将客户端回调对象中的托管异常信息回流到服务，以便进行调试。</span><span class="sxs-lookup"><span data-stu-id="0dcda-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="0dcda-117">注意：向客户端返回托管异常信息可能具有安全风险。</span><span class="sxs-lookup"><span data-stu-id="0dcda-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="0dcda-118">这是因为，异常详细信息公开了有关内部服务实现的信息，这些信息可能被未经授权的客户端使用。</span><span class="sxs-lookup"><span data-stu-id="0dcda-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0dcda-119">子元素</span><span class="sxs-lookup"><span data-stu-id="0dcda-119">Child Elements</span></span>  
 <span data-ttu-id="0dcda-120">无。</span><span class="sxs-lookup"><span data-stu-id="0dcda-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0dcda-121">父元素</span><span class="sxs-lookup"><span data-stu-id="0dcda-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0dcda-122">元素</span><span class="sxs-lookup"><span data-stu-id="0dcda-122">Element</span></span>|<span data-ttu-id="0dcda-123">描述</span><span class="sxs-lookup"><span data-stu-id="0dcda-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0dcda-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0dcda-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="0dcda-125">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="0dcda-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0dcda-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="0dcda-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>

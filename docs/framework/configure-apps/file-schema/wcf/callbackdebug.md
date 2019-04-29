---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: a1190eb1c015ba07488ff5a5952f2f5f1b10974c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704513"
---
# <a name="callbackdebug"></a><span data-ttu-id="69067-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="69067-101">\<callbackDebug></span></span>
<span data-ttu-id="69067-102">指定服务调试 Windows Communication Foundation (WCF) 回调对象。</span><span class="sxs-lookup"><span data-stu-id="69067-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
 <span data-ttu-id="69067-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="69067-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="69067-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="69067-104">\<behaviors></span></span>  
<span data-ttu-id="69067-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="69067-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="69067-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="69067-106">\<behavior></span></span>  
<span data-ttu-id="69067-107">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="69067-107">\<callbackDebug></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69067-108">语法</span><span class="sxs-lookup"><span data-stu-id="69067-108">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="69067-109">类型</span><span class="sxs-lookup"><span data-stu-id="69067-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69067-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="69067-110">Attributes and Elements</span></span>  
 <span data-ttu-id="69067-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="69067-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69067-112">特性</span><span class="sxs-lookup"><span data-stu-id="69067-112">Attributes</span></span>  
  
|<span data-ttu-id="69067-113">特性</span><span class="sxs-lookup"><span data-stu-id="69067-113">Attribute</span></span>|<span data-ttu-id="69067-114">描述</span><span class="sxs-lookup"><span data-stu-id="69067-114">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="69067-115">一个值，指定客户端回调对象是否向服务返回 SOAP 错误中的托管异常信息。</span><span class="sxs-lookup"><span data-stu-id="69067-115">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="69067-116">如果以编程方式将此属性设置为 `true`，则可以将客户端回调对象中的托管异常信息回流到服务，以便进行调试。</span><span class="sxs-lookup"><span data-stu-id="69067-116">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="69067-117">注意：向客户端返回托管异常信息可能具有安全风险。</span><span class="sxs-lookup"><span data-stu-id="69067-117">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="69067-118">这是因为，异常详细信息公开了有关内部服务实现的信息，这些信息可能被未经授权的客户端使用。</span><span class="sxs-lookup"><span data-stu-id="69067-118">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69067-119">子元素</span><span class="sxs-lookup"><span data-stu-id="69067-119">Child Elements</span></span>  
 <span data-ttu-id="69067-120">无。</span><span class="sxs-lookup"><span data-stu-id="69067-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69067-121">父元素</span><span class="sxs-lookup"><span data-stu-id="69067-121">Parent Elements</span></span>  
  
|<span data-ttu-id="69067-122">元素</span><span class="sxs-lookup"><span data-stu-id="69067-122">Element</span></span>|<span data-ttu-id="69067-123">描述</span><span class="sxs-lookup"><span data-stu-id="69067-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69067-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="69067-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="69067-125">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="69067-125">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69067-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="69067-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>

---
title: <callbackDebug>
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 92a8fa83b5cf5f429278ac8edc8439b627839aad
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400569"
---
# <a name="callbackdebug"></a><span data-ttu-id="0dc22-101">\<callbackDebug></span><span class="sxs-lookup"><span data-stu-id="0dc22-101">\<callbackDebug></span></span>
<span data-ttu-id="0dc22-102">指定 Windows Communication Foundation （WCF）回调对象的服务调试。</span><span class="sxs-lookup"><span data-stu-id="0dc22-102">Specifies service debugging for a Windows Communication Foundation (WCF) callback object.</span></span>  
  
<span data-ttu-id="0dc22-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0dc22-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0dc22-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0dc22-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0dc22-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0dc22-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="0dc22-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0dc22-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="0dc22-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0dc22-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="0dc22-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<callbackDebug >**</span><span class="sxs-lookup"><span data-stu-id="0dc22-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackDebug>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dc22-109">语法</span><span class="sxs-lookup"><span data-stu-id="0dc22-109">Syntax</span></span>  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a><span data-ttu-id="0dc22-110">类型</span><span class="sxs-lookup"><span data-stu-id="0dc22-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0dc22-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0dc22-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0dc22-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0dc22-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0dc22-113">特性</span><span class="sxs-lookup"><span data-stu-id="0dc22-113">Attributes</span></span>  
  
|<span data-ttu-id="0dc22-114">特性</span><span class="sxs-lookup"><span data-stu-id="0dc22-114">Attribute</span></span>|<span data-ttu-id="0dc22-115">描述</span><span class="sxs-lookup"><span data-stu-id="0dc22-115">Description</span></span>|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|<span data-ttu-id="0dc22-116">一个值，指定客户端回调对象是否向服务返回 SOAP 错误中的托管异常信息。</span><span class="sxs-lookup"><span data-stu-id="0dc22-116">A value that specifies whether client callback objects return managed exception information in SOAP faults back to the service.</span></span><br /><br /> <span data-ttu-id="0dc22-117">如果以编程方式将此属性设置为 `true`，则可以将客户端回调对象中的托管异常信息回流到服务，以便进行调试。</span><span class="sxs-lookup"><span data-stu-id="0dc22-117">If you set this attribute to `true` programmatically, you can enable the flow of managed exception information in a client callback object back to the service for debugging purposes.</span></span> <span data-ttu-id="0dc22-118">注意：向客户端返回托管异常信息可能具有安全风险。</span><span class="sxs-lookup"><span data-stu-id="0dc22-118">**Caution:**  Returning managed exception information to clients can be a security risk.</span></span> <span data-ttu-id="0dc22-119">这是因为，异常详细信息公开了有关内部服务实现的信息，这些信息可能被未经授权的客户端使用。</span><span class="sxs-lookup"><span data-stu-id="0dc22-119">This is because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0dc22-120">子元素</span><span class="sxs-lookup"><span data-stu-id="0dc22-120">Child Elements</span></span>  
 <span data-ttu-id="0dc22-121">无。</span><span class="sxs-lookup"><span data-stu-id="0dc22-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0dc22-122">父元素</span><span class="sxs-lookup"><span data-stu-id="0dc22-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0dc22-123">元素</span><span class="sxs-lookup"><span data-stu-id="0dc22-123">Element</span></span>|<span data-ttu-id="0dc22-124">描述</span><span class="sxs-lookup"><span data-stu-id="0dc22-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0dc22-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0dc22-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="0dc22-126">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="0dc22-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0dc22-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="0dc22-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>

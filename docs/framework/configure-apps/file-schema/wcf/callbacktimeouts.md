---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e1b40718638ded54e59743730159ea6e65a51a57
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398187"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="340a7-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="340a7-101">\<callbackTimeouts></span></span>
<span data-ttu-id="340a7-102">在双工回调协定方案中指定使事务从服务器流动到客户端时的超时值。</span><span class="sxs-lookup"><span data-stu-id="340a7-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
<span data-ttu-id="340a7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="340a7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="340a7-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="340a7-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="340a7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="340a7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="340a7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="340a7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="340a7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="340a7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="340a7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<callbackTimeOuts >**</span><span class="sxs-lookup"><span data-stu-id="340a7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<callbackTimeOuts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="340a7-109">语法</span><span class="sxs-lookup"><span data-stu-id="340a7-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="340a7-110">类型</span><span class="sxs-lookup"><span data-stu-id="340a7-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="340a7-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="340a7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="340a7-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="340a7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="340a7-113">特性</span><span class="sxs-lookup"><span data-stu-id="340a7-113">Attributes</span></span>  
  
|<span data-ttu-id="340a7-114">特性</span><span class="sxs-lookup"><span data-stu-id="340a7-114">Attribute</span></span>|<span data-ttu-id="340a7-115">描述</span><span class="sxs-lookup"><span data-stu-id="340a7-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="340a7-116">一个 <xref:System.TimeSpan> 值，指定时间间隔，事务必须在此期间完成，否则会自动终止。</span><span class="sxs-lookup"><span data-stu-id="340a7-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="340a7-117">默认值为 "00:00:00"。</span><span class="sxs-lookup"><span data-stu-id="340a7-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="340a7-118">子元素</span><span class="sxs-lookup"><span data-stu-id="340a7-118">Child Elements</span></span>  
 <span data-ttu-id="340a7-119">无。</span><span class="sxs-lookup"><span data-stu-id="340a7-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="340a7-120">父元素</span><span class="sxs-lookup"><span data-stu-id="340a7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="340a7-121">元素</span><span class="sxs-lookup"><span data-stu-id="340a7-121">Element</span></span>|<span data-ttu-id="340a7-122">描述</span><span class="sxs-lookup"><span data-stu-id="340a7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="340a7-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="340a7-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="340a7-124">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="340a7-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="340a7-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="340a7-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>

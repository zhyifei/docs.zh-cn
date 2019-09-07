---
title: <unrecognizedPolicyAssertion>
ms.date: 03/30/2017
ms.assetid: 043c3c8f-f263-4ac7-a1af-945d03413f0b
ms.openlocfilehash: 5a402ce3a4b793c6b50a3702b56d593b64d2f58d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399222"
---
# <a name="unrecognizedpolicyassertion"></a><span data-ttu-id="0017f-101">\<unrecognizedPolicyAssertion></span><span class="sxs-lookup"><span data-stu-id="0017f-101">\<unrecognizedPolicyAssertion></span></span>
<span data-ttu-id="0017f-102">表示用于指定策略断言的绑定元素。</span><span class="sxs-lookup"><span data-stu-id="0017f-102">Represents a binding element that specifies policy assertion.</span></span> <span data-ttu-id="0017f-103">此元素没有属性并且以空开关形式存在。</span><span class="sxs-lookup"><span data-stu-id="0017f-103">This element has no attribute and is present as an empty switch.</span></span>  
  
<span data-ttu-id="0017f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0017f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0017f-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0017f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0017f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="0017f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="0017f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="0017f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="0017f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="0017f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="0017f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<unrecognizedPolicyAssertion >**</span><span class="sxs-lookup"><span data-stu-id="0017f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<unrecognizedPolicyAssertion>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0017f-110">语法</span><span class="sxs-lookup"><span data-stu-id="0017f-110">Syntax</span></span>  
  
```xml  
<unrecognizedPolicyAssertion />
```  
  
## <a name="type"></a><span data-ttu-id="0017f-111">类型</span><span class="sxs-lookup"><span data-stu-id="0017f-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0017f-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0017f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0017f-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0017f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0017f-114">特性</span><span class="sxs-lookup"><span data-stu-id="0017f-114">Attributes</span></span>  
 <span data-ttu-id="0017f-115">无。</span><span class="sxs-lookup"><span data-stu-id="0017f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0017f-116">子元素</span><span class="sxs-lookup"><span data-stu-id="0017f-116">Child Elements</span></span>  
 <span data-ttu-id="0017f-117">无</span><span class="sxs-lookup"><span data-stu-id="0017f-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0017f-118">父元素</span><span class="sxs-lookup"><span data-stu-id="0017f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0017f-119">元素</span><span class="sxs-lookup"><span data-stu-id="0017f-119">Element</span></span>|<span data-ttu-id="0017f-120">描述</span><span class="sxs-lookup"><span data-stu-id="0017f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0017f-121">\<binding></span><span class="sxs-lookup"><span data-stu-id="0017f-121">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="0017f-122">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="0017f-122">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0017f-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="0017f-123">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0017f-124">绑定</span><span class="sxs-lookup"><span data-stu-id="0017f-124">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0017f-125">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="0017f-125">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0017f-126">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="0017f-126">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0017f-127">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0017f-127">\<customBinding></span></span>](custombinding.md)

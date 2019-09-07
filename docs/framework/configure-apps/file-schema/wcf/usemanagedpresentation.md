---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: c410967e84c9318d21ce0b3072d08b026a37b190
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399211"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="0a16b-101">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="0a16b-101">\<useManagedPresentation></span></span>
<span data-ttu-id="0a16b-102">一个绑定元素，用于与支持 WS-Trust 的 CardSpace 配置文件的 CardSpace 安全令牌服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="0a16b-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="0a16b-103">此元素没有属性并且以空开关形式存在。</span><span class="sxs-lookup"><span data-stu-id="0a16b-103">This element has no attribute and is present as an empty switch.</span></span>  
  
<span data-ttu-id="0a16b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0a16b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0a16b-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0a16b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0a16b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="0a16b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="0a16b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="0a16b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="0a16b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="0a16b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="0a16b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<useManagedPresentation >**</span><span class="sxs-lookup"><span data-stu-id="0a16b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useManagedPresentation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a16b-110">语法</span><span class="sxs-lookup"><span data-stu-id="0a16b-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a16b-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0a16b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0a16b-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0a16b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a16b-113">特性</span><span class="sxs-lookup"><span data-stu-id="0a16b-113">Attributes</span></span>  
 <span data-ttu-id="0a16b-114">无。</span><span class="sxs-lookup"><span data-stu-id="0a16b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0a16b-115">子元素</span><span class="sxs-lookup"><span data-stu-id="0a16b-115">Child Elements</span></span>  
 <span data-ttu-id="0a16b-116">无</span><span class="sxs-lookup"><span data-stu-id="0a16b-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0a16b-117">父元素</span><span class="sxs-lookup"><span data-stu-id="0a16b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0a16b-118">元素</span><span class="sxs-lookup"><span data-stu-id="0a16b-118">Element</span></span>|<span data-ttu-id="0a16b-119">描述</span><span class="sxs-lookup"><span data-stu-id="0a16b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a16b-120">\<binding></span><span class="sxs-lookup"><span data-stu-id="0a16b-120">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="0a16b-121">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="0a16b-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a16b-122">备注</span><span class="sxs-lookup"><span data-stu-id="0a16b-122">Remarks</span></span>  
 <span data-ttu-id="0a16b-123">标识提供程序使用此元素，用以在它的策略中表明它支持 WS-Trust 的 CardSpace 配置文件这一事实。</span><span class="sxs-lookup"><span data-stu-id="0a16b-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="0a16b-124">发布这种策略断言的标识提供程序应该能够基于该 CardSpace 配置文件颁发令牌。</span><span class="sxs-lookup"><span data-stu-id="0a16b-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a16b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a16b-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0a16b-126">绑定</span><span class="sxs-lookup"><span data-stu-id="0a16b-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0a16b-127">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="0a16b-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0a16b-128">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="0a16b-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0a16b-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0a16b-129">\<customBinding></span></span>](custombinding.md)

---
title: '&lt;useManagedPresentation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae9851794d77972066fb897aa76528fec86fd6f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltusemanagedpresentationgt"></a><span data-ttu-id="6b969-102">&lt;useManagedPresentation&gt;</span><span class="sxs-lookup"><span data-stu-id="6b969-102">&lt;useManagedPresentation&gt;</span></span>
<span data-ttu-id="6b969-103">一个绑定元素，用于与支持 WS-Trust 的 CardSpace 配置文件的 CardSpace 安全令牌服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="6b969-103">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="6b969-104">此元素没有属性并且以空开关形式存在。</span><span class="sxs-lookup"><span data-stu-id="6b969-104">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="6b969-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6b969-105">\<system.serviceModel></span></span>  
<span data-ttu-id="6b969-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="6b969-106">\<bindings></span></span>  
<span data-ttu-id="6b969-107">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="6b969-107">\<customBinding></span></span>  
<span data-ttu-id="6b969-108">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="6b969-108">\<binding></span></span>  
<span data-ttu-id="6b969-109">\<useManagedPresentation ></span><span class="sxs-lookup"><span data-stu-id="6b969-109">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b969-110">语法</span><span class="sxs-lookup"><span data-stu-id="6b969-110">Syntax</span></span>  
  
```xml  
<useManagedPresentation/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b969-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6b969-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6b969-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6b969-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b969-113">特性</span><span class="sxs-lookup"><span data-stu-id="6b969-113">Attributes</span></span>  
 <span data-ttu-id="6b969-114">无。</span><span class="sxs-lookup"><span data-stu-id="6b969-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6b969-115">子元素</span><span class="sxs-lookup"><span data-stu-id="6b969-115">Child Elements</span></span>  
 <span data-ttu-id="6b969-116">无</span><span class="sxs-lookup"><span data-stu-id="6b969-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b969-117">父元素</span><span class="sxs-lookup"><span data-stu-id="6b969-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6b969-118">元素</span><span class="sxs-lookup"><span data-stu-id="6b969-118">Element</span></span>|<span data-ttu-id="6b969-119">描述</span><span class="sxs-lookup"><span data-stu-id="6b969-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b969-120">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="6b969-120">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="6b969-121">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="6b969-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b969-122">备注</span><span class="sxs-lookup"><span data-stu-id="6b969-122">Remarks</span></span>  
 <span data-ttu-id="6b969-123">标识提供程序使用此元素，用以在它的策略中表明它支持 WS-Trust 的 CardSpace 配置文件这一事实。</span><span class="sxs-lookup"><span data-stu-id="6b969-123">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="6b969-124">发布这种策略断言的标识提供程序应该能够基于该 CardSpace 配置文件颁发令牌。</span><span class="sxs-lookup"><span data-stu-id="6b969-124">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b969-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b969-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>  
 <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="6b969-126">绑定</span><span class="sxs-lookup"><span data-stu-id="6b969-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="6b969-127">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="6b969-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="6b969-128">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="6b969-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="6b969-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="6b969-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

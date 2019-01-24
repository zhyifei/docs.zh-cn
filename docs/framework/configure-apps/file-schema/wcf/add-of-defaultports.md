---
title: '&lt;defaultPorts&gt; 的 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 8b7a4730af6690616058a91cf23bb39734d81abc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541711"
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="1dc26-102">&lt;defaultPorts&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="1dc26-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="1dc26-103">客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="1dc26-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="1dc26-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1dc26-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1dc26-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="1dc26-105">\<behaviors></span></span>  
<span data-ttu-id="1dc26-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1dc26-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1dc26-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1dc26-107">\<behavior></span></span>  
<span data-ttu-id="1dc26-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="1dc26-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="1dc26-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="1dc26-109">\<defaultPorts></span></span>  
<span data-ttu-id="1dc26-110">\<add></span><span class="sxs-lookup"><span data-stu-id="1dc26-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dc26-111">语法</span><span class="sxs-lookup"><span data-stu-id="1dc26-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dc26-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1dc26-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1dc26-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1dc26-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dc26-114">特性</span><span class="sxs-lookup"><span data-stu-id="1dc26-114">Attributes</span></span>  
  
|<span data-ttu-id="1dc26-115">特性</span><span class="sxs-lookup"><span data-stu-id="1dc26-115">Attribute</span></span>|<span data-ttu-id="1dc26-116">描述</span><span class="sxs-lookup"><span data-stu-id="1dc26-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1dc26-117">端口</span><span class="sxs-lookup"><span data-stu-id="1dc26-117">port</span></span>|<span data-ttu-id="1dc26-118">一个整数，指定默认通信端口号。</span><span class="sxs-lookup"><span data-stu-id="1dc26-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="1dc26-119">scheme</span><span class="sxs-lookup"><span data-stu-id="1dc26-119">scheme</span></span>|<span data-ttu-id="1dc26-120">一个字符串，指定与通信端口关联的协议设置组。</span><span class="sxs-lookup"><span data-stu-id="1dc26-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1dc26-121">子元素</span><span class="sxs-lookup"><span data-stu-id="1dc26-121">Child Elements</span></span>  
 <span data-ttu-id="1dc26-122">无。</span><span class="sxs-lookup"><span data-stu-id="1dc26-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1dc26-123">父元素</span><span class="sxs-lookup"><span data-stu-id="1dc26-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1dc26-124">元素</span><span class="sxs-lookup"><span data-stu-id="1dc26-124">Element</span></span>|<span data-ttu-id="1dc26-125">描述</span><span class="sxs-lookup"><span data-stu-id="1dc26-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dc26-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="1dc26-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="1dc26-127">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="1dc26-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1dc26-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="1dc26-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.DefaultPortElement>

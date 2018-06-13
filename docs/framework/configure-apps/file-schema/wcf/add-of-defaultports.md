---
title: '&lt;defaultPorts&gt; 的 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 28ddc98bd66c1f74f857448aa710d3998ddbd3dc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748745"
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="053d2-102">&lt;defaultPorts&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="053d2-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="053d2-103">客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="053d2-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="053d2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="053d2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="053d2-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="053d2-105">\<behaviors></span></span>  
<span data-ttu-id="053d2-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="053d2-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="053d2-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="053d2-107">\<behavior></span></span>  
<span data-ttu-id="053d2-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="053d2-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="053d2-109">\<d d ></span><span class="sxs-lookup"><span data-stu-id="053d2-109">\<defaultPorts></span></span>  
<span data-ttu-id="053d2-110">\<add></span><span class="sxs-lookup"><span data-stu-id="053d2-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="053d2-111">语法</span><span class="sxs-lookup"><span data-stu-id="053d2-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>   <defaultPorts>      <add port="Integer" scheme="String" />   </defaultPorts></useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="053d2-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="053d2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="053d2-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="053d2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="053d2-114">特性</span><span class="sxs-lookup"><span data-stu-id="053d2-114">Attributes</span></span>  
  
|<span data-ttu-id="053d2-115">特性</span><span class="sxs-lookup"><span data-stu-id="053d2-115">Attribute</span></span>|<span data-ttu-id="053d2-116">描述</span><span class="sxs-lookup"><span data-stu-id="053d2-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="053d2-117">端口</span><span class="sxs-lookup"><span data-stu-id="053d2-117">port</span></span>|<span data-ttu-id="053d2-118">一个整数，指定默认通信端口号。</span><span class="sxs-lookup"><span data-stu-id="053d2-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="053d2-119">scheme</span><span class="sxs-lookup"><span data-stu-id="053d2-119">scheme</span></span>|<span data-ttu-id="053d2-120">一个字符串，指定与通信端口关联的协议设置组。</span><span class="sxs-lookup"><span data-stu-id="053d2-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="053d2-121">子元素</span><span class="sxs-lookup"><span data-stu-id="053d2-121">Child Elements</span></span>  
 <span data-ttu-id="053d2-122">无。</span><span class="sxs-lookup"><span data-stu-id="053d2-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="053d2-123">父元素</span><span class="sxs-lookup"><span data-stu-id="053d2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="053d2-124">元素</span><span class="sxs-lookup"><span data-stu-id="053d2-124">Element</span></span>|<span data-ttu-id="053d2-125">描述</span><span class="sxs-lookup"><span data-stu-id="053d2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="053d2-126">\<d d ></span><span class="sxs-lookup"><span data-stu-id="053d2-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="053d2-127">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="053d2-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="053d2-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="053d2-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>

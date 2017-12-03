---
title: "&lt;defaultPorts&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2aa63c7a5e730b2fb45f614cb2fe5f88444cee4a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="13953-102">&lt;defaultPorts&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="13953-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="13953-103">客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="13953-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="13953-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="13953-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="13953-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="13953-105">\<behaviors></span></span>  
<span data-ttu-id="13953-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="13953-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="13953-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="13953-107">\<behavior></span></span>  
<span data-ttu-id="13953-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="13953-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="13953-109">\<d d ></span><span class="sxs-lookup"><span data-stu-id="13953-109">\<defaultPorts></span></span>  
<span data-ttu-id="13953-110">\<add></span><span class="sxs-lookup"><span data-stu-id="13953-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13953-111">语法</span><span class="sxs-lookup"><span data-stu-id="13953-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>   <defaultPorts>      <add port="Integer" scheme="String" />   </defaultPorts></useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13953-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="13953-112">Attributes and Elements</span></span>  
 <span data-ttu-id="13953-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="13953-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13953-114">特性</span><span class="sxs-lookup"><span data-stu-id="13953-114">Attributes</span></span>  
  
|<span data-ttu-id="13953-115">特性</span><span class="sxs-lookup"><span data-stu-id="13953-115">Attribute</span></span>|<span data-ttu-id="13953-116">描述</span><span class="sxs-lookup"><span data-stu-id="13953-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13953-117">端口</span><span class="sxs-lookup"><span data-stu-id="13953-117">port</span></span>|<span data-ttu-id="13953-118">一个整数，指定默认通信端口号。</span><span class="sxs-lookup"><span data-stu-id="13953-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="13953-119">scheme</span><span class="sxs-lookup"><span data-stu-id="13953-119">scheme</span></span>|<span data-ttu-id="13953-120">一个字符串，指定与通信端口关联的协议设置组。</span><span class="sxs-lookup"><span data-stu-id="13953-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13953-121">子元素</span><span class="sxs-lookup"><span data-stu-id="13953-121">Child Elements</span></span>  
 <span data-ttu-id="13953-122">无。</span><span class="sxs-lookup"><span data-stu-id="13953-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13953-123">父元素</span><span class="sxs-lookup"><span data-stu-id="13953-123">Parent Elements</span></span>  
  
|<span data-ttu-id="13953-124">元素</span><span class="sxs-lookup"><span data-stu-id="13953-124">Element</span></span>|<span data-ttu-id="13953-125">描述</span><span class="sxs-lookup"><span data-stu-id="13953-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13953-126">\<d d ></span><span class="sxs-lookup"><span data-stu-id="13953-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="13953-127">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="13953-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="13953-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13953-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>

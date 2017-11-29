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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bd487238ebe327a5f89b737fdf764d94f955a411
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="d63de-102">&lt;defaultPorts&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="d63de-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="d63de-103">客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="d63de-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="d63de-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d63de-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d63de-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="d63de-105">\<behaviors></span></span>  
<span data-ttu-id="d63de-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d63de-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d63de-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="d63de-107">\<behavior></span></span>  
<span data-ttu-id="d63de-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="d63de-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="d63de-109">\<d d ></span><span class="sxs-lookup"><span data-stu-id="d63de-109">\<defaultPorts></span></span>  
<span data-ttu-id="d63de-110">\<add></span><span class="sxs-lookup"><span data-stu-id="d63de-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d63de-111">语法</span><span class="sxs-lookup"><span data-stu-id="d63de-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>   <defaultPorts>      <add port="Integer" scheme="String" />   </defaultPorts></useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d63de-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d63de-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d63de-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d63de-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d63de-114">特性</span><span class="sxs-lookup"><span data-stu-id="d63de-114">Attributes</span></span>  
  
|<span data-ttu-id="d63de-115">特性</span><span class="sxs-lookup"><span data-stu-id="d63de-115">Attribute</span></span>|<span data-ttu-id="d63de-116">描述</span><span class="sxs-lookup"><span data-stu-id="d63de-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d63de-117">端口</span><span class="sxs-lookup"><span data-stu-id="d63de-117">port</span></span>|<span data-ttu-id="d63de-118">一个整数，指定默认通信端口号。</span><span class="sxs-lookup"><span data-stu-id="d63de-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="d63de-119">scheme</span><span class="sxs-lookup"><span data-stu-id="d63de-119">scheme</span></span>|<span data-ttu-id="d63de-120">一个字符串，指定与通信端口关联的协议设置组。</span><span class="sxs-lookup"><span data-stu-id="d63de-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d63de-121">子元素</span><span class="sxs-lookup"><span data-stu-id="d63de-121">Child Elements</span></span>  
 <span data-ttu-id="d63de-122">无。</span><span class="sxs-lookup"><span data-stu-id="d63de-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d63de-123">父元素</span><span class="sxs-lookup"><span data-stu-id="d63de-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d63de-124">元素</span><span class="sxs-lookup"><span data-stu-id="d63de-124">Element</span></span>|<span data-ttu-id="d63de-125">描述</span><span class="sxs-lookup"><span data-stu-id="d63de-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d63de-126">\<d d ></span><span class="sxs-lookup"><span data-stu-id="d63de-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="d63de-127">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="d63de-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d63de-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d63de-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>

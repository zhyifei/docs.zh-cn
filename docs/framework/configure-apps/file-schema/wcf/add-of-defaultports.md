---
title: <add> 的 <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: d2723dad14a63c4b05fdb70157f7eb21d193d3ab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926712"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="8b3bd-102">\<添加 defaultPorts > \<的 ></span><span class="sxs-lookup"><span data-stu-id="8b3bd-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="8b3bd-103">客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="8b3bd-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="8b3bd-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8b3bd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8b3bd-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="8b3bd-105">\<behaviors></span></span>  
<span data-ttu-id="8b3bd-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="8b3bd-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="8b3bd-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="8b3bd-107">\<behavior></span></span>  
<span data-ttu-id="8b3bd-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="8b3bd-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="8b3bd-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="8b3bd-109">\<defaultPorts></span></span>  
<span data-ttu-id="8b3bd-110">\<add></span><span class="sxs-lookup"><span data-stu-id="8b3bd-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b3bd-111">语法</span><span class="sxs-lookup"><span data-stu-id="8b3bd-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b3bd-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8b3bd-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8b3bd-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8b3bd-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b3bd-114">特性</span><span class="sxs-lookup"><span data-stu-id="8b3bd-114">Attributes</span></span>  
  
|<span data-ttu-id="8b3bd-115">特性</span><span class="sxs-lookup"><span data-stu-id="8b3bd-115">Attribute</span></span>|<span data-ttu-id="8b3bd-116">描述</span><span class="sxs-lookup"><span data-stu-id="8b3bd-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8b3bd-117">端口</span><span class="sxs-lookup"><span data-stu-id="8b3bd-117">port</span></span>|<span data-ttu-id="8b3bd-118">一个整数，指定默认通信端口号。</span><span class="sxs-lookup"><span data-stu-id="8b3bd-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="8b3bd-119">scheme</span><span class="sxs-lookup"><span data-stu-id="8b3bd-119">scheme</span></span>|<span data-ttu-id="8b3bd-120">一个字符串，指定与通信端口关联的协议设置组。</span><span class="sxs-lookup"><span data-stu-id="8b3bd-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b3bd-121">子元素</span><span class="sxs-lookup"><span data-stu-id="8b3bd-121">Child Elements</span></span>  
 <span data-ttu-id="8b3bd-122">无。</span><span class="sxs-lookup"><span data-stu-id="8b3bd-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8b3bd-123">父元素</span><span class="sxs-lookup"><span data-stu-id="8b3bd-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8b3bd-124">元素</span><span class="sxs-lookup"><span data-stu-id="8b3bd-124">Element</span></span>|<span data-ttu-id="8b3bd-125">描述</span><span class="sxs-lookup"><span data-stu-id="8b3bd-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b3bd-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="8b3bd-126">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="8b3bd-127">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="8b3bd-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b3bd-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b3bd-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>

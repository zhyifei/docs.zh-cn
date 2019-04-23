---
title: <add> 的 <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 5200c8893a89488b72c2c71d1a3703bf2aad1235
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136742"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="1660c-102">\<添加 > 的\<d d ></span><span class="sxs-lookup"><span data-stu-id="1660c-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="1660c-103">客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="1660c-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="1660c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1660c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1660c-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="1660c-105">\<behaviors></span></span>  
<span data-ttu-id="1660c-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="1660c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1660c-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1660c-107">\<behavior></span></span>  
<span data-ttu-id="1660c-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="1660c-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="1660c-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="1660c-109">\<defaultPorts></span></span>  
<span data-ttu-id="1660c-110">\<add></span><span class="sxs-lookup"><span data-stu-id="1660c-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1660c-111">语法</span><span class="sxs-lookup"><span data-stu-id="1660c-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1660c-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1660c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1660c-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1660c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1660c-114">特性</span><span class="sxs-lookup"><span data-stu-id="1660c-114">Attributes</span></span>  
  
|<span data-ttu-id="1660c-115">特性</span><span class="sxs-lookup"><span data-stu-id="1660c-115">Attribute</span></span>|<span data-ttu-id="1660c-116">描述</span><span class="sxs-lookup"><span data-stu-id="1660c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1660c-117">端口</span><span class="sxs-lookup"><span data-stu-id="1660c-117">port</span></span>|<span data-ttu-id="1660c-118">一个整数，指定默认通信端口号。</span><span class="sxs-lookup"><span data-stu-id="1660c-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="1660c-119">scheme</span><span class="sxs-lookup"><span data-stu-id="1660c-119">scheme</span></span>|<span data-ttu-id="1660c-120">一个字符串，指定与通信端口关联的协议设置组。</span><span class="sxs-lookup"><span data-stu-id="1660c-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1660c-121">子元素</span><span class="sxs-lookup"><span data-stu-id="1660c-121">Child Elements</span></span>  
 <span data-ttu-id="1660c-122">无。</span><span class="sxs-lookup"><span data-stu-id="1660c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1660c-123">父元素</span><span class="sxs-lookup"><span data-stu-id="1660c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1660c-124">元素</span><span class="sxs-lookup"><span data-stu-id="1660c-124">Element</span></span>|<span data-ttu-id="1660c-125">描述</span><span class="sxs-lookup"><span data-stu-id="1660c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1660c-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="1660c-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="1660c-127">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="1660c-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1660c-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="1660c-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>

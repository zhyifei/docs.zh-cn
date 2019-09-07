---
title: <add> 的 <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: f5de2aa897a3bc37d08932451a2c7b94bc603b9e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400643"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="0e253-102">\<添加 defaultPorts > \<的 ></span><span class="sxs-lookup"><span data-stu-id="0e253-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="0e253-103">客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="0e253-103">A default communications endpoint that the client application listens to.</span></span>  
  
<span data-ttu-id="0e253-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0e253-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0e253-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0e253-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0e253-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0e253-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="0e253-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0e253-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="0e253-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="0e253-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="0e253-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<useRequestHeadersForMetadataAddress >** ](userequestheadersformetadataaddress.md)</span><span class="sxs-lookup"><span data-stu-id="0e253-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)</span></span>\
<span data-ttu-id="0e253-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultPorts >** ](defaultports.md)</span><span class="sxs-lookup"><span data-stu-id="0e253-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)</span></span>\
<span data-ttu-id="0e253-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="0e253-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e253-112">语法</span><span class="sxs-lookup"><span data-stu-id="0e253-112">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e253-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0e253-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0e253-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0e253-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e253-115">特性</span><span class="sxs-lookup"><span data-stu-id="0e253-115">Attributes</span></span>  
  
|<span data-ttu-id="0e253-116">特性</span><span class="sxs-lookup"><span data-stu-id="0e253-116">Attribute</span></span>|<span data-ttu-id="0e253-117">描述</span><span class="sxs-lookup"><span data-stu-id="0e253-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e253-118">端口</span><span class="sxs-lookup"><span data-stu-id="0e253-118">port</span></span>|<span data-ttu-id="0e253-119">一个整数，指定默认通信端口号。</span><span class="sxs-lookup"><span data-stu-id="0e253-119">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="0e253-120">scheme</span><span class="sxs-lookup"><span data-stu-id="0e253-120">scheme</span></span>|<span data-ttu-id="0e253-121">一个字符串，指定与通信端口关联的协议设置组。</span><span class="sxs-lookup"><span data-stu-id="0e253-121">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e253-122">子元素</span><span class="sxs-lookup"><span data-stu-id="0e253-122">Child Elements</span></span>  
 <span data-ttu-id="0e253-123">无。</span><span class="sxs-lookup"><span data-stu-id="0e253-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e253-124">父元素</span><span class="sxs-lookup"><span data-stu-id="0e253-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0e253-125">元素</span><span class="sxs-lookup"><span data-stu-id="0e253-125">Element</span></span>|<span data-ttu-id="0e253-126">描述</span><span class="sxs-lookup"><span data-stu-id="0e253-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e253-127">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="0e253-127">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="0e253-128">一个默认端口集合，列出客户端应用程序侦听的默认通信终结点。</span><span class="sxs-lookup"><span data-stu-id="0e253-128">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e253-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e253-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>

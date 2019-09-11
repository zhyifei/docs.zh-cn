---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 8d4f55fd5b51ea77839b7fdbb930e937f5700417
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854796"
---
# <a name="webhttpendpoint"></a><span data-ttu-id="f7d4a-101">\<webHttpEndpoint></span><span class="sxs-lookup"><span data-stu-id="f7d4a-101">\<webHttpEndpoint></span></span>
<span data-ttu-id="f7d4a-102">此配置元素定义一个标准终结点，该终结点具有固定[ \<的 webHttpBinding >](webhttpbinding.md)绑定[ \<](webhttp.md) ，可自动添加 wcf-webhttp > 行为。</span><span class="sxs-lookup"><span data-stu-id="f7d4a-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="f7d4a-103">在编写 REST 服务时，请使用此终结点。</span><span class="sxs-lookup"><span data-stu-id="f7d4a-103">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="f7d4a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f7d4a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f7d4a-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f7d4a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f7d4a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="f7d4a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="f7d4a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<webHttpEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="f7d4a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7d4a-108">语法</span><span class="sxs-lookup"><span data-stu-id="f7d4a-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String"
                        defaultOutgoingResponseFormat="Xml/Json"
                        helpEnabled="Boolean"
                        webEndpointType="String" />
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7d4a-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f7d4a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f7d4a-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f7d4a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7d4a-111">特性</span><span class="sxs-lookup"><span data-stu-id="f7d4a-111">Attributes</span></span>  
  
|<span data-ttu-id="f7d4a-112">特性</span><span class="sxs-lookup"><span data-stu-id="f7d4a-112">Attribute</span></span>|<span data-ttu-id="f7d4a-113">描述</span><span class="sxs-lookup"><span data-stu-id="f7d4a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7d4a-114">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="f7d4a-114">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="f7d4a-115">一个布尔值，指示是否启用自动格式选择。</span><span class="sxs-lookup"><span data-stu-id="f7d4a-115">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="f7d4a-116">如果启用了自动格式选择，基础结构将分析请求消息的 `Accept` 标头，并确定最适合的响应格式。</span><span class="sxs-lookup"><span data-stu-id="f7d4a-116">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="f7d4a-117">如果 `Accept` 标头未指定适合的响应格式，则基础结构将使用请求消息的 `Content-Type`，或使用操作的默认响应格式。</span><span class="sxs-lookup"><span data-stu-id="f7d4a-117">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="f7d4a-118">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="f7d4a-118">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="f7d4a-119">一个指定默认传出响应格式的特性。</span><span class="sxs-lookup"><span data-stu-id="f7d4a-119">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="f7d4a-120">此特性的类型为 <xref:System.ServiceModel.Web.WebMessageFormat></span><span class="sxs-lookup"><span data-stu-id="f7d4a-120">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="f7d4a-121">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="f7d4a-121">helpEnabled</span></span>|<span data-ttu-id="f7d4a-122">一个布尔值，指示是否为终结点启用了 HTTP 帮助页。</span><span class="sxs-lookup"><span data-stu-id="f7d4a-122">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="f7d4a-123">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="f7d4a-123">webEndpointType</span></span>|<span data-ttu-id="f7d4a-124">一个字符串，指定终结点的类型。</span><span class="sxs-lookup"><span data-stu-id="f7d4a-124">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7d4a-125">子元素</span><span class="sxs-lookup"><span data-stu-id="f7d4a-125">Child Elements</span></span>  
 <span data-ttu-id="f7d4a-126">无。</span><span class="sxs-lookup"><span data-stu-id="f7d4a-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7d4a-127">父元素</span><span class="sxs-lookup"><span data-stu-id="f7d4a-127">Parent Elements</span></span>  
  
|<span data-ttu-id="f7d4a-128">元素</span><span class="sxs-lookup"><span data-stu-id="f7d4a-128">Element</span></span>|<span data-ttu-id="f7d4a-129">描述</span><span class="sxs-lookup"><span data-stu-id="f7d4a-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7d4a-130">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="f7d4a-130">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="f7d4a-131">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="f7d4a-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7d4a-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7d4a-132">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>

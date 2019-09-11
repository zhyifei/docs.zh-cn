---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b4bc33cf8ff4e703973efe7df49e9f1d2189302e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854813"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="e43a5-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="e43a5-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="e43a5-102">此配置元素定义一个标准终结点，该终结点具有固定[ \<的 webHttpBinding >](webhttpbinding.md)绑定[ \<](enablewebscript.md) ，可自动添加 enableWebScript > 行为。</span><span class="sxs-lookup"><span data-stu-id="e43a5-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="e43a5-103">在编写从 ASP.NET AJAX 应用程序中调用的服务时，请使用此终结点。</span><span class="sxs-lookup"><span data-stu-id="e43a5-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="e43a5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e43a5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e43a5-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e43a5-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e43a5-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="e43a5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="e43a5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<webScriptEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="e43a5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e43a5-108">语法</span><span class="sxs-lookup"><span data-stu-id="e43a5-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e43a5-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e43a5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e43a5-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e43a5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e43a5-111">特性</span><span class="sxs-lookup"><span data-stu-id="e43a5-111">Attributes</span></span>  
  
|<span data-ttu-id="e43a5-112">特性</span><span class="sxs-lookup"><span data-stu-id="e43a5-112">Attribute</span></span>|<span data-ttu-id="e43a5-113">描述</span><span class="sxs-lookup"><span data-stu-id="e43a5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e43a5-114">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="e43a5-114">webEndpointType</span></span>|<span data-ttu-id="e43a5-115">一个字符串，指定终结点的类型。</span><span class="sxs-lookup"><span data-stu-id="e43a5-115">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e43a5-116">子元素</span><span class="sxs-lookup"><span data-stu-id="e43a5-116">Child Elements</span></span>  
 <span data-ttu-id="e43a5-117">无。</span><span class="sxs-lookup"><span data-stu-id="e43a5-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e43a5-118">父元素</span><span class="sxs-lookup"><span data-stu-id="e43a5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e43a5-119">元素</span><span class="sxs-lookup"><span data-stu-id="e43a5-119">Element</span></span>|<span data-ttu-id="e43a5-120">描述</span><span class="sxs-lookup"><span data-stu-id="e43a5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e43a5-121">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="e43a5-121">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="e43a5-122">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="e43a5-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e43a5-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="e43a5-123">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>

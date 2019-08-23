---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: cc69029d9830fd12df5a4070f11847fadf4c60bb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940409"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="5be96-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="5be96-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="5be96-102">此配置元素定义一个标准终结点, 该终结点具有固定[ \<的 webHttpBinding >](webhttpbinding.md)绑定[ \<](enablewebscript.md) , 可自动添加 enableWebScript > 行为。</span><span class="sxs-lookup"><span data-stu-id="5be96-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="5be96-103">在编写从 ASP.NET AJAX 应用程序中调用的服务时，请使用此终结点。</span><span class="sxs-lookup"><span data-stu-id="5be96-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="5be96-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5be96-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5be96-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="5be96-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5be96-106">语法</span><span class="sxs-lookup"><span data-stu-id="5be96-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5be96-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5be96-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5be96-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5be96-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5be96-109">特性</span><span class="sxs-lookup"><span data-stu-id="5be96-109">Attributes</span></span>  
  
|<span data-ttu-id="5be96-110">特性</span><span class="sxs-lookup"><span data-stu-id="5be96-110">Attribute</span></span>|<span data-ttu-id="5be96-111">描述</span><span class="sxs-lookup"><span data-stu-id="5be96-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5be96-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="5be96-112">webEndpointType</span></span>|<span data-ttu-id="5be96-113">一个字符串，指定终结点的类型。</span><span class="sxs-lookup"><span data-stu-id="5be96-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5be96-114">子元素</span><span class="sxs-lookup"><span data-stu-id="5be96-114">Child Elements</span></span>  
 <span data-ttu-id="5be96-115">无。</span><span class="sxs-lookup"><span data-stu-id="5be96-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5be96-116">父元素</span><span class="sxs-lookup"><span data-stu-id="5be96-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5be96-117">元素</span><span class="sxs-lookup"><span data-stu-id="5be96-117">Element</span></span>|<span data-ttu-id="5be96-118">描述</span><span class="sxs-lookup"><span data-stu-id="5be96-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5be96-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="5be96-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="5be96-120">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="5be96-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5be96-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="5be96-121">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>

---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: 9619c27c8c6d41250eeaeccabebe611e94b7d874
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769728"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="fac54-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="fac54-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="fac54-102">此配置元素定义具有固定的标准终结点[ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)自动绑定，它将添加[ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)行为。</span><span class="sxs-lookup"><span data-stu-id="fac54-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="fac54-103">在编写从 ASP.NET AJAX 应用程序中调用的服务时，请使用此终结点。</span><span class="sxs-lookup"><span data-stu-id="fac54-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="fac54-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fac54-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fac54-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="fac54-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fac54-106">语法</span><span class="sxs-lookup"><span data-stu-id="fac54-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fac54-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fac54-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fac54-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fac54-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fac54-109">特性</span><span class="sxs-lookup"><span data-stu-id="fac54-109">Attributes</span></span>  
  
|<span data-ttu-id="fac54-110">特性</span><span class="sxs-lookup"><span data-stu-id="fac54-110">Attribute</span></span>|<span data-ttu-id="fac54-111">描述</span><span class="sxs-lookup"><span data-stu-id="fac54-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fac54-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="fac54-112">webEndpointType</span></span>|<span data-ttu-id="fac54-113">一个字符串，指定终结点的类型。</span><span class="sxs-lookup"><span data-stu-id="fac54-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fac54-114">子元素</span><span class="sxs-lookup"><span data-stu-id="fac54-114">Child Elements</span></span>  
 <span data-ttu-id="fac54-115">无。</span><span class="sxs-lookup"><span data-stu-id="fac54-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fac54-116">父元素</span><span class="sxs-lookup"><span data-stu-id="fac54-116">Parent Elements</span></span>  
  
|<span data-ttu-id="fac54-117">元素</span><span class="sxs-lookup"><span data-stu-id="fac54-117">Element</span></span>|<span data-ttu-id="fac54-118">描述</span><span class="sxs-lookup"><span data-stu-id="fac54-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fac54-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="fac54-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="fac54-120">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="fac54-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fac54-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="fac54-121">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>

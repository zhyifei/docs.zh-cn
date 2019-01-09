---
title: '&lt;webScriptEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: beb17d4ccc39bcca30e97d4f0df47c797cde6216
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148768"
---
# <a name="ltwebscriptendpointgt"></a><span data-ttu-id="10a12-102">&lt;webScriptEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="10a12-102">&lt;webScriptEndpoint&gt;</span></span>
<span data-ttu-id="10a12-103">此配置元素定义具有固定的标准终结点[ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)自动绑定，它将添加[ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)行为。</span><span class="sxs-lookup"><span data-stu-id="10a12-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="10a12-104">在编写从 ASP.NET AJAX 应用程序中调用的服务时，请使用此终结点。</span><span class="sxs-lookup"><span data-stu-id="10a12-104">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="10a12-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="10a12-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="10a12-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="10a12-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10a12-107">语法</span><span class="sxs-lookup"><span data-stu-id="10a12-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10a12-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="10a12-108">Attributes and Elements</span></span>  
 <span data-ttu-id="10a12-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="10a12-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10a12-110">特性</span><span class="sxs-lookup"><span data-stu-id="10a12-110">Attributes</span></span>  
  
|<span data-ttu-id="10a12-111">特性</span><span class="sxs-lookup"><span data-stu-id="10a12-111">Attribute</span></span>|<span data-ttu-id="10a12-112">描述</span><span class="sxs-lookup"><span data-stu-id="10a12-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10a12-113">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="10a12-113">webEndpointType</span></span>|<span data-ttu-id="10a12-114">一个字符串，指定终结点的类型。</span><span class="sxs-lookup"><span data-stu-id="10a12-114">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10a12-115">子元素</span><span class="sxs-lookup"><span data-stu-id="10a12-115">Child Elements</span></span>  
 <span data-ttu-id="10a12-116">无。</span><span class="sxs-lookup"><span data-stu-id="10a12-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10a12-117">父元素</span><span class="sxs-lookup"><span data-stu-id="10a12-117">Parent Elements</span></span>  
  
|<span data-ttu-id="10a12-118">元素</span><span class="sxs-lookup"><span data-stu-id="10a12-118">Element</span></span>|<span data-ttu-id="10a12-119">描述</span><span class="sxs-lookup"><span data-stu-id="10a12-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10a12-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="10a12-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="10a12-121">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="10a12-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10a12-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="10a12-122">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>

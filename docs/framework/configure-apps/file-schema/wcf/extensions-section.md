---
title: <extensions>区
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 35621acaf96a80ffa3ffe4a3c6605143c48995a5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855355"
---
# <a name="extensions-section"></a><span data-ttu-id="8902e-102">\<扩展 > 部分</span><span class="sxs-lookup"><span data-stu-id="8902e-102">\<extensions> section</span></span>
<span data-ttu-id="8902e-103">此配置节包含一个扩展集合，这些扩展使用户能够创建扩展的用户定义绑定、行为和其他方面。</span><span class="sxs-lookup"><span data-stu-id="8902e-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="8902e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8902e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8902e-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8902e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8902e-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<扩展 >**</span><span class="sxs-lookup"><span data-stu-id="8902e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8902e-107">语法</span><span class="sxs-lookup"><span data-stu-id="8902e-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
    </bindingExtensions>
    <behaviorExtensions>
    </behaviorExtensions>
    <bindingElementExtensions>
    </bindingElementExtensions>
    <endpointExtensions>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8902e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8902e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8902e-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8902e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8902e-110">特性</span><span class="sxs-lookup"><span data-stu-id="8902e-110">Attributes</span></span>  
 <span data-ttu-id="8902e-111">无。</span><span class="sxs-lookup"><span data-stu-id="8902e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8902e-112">子元素</span><span class="sxs-lookup"><span data-stu-id="8902e-112">Child Elements</span></span>  
  
|<span data-ttu-id="8902e-113">元素</span><span class="sxs-lookup"><span data-stu-id="8902e-113">Element</span></span>|<span data-ttu-id="8902e-114">描述</span><span class="sxs-lookup"><span data-stu-id="8902e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8902e-115">\<behaviorExtensions></span><span class="sxs-lookup"><span data-stu-id="8902e-115">\<behaviorExtensions></span></span>](behaviorextensions.md)|<span data-ttu-id="8902e-116">本节包含子元素，这些子元素指定使用户可以自定义服务或终结点行为的行为扩展。</span><span class="sxs-lookup"><span data-stu-id="8902e-116">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="8902e-117">\<bindingElementExtensions></span><span class="sxs-lookup"><span data-stu-id="8902e-117">\<bindingElementExtensions></span></span>](bindingelementextensions.md)|<span data-ttu-id="8902e-118">本节为使用计算机或应用程序配置文件中的自定义绑定元素提供支持。</span><span class="sxs-lookup"><span data-stu-id="8902e-118">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="8902e-119">\<bindingExtensions></span><span class="sxs-lookup"><span data-stu-id="8902e-119">\<bindingExtensions></span></span>](bindingextensions.md)|<span data-ttu-id="8902e-120">本节包含子元素，这些子元素指定使用户可以自定义绑定的绑定扩展。</span><span class="sxs-lookup"><span data-stu-id="8902e-120">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="8902e-121">\<endpointExtensions></span><span class="sxs-lookup"><span data-stu-id="8902e-121">\<endpointExtensions></span></span>](endpointextensions.md)|<span data-ttu-id="8902e-122">本节包含元注册标准终结点的子元素。</span><span class="sxs-lookup"><span data-stu-id="8902e-122">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8902e-123">父元素</span><span class="sxs-lookup"><span data-stu-id="8902e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8902e-124">元素</span><span class="sxs-lookup"><span data-stu-id="8902e-124">Element</span></span>|<span data-ttu-id="8902e-125">描述</span><span class="sxs-lookup"><span data-stu-id="8902e-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8902e-126">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8902e-126">system.ServiceModel</span></span>|<span data-ttu-id="8902e-127">所有 WCF 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="8902e-127">The root element of all WCF configuration elements.</span></span>|

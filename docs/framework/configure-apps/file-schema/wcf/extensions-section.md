---
title: "&lt;extensions&gt; 节"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06c8106f004a25f1e4547e9629b881e5bf216490
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltextensionsgt-section"></a><span data-ttu-id="981a4-102">&lt;extensions&gt; 节</span><span class="sxs-lookup"><span data-stu-id="981a4-102">&lt;extensions&gt; section</span></span>
<span data-ttu-id="981a4-103">此配置节包含一个扩展集合，这些扩展使用户能够创建扩展的用户定义绑定、行为和其他方面。</span><span class="sxs-lookup"><span data-stu-id="981a4-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="981a4-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="981a4-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="981a4-105">语法</span><span class="sxs-lookup"><span data-stu-id="981a4-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="981a4-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="981a4-106">Attributes and Elements</span></span>  
 <span data-ttu-id="981a4-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="981a4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="981a4-108">特性</span><span class="sxs-lookup"><span data-stu-id="981a4-108">Attributes</span></span>  
 <span data-ttu-id="981a4-109">无。</span><span class="sxs-lookup"><span data-stu-id="981a4-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="981a4-110">子元素</span><span class="sxs-lookup"><span data-stu-id="981a4-110">Child Elements</span></span>  
  
|<span data-ttu-id="981a4-111">元素</span><span class="sxs-lookup"><span data-stu-id="981a4-111">Element</span></span>|<span data-ttu-id="981a4-112">描述</span><span class="sxs-lookup"><span data-stu-id="981a4-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="981a4-113">\<behaviorExtensions ></span><span class="sxs-lookup"><span data-stu-id="981a4-113">\<behaviorExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md)|<span data-ttu-id="981a4-114">本节包含子元素，这些子元素指定使用户可以自定义服务或终结点行为的行为扩展。</span><span class="sxs-lookup"><span data-stu-id="981a4-114">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="981a4-115">\<bindingElementExtensions ></span><span class="sxs-lookup"><span data-stu-id="981a4-115">\<bindingElementExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md)|<span data-ttu-id="981a4-116">本节为使用计算机或应用程序配置文件中的自定义绑定元素提供支持。</span><span class="sxs-lookup"><span data-stu-id="981a4-116">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="981a4-117">\<bindingExtensions ></span><span class="sxs-lookup"><span data-stu-id="981a4-117">\<bindingExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingextensions.md)|<span data-ttu-id="981a4-118">本节包含子元素，这些子元素指定使用户可以自定义绑定的绑定扩展。</span><span class="sxs-lookup"><span data-stu-id="981a4-118">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="981a4-119">\<endpointExtensions ></span><span class="sxs-lookup"><span data-stu-id="981a4-119">\<endpointExtensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointextensions.md)|<span data-ttu-id="981a4-120">本节包含元注册标准终结点的子元素。</span><span class="sxs-lookup"><span data-stu-id="981a4-120">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="981a4-121">父元素</span><span class="sxs-lookup"><span data-stu-id="981a4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="981a4-122">元素</span><span class="sxs-lookup"><span data-stu-id="981a4-122">Element</span></span>|<span data-ttu-id="981a4-123">描述</span><span class="sxs-lookup"><span data-stu-id="981a4-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="981a4-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="981a4-124">system.ServiceModel</span></span>|<span data-ttu-id="981a4-125">所有 WCF 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="981a4-125">The root element of all WCF configuration elements.</span></span>|

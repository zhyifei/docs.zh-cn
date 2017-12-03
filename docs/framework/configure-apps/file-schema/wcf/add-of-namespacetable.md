---
title: "&lt;namespaceTable&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5f159e3d92fdc7443cd20cf88300f331b78273ad
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a><span data-ttu-id="af965-102">&lt;namespaceTable&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="af965-102">&lt;add&gt; of &lt;namespaceTable&gt;</span></span>
<span data-ttu-id="af965-103">表示一个配置元素，此元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。</span><span class="sxs-lookup"><span data-stu-id="af965-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="af965-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="af965-104">\<system.serviceModel></span></span>  
<span data-ttu-id="af965-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="af965-105">\<routing></span></span>  
<span data-ttu-id="af965-106">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="af965-106">\<namespaceTable></span></span>  
<span data-ttu-id="af965-107">\<add></span><span class="sxs-lookup"><span data-stu-id="af965-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af965-108">语法</span><span class="sxs-lookup"><span data-stu-id="af965-108">Syntax</span></span>  
  
```xml  
   <routing>   <namespaceTable>  
     <add namespace="String" prefix="String" />    </namespaceTable></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af965-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="af965-109">Attributes and Elements</span></span>  
 <span data-ttu-id="af965-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="af965-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af965-111">特性</span><span class="sxs-lookup"><span data-stu-id="af965-111">Attributes</span></span>  
  
|<span data-ttu-id="af965-112">特性</span><span class="sxs-lookup"><span data-stu-id="af965-112">Attribute</span></span>|<span data-ttu-id="af965-113">描述</span><span class="sxs-lookup"><span data-stu-id="af965-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af965-114">namespace</span><span class="sxs-lookup"><span data-stu-id="af965-114">namespace</span></span>|<span data-ttu-id="af965-115">一个包含命名空间的字符串。</span><span class="sxs-lookup"><span data-stu-id="af965-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="af965-116">prefix</span><span class="sxs-lookup"><span data-stu-id="af965-116">prefix</span></span>|<span data-ttu-id="af965-117">一个包含此命名空间的前缀的字符串。</span><span class="sxs-lookup"><span data-stu-id="af965-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af965-118">子元素</span><span class="sxs-lookup"><span data-stu-id="af965-118">Child Elements</span></span>  
 <span data-ttu-id="af965-119">无。</span><span class="sxs-lookup"><span data-stu-id="af965-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af965-120">父元素</span><span class="sxs-lookup"><span data-stu-id="af965-120">Parent Elements</span></span>  
  
|<span data-ttu-id="af965-121">元素</span><span class="sxs-lookup"><span data-stu-id="af965-121">Element</span></span>|<span data-ttu-id="af965-122">描述</span><span class="sxs-lookup"><span data-stu-id="af965-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af965-123">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="af965-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="af965-124">表示用于定义一组元素的配置节，这些元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。</span><span class="sxs-lookup"><span data-stu-id="af965-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af965-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af965-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>    

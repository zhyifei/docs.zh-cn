---
title: '&lt;namespaceTable&gt; 的 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 1d3b61fa6653b3910e65b95fa96fd0657e72bf7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632893"
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a><span data-ttu-id="da724-102">&lt;namespaceTable&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="da724-102">&lt;add&gt; of &lt;namespaceTable&gt;</span></span>
<span data-ttu-id="da724-103">表示一个配置元素，此元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。</span><span class="sxs-lookup"><span data-stu-id="da724-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="da724-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="da724-104">\<system.serviceModel></span></span>  
<span data-ttu-id="da724-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="da724-105">\<routing></span></span>  
<span data-ttu-id="da724-106">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="da724-106">\<namespaceTable></span></span>  
<span data-ttu-id="da724-107">\<add></span><span class="sxs-lookup"><span data-stu-id="da724-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da724-108">语法</span><span class="sxs-lookup"><span data-stu-id="da724-108">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da724-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="da724-109">Attributes and Elements</span></span>  
 <span data-ttu-id="da724-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="da724-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da724-111">特性</span><span class="sxs-lookup"><span data-stu-id="da724-111">Attributes</span></span>  
  
|<span data-ttu-id="da724-112">特性</span><span class="sxs-lookup"><span data-stu-id="da724-112">Attribute</span></span>|<span data-ttu-id="da724-113">描述</span><span class="sxs-lookup"><span data-stu-id="da724-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da724-114">namespace</span><span class="sxs-lookup"><span data-stu-id="da724-114">namespace</span></span>|<span data-ttu-id="da724-115">一个包含命名空间的字符串。</span><span class="sxs-lookup"><span data-stu-id="da724-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="da724-116">prefix</span><span class="sxs-lookup"><span data-stu-id="da724-116">prefix</span></span>|<span data-ttu-id="da724-117">一个包含此命名空间的前缀的字符串。</span><span class="sxs-lookup"><span data-stu-id="da724-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da724-118">子元素</span><span class="sxs-lookup"><span data-stu-id="da724-118">Child Elements</span></span>  
 <span data-ttu-id="da724-119">无。</span><span class="sxs-lookup"><span data-stu-id="da724-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da724-120">父元素</span><span class="sxs-lookup"><span data-stu-id="da724-120">Parent Elements</span></span>  
  
|<span data-ttu-id="da724-121">元素</span><span class="sxs-lookup"><span data-stu-id="da724-121">Element</span></span>|<span data-ttu-id="da724-122">描述</span><span class="sxs-lookup"><span data-stu-id="da724-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da724-123">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="da724-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="da724-124">表示用于定义一组元素的配置节，这些元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。</span><span class="sxs-lookup"><span data-stu-id="da724-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da724-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="da724-125">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>

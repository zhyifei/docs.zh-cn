---
title: <add> 的 <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7e65b66170465a8b3bb60754feebb7730b959d9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089713"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="8b304-102">\<add> of \<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="8b304-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="8b304-103">表示一个配置元素，此元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。</span><span class="sxs-lookup"><span data-stu-id="8b304-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="8b304-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8b304-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8b304-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="8b304-105">\<routing></span></span>  
<span data-ttu-id="8b304-106">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="8b304-106">\<namespaceTable></span></span>  
<span data-ttu-id="8b304-107">\<add></span><span class="sxs-lookup"><span data-stu-id="8b304-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b304-108">语法</span><span class="sxs-lookup"><span data-stu-id="8b304-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b304-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8b304-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8b304-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8b304-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b304-111">特性</span><span class="sxs-lookup"><span data-stu-id="8b304-111">Attributes</span></span>  
  
|<span data-ttu-id="8b304-112">特性</span><span class="sxs-lookup"><span data-stu-id="8b304-112">Attribute</span></span>|<span data-ttu-id="8b304-113">描述</span><span class="sxs-lookup"><span data-stu-id="8b304-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8b304-114">namespace</span><span class="sxs-lookup"><span data-stu-id="8b304-114">namespace</span></span>|<span data-ttu-id="8b304-115">一个包含命名空间的字符串。</span><span class="sxs-lookup"><span data-stu-id="8b304-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="8b304-116">prefix</span><span class="sxs-lookup"><span data-stu-id="8b304-116">prefix</span></span>|<span data-ttu-id="8b304-117">一个包含此命名空间的前缀的字符串。</span><span class="sxs-lookup"><span data-stu-id="8b304-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8b304-118">子元素</span><span class="sxs-lookup"><span data-stu-id="8b304-118">Child Elements</span></span>  
 <span data-ttu-id="8b304-119">无。</span><span class="sxs-lookup"><span data-stu-id="8b304-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8b304-120">父元素</span><span class="sxs-lookup"><span data-stu-id="8b304-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8b304-121">元素</span><span class="sxs-lookup"><span data-stu-id="8b304-121">Element</span></span>|<span data-ttu-id="8b304-122">描述</span><span class="sxs-lookup"><span data-stu-id="8b304-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b304-123">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="8b304-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="8b304-124">表示用于定义一组元素的配置节，这些元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。</span><span class="sxs-lookup"><span data-stu-id="8b304-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b304-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b304-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>

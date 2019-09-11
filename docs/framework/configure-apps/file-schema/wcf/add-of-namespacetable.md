---
title: <add> 的 <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 3b3b4a1584b37601269368ee0e4e973626ddf9cf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850393"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="3c59f-102">\<添加 namespaceTable > \<的 ></span><span class="sxs-lookup"><span data-stu-id="3c59f-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="3c59f-103">表示一个配置元素，此元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3c59f-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
<span data-ttu-id="3c59f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3c59f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3c59f-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3c59f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3c59f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<路由 >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="3c59f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="3c59f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namespaceTable >** ](namespacetable.md)</span><span class="sxs-lookup"><span data-stu-id="3c59f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)</span></span>\
<span data-ttu-id="3c59f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="3c59f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c59f-109">语法</span><span class="sxs-lookup"><span data-stu-id="3c59f-109">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c59f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3c59f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3c59f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3c59f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c59f-112">特性</span><span class="sxs-lookup"><span data-stu-id="3c59f-112">Attributes</span></span>  
  
|<span data-ttu-id="3c59f-113">特性</span><span class="sxs-lookup"><span data-stu-id="3c59f-113">Attribute</span></span>|<span data-ttu-id="3c59f-114">描述</span><span class="sxs-lookup"><span data-stu-id="3c59f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c59f-115">namespace</span><span class="sxs-lookup"><span data-stu-id="3c59f-115">namespace</span></span>|<span data-ttu-id="3c59f-116">一个包含命名空间的字符串。</span><span class="sxs-lookup"><span data-stu-id="3c59f-116">A string containing the namespace.</span></span>|  
|<span data-ttu-id="3c59f-117">prefix</span><span class="sxs-lookup"><span data-stu-id="3c59f-117">prefix</span></span>|<span data-ttu-id="3c59f-118">一个包含此命名空间的前缀的字符串。</span><span class="sxs-lookup"><span data-stu-id="3c59f-118">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c59f-119">子元素</span><span class="sxs-lookup"><span data-stu-id="3c59f-119">Child Elements</span></span>  
 <span data-ttu-id="3c59f-120">无。</span><span class="sxs-lookup"><span data-stu-id="3c59f-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c59f-121">父元素</span><span class="sxs-lookup"><span data-stu-id="3c59f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3c59f-122">元素</span><span class="sxs-lookup"><span data-stu-id="3c59f-122">Element</span></span>|<span data-ttu-id="3c59f-123">描述</span><span class="sxs-lookup"><span data-stu-id="3c59f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c59f-124">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="3c59f-124">\<namespaceTable></span></span>](namespacetable.md)|<span data-ttu-id="3c59f-125">表示用于定义一组元素的配置节，这些元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3c59f-125">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c59f-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c59f-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>

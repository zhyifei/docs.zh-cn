---
title: '&lt;system.runtime.serialization&gt;'
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: 6321ab192161468142a4cd4d2155d3f787bb0165
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600256"
---
# <a name="ltsystemruntimeserializationgt"></a><span data-ttu-id="8317c-102">&lt;system.runtime.serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="8317c-102">&lt;system.runtime.serialization&gt;</span></span>
<span data-ttu-id="8317c-103">表示 <xref:System.Runtime.Serialization> 命名空间节的根元素，并包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的设置选项的元素。</span><span class="sxs-lookup"><span data-stu-id="8317c-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="8317c-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="8317c-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8317c-105">语法</span><span class="sxs-lookup"><span data-stu-id="8317c-105">Syntax</span></span>  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8317c-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8317c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="8317c-107">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8317c-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8317c-108">特性</span><span class="sxs-lookup"><span data-stu-id="8317c-108">Attributes</span></span>  
 <span data-ttu-id="8317c-109">无。</span><span class="sxs-lookup"><span data-stu-id="8317c-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8317c-110">子元素</span><span class="sxs-lookup"><span data-stu-id="8317c-110">Child Elements</span></span>  
  
|<span data-ttu-id="8317c-111">元素</span><span class="sxs-lookup"><span data-stu-id="8317c-111">Element</span></span>|<span data-ttu-id="8317c-112">描述</span><span class="sxs-lookup"><span data-stu-id="8317c-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8317c-113">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="8317c-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="8317c-114">使得可以在反序列化时添加要使用的已知类型。</span><span class="sxs-lookup"><span data-stu-id="8317c-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8317c-115">父元素</span><span class="sxs-lookup"><span data-stu-id="8317c-115">Parent Elements</span></span>  
  
|<span data-ttu-id="8317c-116">元素</span><span class="sxs-lookup"><span data-stu-id="8317c-116">Element</span></span>|<span data-ttu-id="8317c-117">描述</span><span class="sxs-lookup"><span data-stu-id="8317c-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8317c-118">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="8317c-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="8317c-119">配置的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="8317c-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8317c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8317c-120">See also</span></span>
- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="8317c-121">使用数据协定</span><span class="sxs-lookup"><span data-stu-id="8317c-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="8317c-122">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="8317c-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)

---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: 4ec5cd19ccdc5c21a3caf426520d51442dc5ab3f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938927"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="ca696-102">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="ca696-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="ca696-103">表示 <xref:System.Runtime.Serialization> 命名空间节的根元素，并包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的设置选项的元素。</span><span class="sxs-lookup"><span data-stu-id="ca696-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="ca696-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="ca696-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca696-105">语法</span><span class="sxs-lookup"><span data-stu-id="ca696-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca696-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ca696-106">Attributes and Elements</span></span>  
 <span data-ttu-id="ca696-107">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ca696-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca696-108">特性</span><span class="sxs-lookup"><span data-stu-id="ca696-108">Attributes</span></span>  
 <span data-ttu-id="ca696-109">无。</span><span class="sxs-lookup"><span data-stu-id="ca696-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ca696-110">子元素</span><span class="sxs-lookup"><span data-stu-id="ca696-110">Child Elements</span></span>  
  
|<span data-ttu-id="ca696-111">元素</span><span class="sxs-lookup"><span data-stu-id="ca696-111">Element</span></span>|<span data-ttu-id="ca696-112">描述</span><span class="sxs-lookup"><span data-stu-id="ca696-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca696-113">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="ca696-113">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="ca696-114">使得可以在反序列化时添加要使用的已知类型。</span><span class="sxs-lookup"><span data-stu-id="ca696-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ca696-115">父元素</span><span class="sxs-lookup"><span data-stu-id="ca696-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ca696-116">元素</span><span class="sxs-lookup"><span data-stu-id="ca696-116">Element</span></span>|<span data-ttu-id="ca696-117">描述</span><span class="sxs-lookup"><span data-stu-id="ca696-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca696-118">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="ca696-118">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="ca696-119">配置的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="ca696-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca696-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca696-120">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="ca696-121">使用数据协定</span><span class="sxs-lookup"><span data-stu-id="ca696-121">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="ca696-122">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="ca696-122">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)

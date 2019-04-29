---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c34eba2614a354f1753d8da077f8653f2c260a97
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757906"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="2ce19-102">\<system.runtime.serialization></span><span class="sxs-lookup"><span data-stu-id="2ce19-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="2ce19-103">表示 <xref:System.Runtime.Serialization> 命名空间节的根元素，并包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的设置选项的元素。</span><span class="sxs-lookup"><span data-stu-id="2ce19-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="2ce19-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="2ce19-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ce19-105">语法</span><span class="sxs-lookup"><span data-stu-id="2ce19-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ce19-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2ce19-106">Attributes and Elements</span></span>  
 <span data-ttu-id="2ce19-107">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2ce19-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ce19-108">特性</span><span class="sxs-lookup"><span data-stu-id="2ce19-108">Attributes</span></span>  
 <span data-ttu-id="2ce19-109">无。</span><span class="sxs-lookup"><span data-stu-id="2ce19-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2ce19-110">子元素</span><span class="sxs-lookup"><span data-stu-id="2ce19-110">Child Elements</span></span>  
  
|<span data-ttu-id="2ce19-111">元素</span><span class="sxs-lookup"><span data-stu-id="2ce19-111">Element</span></span>|<span data-ttu-id="2ce19-112">描述</span><span class="sxs-lookup"><span data-stu-id="2ce19-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ce19-113">\<dataContractSerializer></span><span class="sxs-lookup"><span data-stu-id="2ce19-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="2ce19-114">使得可以在反序列化时添加要使用的已知类型。</span><span class="sxs-lookup"><span data-stu-id="2ce19-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ce19-115">父元素</span><span class="sxs-lookup"><span data-stu-id="2ce19-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2ce19-116">元素</span><span class="sxs-lookup"><span data-stu-id="2ce19-116">Element</span></span>|<span data-ttu-id="2ce19-117">描述</span><span class="sxs-lookup"><span data-stu-id="2ce19-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ce19-118">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="2ce19-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="2ce19-119">配置的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="2ce19-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ce19-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ce19-120">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="2ce19-121">使用数据协定</span><span class="sxs-lookup"><span data-stu-id="2ce19-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="2ce19-122">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="2ce19-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)

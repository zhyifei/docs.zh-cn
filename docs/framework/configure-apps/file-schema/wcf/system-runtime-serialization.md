---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c93a1f482882cc8cd9d229d82597efa64ba209bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152965"
---
# <a name="systemruntimeserialization"></a><span data-ttu-id="65282-102">\<系统.运行时.序列化></span><span class="sxs-lookup"><span data-stu-id="65282-102">\<system.runtime.serialization></span></span>
<span data-ttu-id="65282-103">表示 <xref:System.Runtime.Serialization> 命名空间节的根元素，并包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的设置选项的元素。</span><span class="sxs-lookup"><span data-stu-id="65282-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  

<span data-ttu-id="65282-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="65282-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="65282-105">&nbsp;&nbsp;**\<系统.运行时.序列化>**</span><span class="sxs-lookup"><span data-stu-id="65282-105">&nbsp;&nbsp;**\<system.runtime.serialization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65282-106">语法</span><span class="sxs-lookup"><span data-stu-id="65282-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65282-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="65282-107">Attributes and Elements</span></span>  
 <span data-ttu-id="65282-108">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="65282-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65282-109">属性</span><span class="sxs-lookup"><span data-stu-id="65282-109">Attributes</span></span>  
 <span data-ttu-id="65282-110">无。</span><span class="sxs-lookup"><span data-stu-id="65282-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="65282-111">子元素</span><span class="sxs-lookup"><span data-stu-id="65282-111">Child Elements</span></span>  
  
|<span data-ttu-id="65282-112">元素</span><span class="sxs-lookup"><span data-stu-id="65282-112">Element</span></span>|<span data-ttu-id="65282-113">说明</span><span class="sxs-lookup"><span data-stu-id="65282-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65282-114">\<数据合同序列化器></span><span class="sxs-lookup"><span data-stu-id="65282-114">\<dataContractSerializer></span></span>](datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="65282-115">使得可以在反序列化时添加要使用的已知类型。</span><span class="sxs-lookup"><span data-stu-id="65282-115">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="65282-116">父元素</span><span class="sxs-lookup"><span data-stu-id="65282-116">Parent Elements</span></span>  
  
|<span data-ttu-id="65282-117">元素</span><span class="sxs-lookup"><span data-stu-id="65282-117">Element</span></span>|<span data-ttu-id="65282-118">说明</span><span class="sxs-lookup"><span data-stu-id="65282-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="65282-119">\<配置>元素</span><span class="sxs-lookup"><span data-stu-id="65282-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="65282-120">配置的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="65282-120">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65282-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65282-121">See also</span></span>

- <xref:System.Runtime.Serialization>
- [<span data-ttu-id="65282-122">使用数据协定</span><span class="sxs-lookup"><span data-stu-id="65282-122">Using Data Contracts</span></span>](../../../wcf/feature-details/using-data-contracts.md)
- [<span data-ttu-id="65282-123">数据协定 已知类型</span><span class="sxs-lookup"><span data-stu-id="65282-123">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)

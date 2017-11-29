---
title: '&lt;system.runtime.serialization&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5a47417ded6e0917fadf2134eed5997d9d3b3d74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltsystemruntimeserializationgt"></a><span data-ttu-id="6e1eb-102">&lt;system.runtime.serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="6e1eb-102">&lt;system.runtime.serialization&gt;</span></span>
<span data-ttu-id="6e1eb-103">表示 <xref:System.Runtime.Serialization> 命名空间节的根元素，并包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的设置选项的元素。</span><span class="sxs-lookup"><span data-stu-id="6e1eb-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="6e1eb-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="6e1eb-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e1eb-105">语法</span><span class="sxs-lookup"><span data-stu-id="6e1eb-105">Syntax</span></span>  
  
```xml  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer">  
      <declaredTypes>  
        <add type="String ">  
          <knownType type="String">  
             <parameter index="Integer"/>  
          </knownType>  
        </add>  
      </declaredTypes>  
    <dataContractSerializer>  
  </system.runtime.serialization>  
</configuration>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e1eb-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6e1eb-106">Attributes and Elements</span></span>  
 <span data-ttu-id="6e1eb-107">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6e1eb-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e1eb-108">特性</span><span class="sxs-lookup"><span data-stu-id="6e1eb-108">Attributes</span></span>  
 <span data-ttu-id="6e1eb-109">无。</span><span class="sxs-lookup"><span data-stu-id="6e1eb-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6e1eb-110">子元素</span><span class="sxs-lookup"><span data-stu-id="6e1eb-110">Child Elements</span></span>  
  
|<span data-ttu-id="6e1eb-111">元素</span><span class="sxs-lookup"><span data-stu-id="6e1eb-111">Element</span></span>|<span data-ttu-id="6e1eb-112">描述</span><span class="sxs-lookup"><span data-stu-id="6e1eb-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e1eb-113">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="6e1eb-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="6e1eb-114">使得可以在反序列化时添加要使用的已知类型。</span><span class="sxs-lookup"><span data-stu-id="6e1eb-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6e1eb-115">父元素</span><span class="sxs-lookup"><span data-stu-id="6e1eb-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6e1eb-116">元素</span><span class="sxs-lookup"><span data-stu-id="6e1eb-116">Element</span></span>|<span data-ttu-id="6e1eb-117">描述</span><span class="sxs-lookup"><span data-stu-id="6e1eb-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e1eb-118">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="6e1eb-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="6e1eb-119">配置的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="6e1eb-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e1eb-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e1eb-120">See Also</span></span>  
 <xref:System.Runtime.Serialization>  
 [<span data-ttu-id="6e1eb-121">使用数据协定</span><span class="sxs-lookup"><span data-stu-id="6e1eb-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="6e1eb-122">数据协定已知的类型</span><span class="sxs-lookup"><span data-stu-id="6e1eb-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)

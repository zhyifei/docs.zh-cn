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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ab66252ebc5b87c197b3e4ac7b6def9355e5f201
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemruntimeserializationgt"></a><span data-ttu-id="bd53e-102">&lt;system.runtime.serialization&gt;</span><span class="sxs-lookup"><span data-stu-id="bd53e-102">&lt;system.runtime.serialization&gt;</span></span>
<span data-ttu-id="bd53e-103">表示 <xref:System.Runtime.Serialization> 命名空间节的根元素，并包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的设置选项的元素。</span><span class="sxs-lookup"><span data-stu-id="bd53e-103">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
 <span data-ttu-id="bd53e-104">system.runtime.serialization</span><span class="sxs-lookup"><span data-stu-id="bd53e-104">system.runtime.serialization</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd53e-105">语法</span><span class="sxs-lookup"><span data-stu-id="bd53e-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd53e-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bd53e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="bd53e-107">以下几节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bd53e-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd53e-108">特性</span><span class="sxs-lookup"><span data-stu-id="bd53e-108">Attributes</span></span>  
 <span data-ttu-id="bd53e-109">无。</span><span class="sxs-lookup"><span data-stu-id="bd53e-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bd53e-110">子元素</span><span class="sxs-lookup"><span data-stu-id="bd53e-110">Child Elements</span></span>  
  
|<span data-ttu-id="bd53e-111">元素</span><span class="sxs-lookup"><span data-stu-id="bd53e-111">Element</span></span>|<span data-ttu-id="bd53e-112">描述</span><span class="sxs-lookup"><span data-stu-id="bd53e-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd53e-113">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="bd53e-113">\<dataContractSerializer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|<span data-ttu-id="bd53e-114">使得可以在反序列化时添加要使用的已知类型。</span><span class="sxs-lookup"><span data-stu-id="bd53e-114">Enables addition of known types to be used when deserialization.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd53e-115">父元素</span><span class="sxs-lookup"><span data-stu-id="bd53e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="bd53e-116">元素</span><span class="sxs-lookup"><span data-stu-id="bd53e-116">Element</span></span>|<span data-ttu-id="bd53e-117">描述</span><span class="sxs-lookup"><span data-stu-id="bd53e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd53e-118">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="bd53e-118">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="bd53e-119">配置的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="bd53e-119">The top level element for configuration.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd53e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd53e-120">See Also</span></span>  
 <xref:System.Runtime.Serialization>  
 [<span data-ttu-id="bd53e-121">使用数据协定</span><span class="sxs-lookup"><span data-stu-id="bd53e-121">Using Data Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="bd53e-122">数据协定已知类型</span><span class="sxs-lookup"><span data-stu-id="bd53e-122">Data Contract Known Types</span></span>](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)

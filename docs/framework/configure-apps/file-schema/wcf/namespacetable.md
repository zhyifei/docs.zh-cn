---
title: '&lt;namespaceTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4a6646b94449a79c96a8720a798f48298ab32ee0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="272e2-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="272e2-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="272e2-103">表示用于定义一组元素的配置节，这些元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。</span><span class="sxs-lookup"><span data-stu-id="272e2-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="272e2-104">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="272e2-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="272e2-105">&nbsp;&nbsp;**\<路由 >** </span><span class="sxs-lookup"><span data-stu-id="272e2-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="272e2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="272e2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>

## <a name="syntax"></a><span data-ttu-id="272e2-107">语法</span><span class="sxs-lookup"><span data-stu-id="272e2-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
``` 

## <a name="attributes-and-elements"></a><span data-ttu-id="272e2-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="272e2-108">Attributes and elements</span></span>

<span data-ttu-id="272e2-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="272e2-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="272e2-110">特性</span><span class="sxs-lookup"><span data-stu-id="272e2-110">Attributes</span></span>

<span data-ttu-id="272e2-111">无</span><span class="sxs-lookup"><span data-stu-id="272e2-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="272e2-112">子元素</span><span class="sxs-lookup"><span data-stu-id="272e2-112">Child elements</span></span>

|     | <span data-ttu-id="272e2-113">描述</span><span class="sxs-lookup"><span data-stu-id="272e2-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="272e2-114">**\<筛选器 >**</span><span class="sxs-lookup"><span data-stu-id="272e2-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="272e2-115">定义用于 XPath 表达式的命名空间前缀映射。</span><span class="sxs-lookup"><span data-stu-id="272e2-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="272e2-116">父元素</span><span class="sxs-lookup"><span data-stu-id="272e2-116">Parent elements</span></span>

|     | <span data-ttu-id="272e2-117">描述</span><span class="sxs-lookup"><span data-stu-id="272e2-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="272e2-118">**\<路由 >**</span><span class="sxs-lookup"><span data-stu-id="272e2-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="272e2-119">表示用于定义一组路由筛选器的配置节，这些筛选器确定计算传入消息时使用的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> 的类型，以及用于定义在筛选器匹配时消息发送到的目标终结点的路由表。</span><span class="sxs-lookup"><span data-stu-id="272e2-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="272e2-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="272e2-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>

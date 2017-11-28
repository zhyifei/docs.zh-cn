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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 470dd2dcc2e8554bb89eec159c6b96b24795c5d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="02783-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="02783-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="02783-103">表示用于定义一组元素的配置节，这些元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。</span><span class="sxs-lookup"><span data-stu-id="02783-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="02783-104">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="02783-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="02783-105">&nbsp;&nbsp;**\<路由 >** </span><span class="sxs-lookup"><span data-stu-id="02783-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="02783-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="02783-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>

## <a name="syntax"></a><span data-ttu-id="02783-107">语法</span><span class="sxs-lookup"><span data-stu-id="02783-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
``` 

## <a name="attributes-and-elements"></a><span data-ttu-id="02783-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="02783-108">Attributes and elements</span></span>

<span data-ttu-id="02783-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="02783-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="02783-110">特性</span><span class="sxs-lookup"><span data-stu-id="02783-110">Attributes</span></span>

<span data-ttu-id="02783-111">无</span><span class="sxs-lookup"><span data-stu-id="02783-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="02783-112">子元素</span><span class="sxs-lookup"><span data-stu-id="02783-112">Child elements</span></span>

|     | <span data-ttu-id="02783-113">描述</span><span class="sxs-lookup"><span data-stu-id="02783-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="02783-114">**\<筛选器 >**</span><span class="sxs-lookup"><span data-stu-id="02783-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="02783-115">定义用于 XPath 表达式的命名空间前缀映射。</span><span class="sxs-lookup"><span data-stu-id="02783-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="02783-116">父元素</span><span class="sxs-lookup"><span data-stu-id="02783-116">Parent elements</span></span>

|     | <span data-ttu-id="02783-117">描述</span><span class="sxs-lookup"><span data-stu-id="02783-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="02783-118">**\<路由 >**</span><span class="sxs-lookup"><span data-stu-id="02783-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="02783-119">表示用于定义一组路由筛选器的配置节，这些筛选器确定计算传入消息时使用的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> 的类型，以及用于定义在筛选器匹配时消息发送到的目标终结点的路由表。</span><span class="sxs-lookup"><span data-stu-id="02783-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="02783-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="02783-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>

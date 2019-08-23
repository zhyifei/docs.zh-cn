---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 0316e983446644671ead2f8f843dc91b493b29c9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933170"
---
# <a name="namespacetable"></a><span data-ttu-id="9e5d8-101">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="9e5d8-101">\<namespaceTable></span></span>

<span data-ttu-id="9e5d8-102">表示用于定义一组元素的配置节，这些元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。</span><span class="sxs-lookup"><span data-stu-id="9e5d8-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="9e5d8-103">**\<system.serviceModel>**  </span><span class="sxs-lookup"><span data-stu-id="9e5d8-103">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="9e5d8-104">&nbsp;&nbsp; **\<routing>**  </span><span class="sxs-lookup"><span data-stu-id="9e5d8-104">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="9e5d8-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<namespaceTable>**</span><span class="sxs-lookup"><span data-stu-id="9e5d8-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="9e5d8-106">语法</span><span class="sxs-lookup"><span data-stu-id="9e5d8-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String"
           prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e5d8-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9e5d8-107">Attributes and elements</span></span>

<span data-ttu-id="9e5d8-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9e5d8-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9e5d8-109">特性</span><span class="sxs-lookup"><span data-stu-id="9e5d8-109">Attributes</span></span>

<span data-ttu-id="9e5d8-110">无</span><span class="sxs-lookup"><span data-stu-id="9e5d8-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="9e5d8-111">子元素</span><span class="sxs-lookup"><span data-stu-id="9e5d8-111">Child elements</span></span>

|     | <span data-ttu-id="9e5d8-112">描述</span><span class="sxs-lookup"><span data-stu-id="9e5d8-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9e5d8-113"> **\<filter>** </span><span class="sxs-lookup"><span data-stu-id="9e5d8-113">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="9e5d8-114">定义用于 XPath 表达式的命名空间前缀映射。</span><span class="sxs-lookup"><span data-stu-id="9e5d8-114">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="9e5d8-115">父元素</span><span class="sxs-lookup"><span data-stu-id="9e5d8-115">Parent elements</span></span>

|     | <span data-ttu-id="9e5d8-116">描述</span><span class="sxs-lookup"><span data-stu-id="9e5d8-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9e5d8-117"> **\<routing>** </span><span class="sxs-lookup"><span data-stu-id="9e5d8-117">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="9e5d8-118">表示用于定义一组路由筛选器的配置节, 这些筛选器确定计算传入消息时要<xref:System.ServiceModel.Dispatcher.MessageFilter>使用的 Windows Communication Foundation (WCF) 的类型, 以及用于定义目标终结点的路由表。当筛选器匹配时向发送消息。</span><span class="sxs-lookup"><span data-stu-id="9e5d8-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="9e5d8-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e5d8-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>

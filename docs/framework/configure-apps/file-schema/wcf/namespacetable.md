---
title: '&lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 31d661f39f9e3de0f7012c7fa52d4964e7ee4a69
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748875"
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="4fb3f-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="4fb3f-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="4fb3f-103">表示用于定义一组元素的配置节，这些元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。</span><span class="sxs-lookup"><span data-stu-id="4fb3f-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="4fb3f-104">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="4fb3f-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="4fb3f-105">&nbsp;&nbsp;**\<路由 >** </span><span class="sxs-lookup"><span data-stu-id="4fb3f-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="4fb3f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="4fb3f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4fb3f-107">语法</span><span class="sxs-lookup"><span data-stu-id="4fb3f-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
``` 

## <a name="attributes-and-elements"></a><span data-ttu-id="4fb3f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4fb3f-108">Attributes and elements</span></span>

<span data-ttu-id="4fb3f-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4fb3f-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="4fb3f-110">特性</span><span class="sxs-lookup"><span data-stu-id="4fb3f-110">Attributes</span></span>

<span data-ttu-id="4fb3f-111">无</span><span class="sxs-lookup"><span data-stu-id="4fb3f-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="4fb3f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4fb3f-112">Child elements</span></span>

|     | <span data-ttu-id="4fb3f-113">描述</span><span class="sxs-lookup"><span data-stu-id="4fb3f-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4fb3f-114">**\<筛选器 >**</span><span class="sxs-lookup"><span data-stu-id="4fb3f-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="4fb3f-115">定义用于 XPath 表达式的命名空间前缀映射。</span><span class="sxs-lookup"><span data-stu-id="4fb3f-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="4fb3f-116">父元素</span><span class="sxs-lookup"><span data-stu-id="4fb3f-116">Parent elements</span></span>

|     | <span data-ttu-id="4fb3f-117">描述</span><span class="sxs-lookup"><span data-stu-id="4fb3f-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="4fb3f-118">**\<路由 >**</span><span class="sxs-lookup"><span data-stu-id="4fb3f-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="4fb3f-119">表示一个配置节，用于定义一组路由筛选器，这些扩展名决定了类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>计算传入消息，以及路由表定义到的目标终结点时使用将消息发送到筛选器匹配时。</span><span class="sxs-lookup"><span data-stu-id="4fb3f-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4fb3f-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="4fb3f-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>

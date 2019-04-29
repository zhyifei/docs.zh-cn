---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: ee7a0c23adca883af279addf9d1f221bd4056d00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772406"
---
# <a name="namespacetable"></a><span data-ttu-id="23740-101">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="23740-101">\<namespaceTable></span></span>

<span data-ttu-id="23740-102">表示用于定义一组元素的配置节，这些元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。</span><span class="sxs-lookup"><span data-stu-id="23740-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="23740-103">**\<system.serviceModel>** </span><span class="sxs-lookup"><span data-stu-id="23740-103">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="23740-104">&nbsp;&nbsp;**\<routing>** </span><span class="sxs-lookup"><span data-stu-id="23740-104">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="23740-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span><span class="sxs-lookup"><span data-stu-id="23740-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="23740-106">语法</span><span class="sxs-lookup"><span data-stu-id="23740-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23740-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="23740-107">Attributes and elements</span></span>

<span data-ttu-id="23740-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="23740-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="23740-109">特性</span><span class="sxs-lookup"><span data-stu-id="23740-109">Attributes</span></span>

<span data-ttu-id="23740-110">None</span><span class="sxs-lookup"><span data-stu-id="23740-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="23740-111">子元素</span><span class="sxs-lookup"><span data-stu-id="23740-111">Child elements</span></span>

|     | <span data-ttu-id="23740-112">描述</span><span class="sxs-lookup"><span data-stu-id="23740-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="23740-113">**\<filter>**</span><span class="sxs-lookup"><span data-stu-id="23740-113">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="23740-114">定义用于 XPath 表达式的命名空间前缀映射。</span><span class="sxs-lookup"><span data-stu-id="23740-114">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="23740-115">父元素</span><span class="sxs-lookup"><span data-stu-id="23740-115">Parent elements</span></span>

|     | <span data-ttu-id="23740-116">描述</span><span class="sxs-lookup"><span data-stu-id="23740-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="23740-117">**\<routing>**</span><span class="sxs-lookup"><span data-stu-id="23740-117">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="23740-118">表示一个配置节，用于定义一组路由筛选器，确定类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>用于计算传入消息，以及路由表定义到的目标终结点将消息发送到筛选器匹配时。</span><span class="sxs-lookup"><span data-stu-id="23740-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="23740-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="23740-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>

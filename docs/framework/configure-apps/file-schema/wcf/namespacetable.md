---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: aefe7beec7335d80341e670961800907c2bd0200
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855096"
---
# <a name="namespacetable"></a><span data-ttu-id="395aa-101">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="395aa-101">\<namespaceTable></span></span>

<span data-ttu-id="395aa-102">表示用于定义一组元素的配置节，这些元素包含随后可在 XPath 筛选器中用于路由的前缀映射的命名空间。</span><span class="sxs-lookup"><span data-stu-id="395aa-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="395aa-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="395aa-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="395aa-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="395aa-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="395aa-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<路由 >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="395aa-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="395aa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="395aa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="395aa-107">语法</span><span class="sxs-lookup"><span data-stu-id="395aa-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="395aa-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="395aa-108">Attributes and elements</span></span>

<span data-ttu-id="395aa-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="395aa-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="395aa-110">特性</span><span class="sxs-lookup"><span data-stu-id="395aa-110">Attributes</span></span>

<span data-ttu-id="395aa-111">无</span><span class="sxs-lookup"><span data-stu-id="395aa-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="395aa-112">子元素</span><span class="sxs-lookup"><span data-stu-id="395aa-112">Child elements</span></span>

|     | <span data-ttu-id="395aa-113">描述</span><span class="sxs-lookup"><span data-stu-id="395aa-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="395aa-114"> **\<filter>** </span><span class="sxs-lookup"><span data-stu-id="395aa-114">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="395aa-115">定义用于 XPath 表达式的命名空间前缀映射。</span><span class="sxs-lookup"><span data-stu-id="395aa-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="395aa-116">父元素</span><span class="sxs-lookup"><span data-stu-id="395aa-116">Parent elements</span></span>

|     | <span data-ttu-id="395aa-117">描述</span><span class="sxs-lookup"><span data-stu-id="395aa-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="395aa-118"> **\<routing>** </span><span class="sxs-lookup"><span data-stu-id="395aa-118">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="395aa-119">表示用于定义一组路由筛选器的配置节，这些筛选器确定计算传入消息时要<xref:System.ServiceModel.Dispatcher.MessageFilter>使用的 Windows Communication Foundation （WCF）的类型，以及用于定义目标终结点的路由表。当筛选器匹配时向发送消息。</span><span class="sxs-lookup"><span data-stu-id="395aa-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="395aa-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="395aa-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>

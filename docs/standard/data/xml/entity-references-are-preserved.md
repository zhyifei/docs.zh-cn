---
title: 保留实体引用
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e512f2077c2e6b9feba5024c4eabc2568357ecab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965919"
---
# <a name="entity-references-are-preserved"></a><span data-ttu-id="a89c1-102">保留实体引用</span><span class="sxs-lookup"><span data-stu-id="a89c1-102">Entity References are Preserved</span></span>
<span data-ttu-id="a89c1-103">如果实体引用不是被扩展，而是被暂留，XML 文档对象模型 (DOM) 在遇到实体引用时生成 XmlEntityReference  节点。</span><span class="sxs-lookup"><span data-stu-id="a89c1-103">When the entity reference is not expanded, but preserved, the XML Document Object Model (DOM) builds an **XmlEntityReference** node when it encounters an entity reference.</span></span>  
  
 <span data-ttu-id="a89c1-104">使用以下 XML，</span><span class="sxs-lookup"><span data-stu-id="a89c1-104">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="a89c1-105">DOM 可以在遇到 `&publisher;` 引用时生成 XmlEntityReference  节点。</span><span class="sxs-lookup"><span data-stu-id="a89c1-105">the DOM builds an **XmlEntityReference** node when it encounters the `&publisher;` reference.</span></span> <span data-ttu-id="a89c1-106">XmlEntityReference  包含从实体声明内容中复制的子节点。</span><span class="sxs-lookup"><span data-stu-id="a89c1-106">The **XmlEntityReference** contains child nodes copied from the content in the entity declaration.</span></span> <span data-ttu-id="a89c1-107">由于上一代码示例包含实体声明文本，因此 XmlText  节点被创建为实体引用节点的子节点。</span><span class="sxs-lookup"><span data-stu-id="a89c1-107">The preceding code example contains text in the entity declaration, so an **XmlText** node is created as the child node of the entity reference node.</span></span>  
  
 <span data-ttu-id="a89c1-108">![暂留的实体引用的树结构](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span><span class="sxs-lookup"><span data-stu-id="a89c1-108">![Tree structure for preserved entity references](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span></span>  
<span data-ttu-id="a89c1-109">保留的实体引用的树结构</span><span class="sxs-lookup"><span data-stu-id="a89c1-109">Tree structure for entity references that are preserved</span></span>  
  
 <span data-ttu-id="a89c1-110">XmlEntityReference  的子节点是在遇到实体声明时，从 XmlEntity  节点创建的所有子节点的副本。</span><span class="sxs-lookup"><span data-stu-id="a89c1-110">The child nodes of the **XmlEntityReference** are copies of all the child nodes created from the **XmlEntity** node when the entity declaration was encountered.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a89c1-111">一旦置于实体引用节点下，从 XmlEntity  复制的节点就不一定是完全相同的副本。</span><span class="sxs-lookup"><span data-stu-id="a89c1-111">The nodes copied from the **XmlEntity** are not always exact copies once placed under the entity reference node.</span></span> <span data-ttu-id="a89c1-112">可以有在实体引用节点范围内并影响子节点的最终配置的命名空间。</span><span class="sxs-lookup"><span data-stu-id="a89c1-112">There can be namespaces that are in scope at the entity reference node, and that affects the final configuration of the child nodes.</span></span>  
  
 <span data-ttu-id="a89c1-113">默认情况下，暂留的是 `&abc;` 等常规实体，并且始终都会创建 XmlEntityReference  节点。</span><span class="sxs-lookup"><span data-stu-id="a89c1-113">By default, general entities like `&abc;` are preserved and **XmlEntityReference** nodes always created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a89c1-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a89c1-114">See also</span></span>

- [<span data-ttu-id="a89c1-115">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="a89c1-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)

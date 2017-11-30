---
title: "命名空间对包含元素和属性的新节点的实体引用扩展的影响"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64359aee-aab0-4042-9a32-d19789af6ca7
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 39110a9b44e6efbe7ad0331cfdb4fbe6078e7cfc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="namespace-affect-on-entity-reference-expansion-for-new-nodes-containing-elements-and-attributes"></a><span data-ttu-id="d6e8f-102">命名空间对包含元素和属性的新节点的实体引用扩展的影响</span><span class="sxs-lookup"><span data-stu-id="d6e8f-102">Namespace Affect on Entity Reference Expansion for New Nodes Containing Elements and Attributes</span></span>
<span data-ttu-id="d6e8f-103">由于实体声明的内容可以包含几乎所有内容，因此该内容有可能包含像 `<!ENTITY aname "<elem>test</elem>">` 这样的元素。</span><span class="sxs-lookup"><span data-stu-id="d6e8f-103">Because the content of an entity declaration can contain almost anything, there is a possibility that the content could contain an element like `<!ENTITY aname "<elem>test</elem>">`.</span></span>  
  
 <span data-ttu-id="d6e8f-104">分析 XML 时，`&aname;` 在分析时不用其替换内容扩展。</span><span class="sxs-lookup"><span data-stu-id="d6e8f-104">When the XML is parsed, `&aname;` is not expanded with its replacement content at parse time.</span></span> <span data-ttu-id="d6e8f-105">不执行 XML 扩展的原因在于对元素的命名空间解析只有在将节点放入文档中时才发生。</span><span class="sxs-lookup"><span data-stu-id="d6e8f-105">The expansion of the XML is not done because resolution of the namespace for the element cannot occur until the node is placed in the document.</span></span> <span data-ttu-id="d6e8f-106">在此之前，并不知道范围中存在哪个命名空间。</span><span class="sxs-lookup"><span data-stu-id="d6e8f-106">Until that time, there is no knowledge of what namespace is in scope.</span></span> <span data-ttu-id="d6e8f-107">将节点放入文档中后，将进行命名空间解析，生成的实体内容将被分析为相应节点。</span><span class="sxs-lookup"><span data-stu-id="d6e8f-107">When the node is put into the document, then the namespace resolution occurs, and the resulting entity content is parsed into its appropriate nodes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6e8f-108">新创建的实体引用节点进行扩展后，该扩展永远不会再次进行。</span><span class="sxs-lookup"><span data-stu-id="d6e8f-108">Once the expansion occurs on a newly created entity reference node, it never reoccurs.</span></span> <span data-ttu-id="d6e8f-109">因此，在元素的替换文本中使用的命名空间将在设置父节点时绑定。</span><span class="sxs-lookup"><span data-stu-id="d6e8f-109">Therefore, the namespaces used in the replacement text for the element are bound at the time that the parent node is set.</span></span> <span data-ttu-id="d6e8f-110">但是，可以为现有实体引用节点时移除并插入到其他地方，或与克隆的实体引用节点上更改命名空间**CloneNode**方法。</span><span class="sxs-lookup"><span data-stu-id="d6e8f-110">However, the namespace can be changed for existing entity reference nodes when you remove and insert them somewhere else, or on entity reference nodes that are cloned with the **CloneNode** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e8f-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6e8f-111">See Also</span></span>  
 [<span data-ttu-id="d6e8f-112">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="d6e8f-112">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)

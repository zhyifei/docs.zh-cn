---
title: "更改 XML 文档中的命名空间声明"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 627882efcbc41310ee177cba984e4add5b07bd15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a><span data-ttu-id="1add3-102">更改 XML 文档中的命名空间声明</span><span class="sxs-lookup"><span data-stu-id="1add3-102">Changing Namespace Declarations in an XML Document</span></span>
<span data-ttu-id="1add3-103">**XmlDocument**公开命名空间声明和**xmlns**文档对象模型的一部分的属性。</span><span class="sxs-lookup"><span data-stu-id="1add3-103">The **XmlDocument** exposes namespace declarations and **xmlns** attributes as part of the document object model.</span></span> <span data-ttu-id="1add3-104">这些模板存储在**XmlDocument**，因此当保存文档时，可以保留这些特性的位置。</span><span class="sxs-lookup"><span data-stu-id="1add3-104">These are stored in the **XmlDocument**, so when you save the document, it can preserve the location of those attributes.</span></span> <span data-ttu-id="1add3-105">更改这些属性没有任何影响**名称**， **NamespaceURI**，和**前缀**属性对树中的其他节点。</span><span class="sxs-lookup"><span data-stu-id="1add3-105">Changing these attributes has no affect on the **Name**, **NamespaceURI**, and **Prefix** properties of other nodes already in the tree.</span></span> <span data-ttu-id="1add3-106">例如，如果你加载下面的文档中，则`test`元素具有**NamespaceURI**`123.`</span><span class="sxs-lookup"><span data-stu-id="1add3-106">For example, if you load the following document, then the `test` element has **NamespaceURI** `123.`</span></span>  
  
```xml  
<test xmlns="123"/>  
```  
  
 <span data-ttu-id="1add3-107">如果你删除`xmlns`属性，如下所示，则`test`元素仍具有**NamespaceURI**的`123`。</span><span class="sxs-lookup"><span data-stu-id="1add3-107">If you remove the `xmlns` attribute as follows, then the `test` element still has the **NamespaceURI** of `123`.</span></span>  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 <span data-ttu-id="1add3-108">同样，如果你添加为其他`xmlns`属性设为`doc`元素，如下所示，则`test`元素仍具有**NamespaceURI** `123`。</span><span class="sxs-lookup"><span data-stu-id="1add3-108">Likewise, if you add a different `xmlns` attribute to the `doc` element as follows, then the `test` element still has **NamespaceURI** `123`.</span></span>  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 <span data-ttu-id="1add3-109">因此，更改`xmlns`属性会有任何影响，直到保存并重新加载**XmlDocument**对象。</span><span class="sxs-lookup"><span data-stu-id="1add3-109">Therefore, changing `xmlns` attributes will have no affect until you save and reload the **XmlDocument** object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1add3-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1add3-110">See Also</span></span>  
 [<span data-ttu-id="1add3-111">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="1add3-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)

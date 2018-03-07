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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6db78e689b8529ef62a3b42c2cefb6a5b3d3f02f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a><span data-ttu-id="cf7ca-102">更改 XML 文档中的命名空间声明</span><span class="sxs-lookup"><span data-stu-id="cf7ca-102">Changing Namespace Declarations in an XML Document</span></span>
<span data-ttu-id="cf7ca-103">XmlDocument 将命名空间声明和 xmlns 属性公开为文档对象模型的一部分。</span><span class="sxs-lookup"><span data-stu-id="cf7ca-103">The **XmlDocument** exposes namespace declarations and **xmlns** attributes as part of the document object model.</span></span> <span data-ttu-id="cf7ca-104">这些声明和属性存储在 XmlDocument 中，因此在可以保存文档时暂留这些属性的位置。</span><span class="sxs-lookup"><span data-stu-id="cf7ca-104">These are stored in the **XmlDocument**, so when you save the document, it can preserve the location of those attributes.</span></span> <span data-ttu-id="cf7ca-105">更改这些属性对树中现有其他节点的 Name、NamespaceURI 和 Prefix 属性没有影响。</span><span class="sxs-lookup"><span data-stu-id="cf7ca-105">Changing these attributes has no affect on the **Name**, **NamespaceURI**, and **Prefix** properties of other nodes already in the tree.</span></span> <span data-ttu-id="cf7ca-106">例如，如果加载以下文档，`test` 元素包含 NamespaceURI `123.`</span><span class="sxs-lookup"><span data-stu-id="cf7ca-106">For example, if you load the following document, then the `test` element has **NamespaceURI** `123.`</span></span>  
  
```xml  
<test xmlns="123"/>  
```  
  
 <span data-ttu-id="cf7ca-107">如果删除 `xmlns` 属性（如下所示），`test` 元素仍包含 NamespaceURI `123`。</span><span class="sxs-lookup"><span data-stu-id="cf7ca-107">If you remove the `xmlns` attribute as follows, then the `test` element still has the **NamespaceURI** of `123`.</span></span>  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 <span data-ttu-id="cf7ca-108">同样，如果将不同的 `xmlns` 属性添加到 `doc` 元素（如下所示），`test` 元素仍包含 NamespaceURI `123`。</span><span class="sxs-lookup"><span data-stu-id="cf7ca-108">Likewise, if you add a different `xmlns` attribute to the `doc` element as follows, then the `test` element still has **NamespaceURI** `123`.</span></span>  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 <span data-ttu-id="cf7ca-109">因此，保存并重新加载 XmlDocument 对象前，更改 `xmlns` 属性不会有任何影响。</span><span class="sxs-lookup"><span data-stu-id="cf7ca-109">Therefore, changing `xmlns` attributes will have no affect until you save and reload the **XmlDocument** object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf7ca-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf7ca-110">See Also</span></span>  
 [<span data-ttu-id="cf7ca-111">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="cf7ca-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)

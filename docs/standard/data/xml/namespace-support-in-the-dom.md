---
title: "DOM 中的命名空间支持"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0548ead-0fed-41ee-b33e-117ba900d3bc
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3145df6517df9db580bfcc5d67edd9d1a61f290b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="namespace-support-in-the-dom"></a><span data-ttu-id="cae68-102">DOM 中的命名空间支持</span><span class="sxs-lookup"><span data-stu-id="cae68-102">Namespace Support in the DOM</span></span>
<span data-ttu-id="cae68-103">XML 文档对象模型 (DOM) 完全识别命名空间。</span><span class="sxs-lookup"><span data-stu-id="cae68-103">The XML Document Object Model (DOM) is completely namespace-aware.</span></span> <span data-ttu-id="cae68-104">只支持识别命名空间的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="cae68-104">Only namespace-aware XML documents are supported.</span></span> <span data-ttu-id="cae68-105">万维网联合会 (W3C) 指定实现级别 1 的 DOM 应用程序可以不识别命名空间，而 DOM 级别 2 功能识别命名空间。</span><span class="sxs-lookup"><span data-stu-id="cae68-105">The World Wide Web Consortium (W3C) specifies that DOM applications that implement Level 1 can be non-namespace-aware, and DOM Level 2 features are namespace-aware.</span></span> <span data-ttu-id="cae68-106">然而，XML DOM 中的所有功能都识别命名空间，不论该方法来自级别 1 还是级别 2 DOM 建议。</span><span class="sxs-lookup"><span data-stu-id="cae68-106">However, all features in the XML DOM are namespace-aware, regardless if the method is from the Level 1 or Level 2 DOM Recommendation.</span></span>  
  
 <span data-ttu-id="cae68-107">例如，在不识别命名空间的设置中，调用 DOM 级别 1 建议中指定的 `setAttribute("A:b", "123")` 不会生成前缀为 `A`、本地名称为 `b` 的属性。</span><span class="sxs-lookup"><span data-stu-id="cae68-107">For example, in a non-namespace-aware setting, calling `setAttribute("A:b", "123")`, as specified in the DOM Level 1 Recommendation, does not result in an attribute with a prefix of `A` and a local name of `b`.</span></span> <span data-ttu-id="cae68-108">将产生值为 `A:b` 的属性。</span><span class="sxs-lookup"><span data-stu-id="cae68-108">It would result in an attribute with the value `A:b`.</span></span>  
  
 <span data-ttu-id="cae68-109">在识别命名空间的环境中，调用 DOM 级别 2 `setAttribute("A:b", "123")` 将生成前缀为 `A`、本地名称为 `b` 的属性。</span><span class="sxs-lookup"><span data-stu-id="cae68-109">In a namespace-aware environment, the call to the DOM Level 2 `setAttribute("A:b", "123")` results in an attribute with a prefix of `A` and a local name of `b`.</span></span> <span data-ttu-id="cae68-110">这是 Microsoft.NET Framework DOM 的工作原理。</span><span class="sxs-lookup"><span data-stu-id="cae68-110">This is how the Microsoft .NET Framework DOM works.</span></span>  
  
 <span data-ttu-id="cae68-111">因此，对于所有接受名称参数的方法，这些方法也接受用于限定名称的前缀。</span><span class="sxs-lookup"><span data-stu-id="cae68-111">Therefore, for all methods that take a name parameter, these methods also take a prefix to qualify the name.</span></span> <span data-ttu-id="cae68-112">Name 参数，如`A:b`中**setAttribute** DOM 级别 1 方法分析，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cae68-112">The name parameter, such as the `A:b` in the **setAttribute** DOM Level 1 method, is parsed as follows:</span></span>  
  
-   <span data-ttu-id="cae68-113">如果没有冒号 (:) 字符，则本地名称设置为 `name` 参数，而前缀和 NamespaceURI 为空字符串。</span><span class="sxs-lookup"><span data-stu-id="cae68-113">If there are no colon (:) characters, then the local name is set to the `name` parameter, and the prefix and NamespaceURI are empty strings.</span></span>  
  
-   <span data-ttu-id="cae68-114">如果找到冒号，则根据第一个冒号字符的位置将该名称分为两个部分。</span><span class="sxs-lookup"><span data-stu-id="cae68-114">If a colon is found, then the name is split into two parts based on the position of the first colon character.</span></span> <span data-ttu-id="cae68-115">将前缀设置为该冒号前面的字符串，将本地名称设置为该冒号后面的字符串。</span><span class="sxs-lookup"><span data-stu-id="cae68-115">The prefix is set to the string found before the colon, and local name is set to the string found after the colon.</span></span> <span data-ttu-id="cae68-116">对于不接受 NamespaceURI 值的方法，不解析 NamespaceURI 并保持设置为空字符串。</span><span class="sxs-lookup"><span data-stu-id="cae68-116">For methods that do not take a NamespaceURI value, the NamespaceURI is not resolved and remains set to empty string.</span></span> <span data-ttu-id="cae68-117">否则，将 NamespaceURI 设置为传递给该方法的字符串。</span><span class="sxs-lookup"><span data-stu-id="cae68-117">Otherwise, the NamespaceURI is set to the string passed to the method.</span></span> <span data-ttu-id="cae68-118">如果未定义前缀，则**保存**方法和**InnerXml**和**OuterXml**属性将失败。</span><span class="sxs-lookup"><span data-stu-id="cae68-118">If the prefix is undefined, then the **Save** method and **InnerXml** and **OuterXml** properties fail.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cae68-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cae68-119">See Also</span></span>  
 [<span data-ttu-id="cae68-120">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="cae68-120">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)

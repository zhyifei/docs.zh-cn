---
title: "嵌入到文档中的样式表指令"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c5cfcc9f35e4a07e9426a4dd24c1e2f04985f16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="style-sheet-directives-embedded-in-a-document"></a><span data-ttu-id="4579b-102">嵌入到文档中的样式表指令</span><span class="sxs-lookup"><span data-stu-id="4579b-102">Style Sheet Directives Embedded in a Document</span></span>
<span data-ttu-id="4579b-103">有时，现有 XML 会包含 `<?xml:stylesheet?>` 形式的样式表指令。</span><span class="sxs-lookup"><span data-stu-id="4579b-103">Occasionally, existing XML contains the style sheet directive of `<?xml:stylesheet?>`.</span></span> <span data-ttu-id="4579b-104">作为替代方法的 Microsoft Internet Explorer 接受此`<?xml-stylesheet?>`语法。</span><span class="sxs-lookup"><span data-stu-id="4579b-104">Microsoft Internet Explorer accepts this as an alternative to the `<?xml-stylesheet?>` syntax.</span></span> <span data-ttu-id="4579b-105">当 XML 数据包含 `<?xml:stylesheet?>` 指令时（如下面的数据所示），试图将此数据加载到 XML 文档对象模型 (DOM) 中将引发异常。</span><span class="sxs-lookup"><span data-stu-id="4579b-105">When the XML data contains an `<?xml:stylesheet?>` directive, as shown in the following data, attempting to load this data into the XML Document Object Model (DOM) throws an exception.</span></span>  
  
```xml  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 <span data-ttu-id="4579b-106">这是因为`<?xml:stylesheet?>`被视为无效**ProcessingInstruction** dom</span><span class="sxs-lookup"><span data-stu-id="4579b-106">This occurs because the `<?xml:stylesheet?>` is considered an invalid **ProcessingInstruction** to the DOM.</span></span> <span data-ttu-id="4579b-107">任何**ProcessingInstruction**，根据 XML 规范中的命名空间，只能是无冒号名称 (NCNames)，与限定名 (QNames)。</span><span class="sxs-lookup"><span data-stu-id="4579b-107">Any **ProcessingInstruction**, according to the Namespaces in XML specification, can only be no-colon names (NCNames), as opposed to qualified names (QNames).</span></span>  
  
 <span data-ttu-id="4579b-108">从 XML 规范，个的效果中的命名空间的第 6 节**负载**和**LoadXml**方法符合该规范是，在文档中：</span><span class="sxs-lookup"><span data-stu-id="4579b-108">From Section 6 of the Namespaces in XML specification, the effect of having the **Load** and **LoadXml** methods conform to the specification is that in a document:</span></span>  
  
-   <span data-ttu-id="4579b-109">所有元素类型和属性名都包含零个或一个冒号。</span><span class="sxs-lookup"><span data-stu-id="4579b-109">All element types and attribute names contain either zero or one colon.</span></span>  
  
-   <span data-ttu-id="4579b-110">任何实体名称、ProcessingInstruction 目标或表示法名称都不包含冒号。</span><span class="sxs-lookup"><span data-stu-id="4579b-110">No entity names, ProcessingInstruction targets, or notation names contain any colons.</span></span>  
  
 <span data-ttu-id="4579b-111">因为 `<?xml:stylesheet?>` 包含一个冒号，所以您违反了第二条规则。</span><span class="sxs-lookup"><span data-stu-id="4579b-111">With the `<?xml:stylesheet?>` containing a colon, you now violate the rule in the second bullet.</span></span>  
  
 <span data-ttu-id="4579b-112">根据万维网联合会 (W3C) 将样式表与 XML 文档关联的 1.0 版建议（位于 www.w3.org/TR/xml-stylesheet），将 XSL 样式表与 XML 文档关联的处理指令是 `<?xml-stylesheet?>`（用短划线代替冒号）。</span><span class="sxs-lookup"><span data-stu-id="4579b-112">According to the World Wide Web Consortium (W3C) Associating Style Sheets with XML documents Version 1.0 Recommendation, located at www.w3.org/TR/xml-stylesheet, the processing instruction to associate an XSLT style sheet with an XML document is `<?xml-stylesheet?>`, with a dash replacing the colon.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4579b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4579b-113">See Also</span></span>  
 [<span data-ttu-id="4579b-114">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="4579b-114">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)

---
title: "扩展 XSLT 样式表"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df4ba2bf-a99e-4d22-bbf3-04fc67669dbc
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8ccd1a95586bc92bcc712639eded135a69da1a36
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="extending-xslt-style-sheets"></a><span data-ttu-id="da616-102">扩展 XSLT 样式表</span><span class="sxs-lookup"><span data-stu-id="da616-102">Extending XSLT Style Sheets</span></span>
<span data-ttu-id="da616-103">本节介绍扩展 XSLT 功能的不同方法。</span><span class="sxs-lookup"><span data-stu-id="da616-103">This section describes the different methods of extending the XSLT functionality.</span></span> <span data-ttu-id="da616-104">可以使用 <xref:System.Xml.Xsl.XsltArgumentList> 类添加扩展对象或参数。</span><span class="sxs-lookup"><span data-stu-id="da616-104">You can add extension objects or parameters using the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span> <span data-ttu-id="da616-105">然后，可以从样式表中调用扩展对象或参数。</span><span class="sxs-lookup"><span data-stu-id="da616-105">The extension objects or parameters can then be called from the style sheet.</span></span> <span data-ttu-id="da616-106">此外，还可以使用 `msxsl:script` 元素将脚本块嵌入样式表中。</span><span class="sxs-lookup"><span data-stu-id="da616-106">In addition, you can also embed script blocks into the style sheet by using the `msxsl:script` element.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="da616-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="da616-107">In This Section</span></span>  
 [<span data-ttu-id="da616-108">XSLT 扩展对象</span><span class="sxs-lookup"><span data-stu-id="da616-108">XSLT Extension Objects</span></span>](../../../../docs/standard/data/xml/xslt-extension-objects.md)  
 <span data-ttu-id="da616-109">讨论如何使用 <xref:System.Xml.Xsl.XsltArgumentList> 类来处理 XSLT 扩展对象。</span><span class="sxs-lookup"><span data-stu-id="da616-109">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT extension objects.</span></span>  
  
 [<span data-ttu-id="da616-110">XSLT 参数</span><span class="sxs-lookup"><span data-stu-id="da616-110">XSLT Parameters</span></span>](../../../../docs/standard/data/xml/xslt-parameters.md)  
 <span data-ttu-id="da616-111">讨论如何使用 <xref:System.Xml.Xsl.XsltArgumentList> 类来处理 XSLT 参数。</span><span class="sxs-lookup"><span data-stu-id="da616-111">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT parameters.</span></span>  
  
 [<span data-ttu-id="da616-112">脚本块使用 msxsl: script</span><span class="sxs-lookup"><span data-stu-id="da616-112">Script Blocks Using msxsl:script</span></span>](../../../../docs/standard/data/xml/script-blocks-using-msxsl-script.md)  
 <span data-ttu-id="da616-113">讨论如何使用 `msxsl:script` 元素。</span><span class="sxs-lookup"><span data-stu-id="da616-113">Discusses using the `msxsl:script` element.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="da616-114">相关章节</span><span class="sxs-lookup"><span data-stu-id="da616-114">Related Sections</span></span>  
 [<span data-ttu-id="da616-115">XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="da616-115">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)

---
title: 扩展 XSLT 样式表
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: df4ba2bf-a99e-4d22-bbf3-04fc67669dbc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff952df59dc8291b12df2b238052d4c40c834e2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568818"
---
# <a name="extending-xslt-style-sheets"></a><span data-ttu-id="a296b-102">扩展 XSLT 样式表</span><span class="sxs-lookup"><span data-stu-id="a296b-102">Extending XSLT Style Sheets</span></span>
<span data-ttu-id="a296b-103">本节介绍扩展 XSLT 功能的不同方法。</span><span class="sxs-lookup"><span data-stu-id="a296b-103">This section describes the different methods of extending the XSLT functionality.</span></span> <span data-ttu-id="a296b-104">可以使用 <xref:System.Xml.Xsl.XsltArgumentList> 类添加扩展对象或参数。</span><span class="sxs-lookup"><span data-stu-id="a296b-104">You can add extension objects or parameters using the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span> <span data-ttu-id="a296b-105">然后，可以从样式表中调用扩展对象或参数。</span><span class="sxs-lookup"><span data-stu-id="a296b-105">The extension objects or parameters can then be called from the style sheet.</span></span> <span data-ttu-id="a296b-106">此外，还可以使用 `msxsl:script` 元素将脚本块嵌入样式表中。</span><span class="sxs-lookup"><span data-stu-id="a296b-106">In addition, you can also embed script blocks into the style sheet by using the `msxsl:script` element.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a296b-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="a296b-107">In This Section</span></span>  
 [<span data-ttu-id="a296b-108">XSLT 扩展对象</span><span class="sxs-lookup"><span data-stu-id="a296b-108">XSLT Extension Objects</span></span>](../../../../docs/standard/data/xml/xslt-extension-objects.md)  
 <span data-ttu-id="a296b-109">讨论如何使用 <xref:System.Xml.Xsl.XsltArgumentList> 类来处理 XSLT 扩展对象。</span><span class="sxs-lookup"><span data-stu-id="a296b-109">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT extension objects.</span></span>  
  
 [<span data-ttu-id="a296b-110">XSLT 参数</span><span class="sxs-lookup"><span data-stu-id="a296b-110">XSLT Parameters</span></span>](../../../../docs/standard/data/xml/xslt-parameters.md)  
 <span data-ttu-id="a296b-111">讨论如何使用 <xref:System.Xml.Xsl.XsltArgumentList> 类来处理 XSLT 参数。</span><span class="sxs-lookup"><span data-stu-id="a296b-111">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT parameters.</span></span>  
  
 [<span data-ttu-id="a296b-112">使用 msxsl:script 的脚本块</span><span class="sxs-lookup"><span data-stu-id="a296b-112">Script Blocks Using msxsl:script</span></span>](../../../../docs/standard/data/xml/script-blocks-using-msxsl-script.md)  
 <span data-ttu-id="a296b-113">讨论如何使用 `msxsl:script` 元素。</span><span class="sxs-lookup"><span data-stu-id="a296b-113">Discusses using the `msxsl:script` element.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a296b-114">相关章节</span><span class="sxs-lookup"><span data-stu-id="a296b-114">Related Sections</span></span>  
 [<span data-ttu-id="a296b-115">XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="a296b-115">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)

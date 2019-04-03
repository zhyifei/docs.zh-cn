---
title: ASP.NET 中的嵌入式代码不支持 XML 文本和 XML 属性
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 79be695478983055ae1f016cf841d733d3f4c430
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813920"
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a><span data-ttu-id="b33f5-102">ASP.NET 中的嵌入式代码不支持 XML 文本和 XML 属性</span><span class="sxs-lookup"><span data-stu-id="b33f5-102">XML literals and XML properties are not supported in embedded code within ASP.NET</span></span>
<span data-ttu-id="b33f5-103">在 ASP.NET 中的嵌入代码中不支持 XML 文本和 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="b33f5-103">XML literals and XML properties are not supported in embedded code within ASP.NET.</span></span> <span data-ttu-id="b33f5-104">若要使用的 XML 功能，将代码移到代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="b33f5-104">To use XML features, move the code to code-behind.</span></span>  
  
 <span data-ttu-id="b33f5-105">嵌入代码中定义了 XML 文本或 XML 轴属性 (`<%= =>`) ASP.NET 文件中。</span><span class="sxs-lookup"><span data-stu-id="b33f5-105">An XML literal or XML axis property is defined within embedded code (`<%= =>`) in an ASP.NET file.</span></span>  
  
 <span data-ttu-id="b33f5-106">**错误 ID:** BC31200</span><span class="sxs-lookup"><span data-stu-id="b33f5-106">**Error ID:** BC31200</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b33f5-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="b33f5-107">To correct this error</span></span>  
  
-   <span data-ttu-id="b33f5-108">将代码，其中包括 XML 文本或 XML 轴属性移动到 ASP.NET 代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="b33f5-108">Move the code that includes the XML literal or XML axis property to an ASP.NET code-behind file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b33f5-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="b33f5-109">See also</span></span>

- [<span data-ttu-id="b33f5-110">XML 文本</span><span class="sxs-lookup"><span data-stu-id="b33f5-110">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="b33f5-111">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="b33f5-111">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="b33f5-112">XML</span><span class="sxs-lookup"><span data-stu-id="b33f5-112">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)

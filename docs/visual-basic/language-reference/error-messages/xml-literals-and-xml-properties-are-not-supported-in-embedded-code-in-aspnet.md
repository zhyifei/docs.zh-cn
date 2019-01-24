---
title: ASP.NET 中的嵌入式代码不支持 XML 文本和 XML 属性
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 7bec146f0100971d78eed69412ce27889e7a6263
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597159"
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a><span data-ttu-id="43fd0-102">ASP.NET 中的嵌入式代码不支持 XML 文本和 XML 属性</span><span class="sxs-lookup"><span data-stu-id="43fd0-102">XML literals and XML properties are not supported in embedded code within ASP.NET</span></span>
<span data-ttu-id="43fd0-103">在 ASP.NET 中的嵌入代码中不支持 XML 文本和 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="43fd0-103">XML literals and XML properties are not supported in embedded code within ASP.NET.</span></span> <span data-ttu-id="43fd0-104">若要使用的 XML 功能，将代码移到代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="43fd0-104">To use XML features, move the code to code-behind.</span></span>  
  
 <span data-ttu-id="43fd0-105">嵌入代码中定义了 XML 文本或 XML 轴属性 (`<%= =>`) ASP.NET 文件中。</span><span class="sxs-lookup"><span data-stu-id="43fd0-105">An XML literal or XML axis property is defined within embedded code (`<%= =>`) in an ASP.NET file.</span></span>  
  
 <span data-ttu-id="43fd0-106">**错误 ID:** BC31200</span><span class="sxs-lookup"><span data-stu-id="43fd0-106">**Error ID:** BC31200</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="43fd0-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="43fd0-107">To correct this error</span></span>  
  
-   <span data-ttu-id="43fd0-108">将代码，其中包括 XML 文本或 XML 轴属性移动到 ASP.NET 代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="43fd0-108">Move the code that includes the XML literal or XML axis property to an ASP.NET code-behind file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43fd0-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="43fd0-109">See also</span></span>
- [<span data-ttu-id="43fd0-110">XML 文本</span><span class="sxs-lookup"><span data-stu-id="43fd0-110">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="43fd0-111">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="43fd0-111">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="43fd0-112">XML</span><span class="sxs-lookup"><span data-stu-id="43fd0-112">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)

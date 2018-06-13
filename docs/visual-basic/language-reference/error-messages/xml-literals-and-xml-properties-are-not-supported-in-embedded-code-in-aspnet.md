---
title: ASP.NET 中的嵌入式代码不支持 XML 文本和 XML 属性
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 559889587b30418dc2fe2860cfbf90f91605c668
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594837"
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a><span data-ttu-id="df2b8-102">ASP.NET 中的嵌入式代码不支持 XML 文本和 XML 属性</span><span class="sxs-lookup"><span data-stu-id="df2b8-102">XML literals and XML properties are not supported in embedded code within ASP.NET</span></span>
<span data-ttu-id="df2b8-103">在 ASP.NET 内的嵌入代码中不支持 XML 文本和 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="df2b8-103">XML literals and XML properties are not supported in embedded code within ASP.NET.</span></span> <span data-ttu-id="df2b8-104">若要使用的 XML 功能，将代码移到代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="df2b8-104">To use XML features, move the code to code-behind.</span></span>  
  
 <span data-ttu-id="df2b8-105">嵌入代码中定义了 XML 文本或 XML 轴属性 (`<%= =>`) ASP.NET 文件中。</span><span class="sxs-lookup"><span data-stu-id="df2b8-105">An XML literal or XML axis property is defined within embedded code (`<%= =>`) in an ASP.NET file.</span></span>  
  
 <span data-ttu-id="df2b8-106">**错误 ID:** BC31200</span><span class="sxs-lookup"><span data-stu-id="df2b8-106">**Error ID:** BC31200</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="df2b8-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="df2b8-107">To correct this error</span></span>  
  
-   <span data-ttu-id="df2b8-108">将代码，其中包括 XML 文本或 XML 轴属性移动到 ASP.NET 代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="df2b8-108">Move the code that includes the XML literal or XML axis property to an ASP.NET code-behind file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df2b8-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="df2b8-109">See Also</span></span>  
 [<span data-ttu-id="df2b8-110">XML 文本</span><span class="sxs-lookup"><span data-stu-id="df2b8-110">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="df2b8-111">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="df2b8-111">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="df2b8-112">XML</span><span class="sxs-lookup"><span data-stu-id="df2b8-112">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)

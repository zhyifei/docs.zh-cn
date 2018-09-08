---
title: ASP.NET 中的嵌入式代码不支持 XML 文本和 XML 属性
ms.date: 07/20/2015
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
ms.openlocfilehash: 893fdb1b9b3b5ace6b869c7b64ce7483ff523023
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44180674"
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a><span data-ttu-id="59729-102">ASP.NET 中的嵌入式代码不支持 XML 文本和 XML 属性</span><span class="sxs-lookup"><span data-stu-id="59729-102">XML literals and XML properties are not supported in embedded code within ASP.NET</span></span>
<span data-ttu-id="59729-103">在 ASP.NET 中的嵌入代码中不支持 XML 文本和 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="59729-103">XML literals and XML properties are not supported in embedded code within ASP.NET.</span></span> <span data-ttu-id="59729-104">若要使用的 XML 功能，将代码移到代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="59729-104">To use XML features, move the code to code-behind.</span></span>  
  
 <span data-ttu-id="59729-105">嵌入代码中定义了 XML 文本或 XML 轴属性 (`<%= =>`) ASP.NET 文件中。</span><span class="sxs-lookup"><span data-stu-id="59729-105">An XML literal or XML axis property is defined within embedded code (`<%= =>`) in an ASP.NET file.</span></span>  
  
 <span data-ttu-id="59729-106">**错误 ID:** BC31200</span><span class="sxs-lookup"><span data-stu-id="59729-106">**Error ID:** BC31200</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="59729-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="59729-107">To correct this error</span></span>  
  
-   <span data-ttu-id="59729-108">将代码，其中包括 XML 文本或 XML 轴属性移动到 ASP.NET 代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="59729-108">Move the code that includes the XML literal or XML axis property to an ASP.NET code-behind file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59729-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="59729-109">See Also</span></span>  
 [<span data-ttu-id="59729-110">XML 文本</span><span class="sxs-lookup"><span data-stu-id="59729-110">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="59729-111">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="59729-111">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)  
 [<span data-ttu-id="59729-112">XML</span><span class="sxs-lookup"><span data-stu-id="59729-112">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)

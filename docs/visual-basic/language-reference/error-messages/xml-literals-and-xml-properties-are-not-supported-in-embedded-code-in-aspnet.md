---
title: ASP.NET 中的嵌入式代码不支持 XML 文本和 XML 属性
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31200
- bc31200
helpviewer_keywords:
- BC31200
ms.assetid: 053e8cba-8584-45cc-9fa0-43d122779772
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 932c36778720718d777412f958c16b4a650e3b5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xml-literals-and-xml-properties-are-not-supported-in-embedded-code-within-aspnet"></a><span data-ttu-id="9b90d-102">ASP.NET 中的嵌入式代码不支持 XML 文本和 XML 属性</span><span class="sxs-lookup"><span data-stu-id="9b90d-102">XML literals and XML properties are not supported in embedded code within ASP.NET</span></span>
<span data-ttu-id="9b90d-103">在 ASP.NET 内的嵌入代码中不支持 XML 文本和 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="9b90d-103">XML literals and XML properties are not supported in embedded code within ASP.NET.</span></span> <span data-ttu-id="9b90d-104">若要使用的 XML 功能，将代码移到代码隐藏。</span><span class="sxs-lookup"><span data-stu-id="9b90d-104">To use XML features, move the code to code-behind.</span></span>  
  
 <span data-ttu-id="9b90d-105">嵌入代码中定义了 XML 文本或 XML 轴属性 (`<%= =>`) ASP.NET 文件中。</span><span class="sxs-lookup"><span data-stu-id="9b90d-105">An XML literal or XML axis property is defined within embedded code (`<%= =>`) in an ASP.NET file.</span></span>  
  
 <span data-ttu-id="9b90d-106">**错误 ID:** BC31200</span><span class="sxs-lookup"><span data-stu-id="9b90d-106">**Error ID:** BC31200</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9b90d-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="9b90d-107">To correct this error</span></span>  
  
-   <span data-ttu-id="9b90d-108">将代码，其中包括 XML 文本或 XML 轴属性移动到 ASP.NET 代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="9b90d-108">Move the code that includes the XML literal or XML axis property to an ASP.NET code-behind file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b90d-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b90d-109">See Also</span></span>  
 [<span data-ttu-id="9b90d-110">XML 文本</span><span class="sxs-lookup"><span data-stu-id="9b90d-110">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="9b90d-111">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="9b90d-111">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="9b90d-112">XML</span><span class="sxs-lookup"><span data-stu-id="9b90d-112">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)

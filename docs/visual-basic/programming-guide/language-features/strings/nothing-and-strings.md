---
title: "Nothing 和字符串在 Visual Basic |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2d7685c688e96b506cfc2ddddc44ce534625e3b7
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="5a983-102">Nothing 和字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a983-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="5a983-103">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]运行时和[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]评估`Nothing`以不同的方式在处理时的字符串。</span><span class="sxs-lookup"><span data-stu-id="5a983-103">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] runtime and the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="5a983-104">Visual Basic 运行时和.NET Framework</span><span class="sxs-lookup"><span data-stu-id="5a983-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="5a983-105">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="5a983-105">Consider the following example:</span></span>  
  
 <span data-ttu-id="5a983-106">[!code-vb[VbVbalrStrings #&47;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5a983-106">[!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]</span></span>  
  
 <span data-ttu-id="5a983-107">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]运行时通常计算`Nothing`为空字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="5a983-107">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="5a983-108">[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]不存在，但是，并在引发异常，每当尝试执行字符串操作`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="5a983-108">The [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a983-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a983-109">See Also</span></span>  
 [<span data-ttu-id="5a983-110">在 Visual Basic 中字符串的简介</span><span class="sxs-lookup"><span data-stu-id="5a983-110">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)

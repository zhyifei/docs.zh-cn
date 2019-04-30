---
title: Nothing 和字符串 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 5fbcf86261892e3eb8e43ee8eaa3728cd8e42ced
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032274"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="7d389-102">Nothing 和字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d389-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="7d389-103">Visual Basic 运行时，[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]评估`Nothing`以不同的方式时涉及到字符串。</span><span class="sxs-lookup"><span data-stu-id="7d389-103">The Visual Basic runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="7d389-104">Visual Basic 运行时和.NET Framework</span><span class="sxs-lookup"><span data-stu-id="7d389-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="7d389-105">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="7d389-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="7d389-106">Visual Basic 运行时通常计算结果`Nothing`为空字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="7d389-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="7d389-107">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]但是，不，不会引发异常，只要尝试对其执行字符串操作`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="7d389-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d389-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d389-108">See also</span></span>

- [<span data-ttu-id="7d389-109">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="7d389-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)

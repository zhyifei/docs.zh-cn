---
title: Nothing 和字符串 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: f5c1ea8cc0728b25e8e874963967aed504e466d7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591343"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="71cf6-102">Nothing 和字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71cf6-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="71cf6-103">Visual Basic 运行时和.NET Framework 的计算结果`Nothing`以不同的方式时涉及到字符串。</span><span class="sxs-lookup"><span data-stu-id="71cf6-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="71cf6-104">Visual Basic 运行时和.NET Framework</span><span class="sxs-lookup"><span data-stu-id="71cf6-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="71cf6-105">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="71cf6-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="71cf6-106">Visual Basic 运行时通常计算结果`Nothing`为空字符串 ("")。</span><span class="sxs-lookup"><span data-stu-id="71cf6-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="71cf6-107">.NET Framework 却没有，但是，并引发异常，只要尝试对其执行字符串操作`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="71cf6-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71cf6-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="71cf6-108">See also</span></span>

- [<span data-ttu-id="71cf6-109">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="71cf6-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)

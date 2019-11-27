---
title: Nothing 和字符串
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: dfc43748d0754f0a6a29763c42ab82d9937f89f8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344299"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="93b38-102">Nothing 和字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93b38-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="93b38-103">当涉及到字符串时，Visual Basic 运行时和 .NET Framework 的计算 `Nothing` 有所不同。</span><span class="sxs-lookup"><span data-stu-id="93b38-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="93b38-104">Visual Basic 运行时和 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="93b38-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="93b38-105">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="93b38-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="93b38-106">Visual Basic 运行时通常将 `Nothing` 计算为空字符串（""）。</span><span class="sxs-lookup"><span data-stu-id="93b38-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="93b38-107">但是，当尝试对 `Nothing`执行字符串操作时，.NET Framework 不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="93b38-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93b38-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93b38-108">See also</span></span>

- [<span data-ttu-id="93b38-109">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="93b38-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)

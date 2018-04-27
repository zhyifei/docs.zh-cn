---
title: 从零开始的 vs。在 Visual Basic 中的基于 1 的字符串访问
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bbc418147a83b93f94449beb607d7f6bc3eff7a2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="c5b58-102">从零开始的 vs。在 Visual Basic 中的基于 1 的字符串访问</span><span class="sxs-lookup"><span data-stu-id="c5b58-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="c5b58-103">本主题将比较如何 Visual Basic 和[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]提供对字符串中字符的访问。</span><span class="sxs-lookup"><span data-stu-id="c5b58-103">This topic compares how Visual Basic and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide access to the characters in a string.</span></span> <span data-ttu-id="c5b58-104">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]始终提供对在字符串中，字符的从零开始访问，而 Visual Basic 提供从零开始的和基于 1 的访问权限，具体取决于该函数。</span><span class="sxs-lookup"><span data-stu-id="c5b58-104">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="c5b58-105">基于 1 的</span><span class="sxs-lookup"><span data-stu-id="c5b58-105">One-Based</span></span>  
 <span data-ttu-id="c5b58-106">对于基于 1 的 Visual Basic 函数的示例，请考虑`Mid`函数。</span><span class="sxs-lookup"><span data-stu-id="c5b58-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="c5b58-107">它采用了参数，该值指示子字符串将开始，从位置 1 开始的字符位置。</span><span class="sxs-lookup"><span data-stu-id="c5b58-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="c5b58-108">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType>方法采用的字符索引处的子字符串将启动的字符串中从位置 0 开始。</span><span class="sxs-lookup"><span data-stu-id="c5b58-108">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="c5b58-109">因此，如果你有一个字符串"ABCDE"，每个字符进行编号用于 1,2,3,4,5`Mid`函数，但用于 0,1,2,3,4<xref:System.String.Substring%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="c5b58-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="c5b58-110">从零开始</span><span class="sxs-lookup"><span data-stu-id="c5b58-110">Zero-Based</span></span>  
 <span data-ttu-id="c5b58-111">从零开始的 Visual Basic 函数的示例，请考虑`Split`函数。</span><span class="sxs-lookup"><span data-stu-id="c5b58-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="c5b58-112">它将一个字符串拆分，并返回包含子字符串的数组。</span><span class="sxs-lookup"><span data-stu-id="c5b58-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="c5b58-113">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType>方法还将字符串拆分，并返回包含子字符串的数组。</span><span class="sxs-lookup"><span data-stu-id="c5b58-113">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="c5b58-114">因为`Split`函数和<xref:System.String.Split%2A>方法返回[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]的数组，它们必须是从零开始。</span><span class="sxs-lookup"><span data-stu-id="c5b58-114">Because the `Split` function and <xref:System.String.Split%2A> method return [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b58-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5b58-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:System.String.Substring%2A>  
 <xref:System.String.Split%2A>  
 [<span data-ttu-id="c5b58-116">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="c5b58-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)

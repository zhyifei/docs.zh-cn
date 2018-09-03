---
title: 从零开始的 vs。在 Visual Basic 中的基于 1 的字符串访问
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: a0a42f72d94adf1c10865374017fa61e833df40f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43461665"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="7edb3-102">从零开始的 vs。在 Visual Basic 中的基于 1 的字符串访问</span><span class="sxs-lookup"><span data-stu-id="7edb3-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="7edb3-103">本主题将比较了 Visual Basic 和[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]提供对字符串中字符的访问。</span><span class="sxs-lookup"><span data-stu-id="7edb3-103">This topic compares how Visual Basic and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide access to the characters in a string.</span></span> <span data-ttu-id="7edb3-104">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]始终提供了对字符串中字符的从零开始访问权限，而 Visual Basic 提供的从零开始的和基于 1 的访问权限，具体取决于该函数。</span><span class="sxs-lookup"><span data-stu-id="7edb3-104">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="7edb3-105">基于 1 的</span><span class="sxs-lookup"><span data-stu-id="7edb3-105">One-Based</span></span>  
 <span data-ttu-id="7edb3-106">对于基于 1 的 Visual Basic 函数的示例，请考虑`Mid`函数。</span><span class="sxs-lookup"><span data-stu-id="7edb3-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="7edb3-107">它采用自变量，指示子字符串开始，从位置 1 开始的字符位置。</span><span class="sxs-lookup"><span data-stu-id="7edb3-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="7edb3-108">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType>方法接受的字符的索引子字符串将启动，请在字符串中从位置 0 开始。</span><span class="sxs-lookup"><span data-stu-id="7edb3-108">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="7edb3-109">因此，如果您有一个字符串"ABCDE"，单个字符进行编号用于 1,2,3,4,5`Mid`函数，但用于 0,1,2,3,4<xref:System.String.Substring%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="7edb3-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="7edb3-110">从零开始</span><span class="sxs-lookup"><span data-stu-id="7edb3-110">Zero-Based</span></span>  
 <span data-ttu-id="7edb3-111">从零开始的 Visual Basic 函数的示例，请考虑`Split`函数。</span><span class="sxs-lookup"><span data-stu-id="7edb3-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="7edb3-112">它将字符串拆分，并返回一个包含子字符串的数组。</span><span class="sxs-lookup"><span data-stu-id="7edb3-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="7edb3-113">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType>方法还将字符串拆分，并返回一个包含子字符串的数组。</span><span class="sxs-lookup"><span data-stu-id="7edb3-113">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="7edb3-114">因为`Split`函数和<xref:System.String.Split%2A>方法将返回[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]的数组，它们必须是从零开始。</span><span class="sxs-lookup"><span data-stu-id="7edb3-114">Because the `Split` function and <xref:System.String.Split%2A> method return [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7edb3-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="7edb3-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:System.String.Substring%2A>  
 <xref:System.String.Split%2A>  
 [<span data-ttu-id="7edb3-116">Visual Basic 中的字符串简介</span><span class="sxs-lookup"><span data-stu-id="7edb3-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)

---
title: 如何：将字符串转换为 Visual Basic 中的字符数组
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: 9d68e3d90c52d6a4312ccb7c0c9610968e7a4b55
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603750"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="65fbd-102">如何：将字符串转换为 Visual Basic 中的字符数组</span><span class="sxs-lookup"><span data-stu-id="65fbd-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="65fbd-103">有时是有关你的字符串和这些字符在字符串中，例如当需要分析字符串的位置中的字符的数据很有用。</span><span class="sxs-lookup"><span data-stu-id="65fbd-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="65fbd-104">此示例演示如何获取字符数组的字符串中通过调用字符串的<xref:System.String.ToCharArray%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="65fbd-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65fbd-105">示例</span><span class="sxs-lookup"><span data-stu-id="65fbd-105">Example</span></span>  
 <span data-ttu-id="65fbd-106">此示例演示如何将字符串拆分`Char`数组，以及如何拆分字符串`String`其 Unicode 文本字符的数组。</span><span class="sxs-lookup"><span data-stu-id="65fbd-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="65fbd-107">这一区别的原因是 Unicode 文本字符可以由两个或多个组成`Char`字符 (例如，代理项对或组合字符序列)。</span><span class="sxs-lookup"><span data-stu-id="65fbd-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="65fbd-108">有关详细信息，请参阅<xref:System.Globalization.TextElementEnumerator>并[Unicode 标准](https://www.unicode.org/standard/standard.html)。</span><span class="sxs-lookup"><span data-stu-id="65fbd-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="65fbd-109">示例</span><span class="sxs-lookup"><span data-stu-id="65fbd-109">Example</span></span>  
 <span data-ttu-id="65fbd-110">更难以将字符串拆分为其 Unicode 文本字符，但这是必需的如果需要有关字符串的可视表示形式的信息。</span><span class="sxs-lookup"><span data-stu-id="65fbd-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="65fbd-111">此示例使用<xref:System.Globalization.StringInfo.SubstringByTextElements%2A>方法以获取有关构成了一个字符串的 Unicode 文本字符的信息。</span><span class="sxs-lookup"><span data-stu-id="65fbd-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="65fbd-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="65fbd-112">See also</span></span>
- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [<span data-ttu-id="65fbd-113">如何：访问字符串中的字符</span><span class="sxs-lookup"><span data-stu-id="65fbd-113">How to: Access Characters in Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [<span data-ttu-id="65fbd-114">在 Visual Basic 中将字符串转换为其他数据类型</span><span class="sxs-lookup"><span data-stu-id="65fbd-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="65fbd-115">字符串</span><span class="sxs-lookup"><span data-stu-id="65fbd-115">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)

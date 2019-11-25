---
title: 如何：将字符串转换为字节数组
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: d2f7128f97e576d37216d3aa9736921f13f77004
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352449"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="d8889-102">如何：在 Visual Basic 中将字符串转换为字符数组</span><span class="sxs-lookup"><span data-stu-id="d8889-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="d8889-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span><span class="sxs-lookup"><span data-stu-id="d8889-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="d8889-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span><span class="sxs-lookup"><span data-stu-id="d8889-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8889-105">示例</span><span class="sxs-lookup"><span data-stu-id="d8889-105">Example</span></span>  
 <span data-ttu-id="d8889-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span><span class="sxs-lookup"><span data-stu-id="d8889-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="d8889-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span><span class="sxs-lookup"><span data-stu-id="d8889-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="d8889-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span><span class="sxs-lookup"><span data-stu-id="d8889-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a><span data-ttu-id="d8889-109">示例</span><span class="sxs-lookup"><span data-stu-id="d8889-109">Example</span></span>  
 <span data-ttu-id="d8889-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span><span class="sxs-lookup"><span data-stu-id="d8889-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="d8889-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span><span class="sxs-lookup"><span data-stu-id="d8889-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a><span data-ttu-id="d8889-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8889-112">See also</span></span>

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [<span data-ttu-id="d8889-113">如何：访问字符串中的字符</span><span class="sxs-lookup"><span data-stu-id="d8889-113">How to: Access Characters in Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [<span data-ttu-id="d8889-114">在 Visual Basic 中将字符串转换为其他数据类型</span><span class="sxs-lookup"><span data-stu-id="d8889-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="d8889-115">字符串</span><span class="sxs-lookup"><span data-stu-id="d8889-115">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)

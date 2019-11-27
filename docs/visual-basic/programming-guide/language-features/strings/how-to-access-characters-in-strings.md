---
title: 如何：访问字符串中的字符
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 44a021ed3ce1d10613cf6ab7c959c62feec6046c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352464"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="def5b-102">如何：在 Visual Basic 中访问字符串中的字符</span><span class="sxs-lookup"><span data-stu-id="def5b-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="def5b-103">此示例演示如何使用 <xref:System.String.Chars%2A> 属性访问字符串中指定位置处的字符。</span><span class="sxs-lookup"><span data-stu-id="def5b-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="def5b-104">示例</span><span class="sxs-lookup"><span data-stu-id="def5b-104">Example</span></span>  
 <span data-ttu-id="def5b-105">有时，请在字符串中包含有关字符串中的字符和这些字符的位置的数据。</span><span class="sxs-lookup"><span data-stu-id="def5b-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="def5b-106">可以将字符串视为字符数组（`Char` 实例）;您可以通过使用 <xref:System.String.Chars%2A> 属性引用该字符的索引来检索特定字符。</span><span class="sxs-lookup"><span data-stu-id="def5b-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 <span data-ttu-id="def5b-107"><xref:System.String.Chars%2A> 属性的 `index` 参数是从零开始的。</span><span class="sxs-lookup"><span data-stu-id="def5b-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="def5b-108">可靠的编程</span><span class="sxs-lookup"><span data-stu-id="def5b-108">Robust Programming</span></span>  
 <span data-ttu-id="def5b-109"><xref:System.String.Chars%2A> 属性返回指定位置处的字符。</span><span class="sxs-lookup"><span data-stu-id="def5b-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="def5b-110">但是，某些 Unicode 字符可以由多个字符表示。</span><span class="sxs-lookup"><span data-stu-id="def5b-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="def5b-111">有关如何使用 Unicode 字符的详细信息，请参阅[如何：将字符串转换为字符数组](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)。</span><span class="sxs-lookup"><span data-stu-id="def5b-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="def5b-112">如果 `index` 参数大于或等于字符串的长度，或小于零，则 <xref:System.String.Chars%2A> 属性将引发 <xref:System.IndexOutOfRangeException> 异常</span><span class="sxs-lookup"><span data-stu-id="def5b-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def5b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="def5b-113">See also</span></span>

- <xref:System.String.Chars%2A>
- [<span data-ttu-id="def5b-114">如何：将字符串转换为字符数组</span><span class="sxs-lookup"><span data-stu-id="def5b-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="def5b-115">在 Visual Basic 中将字符串转换为其他数据类型</span><span class="sxs-lookup"><span data-stu-id="def5b-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="def5b-116">字符串</span><span class="sxs-lookup"><span data-stu-id="def5b-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)

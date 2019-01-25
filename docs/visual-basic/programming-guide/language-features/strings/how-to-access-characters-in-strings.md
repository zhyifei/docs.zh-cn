---
title: 如何：在 Visual Basic 中的字符串中的访问字符
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 9833b562fc0b4115448ebefb8631f0d73eb15f6f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618917"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="dd900-102">如何：在 Visual Basic 中的字符串中的访问字符</span><span class="sxs-lookup"><span data-stu-id="dd900-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="dd900-103">此示例演示如何使用<xref:System.String.Chars%2A>属性来访问位于字符串中的指定位置处的字符。</span><span class="sxs-lookup"><span data-stu-id="dd900-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd900-104">示例</span><span class="sxs-lookup"><span data-stu-id="dd900-104">Example</span></span>  
 <span data-ttu-id="dd900-105">有时是有关你的字符串和这些字符在字符串中的位置中的字符的数据很有用。</span><span class="sxs-lookup"><span data-stu-id="dd900-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="dd900-106">您可以将字符串视为字符数组 (`Char`实例); 您可以通过引用通过该字符的索引检索特定字符<xref:System.String.Chars%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="dd900-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 <span data-ttu-id="dd900-107">`index`参数的<xref:System.String.Chars%2A>属性是从零开始。</span><span class="sxs-lookup"><span data-stu-id="dd900-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="dd900-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="dd900-108">Robust Programming</span></span>  
 <span data-ttu-id="dd900-109"><xref:System.String.Chars%2A>属性返回位于指定位置处的字符。</span><span class="sxs-lookup"><span data-stu-id="dd900-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="dd900-110">但是，可以由多个字符表示的某些 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="dd900-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="dd900-111">有关如何使用 Unicode 字符的详细信息，请参阅[如何：将字符串转换为字符数组](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)。</span><span class="sxs-lookup"><span data-stu-id="dd900-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="dd900-112"><xref:System.String.Chars%2A>属性，则会引发<xref:System.IndexOutOfRangeException>异常如果`index`参数是否大于或等于字符串的长度，或如果它小于零</span><span class="sxs-lookup"><span data-stu-id="dd900-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd900-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd900-113">See also</span></span>
- <xref:System.String.Chars%2A>
- [<span data-ttu-id="dd900-114">如何：将字符串转换为字符数组</span><span class="sxs-lookup"><span data-stu-id="dd900-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="dd900-115">在 Visual Basic 中将字符串转换为其他数据类型</span><span class="sxs-lookup"><span data-stu-id="dd900-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="dd900-116">字符串</span><span class="sxs-lookup"><span data-stu-id="dd900-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)

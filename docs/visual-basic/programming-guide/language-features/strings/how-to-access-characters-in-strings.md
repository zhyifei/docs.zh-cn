---
title: "如何：在 Visual Basic 中访问字符串中的字符"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 54d604fc08dd97e0e31f9bcec148431374e8ef8f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="911fd-102">如何：在 Visual Basic 中访问字符串中的字符</span><span class="sxs-lookup"><span data-stu-id="911fd-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="911fd-103">此示例演示如何使用<xref:System.String.Chars%2A>属性来访问位于字符串中的指定位置处的字符。</span><span class="sxs-lookup"><span data-stu-id="911fd-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="911fd-104">示例</span><span class="sxs-lookup"><span data-stu-id="911fd-104">Example</span></span>  
 <span data-ttu-id="911fd-105">有时很有用具有了解你的字符串和这些字符在字符串中的位置中的字符的数据。</span><span class="sxs-lookup"><span data-stu-id="911fd-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="911fd-106">你可以将字符串的字符的数组视为 (`Char`实例); 你可以通过引用通过该字符的索引检索特定字符<xref:System.String.Chars%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="911fd-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 <span data-ttu-id="911fd-107">`index`参数<xref:System.String.Chars%2A>属性是从零开始。</span><span class="sxs-lookup"><span data-stu-id="911fd-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="911fd-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="911fd-108">Robust Programming</span></span>  
 <span data-ttu-id="911fd-109"><xref:System.String.Chars%2A>属性返回位于指定位置处的字符。</span><span class="sxs-lookup"><span data-stu-id="911fd-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="911fd-110">但是，可以由多个字符表示某些 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="911fd-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="911fd-111">有关如何使用 Unicode 字符的详细信息，请参阅[如何： 将字符串转换为字符数组](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)。</span><span class="sxs-lookup"><span data-stu-id="911fd-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="911fd-112"><xref:System.String.Chars%2A>属性将引发<xref:System.IndexOutOfRangeException>异常如果`index`参数为大于或等于的长度的字符串，或如果它小于零</span><span class="sxs-lookup"><span data-stu-id="911fd-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="911fd-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="911fd-113">See Also</span></span>  
 <xref:System.String.Chars%2A>  
 [<span data-ttu-id="911fd-114">如何：将字符串转换为字符数组</span><span class="sxs-lookup"><span data-stu-id="911fd-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)  
 [<span data-ttu-id="911fd-115">在 Visual Basic 中将字符串转换为其他数据类型</span><span class="sxs-lookup"><span data-stu-id="911fd-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [<span data-ttu-id="911fd-116">字符串</span><span class="sxs-lookup"><span data-stu-id="911fd-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)

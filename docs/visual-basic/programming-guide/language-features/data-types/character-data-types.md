---
title: "字符数据类型 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data types [Visual Basic], character
- String data type, character data types
- character data types [Visual Basic]
- Char data type, character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3407f614d5898f4fccf04e0363ec31669661b60a
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="30376-102">字符数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30376-102">Character Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="30376-103">提供了*字符数据类型*来处理可打印和可显示的字符。</span><span class="sxs-lookup"><span data-stu-id="30376-103"> provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="30376-104">尽管它们都处理 Unicode 字符`Char`包含一个字符，而`String`包含不限数目的字符。</span><span class="sxs-lookup"><span data-stu-id="30376-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="30376-105">对于表，其中显示的通过并行比较[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]数据类型，请参阅[数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)。</span><span class="sxs-lookup"><span data-stu-id="30376-105">For a table that displays a side-by-side comparison of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="30376-106">Char 类型</span><span class="sxs-lookup"><span data-stu-id="30376-106">Char Type</span></span>  
 <span data-ttu-id="30376-107">`Char`数据类型是一个单一的两个字节 （16 位） Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="30376-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="30376-108">如果某个变量始终存储恰好一个字符，将其声明为`Char`。</span><span class="sxs-lookup"><span data-stu-id="30376-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="30376-109">例如：</span><span class="sxs-lookup"><span data-stu-id="30376-109">For example:</span></span>  
  
 <span data-ttu-id="30376-110">[!code-vb[VbVbalrCharTypes #&1;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="30376-110">[!code-vb[VbVbalrCharTypes#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_1.vb)]</span></span>  
  
 <span data-ttu-id="30376-111">在每个可能值`Char`或`String`变量是*代码点*，或在 Unicode 字符集中的字符代码。</span><span class="sxs-lookup"><span data-stu-id="30376-111">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="30376-112">Unicode 字符包括基本 ASCII 字符集、 各种其他字母、 重音、 货币符号、 分数、 音调符号和数学和技术符号。</span><span class="sxs-lookup"><span data-stu-id="30376-112">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30376-113">Unicode 字符集的预留的码位 D800 到 DFFF (十进制是从 55296 到 55551) 为*代理项对*，这需要两个 16 位值来表示单个码位。</span><span class="sxs-lookup"><span data-stu-id="30376-113">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="30376-114">一个`Char`变量不能保存代理项对和一个`String`使用两个位置来保存此类对。</span><span class="sxs-lookup"><span data-stu-id="30376-114">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="30376-115">有关详细信息，请参阅[Char 数据类型](../../../../visual-basic/language-reference/data-types/char-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="30376-115">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="30376-116">字符串类型</span><span class="sxs-lookup"><span data-stu-id="30376-116">String Type</span></span>  
 <span data-ttu-id="30376-117">`String`数据类型是零个或多个双字节 （16 位） Unicode 字符序列。</span><span class="sxs-lookup"><span data-stu-id="30376-117">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="30376-118">如果一个变量可以包含任意个数的字符，将其声明为`String`。</span><span class="sxs-lookup"><span data-stu-id="30376-118">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="30376-119">例如：</span><span class="sxs-lookup"><span data-stu-id="30376-119">For example:</span></span>  
  
 <span data-ttu-id="30376-120">[!code-vb[VbVbalrCharTypes #&2;](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="30376-120">[!code-vb[VbVbalrCharTypes#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/character-data-types_2.vb)]</span></span>  
  
 <span data-ttu-id="30376-121">有关详细信息，请参阅[字符串数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="30376-121">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30376-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30376-122">See Also</span></span>  
 <span data-ttu-id="30376-123">[基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="30376-123">[Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md) </span></span>  
<span data-ttu-id="30376-124"> [复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="30376-124"> [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) </span></span>  
<span data-ttu-id="30376-125"> [Visual Basic 中的泛型类型](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="30376-125"> [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="30376-126"> [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="30376-126"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="30376-127"> [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="30376-127"> [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="30376-128"> [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="30376-128"> [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md) </span></span>  
<span data-ttu-id="30376-129"> [类型字符](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span><span class="sxs-lookup"><span data-stu-id="30376-129"> [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span>

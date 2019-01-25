---
title: 字符数据类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- data types [Visual Basic], character
- String data type [Visual Basic], character data types
- character data types [Visual Basic]
- Char data type [Visual Basic], character data types
- data types [Visual Basic], choosing
ms.assetid: 902479ef-1679-47fc-9911-0c1c5008226c
ms.openlocfilehash: 5ede86cca1bddb15cab6518e17405837bda008f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536888"
---
# <a name="character-data-types-visual-basic"></a><span data-ttu-id="a37f7-102">字符数据类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a37f7-102">Character Data Types (Visual Basic)</span></span>
<span data-ttu-id="a37f7-103">Visual Basic 提供了一些*字符数据类型*来处理可打印和可显示的字符。</span><span class="sxs-lookup"><span data-stu-id="a37f7-103">Visual Basic provides *character data types* to deal with printable and displayable characters.</span></span> <span data-ttu-id="a37f7-104">尽管它们都处理 Unicode 字符`Char`包含一个字符，而`String`包含字符数量不确定。</span><span class="sxs-lookup"><span data-stu-id="a37f7-104">While they both deal with Unicode characters, `Char` holds a single character whereas `String` contains an indefinite number of characters.</span></span>  
  
 <span data-ttu-id="a37f7-105">显示的 Visual Basic 数据类型的并排比较的表，请参阅[数据类型](../../../../visual-basic/language-reference/data-types/index.md)。</span><span class="sxs-lookup"><span data-stu-id="a37f7-105">For a table that displays a side-by-side comparison of the Visual Basic data types, see [Data Types](../../../../visual-basic/language-reference/data-types/index.md).</span></span>  
  
## <a name="char-type"></a><span data-ttu-id="a37f7-106">Char 类型</span><span class="sxs-lookup"><span data-stu-id="a37f7-106">Char Type</span></span>  
 <span data-ttu-id="a37f7-107">`Char`数据类型是一个单一的两个字节 （16 位） Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="a37f7-107">The `Char` data type is a single two-byte (16-bit) Unicode character.</span></span> <span data-ttu-id="a37f7-108">如果某个变量始终存储的一个字符，将其声明为`Char`。</span><span class="sxs-lookup"><span data-stu-id="a37f7-108">If a variable always stores exactly one character, declare it as `Char`.</span></span> <span data-ttu-id="a37f7-109">例如：</span><span class="sxs-lookup"><span data-stu-id="a37f7-109">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#1)]
  
 <span data-ttu-id="a37f7-110">在每个可能值`Char`或`String`变量是*代码点*，或在 Unicode 字符集中的字符代码。</span><span class="sxs-lookup"><span data-stu-id="a37f7-110">Each possible value in a `Char` or `String` variable is a *code point*, or character code, in the Unicode character set.</span></span> <span data-ttu-id="a37f7-111">Unicode 字符包含基本 ASCII 字符集、 各种其他字母、 重音符号、 货币符号、 分数、 音调符号和数学和技术符号。</span><span class="sxs-lookup"><span data-stu-id="a37f7-111">Unicode characters include the basic ASCII character set, various other alphabet letters, accents, currency symbols, fractions, diacritics, and mathematical and technical symbols.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a37f7-112">Unicode 字符设置的码位 D800 到 DFFF (十进制是从 55296 到 55551) 为预留*代理项对*，这需要两个 16 位值表示一个码位。</span><span class="sxs-lookup"><span data-stu-id="a37f7-112">The Unicode character set reserves the code points D800 through DFFF (55296 through 55551 decimal) for *surrogate pairs*, which require two 16-bit values to represent a single code point.</span></span> <span data-ttu-id="a37f7-113">一个`Char`变量不能包含代理项对和一个`String`使用两个位置来保存此类对。</span><span class="sxs-lookup"><span data-stu-id="a37f7-113">A `Char` variable cannot hold a surrogate pair, and a `String` uses two positions to hold such a pair.</span></span>  
  
 <span data-ttu-id="a37f7-114">有关详细信息，请参阅[Char 数据类型](../../../../visual-basic/language-reference/data-types/char-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="a37f7-114">For more information, see [Char Data Type](../../../../visual-basic/language-reference/data-types/char-data-type.md).</span></span>  
  
## <a name="string-type"></a><span data-ttu-id="a37f7-115">字符串类型</span><span class="sxs-lookup"><span data-stu-id="a37f7-115">String Type</span></span>  
 <span data-ttu-id="a37f7-116">`String`数据类型是零个或多个双字节 （16 位） Unicode 字符序列。</span><span class="sxs-lookup"><span data-stu-id="a37f7-116">The `String` data type is a sequence of zero or more two-byte (16-bit) Unicode characters.</span></span> <span data-ttu-id="a37f7-117">如果一个变量可以包含字符数量不确定，其声明为`String`。</span><span class="sxs-lookup"><span data-stu-id="a37f7-117">If a variable can contain an indefinite number of characters, declare it as `String`.</span></span> <span data-ttu-id="a37f7-118">例如：</span><span class="sxs-lookup"><span data-stu-id="a37f7-118">For example:</span></span>  
  
 [!code-vb[VbVbalrCharTypes#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrchartypes/vb/module1.vb#2)]
  
 <span data-ttu-id="a37f7-119">有关详细信息，请参阅[字符串数据类型](../../../../visual-basic/language-reference/data-types/string-data-type.md)。</span><span class="sxs-lookup"><span data-stu-id="a37f7-119">For more information, see [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a37f7-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a37f7-120">See also</span></span>
- [<span data-ttu-id="a37f7-121">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="a37f7-121">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="a37f7-122">复合数据类型</span><span class="sxs-lookup"><span data-stu-id="a37f7-122">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="a37f7-123">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="a37f7-123">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="a37f7-124">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="a37f7-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="a37f7-125">在 Visual Basic 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="a37f7-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="a37f7-126">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="a37f7-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="a37f7-127">类型字符</span><span class="sxs-lookup"><span data-stu-id="a37f7-127">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)

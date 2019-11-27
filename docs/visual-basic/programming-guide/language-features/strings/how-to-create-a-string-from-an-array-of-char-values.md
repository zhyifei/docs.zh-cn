---
title: 如何：从 Char 值的数组创建字符串
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 03138a851afc55f735cc66edeb345817428a0452
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344390"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="3b24a-102">如何：从 Char 值的数组创建字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b24a-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="3b24a-103">此示例从单个字符创建字符串 "abcd"。</span><span class="sxs-lookup"><span data-stu-id="3b24a-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b24a-104">示例</span><span class="sxs-lookup"><span data-stu-id="3b24a-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3b24a-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="3b24a-105">Compiling the Code</span></span>  
 <span data-ttu-id="3b24a-106">此方法没有特殊要求。</span><span class="sxs-lookup"><span data-stu-id="3b24a-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="3b24a-107">语法 `"a"c`，其中单个 `c` 跟在引号中的单个字符，用于创建字符文本。</span><span class="sxs-lookup"><span data-stu-id="3b24a-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3b24a-108">可靠的编程</span><span class="sxs-lookup"><span data-stu-id="3b24a-108">Robust Programming</span></span>  
 <span data-ttu-id="3b24a-109">字符串中的 Null 字符（等效于 `Chr(0)`）在使用字符串时导致意外的结果。</span><span class="sxs-lookup"><span data-stu-id="3b24a-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="3b24a-110">字符串中将包含 null 字符，但在某些情况下，将不会显示空字符后面的字符。</span><span class="sxs-lookup"><span data-stu-id="3b24a-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b24a-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b24a-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="3b24a-112">Char 数据类型</span><span class="sxs-lookup"><span data-stu-id="3b24a-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="3b24a-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="3b24a-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)

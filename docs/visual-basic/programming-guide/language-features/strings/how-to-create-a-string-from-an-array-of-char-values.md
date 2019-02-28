---
title: 如何：从 Char 值 (Visual Basic 中) 的数组创建字符串
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 0d3a4caf0967ab77de7d91470e43e52521dbd2da
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975506"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="a5d99-102">如何：从 Char 值 (Visual Basic 中) 的数组创建字符串</span><span class="sxs-lookup"><span data-stu-id="a5d99-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="a5d99-103">此示例创建从单独的字符的字符串"abcd"。</span><span class="sxs-lookup"><span data-stu-id="a5d99-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5d99-104">示例</span><span class="sxs-lookup"><span data-stu-id="a5d99-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a5d99-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="a5d99-105">Compiling the Code</span></span>  
 <span data-ttu-id="a5d99-106">此方法具有任何特殊要求。</span><span class="sxs-lookup"><span data-stu-id="a5d99-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="a5d99-107">语法`"a"c`，其中单个`c`跟随在引号内的单个字符，用于创建字符文本。</span><span class="sxs-lookup"><span data-stu-id="a5d99-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a5d99-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="a5d99-108">Robust Programming</span></span>  
 <span data-ttu-id="a5d99-109">Null 字符 (等效于`Chr(0)`) 在字符串中会导致意外结果时使用的字符串。</span><span class="sxs-lookup"><span data-stu-id="a5d99-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="a5d99-110">Null 字符将包含在字符串中，但在某些情况下将不会显示在 null 字符后面的字符。</span><span class="sxs-lookup"><span data-stu-id="a5d99-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d99-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5d99-111">See also</span></span>
- <xref:System.String>
- [<span data-ttu-id="a5d99-112">Char 数据类型</span><span class="sxs-lookup"><span data-stu-id="a5d99-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="a5d99-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="a5d99-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)

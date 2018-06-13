---
title: 如何：从 Char 值的数组创建字符串 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 104b329011d69e10a2926f31ce5d296759a3cce8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647159"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="a459e-102">如何：从 Char 值的数组创建字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a459e-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="a459e-103">此示例创建从单独的字符的字符串"abcd"。</span><span class="sxs-lookup"><span data-stu-id="a459e-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a459e-104">示例</span><span class="sxs-lookup"><span data-stu-id="a459e-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a459e-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="a459e-105">Compiling the Code</span></span>  
 <span data-ttu-id="a459e-106">此方法没有任何特殊要求。</span><span class="sxs-lookup"><span data-stu-id="a459e-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="a459e-107">语法`"a"c`，其中单个`c`跟随用引号括起来的单个字符，用于创建一个字符文本。</span><span class="sxs-lookup"><span data-stu-id="a459e-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a459e-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="a459e-108">Robust Programming</span></span>  
 <span data-ttu-id="a459e-109">Null 字符 (等效于`Chr(0)`) 在字符串中导致意外结果时使用的字符串。</span><span class="sxs-lookup"><span data-stu-id="a459e-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="a459e-110">Null 字符将包括替换字符串，但在某些情况下将不会显示在 null 字符后面的字符。</span><span class="sxs-lookup"><span data-stu-id="a459e-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a459e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="a459e-111">See Also</span></span>  
 <xref:System.String>  
 [<span data-ttu-id="a459e-112">Char 数据类型</span><span class="sxs-lookup"><span data-stu-id="a459e-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [<span data-ttu-id="a459e-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="a459e-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)

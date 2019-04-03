---
title: 需要语句结束
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: ab6a4a0e6736e2af9c1fa0dd170b6aa4c42d9e4a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817144"
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="47637-102">需要语句结束</span><span class="sxs-lookup"><span data-stu-id="47637-102">End of statement expected</span></span>
<span data-ttu-id="47637-103">该语句是语法上完成，但其他编程元素如下所示完成该语句的元素。</span><span class="sxs-lookup"><span data-stu-id="47637-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="47637-104">需要在每个语句末尾行结束符。</span><span class="sxs-lookup"><span data-stu-id="47637-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="47637-105">行终止符将 Visual Basic 源文件字符划分为行。</span><span class="sxs-lookup"><span data-stu-id="47637-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="47637-106">行终止符的示例包括 Unicode 回车符返回字符 （HD），Unicode 换行字符 (HA），并使用 Unicode 回车字符后跟 Unicode 换行字符。</span><span class="sxs-lookup"><span data-stu-id="47637-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="47637-107">有关行终止符的详细信息，请参阅[Visual Basic 语言规范](~/_vblang/spec/lexical-grammar.md#line-terminators)。</span><span class="sxs-lookup"><span data-stu-id="47637-107">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>
  
 <span data-ttu-id="47637-108">**错误 ID:** BC30205</span><span class="sxs-lookup"><span data-stu-id="47637-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="47637-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="47637-109">To correct this error</span></span>
  
1.  <span data-ttu-id="47637-110">检查以确定是否两个不同的语句无意中已放在同一行。</span><span class="sxs-lookup"><span data-stu-id="47637-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2.  <span data-ttu-id="47637-111">完成该语句的元素之后插入一个行结束符。</span><span class="sxs-lookup"><span data-stu-id="47637-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="47637-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="47637-112">See also</span></span>

- [<span data-ttu-id="47637-113">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="47637-113">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="47637-114">语句</span><span class="sxs-lookup"><span data-stu-id="47637-114">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)

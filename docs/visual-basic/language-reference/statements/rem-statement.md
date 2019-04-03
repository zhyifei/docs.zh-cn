---
title: REM 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: 3c63c5613b40cb2014c77a0a996e3acb2cc304d4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817014"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="48e78-102">REM 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48e78-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="48e78-103">使用要包含在程序的源代码中的说明性备注。</span><span class="sxs-lookup"><span data-stu-id="48e78-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48e78-104">语法</span><span class="sxs-lookup"><span data-stu-id="48e78-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="48e78-105">部件</span><span class="sxs-lookup"><span data-stu-id="48e78-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="48e78-106">可选。</span><span class="sxs-lookup"><span data-stu-id="48e78-106">Optional.</span></span> <span data-ttu-id="48e78-107">想要包括的任何注释的文本。</span><span class="sxs-lookup"><span data-stu-id="48e78-107">The text of any comment you want to include.</span></span> <span data-ttu-id="48e78-108">是之间需要空格`REM`关键字和`comment`。</span><span class="sxs-lookup"><span data-stu-id="48e78-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48e78-109">备注</span><span class="sxs-lookup"><span data-stu-id="48e78-109">Remarks</span></span>  
 <span data-ttu-id="48e78-110">可以将`REM`上某一行，或在单独的语句可以将其放在另一个语句后的行。</span><span class="sxs-lookup"><span data-stu-id="48e78-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="48e78-111">`REM`语句必须是在行上的最后一个语句。</span><span class="sxs-lookup"><span data-stu-id="48e78-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="48e78-112">如果它跟在另一个语句，`REM`必须从该语句由空格分隔。</span><span class="sxs-lookup"><span data-stu-id="48e78-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="48e78-113">可以使用单引号 (`'`) 而不是`REM`。</span><span class="sxs-lookup"><span data-stu-id="48e78-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="48e78-114">您的评论另一个语句后面的同一行上还是位于单独一行上，也是如此。</span><span class="sxs-lookup"><span data-stu-id="48e78-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48e78-115">无法继续`REM`语句通过使用行继续符序列 (`_`)。</span><span class="sxs-lookup"><span data-stu-id="48e78-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="48e78-116">注释开始后，编译器不检查具有特殊含义的字符。</span><span class="sxs-lookup"><span data-stu-id="48e78-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="48e78-117">对于多行注释，使用另一个`REM`语句或注释符号 (`'`) 在每一行上。</span><span class="sxs-lookup"><span data-stu-id="48e78-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48e78-118">示例</span><span class="sxs-lookup"><span data-stu-id="48e78-118">Example</span></span>  
 <span data-ttu-id="48e78-119">下面的示例演示`REM`用于解释性备注包含在程序中的语句。</span><span class="sxs-lookup"><span data-stu-id="48e78-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="48e78-120">它还演示了替代方法，即使用单引号字符 (`'`) 而不是`REM`。</span><span class="sxs-lookup"><span data-stu-id="48e78-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="48e78-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="48e78-121">See also</span></span>

- [<span data-ttu-id="48e78-122">代码中的注释</span><span class="sxs-lookup"><span data-stu-id="48e78-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [<span data-ttu-id="48e78-123">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="48e78-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

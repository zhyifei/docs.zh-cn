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
ms.openlocfilehash: 3bd526b08e1ba3be856e1e823cf8ef49ea9b6c97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604271"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="f1cd9-102">REM 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1cd9-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="f1cd9-103">用于将解释性备注包含在程序的源代码。</span><span class="sxs-lookup"><span data-stu-id="f1cd9-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1cd9-104">语法</span><span class="sxs-lookup"><span data-stu-id="f1cd9-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="f1cd9-105">部件</span><span class="sxs-lookup"><span data-stu-id="f1cd9-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="f1cd9-106">可选。</span><span class="sxs-lookup"><span data-stu-id="f1cd9-106">Optional.</span></span> <span data-ttu-id="f1cd9-107">想要包括的任何注释的文本。</span><span class="sxs-lookup"><span data-stu-id="f1cd9-107">The text of any comment you want to include.</span></span> <span data-ttu-id="f1cd9-108">则之间需要空间`REM`关键字和`comment`。</span><span class="sxs-lookup"><span data-stu-id="f1cd9-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1cd9-109">备注</span><span class="sxs-lookup"><span data-stu-id="f1cd9-109">Remarks</span></span>  
 <span data-ttu-id="f1cd9-110">您可以放入`REM`上一行，或你单独的语句可以将其置于另一个语句后的行。</span><span class="sxs-lookup"><span data-stu-id="f1cd9-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="f1cd9-111">`REM`语句必须是行的最后一个语句。</span><span class="sxs-lookup"><span data-stu-id="f1cd9-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="f1cd9-112">如果另一个语句，之后它`REM`必须从该语句由空格分隔。</span><span class="sxs-lookup"><span data-stu-id="f1cd9-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="f1cd9-113">你可以使用单引号 (`'`) 而不是`REM`。</span><span class="sxs-lookup"><span data-stu-id="f1cd9-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="f1cd9-114">你的评论相同行中的以下另一个语句还是单独位于行上，也是如此。</span><span class="sxs-lookup"><span data-stu-id="f1cd9-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1cd9-115">无法继续`REM`语句通过使用行继续序列 (`_`)。</span><span class="sxs-lookup"><span data-stu-id="f1cd9-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="f1cd9-116">注释开始之后，编译器将不检查具有特殊含义的字符。</span><span class="sxs-lookup"><span data-stu-id="f1cd9-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="f1cd9-117">对于多行注释，使用另一`REM`语句或者使用注释符号 (`'`) 在每一行上。</span><span class="sxs-lookup"><span data-stu-id="f1cd9-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1cd9-118">示例</span><span class="sxs-lookup"><span data-stu-id="f1cd9-118">Example</span></span>  
 <span data-ttu-id="f1cd9-119">下面的示例演示`REM`语句，用于将解释性备注包含在程序中。</span><span class="sxs-lookup"><span data-stu-id="f1cd9-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="f1cd9-120">它还演示的替代方案，即使用一个单引号字符 (`'`) 而不是`REM`。</span><span class="sxs-lookup"><span data-stu-id="f1cd9-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f1cd9-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1cd9-121">See Also</span></span>  
 [<span data-ttu-id="f1cd9-122">代码中的注释</span><span class="sxs-lookup"><span data-stu-id="f1cd9-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 [<span data-ttu-id="f1cd9-123">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="f1cd9-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

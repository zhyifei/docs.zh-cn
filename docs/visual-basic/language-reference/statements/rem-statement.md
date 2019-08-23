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
ms.openlocfilehash: 16149ce42e3476cf07a62298f83734fee9ec7253
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957758"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="183d0-102">REM 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="183d0-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="183d0-103">用于在程序的源代码中包括解释性注释。</span><span class="sxs-lookup"><span data-stu-id="183d0-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="183d0-104">语法</span><span class="sxs-lookup"><span data-stu-id="183d0-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="183d0-105">部件</span><span class="sxs-lookup"><span data-stu-id="183d0-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="183d0-106">可选。</span><span class="sxs-lookup"><span data-stu-id="183d0-106">Optional.</span></span> <span data-ttu-id="183d0-107">要包括的任何注释的文本。</span><span class="sxs-lookup"><span data-stu-id="183d0-107">The text of any comment you want to include.</span></span> <span data-ttu-id="183d0-108">`REM`关键字和`comment`之间必须有一个空格。</span><span class="sxs-lookup"><span data-stu-id="183d0-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="183d0-109">备注</span><span class="sxs-lookup"><span data-stu-id="183d0-109">Remarks</span></span>  
 <span data-ttu-id="183d0-110">您可以将`REM`语句放在一行上, 也可以将其放在另一语句后面的行上。</span><span class="sxs-lookup"><span data-stu-id="183d0-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="183d0-111">`REM`语句必须是行中的最后一条语句。</span><span class="sxs-lookup"><span data-stu-id="183d0-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="183d0-112">如果它跟在另一语句`REM`之后, 则必须用空格将其与该语句分隔开。</span><span class="sxs-lookup"><span data-stu-id="183d0-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="183d0-113">您可以使用单引号 (`'`), `REM`而不是。</span><span class="sxs-lookup"><span data-stu-id="183d0-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="183d0-114">无论您的注释是在同一行后面还是单独的行上, 都是如此。</span><span class="sxs-lookup"><span data-stu-id="183d0-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="183d0-115">不能使用行`REM`继续符 (`_`) 继续执行语句。</span><span class="sxs-lookup"><span data-stu-id="183d0-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="183d0-116">注释开始后, 编译器不会检查字符的特殊含义。</span><span class="sxs-lookup"><span data-stu-id="183d0-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="183d0-117">对于多行注释, 请在每行`REM`上使用另一个语句或`'`注释符号 ()。</span><span class="sxs-lookup"><span data-stu-id="183d0-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="183d0-118">示例</span><span class="sxs-lookup"><span data-stu-id="183d0-118">Example</span></span>  
 <span data-ttu-id="183d0-119">下面的示例说明`REM`语句, 该语句用于在程序中包含解释性注释。</span><span class="sxs-lookup"><span data-stu-id="183d0-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="183d0-120">它还显示了使用单引号 (`'`) 而不是的`REM`的替代方法。</span><span class="sxs-lookup"><span data-stu-id="183d0-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="183d0-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="183d0-121">See also</span></span>

- [<span data-ttu-id="183d0-122">代码中的注释</span><span class="sxs-lookup"><span data-stu-id="183d0-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [<span data-ttu-id="183d0-123">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="183d0-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

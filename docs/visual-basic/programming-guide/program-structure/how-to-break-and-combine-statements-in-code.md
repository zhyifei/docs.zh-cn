---
title: 如何：在代码中拆分和合并语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
ms.openlocfilehash: 6bca3d62cb3e886ee08b9169d63d4c3a38247f3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651013"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="35e65-102">如何：在代码中拆分和合并语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="35e65-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="35e65-103">当编写代码时，你有时可能会创建一些冗长需要水平滚动在代码编辑器中的语句。</span><span class="sxs-lookup"><span data-stu-id="35e65-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="35e65-104">尽管这不会影响的方式代码运行，这使得困难为你或任何其他人阅读代码，因为在监视器上显示。</span><span class="sxs-lookup"><span data-stu-id="35e65-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="35e65-105">在这种情况下，你应考虑将单个长语句拆分为多个行。</span><span class="sxs-lookup"><span data-stu-id="35e65-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="35e65-106">若要拆分为多行的单个语句</span><span class="sxs-lookup"><span data-stu-id="35e65-106">To break a single statement into multiple lines</span></span>  
  
-   <span data-ttu-id="35e65-107">使用行继续符，它是一个下划线 (`_`)，在您想要中断的行的点。</span><span class="sxs-lookup"><span data-stu-id="35e65-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="35e65-108">该下划线必须紧跟在空格后，并且在它后面紧跟行终止符（回车）。</span><span class="sxs-lookup"><span data-stu-id="35e65-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35e65-109">在某些情况下，如果省略行继续符，Visual Basic 编译器将隐式 continue 语句在下一行代码上。</span><span class="sxs-lookup"><span data-stu-id="35e65-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="35e65-110">有关可以为其省略行继续符的语法元素的列表，请参阅"隐式行继续符"[语句](../../../visual-basic/programming-guide/language-features/statements.md)。</span><span class="sxs-lookup"><span data-stu-id="35e65-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="35e65-111">在下面的示例中，该语句将划分成四个行与行继续符终止所有但最后一行。</span><span class="sxs-lookup"><span data-stu-id="35e65-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     <span data-ttu-id="35e65-112">使用此序列使得你的代码易于阅读，不管是联机还是在打印。</span><span class="sxs-lookup"><span data-stu-id="35e65-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="35e65-113">行继续符必须在行上的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="35e65-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="35e65-114">你不能与它与任何其他内容相同的行。</span><span class="sxs-lookup"><span data-stu-id="35e65-114">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="35e65-115">存在一些限制，可以使用行继续符中;例如，你无法使用它中间自变量名称。</span><span class="sxs-lookup"><span data-stu-id="35e65-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="35e65-116">你可以中断自变量列表与行继续符，但自变量的单个名称必须保持不变。</span><span class="sxs-lookup"><span data-stu-id="35e65-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="35e65-117">通过使用行继续符将无法继续注释。</span><span class="sxs-lookup"><span data-stu-id="35e65-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="35e65-118">编译器不检查具有特殊含义的注释中的字符。</span><span class="sxs-lookup"><span data-stu-id="35e65-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="35e65-119">对于多行注释，请重复注释符号 (`'`) 在每一行上。</span><span class="sxs-lookup"><span data-stu-id="35e65-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="35e65-120">尽管推荐的方法是将每个语句放在单独的行，Visual Basic 还允许你在同一行上放置多个语句。</span><span class="sxs-lookup"><span data-stu-id="35e65-120">Although placing each statement on a separate line is the recommended method, Visual Basic also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="35e65-121">若要在同一行上放置多个语句</span><span class="sxs-lookup"><span data-stu-id="35e65-121">To place multiple statements on the same line</span></span>  
  
-   <span data-ttu-id="35e65-122">用冒号分隔的语句 (`:`)，如下面的示例。</span><span class="sxs-lookup"><span data-stu-id="35e65-122">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="35e65-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="35e65-123">See Also</span></span>  
 [<span data-ttu-id="35e65-124">程序结构和代码约定</span><span class="sxs-lookup"><span data-stu-id="35e65-124">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="35e65-125">语句</span><span class="sxs-lookup"><span data-stu-id="35e65-125">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)

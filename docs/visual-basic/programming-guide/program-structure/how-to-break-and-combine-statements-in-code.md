---
title: 如何：拆分和合并语句中的代码 (Visual Basic)
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
ms.openlocfilehash: 680084c39b90d4f664f48559fa21388ce192d999
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955618"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="24a02-102">如何：拆分和合并语句中的代码 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24a02-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="24a02-103">编写你的代码时，可能有时创建耗时较长的语句都必须采取措施水平滚动代码编辑器中。</span><span class="sxs-lookup"><span data-stu-id="24a02-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="24a02-104">尽管这不会影响的方式运行代码，它使得您或任何其他人无法读取代码在监视器上显示。</span><span class="sxs-lookup"><span data-stu-id="24a02-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="24a02-105">在这种情况下，应考虑将单个的长语句分成多个行。</span><span class="sxs-lookup"><span data-stu-id="24a02-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="24a02-106">若要拆分为多行的一条语句</span><span class="sxs-lookup"><span data-stu-id="24a02-106">To break a single statement into multiple lines</span></span>  
  
- <span data-ttu-id="24a02-107">使用行继续符，它是一个下划线 (`_`)，在想要中断的行的点。</span><span class="sxs-lookup"><span data-stu-id="24a02-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="24a02-108">该下划线必须紧跟在空格后，并且在它后面紧跟行终止符（回车）。</span><span class="sxs-lookup"><span data-stu-id="24a02-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="24a02-109">在某些情况下，如果您忽略行继续符，Visual Basic 编译器将隐式 continue 语句在下一行代码上。</span><span class="sxs-lookup"><span data-stu-id="24a02-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="24a02-110">可以为其省略行继续符的语法元素的列表，请参阅"隐式行继续符"中的[语句](../../../visual-basic/programming-guide/language-features/statements.md)。</span><span class="sxs-lookup"><span data-stu-id="24a02-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="24a02-111">在以下示例中，该语句将划分成四行延续字符终止所有行，但最后一行。</span><span class="sxs-lookup"><span data-stu-id="24a02-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]  
  
     <span data-ttu-id="24a02-112">这样可以使代码易于阅读，均通过在线和当打印。</span><span class="sxs-lookup"><span data-stu-id="24a02-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="24a02-113">行继续符必须是一行的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="24a02-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="24a02-114">您不能与任何其他操作跟它在同一行。</span><span class="sxs-lookup"><span data-stu-id="24a02-114">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="24a02-115">可以在其中使用行继续符; 存在一些限制例如，不能使用它的中间参数名称。</span><span class="sxs-lookup"><span data-stu-id="24a02-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="24a02-116">可以中断参数列表与行继续符，但单个自变量名必须保持不变。</span><span class="sxs-lookup"><span data-stu-id="24a02-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="24a02-117">通过使用行继续符将无法继续注释。</span><span class="sxs-lookup"><span data-stu-id="24a02-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="24a02-118">编译器不会检查具有特殊含义的注释中的字符。</span><span class="sxs-lookup"><span data-stu-id="24a02-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="24a02-119">对于多行注释，重复注释符号 (`'`) 在每一行上。</span><span class="sxs-lookup"><span data-stu-id="24a02-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="24a02-120">尽管推荐的方法是将每个语句放在单独的行，但 Visual Basic 还允许您在同一行上放置多个语句。</span><span class="sxs-lookup"><span data-stu-id="24a02-120">Although placing each statement on a separate line is the recommended method, Visual Basic also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="24a02-121">若要将多个语句置于同一行上</span><span class="sxs-lookup"><span data-stu-id="24a02-121">To place multiple statements on the same line</span></span>  
  
- <span data-ttu-id="24a02-122">用冒号分隔的语句 (`:`)，如下面的示例。</span><span class="sxs-lookup"><span data-stu-id="24a02-122">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="24a02-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="24a02-123">See also</span></span>

- [<span data-ttu-id="24a02-124">程序结构和代码约定</span><span class="sxs-lookup"><span data-stu-id="24a02-124">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="24a02-125">语句</span><span class="sxs-lookup"><span data-stu-id="24a02-125">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)

---
title: "如何︰ 拆分和合并代码 (Visual Basic 中) 中的语句 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb._
dev_langs:
- VB
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
- underscores, in code
- statements [Visual Basic], line continuation in
- line breaks, in code
- line-continuation character
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2ca281035a0bd81a9b52cdd60f2bc59724852709
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="55694-102">如何：在代码中拆分和合并语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55694-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="55694-103">时编写代码时，有时可能要创建一些冗长的语句都必须采取措施水平滚动在代码编辑器中。</span><span class="sxs-lookup"><span data-stu-id="55694-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="55694-104">尽管这不会影响的方式代码运行，这使得困难为你或其他任何人阅读该代码，因为其出现在显示器上。</span><span class="sxs-lookup"><span data-stu-id="55694-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="55694-105">在这种情况下，应考虑将单个的长语句分成多个行。</span><span class="sxs-lookup"><span data-stu-id="55694-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="55694-106">若要拆分为多行的一条语句</span><span class="sxs-lookup"><span data-stu-id="55694-106">To break a single statement into multiple lines</span></span>  
  
-   <span data-ttu-id="55694-107">使用行继续符，它是一个下划线 (`_`)，您想要中断的行的时刻。</span><span class="sxs-lookup"><span data-stu-id="55694-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="55694-108">该下划线必须紧跟在空格后，并且在它后面紧跟行终止符（回车）。</span><span class="sxs-lookup"><span data-stu-id="55694-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="55694-109">在某些情况下，如果您忽略行继续符，Visual Basic 编译器将隐式 continue 语句在下一行代码上。</span><span class="sxs-lookup"><span data-stu-id="55694-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="55694-110">有关可以为其省略行继续符的语法元素的列表，请参阅"隐式行继续符"[语句](../../../visual-basic/programming-guide/language-features/statements.md)。</span><span class="sxs-lookup"><span data-stu-id="55694-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="55694-111">在下面的示例中，该语句分成四行终止所有的行继续符，但最后一行。</span><span class="sxs-lookup"><span data-stu-id="55694-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     <span data-ttu-id="55694-112">[!code-vb[VbVbcnConventions #&20;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="55694-112">[!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]</span></span>  
  
     <span data-ttu-id="55694-113">这样可以使代码易于阅读，在线和当打印。</span><span class="sxs-lookup"><span data-stu-id="55694-113">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="55694-114">行继续符必须在行上的最后一个字符。</span><span class="sxs-lookup"><span data-stu-id="55694-114">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="55694-115">您不能与任何其他内容按照其在同一行。</span><span class="sxs-lookup"><span data-stu-id="55694-115">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="55694-116">存在一些限制，您可以使用行继续符字符;例如，不能使用它的参数名的中间。</span><span class="sxs-lookup"><span data-stu-id="55694-116">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="55694-117">您可以中断参数列表与行继续符，但参数的各个名称必须保持不变。</span><span class="sxs-lookup"><span data-stu-id="55694-117">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="55694-118">通过使用行继续符，无法继续注释。</span><span class="sxs-lookup"><span data-stu-id="55694-118">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="55694-119">编译器不会检查具有特殊含义的注释中的字符。</span><span class="sxs-lookup"><span data-stu-id="55694-119">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="55694-120">对于多行注释，请重复注释符号 (`'`) 在每一行上。</span><span class="sxs-lookup"><span data-stu-id="55694-120">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="55694-121">将每个语句放在单独的行是推荐的方法，尽管[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]还允许您在同一行上放置多个语句。</span><span class="sxs-lookup"><span data-stu-id="55694-121">Although placing each statement on a separate line is the recommended method, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="55694-122">若要在同一行上放置多个语句</span><span class="sxs-lookup"><span data-stu-id="55694-122">To place multiple statements on the same line</span></span>  
  
-   <span data-ttu-id="55694-123">将语句分隔冒号开头 (`:`)，如下面的示例。</span><span class="sxs-lookup"><span data-stu-id="55694-123">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     <span data-ttu-id="55694-124">[!code-vb[VbVbcnConventions #&10;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="55694-124">[!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55694-125">请参见</span><span class="sxs-lookup"><span data-stu-id="55694-125">See Also</span></span>  
 <span data-ttu-id="55694-126">[程序结构和代码约定](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="55694-126">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="55694-127"> [语句](../../../visual-basic/programming-guide/language-features/statements.md)</span><span class="sxs-lookup"><span data-stu-id="55694-127"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md)</span></span>

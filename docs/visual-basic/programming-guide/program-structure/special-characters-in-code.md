---
title: "在代码 (Visual Basic 中) 中的特殊字符 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
dev_langs:
- VB
helpviewer_keywords:
- special characters, in code
- parentheses, using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator
- concatenation operators, special characters in code
- concatenation operators, vs. addition operator
- '! operator'
- separators, using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator
- addition operator
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: cd7fbce5c382c3acd88a12277a3d7899b823d049
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="94990-102">代码中的特殊字符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94990-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="94990-103">有时您必须使用特殊字符，在代码中，即，不是字母或数字的字符。</span><span class="sxs-lookup"><span data-stu-id="94990-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="94990-104">标点和特殊字符在[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]字符集各有其用途，从组织程序文本到定义编译器或已编译的程序执行的任务。</span><span class="sxs-lookup"><span data-stu-id="94990-104">The punctuation and special characters in the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="94990-105">它们不指定要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="94990-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="94990-106">括号</span><span class="sxs-lookup"><span data-stu-id="94990-106">Parentheses</span></span>  
 <span data-ttu-id="94990-107">使用括号时定义一个过程，如`Sub`或`Function`。</span><span class="sxs-lookup"><span data-stu-id="94990-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="94990-108">必须将所有过程参数列表都括在括号中。</span><span class="sxs-lookup"><span data-stu-id="94990-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="94990-109">您还使用括号为将变量或参数放入逻辑组，特别是可重写中的复杂表达式的运算符优先级的默认顺序。</span><span class="sxs-lookup"><span data-stu-id="94990-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="94990-110">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="94990-110">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="94990-111">[!code-vb[VbVbcnConventions #&11;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="94990-111">[!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]</span></span>  
  
 <span data-ttu-id="94990-112">在前面的代码的值执行`d`8.225 和的值是`e`为 3。</span><span class="sxs-lookup"><span data-stu-id="94990-112">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="94990-113">用于计算`d`使用默认优先顺序，`/`通过`+`，等同于`d = b + (c / a)`。</span><span class="sxs-lookup"><span data-stu-id="94990-113">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="94990-114">在计算中使用的括号`e`重写默认的优先级。</span><span class="sxs-lookup"><span data-stu-id="94990-114">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="94990-115">分隔符</span><span class="sxs-lookup"><span data-stu-id="94990-115">Separators</span></span>  
 <span data-ttu-id="94990-116">分隔符执行其名称所示︰ 它们分隔各部分代码。</span><span class="sxs-lookup"><span data-stu-id="94990-116">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="94990-117">在[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]，分隔符为冒号 (`:`)。</span><span class="sxs-lookup"><span data-stu-id="94990-117">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], the separator character is the colon (`:`).</span></span> <span data-ttu-id="94990-118">当你想要包括在单独的行，而不是单独的行的多个语句时可以使用分隔符。</span><span class="sxs-lookup"><span data-stu-id="94990-118">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="94990-119">这可节省空间，并提高代码的可读性。</span><span class="sxs-lookup"><span data-stu-id="94990-119">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="94990-120">下面的示例演示由冒号分隔的三个语句。</span><span class="sxs-lookup"><span data-stu-id="94990-120">The following example shows three statements separated by colons.</span></span>  
  
 <span data-ttu-id="94990-121">[!code-vb[VbVbcnConventions #&12;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="94990-121">[!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]</span></span>  
  
 <span data-ttu-id="94990-122">有关详细信息，请参阅[如何︰ 中断并组合在代码中的语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)。</span><span class="sxs-lookup"><span data-stu-id="94990-122">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="94990-123">冒号 (`:`) 字符也用于标识语句标签。</span><span class="sxs-lookup"><span data-stu-id="94990-123">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="94990-124">有关详细信息，请参阅[How to︰ 标签语句](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)。</span><span class="sxs-lookup"><span data-stu-id="94990-124">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="94990-125">串联</span><span class="sxs-lookup"><span data-stu-id="94990-125">Concatenation</span></span>  
 <span data-ttu-id="94990-126">使用`&`运算符*串联*，或将字符串链接在一起。</span><span class="sxs-lookup"><span data-stu-id="94990-126">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="94990-127">不要将其与混淆`+`运算符，将数值相加。</span><span class="sxs-lookup"><span data-stu-id="94990-127">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="94990-128">如果您使用`+`运算符可串联在基于数值，运行时可以获得不正确的结果。</span><span class="sxs-lookup"><span data-stu-id="94990-128">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="94990-129">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="94990-129">The following example demonstrates this.</span></span>  
  
 <span data-ttu-id="94990-130">[!code-vb[VbVbcnConventions #&13;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="94990-130">[!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]</span></span>  
  
 <span data-ttu-id="94990-131">在前面的代码的值执行`resultA`为 21.01，而值`resultB`为"10.0111"。</span><span class="sxs-lookup"><span data-stu-id="94990-131">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="94990-132">成员访问运算符</span><span class="sxs-lookup"><span data-stu-id="94990-132">Member Access Operators</span></span>  
 <span data-ttu-id="94990-133">若要访问的一种类型的成员，您使用圆点 (`.`) 或感叹号 (`!`) 之间的类型名称和成员名称的运算符。</span><span class="sxs-lookup"><span data-stu-id="94990-133">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="94990-134">点 （.）运算符</span><span class="sxs-lookup"><span data-stu-id="94990-134">Dot (.) Operator</span></span>  
 <span data-ttu-id="94990-135">使用`.`运算符是成员访问运算符作为类、 结构、 接口或枚举。</span><span class="sxs-lookup"><span data-stu-id="94990-135">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="94990-136">成员可以是字段、 属性、 事件或方法。</span><span class="sxs-lookup"><span data-stu-id="94990-136">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="94990-137">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="94990-137">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="94990-138">[!code-vb[VbVbcnConventions #&14;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="94990-138">[!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]</span></span>  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="94990-139">惊叹号 （！）运算符</span><span class="sxs-lookup"><span data-stu-id="94990-139">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="94990-140">使用`!`运算符仅对类或接口用作字典访问运算符。</span><span class="sxs-lookup"><span data-stu-id="94990-140">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="94990-141">类或接口必须具有一个接受单个的默认属性`String`参数。</span><span class="sxs-lookup"><span data-stu-id="94990-141">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="94990-142">紧随`!`运算符将成为传递给默认属性的字符串形式的参数值。</span><span class="sxs-lookup"><span data-stu-id="94990-142">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="94990-143">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="94990-143">The following example demonstrates this.</span></span>  
  
 <span data-ttu-id="94990-144">[!code-vb[VbVbcnConventions #&15;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="94990-144">[!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]</span></span>  
  
 <span data-ttu-id="94990-145">三个输出行的`MsgBox`所有显示的值`32856`。</span><span class="sxs-lookup"><span data-stu-id="94990-145">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="94990-146">第一行使用传统属性的访问权限`index`，第二个利用了这一事实，`index`是类的默认属性`hasDefault`，并且第三个使用字典访问该类。</span><span class="sxs-lookup"><span data-stu-id="94990-146">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="94990-147">请注意，第二个操作数的`!`运算符必须是有效的 Visual Basic 标识符不括在双引号内 (`" "`)。</span><span class="sxs-lookup"><span data-stu-id="94990-147">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="94990-148">换而言之，不能使用字符串文字或字符串变量。</span><span class="sxs-lookup"><span data-stu-id="94990-148">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="94990-149">下面的最后一个更改行`MsgBox`调用生成一个错误，因为`"X"`是括起来的字符串。</span><span class="sxs-lookup"><span data-stu-id="94990-149">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  <span data-ttu-id="94990-150">必须显式默认集合的引用。</span><span class="sxs-lookup"><span data-stu-id="94990-150">References to default collections must be explicit.</span></span> <span data-ttu-id="94990-151">具体而言，不能使用`!`运算符后期绑定变量。</span><span class="sxs-lookup"><span data-stu-id="94990-151">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="94990-152">`!`字符也用作`Single`键入字符。</span><span class="sxs-lookup"><span data-stu-id="94990-152">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94990-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94990-153">See Also</span></span>  
 <span data-ttu-id="94990-154">[程序结构和代码约定](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="94990-154">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="94990-155"> [类型字符](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span><span class="sxs-lookup"><span data-stu-id="94990-155"> [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span>

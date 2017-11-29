---
title: "代码中的特殊字符 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 11c5ef9ad41fc2362d9ba4f2cb5eb5b63a9ca31c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="c39db-102">代码中的特殊字符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c39db-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="c39db-103">有时您必须使用特殊字符，在代码中，即，不是字母或数字的字符。</span><span class="sxs-lookup"><span data-stu-id="c39db-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="c39db-104">标点和特殊字符中的[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]字符集各有其用途，从组织程序文本到定义编译器或已编译的程序执行的任务。</span><span class="sxs-lookup"><span data-stu-id="c39db-104">The punctuation and special characters in the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="c39db-105">它们不指定要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c39db-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="c39db-106">括号</span><span class="sxs-lookup"><span data-stu-id="c39db-106">Parentheses</span></span>  
 <span data-ttu-id="c39db-107">当你定义的过程中，如使用括号`Sub`或`Function`。</span><span class="sxs-lookup"><span data-stu-id="c39db-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="c39db-108">必须将所有过程自变量列表都括在括号中。</span><span class="sxs-lookup"><span data-stu-id="c39db-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="c39db-109">你还使用括号的变量或自变量置于逻辑组，特别是可重写中的复杂表达式的运算符优先级的默认顺序。</span><span class="sxs-lookup"><span data-stu-id="c39db-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="c39db-110">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="c39db-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 <span data-ttu-id="c39db-111">按照前面的代码的值执行`d`8.225 和的值`e`为 3。</span><span class="sxs-lookup"><span data-stu-id="c39db-111">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="c39db-112">对计算`d`使用默认优先顺序，`/`通过`+`并且等效于`d = b + (c / a)`。</span><span class="sxs-lookup"><span data-stu-id="c39db-112">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="c39db-113">计算中的括号`e`重写默认的优先级。</span><span class="sxs-lookup"><span data-stu-id="c39db-113">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="c39db-114">分隔符</span><span class="sxs-lookup"><span data-stu-id="c39db-114">Separators</span></span>  
 <span data-ttu-id="c39db-115">分隔符执行其名称所示： 分隔各部分的代码。</span><span class="sxs-lookup"><span data-stu-id="c39db-115">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="c39db-116">在[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]，分隔符字符是冒号 (`:`)。</span><span class="sxs-lookup"><span data-stu-id="c39db-116">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], the separator character is the colon (`:`).</span></span> <span data-ttu-id="c39db-117">当你想要包括在单独的行，而不是单独的行的多个语句时，请使用分隔符。</span><span class="sxs-lookup"><span data-stu-id="c39db-117">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="c39db-118">这可以节省空间，并提高代码的可读性。</span><span class="sxs-lookup"><span data-stu-id="c39db-118">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="c39db-119">下面的示例演示用冒号分隔的三个语句。</span><span class="sxs-lookup"><span data-stu-id="c39db-119">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 <span data-ttu-id="c39db-120">有关详细信息，请参阅[How to： 中断和合并代码中的语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)。</span><span class="sxs-lookup"><span data-stu-id="c39db-120">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="c39db-121">冒号 (`:`) 字符也用于标识语句标签。</span><span class="sxs-lookup"><span data-stu-id="c39db-121">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="c39db-122">有关详细信息，请参阅[How to： 标签语句](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)。</span><span class="sxs-lookup"><span data-stu-id="c39db-122">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="c39db-123">串联</span><span class="sxs-lookup"><span data-stu-id="c39db-123">Concatenation</span></span>  
 <span data-ttu-id="c39db-124">使用`&`运算符*串联*，或将字符串链接在一起。</span><span class="sxs-lookup"><span data-stu-id="c39db-124">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="c39db-125">不要将其与混淆`+`运算符，将数值相加。</span><span class="sxs-lookup"><span data-stu-id="c39db-125">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="c39db-126">如果你使用`+`运算符来连接在基于数值，运行时可以获得不正确的结果。</span><span class="sxs-lookup"><span data-stu-id="c39db-126">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="c39db-127">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="c39db-127">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 <span data-ttu-id="c39db-128">按照前面的代码的值执行`resultA`为 21.01，而值`resultB`为"10.0111"。</span><span class="sxs-lookup"><span data-stu-id="c39db-128">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="c39db-129">成员访问运算符</span><span class="sxs-lookup"><span data-stu-id="c39db-129">Member Access Operators</span></span>  
 <span data-ttu-id="c39db-130">若要访问的类型成员，你可以使用点 (`.`) 或感叹号 (`!`) 之间的类型名称和成员名称的运算符。</span><span class="sxs-lookup"><span data-stu-id="c39db-130">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="c39db-131">句点 （.）运算符</span><span class="sxs-lookup"><span data-stu-id="c39db-131">Dot (.) Operator</span></span>  
 <span data-ttu-id="c39db-132">使用`.`运算符作为成员访问运算符的类、 结构、 接口或枚举。</span><span class="sxs-lookup"><span data-stu-id="c39db-132">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="c39db-133">成员可以是字段、 属性、 事件或方法。</span><span class="sxs-lookup"><span data-stu-id="c39db-133">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="c39db-134">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="c39db-134">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="c39db-135">惊叹号 （！）运算符</span><span class="sxs-lookup"><span data-stu-id="c39db-135">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="c39db-136">使用`!`运算符仅在类或接口上的用作字典访问运算符。</span><span class="sxs-lookup"><span data-stu-id="c39db-136">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="c39db-137">类或接口必须具有一个默认属性，接受单个`String`自变量。</span><span class="sxs-lookup"><span data-stu-id="c39db-137">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="c39db-138">紧随`!`运算符将成为传递给以字符串形式的默认属性的自变量值。</span><span class="sxs-lookup"><span data-stu-id="c39db-138">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="c39db-139">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="c39db-139">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 <span data-ttu-id="c39db-140">三个输出行`MsgBox`所有显示的值`32856`。</span><span class="sxs-lookup"><span data-stu-id="c39db-140">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="c39db-141">第一行使用传统的访问权限属性`index`，第二个利用这一事实，`index`是类的默认属性`hasDefault`，和第三个使用字典访问权限类。</span><span class="sxs-lookup"><span data-stu-id="c39db-141">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="c39db-142">请注意，第二个操作数的`!`运算符必须是有效的 Visual Basic 标识符，未括在双引号 (`" "`)。</span><span class="sxs-lookup"><span data-stu-id="c39db-142">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="c39db-143">换而言之，你不能使用字符串文本或字符串变量。</span><span class="sxs-lookup"><span data-stu-id="c39db-143">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="c39db-144">以下到最后一个更改行的`MsgBox`调用生成错误，因为`"X"`未括起来的字符串文字。</span><span class="sxs-lookup"><span data-stu-id="c39db-144">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  <span data-ttu-id="c39db-145">必须显式默认集合的引用。</span><span class="sxs-lookup"><span data-stu-id="c39db-145">References to default collections must be explicit.</span></span> <span data-ttu-id="c39db-146">具体而言，不能使用`!`后期绑定变量上的运算符。</span><span class="sxs-lookup"><span data-stu-id="c39db-146">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="c39db-147">`!`字符也用作`Single`类型字符。</span><span class="sxs-lookup"><span data-stu-id="c39db-147">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c39db-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c39db-148">See Also</span></span>  
 [<span data-ttu-id="c39db-149">程序结构和代码约定</span><span class="sxs-lookup"><span data-stu-id="c39db-149">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="c39db-150">类型字符</span><span class="sxs-lookup"><span data-stu-id="c39db-150">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)

---
title: 代码中的特殊字符 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 65fcd10521742e287c7934080b3352a06668df7a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835552"
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="c9853-102">代码中的特殊字符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9853-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="c9853-103">有时您必须在代码中，即，不是字母或数字的字符使用特殊字符。</span><span class="sxs-lookup"><span data-stu-id="c9853-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="c9853-104">标点和 Visual Basic 字符集中的特殊字符各有其用途，从组织程序文本到定义编译器或已编译的程序执行的任务。</span><span class="sxs-lookup"><span data-stu-id="c9853-104">The punctuation and special characters in the Visual Basic character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="c9853-105">它们不指定要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="c9853-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="c9853-106">括号</span><span class="sxs-lookup"><span data-stu-id="c9853-106">Parentheses</span></span>  
 <span data-ttu-id="c9853-107">使用括号时定义一个过程，如`Sub`或`Function`。</span><span class="sxs-lookup"><span data-stu-id="c9853-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="c9853-108">必须将所有过程自变量列表都括在括号中。</span><span class="sxs-lookup"><span data-stu-id="c9853-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="c9853-109">你还使用括号将变量或参数放到逻辑组，尤其是重写中的复杂表达式的运算符优先级的默认顺序。</span><span class="sxs-lookup"><span data-stu-id="c9853-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="c9853-110">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="c9853-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 <span data-ttu-id="c9853-111">按照上面的代码的值执行`d`8.225 和的值是`e`为 3。</span><span class="sxs-lookup"><span data-stu-id="c9853-111">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="c9853-112">计算`d`使用的默认优先级`/`转移`+`，等效于`d = b + (c / a)`。</span><span class="sxs-lookup"><span data-stu-id="c9853-112">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="c9853-113">中的计算的括号`e`重写默认的优先级。</span><span class="sxs-lookup"><span data-stu-id="c9853-113">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="c9853-114">分隔符</span><span class="sxs-lookup"><span data-stu-id="c9853-114">Separators</span></span>  
 <span data-ttu-id="c9853-115">分隔符执行其名称所示： 分隔各部分的代码。</span><span class="sxs-lookup"><span data-stu-id="c9853-115">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="c9853-116">在 Visual Basic 中，分隔符为冒号 (`:`)。</span><span class="sxs-lookup"><span data-stu-id="c9853-116">In Visual Basic, the separator character is the colon (`:`).</span></span> <span data-ttu-id="c9853-117">当你想要包括在单个行而不是单独的行上的多个语句时，请使用分隔符。</span><span class="sxs-lookup"><span data-stu-id="c9853-117">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="c9853-118">这可节省空间并提高你的代码的可读性。</span><span class="sxs-lookup"><span data-stu-id="c9853-118">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="c9853-119">下面的示例演示三个由冒号分隔的语句。</span><span class="sxs-lookup"><span data-stu-id="c9853-119">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 <span data-ttu-id="c9853-120">有关详细信息，请参阅[如何：拆分和合并代码中的语句](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)。</span><span class="sxs-lookup"><span data-stu-id="c9853-120">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="c9853-121">冒号 (`:`) 字符也用于标识语句标签。</span><span class="sxs-lookup"><span data-stu-id="c9853-121">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="c9853-122">有关详细信息，请参阅[如何：标记语句](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)。</span><span class="sxs-lookup"><span data-stu-id="c9853-122">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="c9853-123">串联</span><span class="sxs-lookup"><span data-stu-id="c9853-123">Concatenation</span></span>  
 <span data-ttu-id="c9853-124">使用`&`运算符*串联*，或将字符串链接在一起。</span><span class="sxs-lookup"><span data-stu-id="c9853-124">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="c9853-125">请将其与混淆`+`运算符，将数值相加。</span><span class="sxs-lookup"><span data-stu-id="c9853-125">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="c9853-126">如果使用`+`运算符来串联时对数字值，您可以获得不正确的结果。</span><span class="sxs-lookup"><span data-stu-id="c9853-126">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="c9853-127">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="c9853-127">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 <span data-ttu-id="c9853-128">按照上面的代码的值执行`resultA`21.01 和的值是`resultB`为"10.0111"。</span><span class="sxs-lookup"><span data-stu-id="c9853-128">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="c9853-129">成员访问运算符</span><span class="sxs-lookup"><span data-stu-id="c9853-129">Member Access Operators</span></span>  
 <span data-ttu-id="c9853-130">若要访问类型的成员，请使用句点 (`.`) 或感叹号 (`!`) 之间的类型名称和成员名称的运算符。</span><span class="sxs-lookup"><span data-stu-id="c9853-130">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="c9853-131">点 （.）运算符</span><span class="sxs-lookup"><span data-stu-id="c9853-131">Dot (.) Operator</span></span>  
 <span data-ttu-id="c9853-132">使用`.`运算符是成员访问运算符作为类、 结构、 接口或枚举。</span><span class="sxs-lookup"><span data-stu-id="c9853-132">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="c9853-133">成员可以是字段、 属性、 事件或方法。</span><span class="sxs-lookup"><span data-stu-id="c9853-133">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="c9853-134">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="c9853-134">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="c9853-135">惊叹号 （！）运算符</span><span class="sxs-lookup"><span data-stu-id="c9853-135">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="c9853-136">使用`!`运算符仅在类或接口上的作为字典访问运算符。</span><span class="sxs-lookup"><span data-stu-id="c9853-136">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="c9853-137">类或接口必须具有默认属性接受单个`String`参数。</span><span class="sxs-lookup"><span data-stu-id="c9853-137">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="c9853-138">紧随`!`运算符将成为传递给字符串形式的默认属性的参数值。</span><span class="sxs-lookup"><span data-stu-id="c9853-138">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="c9853-139">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="c9853-139">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="c9853-140">三个输出行`MsgBox`的值显示所有`32856`。</span><span class="sxs-lookup"><span data-stu-id="c9853-140">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="c9853-141">第一行使用传统的访问权限属性`index`，第二个利用了这一事实，`index`是类的默认属性`hasDefault`，和第三个使用字典访问权限类。</span><span class="sxs-lookup"><span data-stu-id="c9853-141">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="c9853-142">请注意，第二个操作数`!`运算符必须是有效的 Visual Basic 标识符不括在双引号内 (`" "`)。</span><span class="sxs-lookup"><span data-stu-id="c9853-142">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="c9853-143">换而言之，不能使用字符串文字或字符串变量。</span><span class="sxs-lookup"><span data-stu-id="c9853-143">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="c9853-144">以下的最后一个更改的行`MsgBox`调用将生成一个错误，因为`"X"`是文字括住的字符串。</span><span class="sxs-lookup"><span data-stu-id="c9853-144">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  <span data-ttu-id="c9853-145">对默认集合的引用必须为显式。</span><span class="sxs-lookup"><span data-stu-id="c9853-145">References to default collections must be explicit.</span></span> <span data-ttu-id="c9853-146">具体而言，不能使用`!`运算符的后期绑定变量。</span><span class="sxs-lookup"><span data-stu-id="c9853-146">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="c9853-147">`!`字符也用作`Single`键入字符。</span><span class="sxs-lookup"><span data-stu-id="c9853-147">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9853-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9853-148">See also</span></span>

- [<span data-ttu-id="c9853-149">程序结构和代码约定</span><span class="sxs-lookup"><span data-stu-id="c9853-149">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="c9853-150">类型字符</span><span class="sxs-lookup"><span data-stu-id="c9853-150">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)

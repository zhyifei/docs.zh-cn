---
title: Sub 表达式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 6cdb75f150831ae3857a510d87b58773bdcf13c9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609602"
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="c5521-102">Sub 表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5521-102">Sub Expression (Visual Basic)</span></span>
<span data-ttu-id="c5521-103">声明的参数和子例程 lambda 表达式定义的代码。</span><span class="sxs-lookup"><span data-stu-id="c5521-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5521-104">语法</span><span class="sxs-lookup"><span data-stu-id="c5521-104">Syntax</span></span>  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="c5521-105">部件</span><span class="sxs-lookup"><span data-stu-id="c5521-105">Parts</span></span>  
  
|<span data-ttu-id="c5521-106">术语</span><span class="sxs-lookup"><span data-stu-id="c5521-106">Term</span></span>|<span data-ttu-id="c5521-107">定义</span><span class="sxs-lookup"><span data-stu-id="c5521-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="c5521-108">可选。</span><span class="sxs-lookup"><span data-stu-id="c5521-108">Optional.</span></span> <span data-ttu-id="c5521-109">表示过程的参数的本地变量名称的列表。</span><span class="sxs-lookup"><span data-stu-id="c5521-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="c5521-110">括号必须存在，即使该列表为空。</span><span class="sxs-lookup"><span data-stu-id="c5521-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="c5521-111">有关更多信息，请参见 [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md)。</span><span class="sxs-lookup"><span data-stu-id="c5521-111">For more information, see [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="c5521-112">必需。</span><span class="sxs-lookup"><span data-stu-id="c5521-112">Required.</span></span> <span data-ttu-id="c5521-113">一条语句。</span><span class="sxs-lookup"><span data-stu-id="c5521-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="c5521-114">必需。</span><span class="sxs-lookup"><span data-stu-id="c5521-114">Required.</span></span> <span data-ttu-id="c5521-115">语句的列表。</span><span class="sxs-lookup"><span data-stu-id="c5521-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5521-116">备注</span><span class="sxs-lookup"><span data-stu-id="c5521-116">Remarks</span></span>  
 <span data-ttu-id="c5521-117">一个*lambda 表达式*是不具有名称的子例程并执行一个或多个语句。</span><span class="sxs-lookup"><span data-stu-id="c5521-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="c5521-118">可以任意位置使用 lambda 表达式，您可以使用委托类型，除作为自变量到`RemoveHandler`。</span><span class="sxs-lookup"><span data-stu-id="c5521-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="c5521-119">有关委托和 lambda 表达式与委托一起使用的详细信息，请参阅[委托语句](../../../visual-basic/language-reference/statements/delegate-statement.md)并[宽松委托转换](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)。</span><span class="sxs-lookup"><span data-stu-id="c5521-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="c5521-120">Lambda 表达式语法</span><span class="sxs-lookup"><span data-stu-id="c5521-120">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="c5521-121">Lambda 表达式的语法类似于标准的子例程。</span><span class="sxs-lookup"><span data-stu-id="c5521-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="c5521-122">差异如下所示：</span><span class="sxs-lookup"><span data-stu-id="c5521-122">The differences are as follows:</span></span>  
  
- <span data-ttu-id="c5521-123">Lambda 表达式没有名称。</span><span class="sxs-lookup"><span data-stu-id="c5521-123">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="c5521-124">Lambda 表达式不能有修饰符，如`Overloads`或`Overrides`。</span><span class="sxs-lookup"><span data-stu-id="c5521-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="c5521-125">单行 lambda 表达式的主体必须是一条语句，不是表达式。</span><span class="sxs-lookup"><span data-stu-id="c5521-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="c5521-126">主体可以包含调用的 sub 过程，但不是为 function 过程的调用。</span><span class="sxs-lookup"><span data-stu-id="c5521-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
- <span data-ttu-id="c5521-127">在 lambda 表达式中，必须必须推断数据类型或所有参数已指定所有参数。</span><span class="sxs-lookup"><span data-stu-id="c5521-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
- <span data-ttu-id="c5521-128">可选和`ParamArray`lambda 表达式中不允许使用参数。</span><span class="sxs-lookup"><span data-stu-id="c5521-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
- <span data-ttu-id="c5521-129">在 lambda 表达式中不允许使用泛型参数。</span><span class="sxs-lookup"><span data-stu-id="c5521-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5521-130">示例</span><span class="sxs-lookup"><span data-stu-id="c5521-130">Example</span></span>  
 <span data-ttu-id="c5521-131">下面是向控制台写入值的 lambda 表达式的示例。</span><span class="sxs-lookup"><span data-stu-id="c5521-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="c5521-132">该示例显示了一个子例程的这两个单行和多行 lambda 表达式语法。</span><span class="sxs-lookup"><span data-stu-id="c5521-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="c5521-133">有关更多示例，请参阅[Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="c5521-133">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="c5521-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5521-134">See also</span></span>

- [<span data-ttu-id="c5521-135">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="c5521-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="c5521-136">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="c5521-136">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="c5521-137">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="c5521-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="c5521-138">语句</span><span class="sxs-lookup"><span data-stu-id="c5521-138">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="c5521-139">宽松委托转换</span><span class="sxs-lookup"><span data-stu-id="c5521-139">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)

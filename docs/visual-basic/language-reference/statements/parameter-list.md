---
title: 参数列表 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: 147a2501219db9f1f1c10f9cf1a81aa395b5ec2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605051"
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="f15f9-102">参数列表 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f15f9-102">Parameter List (Visual Basic)</span></span>
<span data-ttu-id="f15f9-103">指定一个过程需要调用的参数。</span><span class="sxs-lookup"><span data-stu-id="f15f9-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="f15f9-104">用逗号分隔多个参数。</span><span class="sxs-lookup"><span data-stu-id="f15f9-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="f15f9-105">下面是一个参数的语法。</span><span class="sxs-lookup"><span data-stu-id="f15f9-105">The following is the syntax for one parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f15f9-106">语法</span><span class="sxs-lookup"><span data-stu-id="f15f9-106">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a><span data-ttu-id="f15f9-107">部件</span><span class="sxs-lookup"><span data-stu-id="f15f9-107">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="f15f9-108">可选。</span><span class="sxs-lookup"><span data-stu-id="f15f9-108">Optional.</span></span> <span data-ttu-id="f15f9-109">将应用于此参数的属性的列表。</span><span class="sxs-lookup"><span data-stu-id="f15f9-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="f15f9-110">必须将括[特性列表](../../../visual-basic/language-reference/statements/attribute-list.md)中命令的尖括号 ("`<`"和"`>`")。</span><span class="sxs-lookup"><span data-stu-id="f15f9-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `Optional`  
 <span data-ttu-id="f15f9-111">可选。</span><span class="sxs-lookup"><span data-stu-id="f15f9-111">Optional.</span></span> <span data-ttu-id="f15f9-112">指定此参数不需要调用该过程时。</span><span class="sxs-lookup"><span data-stu-id="f15f9-112">Specifies that this parameter is not required when the procedure is called.</span></span>  
  
 `ByVal`  
 <span data-ttu-id="f15f9-113">可选。</span><span class="sxs-lookup"><span data-stu-id="f15f9-113">Optional.</span></span> <span data-ttu-id="f15f9-114">指定该过程不能替换或重新分配基础中调用代码的相应自变量的变量的元素。</span><span class="sxs-lookup"><span data-stu-id="f15f9-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>  
  
 `ByRef`  
 <span data-ttu-id="f15f9-115">可选。</span><span class="sxs-lookup"><span data-stu-id="f15f9-115">Optional.</span></span> <span data-ttu-id="f15f9-116">指定过程可以用相同的方式与调用代码本身可以修改调用代码中的基础变量元素。</span><span class="sxs-lookup"><span data-stu-id="f15f9-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>  
  
 `ParamArray`  
 <span data-ttu-id="f15f9-117">可选。</span><span class="sxs-lookup"><span data-stu-id="f15f9-117">Optional.</span></span> <span data-ttu-id="f15f9-118">指定的参数列表中的最后一个参数是指定的数据类型的元素的可选数组。</span><span class="sxs-lookup"><span data-stu-id="f15f9-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="f15f9-119">这样将任意数量的参数传递给过程调用的代码。</span><span class="sxs-lookup"><span data-stu-id="f15f9-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>  
  
 `parametername`  
 <span data-ttu-id="f15f9-120">必须的。</span><span class="sxs-lookup"><span data-stu-id="f15f9-120">Required.</span></span> <span data-ttu-id="f15f9-121">表示参数的本地变量的名称。</span><span class="sxs-lookup"><span data-stu-id="f15f9-121">Name of the local variable representing the parameter.</span></span>  
  
 `parametertype`  
 <span data-ttu-id="f15f9-122">如果存在`Option Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="f15f9-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="f15f9-123">表示参数的本地变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f15f9-123">Data type of the local variable representing the parameter.</span></span>  
  
 `defaultvalue`  
 <span data-ttu-id="f15f9-124">所需的`Optional`参数。</span><span class="sxs-lookup"><span data-stu-id="f15f9-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="f15f9-125">任何常量或常量表达式的计算结果为参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="f15f9-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="f15f9-126">如果类型为`Object`，或类、 接口、 数组或结构，默认值只能是`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="f15f9-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f15f9-127">备注</span><span class="sxs-lookup"><span data-stu-id="f15f9-127">Remarks</span></span>  
 <span data-ttu-id="f15f9-128">参数是括号括起来，并且用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="f15f9-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="f15f9-129">参数可以使用任何数据类型声明。</span><span class="sxs-lookup"><span data-stu-id="f15f9-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="f15f9-130">如果不指定`parametertype`，它默认为`Object`。</span><span class="sxs-lookup"><span data-stu-id="f15f9-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>  
  
 <span data-ttu-id="f15f9-131">当调用的代码调用该过程时，它将传递*参数*到每个所需的参数。</span><span class="sxs-lookup"><span data-stu-id="f15f9-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="f15f9-132">有关详细信息，请参阅[参数之间的差异和自变量](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="f15f9-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>  
  
 <span data-ttu-id="f15f9-133">调用代码将传递给每个参数的自变量是到调用代码中的基础元素的指针。</span><span class="sxs-lookup"><span data-stu-id="f15f9-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="f15f9-134">如果此元素为*不可变元素*（常量、 文本、 枚举或表达式），则都无法更改它的任何代码。</span><span class="sxs-lookup"><span data-stu-id="f15f9-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="f15f9-135">如果它是*变量*元素 （声明的变量、 字段、 属性、 数组元素或结构元素），调用代码可以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="f15f9-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="f15f9-136">有关详细信息，请参阅[差异之间可修改和不可修改自变量](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="f15f9-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>  
  
 <span data-ttu-id="f15f9-137">如果变量的元素的传入`ByRef`，过程它也可以进行更改。</span><span class="sxs-lookup"><span data-stu-id="f15f9-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="f15f9-138">有关详细信息，请参阅[差异之间传递自变量传递的值和按引用](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="f15f9-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f15f9-139">规则</span><span class="sxs-lookup"><span data-stu-id="f15f9-139">Rules</span></span>  
  
-   <span data-ttu-id="f15f9-140">**括号。**</span><span class="sxs-lookup"><span data-stu-id="f15f9-140">**Parentheses.**</span></span> <span data-ttu-id="f15f9-141">如果指定参数列表时，必须将它括在括号中。</span><span class="sxs-lookup"><span data-stu-id="f15f9-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="f15f9-142">如果任何参数，你仍然可以使用括号内包含一个空列表。</span><span class="sxs-lookup"><span data-stu-id="f15f9-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="f15f9-143">这可以提高代码的可读性阐明元素一个过程。</span><span class="sxs-lookup"><span data-stu-id="f15f9-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>  
  
-   <span data-ttu-id="f15f9-144">**可选参数。**</span><span class="sxs-lookup"><span data-stu-id="f15f9-144">**Optional Parameters.**</span></span> <span data-ttu-id="f15f9-145">如果你使用`Optional`参数上的修饰符，列表中的所有后续参数还必须是可选，并使用来声明`Optional`修饰符。</span><span class="sxs-lookup"><span data-stu-id="f15f9-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>  
  
     <span data-ttu-id="f15f9-146">每个可选参数声明必须提供`defaultvalue`子句。</span><span class="sxs-lookup"><span data-stu-id="f15f9-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>  
  
     <span data-ttu-id="f15f9-147">有关详细信息，请参阅[可选参数](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="f15f9-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>  
  
-   <span data-ttu-id="f15f9-148">**参数数组。**</span><span class="sxs-lookup"><span data-stu-id="f15f9-148">**Parameter Arrays.**</span></span> <span data-ttu-id="f15f9-149">必须指定`ByVal`为`ParamArray`参数。</span><span class="sxs-lookup"><span data-stu-id="f15f9-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>  
  
     <span data-ttu-id="f15f9-150">你不能同时使用`Optional`和`ParamArray`相同的参数列表中。</span><span class="sxs-lookup"><span data-stu-id="f15f9-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>  
  
     <span data-ttu-id="f15f9-151">有关详细信息，请参阅[参数数组](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)。</span><span class="sxs-lookup"><span data-stu-id="f15f9-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
-   <span data-ttu-id="f15f9-152">**传递机制。**</span><span class="sxs-lookup"><span data-stu-id="f15f9-152">**Passing Mechanism.**</span></span> <span data-ttu-id="f15f9-153">每个自变量的默认机制是`ByVal`，这意味着该过程不能更改基础变量元素。</span><span class="sxs-lookup"><span data-stu-id="f15f9-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="f15f9-154">但是，如果元素是引用类型，该过程可以修改的内容或成员的基础对象，即使它不能替换或重新分配对象本身。</span><span class="sxs-lookup"><span data-stu-id="f15f9-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>  
  
-   <span data-ttu-id="f15f9-155">**参数名称。**</span><span class="sxs-lookup"><span data-stu-id="f15f9-155">**Parameter Names.**</span></span> <span data-ttu-id="f15f9-156">如果参数的数据类型是一个数组，请按照`parametername`紧跟括号。</span><span class="sxs-lookup"><span data-stu-id="f15f9-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="f15f9-157">参数名称的详细信息，请参阅[声明元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="f15f9-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f15f9-158">示例</span><span class="sxs-lookup"><span data-stu-id="f15f9-158">Example</span></span>  
 <span data-ttu-id="f15f9-159">下面的示例演示`Function`定义两个参数的过程。</span><span class="sxs-lookup"><span data-stu-id="f15f9-159">The following example shows a `Function` procedure that defines two parameters.</span></span>  
  
 [!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f15f9-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="f15f9-160">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [<span data-ttu-id="f15f9-161">Function 语句</span><span class="sxs-lookup"><span data-stu-id="f15f9-161">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="f15f9-162">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="f15f9-162">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="f15f9-163">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="f15f9-163">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="f15f9-164">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="f15f9-164">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="f15f9-165">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="f15f9-165">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="f15f9-166">属性概述</span><span class="sxs-lookup"><span data-stu-id="f15f9-166">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="f15f9-167">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="f15f9-167">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

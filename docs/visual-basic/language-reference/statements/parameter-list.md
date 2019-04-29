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
ms.openlocfilehash: 651f08812032aa1c5aacc04fdb3d7f491f12b607
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61784002"
---
# <a name="parameter-list-visual-basic"></a><span data-ttu-id="8a8b4-102">参数列表 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a8b4-102">Parameter List (Visual Basic)</span></span>
<span data-ttu-id="8a8b4-103">指定过程需要被调用时的参数。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-103">Specifies the parameters a procedure expects when it is called.</span></span> <span data-ttu-id="8a8b4-104">由逗号分隔多个参数。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="8a8b4-105">下面是一个参数的语法。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-105">The following is the syntax for one parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a8b4-106">语法</span><span class="sxs-lookup"><span data-stu-id="8a8b4-106">Syntax</span></span>  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a><span data-ttu-id="8a8b4-107">部件</span><span class="sxs-lookup"><span data-stu-id="8a8b4-107">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="8a8b4-108">可选。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-108">Optional.</span></span> <span data-ttu-id="8a8b4-109">将应用于此参数的特性的列表。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-109">List of attributes that apply to this parameter.</span></span> <span data-ttu-id="8a8b4-110">必须将[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)括进尖括号 ("`<`"和"`>`")。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-110">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `Optional`  
 <span data-ttu-id="8a8b4-111">可选。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-111">Optional.</span></span> <span data-ttu-id="8a8b4-112">指定此参数不需要时调用该过程。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-112">Specifies that this parameter is not required when the procedure is called.</span></span>  
  
 `ByVal`  
 <span data-ttu-id="8a8b4-113">可选。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-113">Optional.</span></span> <span data-ttu-id="8a8b4-114">指定该过程不能替换或重新分配基础调用代码中的相应参数的变量元素。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-114">Specifies that the procedure cannot replace or reassign the variable element underlying the corresponding argument in the calling code.</span></span>  
  
 `ByRef`  
 <span data-ttu-id="8a8b4-115">可选。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-115">Optional.</span></span> <span data-ttu-id="8a8b4-116">指定该过程可以用相同的方式与调用代码本身可以修改调用代码中的基础变量元素。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-116">Specifies that the procedure can modify the underlying variable element in the calling code the same way the calling code itself can.</span></span>  
  
 `ParamArray`  
 <span data-ttu-id="8a8b4-117">可选。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-117">Optional.</span></span> <span data-ttu-id="8a8b4-118">指定的参数列表中的最后一个参数是指定的数据类型的元素的可选数组。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-118">Specifies that the last parameter in the parameter list is an optional array of elements of the specified data type.</span></span> <span data-ttu-id="8a8b4-119">这允许将任意数量的参数传递给过程的调用代码。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-119">This lets the calling code pass an arbitrary number of arguments to the procedure.</span></span>  
  
 `parametername`  
 <span data-ttu-id="8a8b4-120">必需。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-120">Required.</span></span> <span data-ttu-id="8a8b4-121">表示参数的本地变量的名称。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-121">Name of the local variable representing the parameter.</span></span>  
  
 `parametertype`  
 <span data-ttu-id="8a8b4-122">需要`Option Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-122">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="8a8b4-123">表示参数的本地变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-123">Data type of the local variable representing the parameter.</span></span>  
  
 `defaultvalue`  
 <span data-ttu-id="8a8b4-124">所需的`Optional`参数。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-124">Required for `Optional` parameters.</span></span> <span data-ttu-id="8a8b4-125">任何常量或常量表达式的计算结果为该参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-125">Any constant or constant expression that evaluates to the data type of the parameter.</span></span> <span data-ttu-id="8a8b4-126">如果类型为`Object`，或类、 接口、 数组或结构，默认值只能是`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-126">If the type is `Object`, or a class, interface, array, or structure, the default value can only be `Nothing`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a8b4-127">备注</span><span class="sxs-lookup"><span data-stu-id="8a8b4-127">Remarks</span></span>  
 <span data-ttu-id="8a8b4-128">参数是用括号括起来，并且用逗号隔开。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-128">Parameters are surrounded by parentheses and separated by commas.</span></span> <span data-ttu-id="8a8b4-129">可以使用任何数据类型声明的参数。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-129">A parameter can be declared with any data type.</span></span> <span data-ttu-id="8a8b4-130">如果未指定`parametertype`，则默认为`Object`。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-130">If you do not specify `parametertype`, it defaults to `Object`.</span></span>  
  
 <span data-ttu-id="8a8b4-131">当调用的代码调用该过程时，会传递*自变量*到每个所需的参数。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-131">When the calling code calls the procedure, it passes an *argument* to each required parameter.</span></span> <span data-ttu-id="8a8b4-132">有关详细信息，请参阅[差异之间形参和实参](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-132">For more information, see [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).</span></span>  
  
 <span data-ttu-id="8a8b4-133">调用代码将传递给每个参数的参数是指向中调用代码的基础元素。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-133">The argument the calling code passes to each parameter is a pointer to an underlying element in the calling code.</span></span> <span data-ttu-id="8a8b4-134">如果此元素是*不可变元素*（常量、 文本、 枚举或表达式），就无法更改它的任何代码。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-134">If this element is *nonvariable* (a constant, literal, enumeration, or expression), it is impossible for any code to change it.</span></span> <span data-ttu-id="8a8b4-135">如果它是*变量*元素 （声明的变量、 字段、 属性、 数组元素或结构元素），调用代码可以对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-135">If it is a *variable* element (a declared variable, field, property, array element, or structure element), the calling code can change it.</span></span> <span data-ttu-id="8a8b4-136">有关详细信息，请参阅[差异之间可修改和不可修改自变量](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-136">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).</span></span>  
  
 <span data-ttu-id="8a8b4-137">如果传递的变量元素`ByRef`，该过程它也可以进行更改。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-137">If a variable element is passed `ByRef`, the procedure can change it as well.</span></span> <span data-ttu-id="8a8b4-138">有关详细信息，请参阅[差异之间传递参数值和按引用来](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-138">For more information, see [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="8a8b4-139">规则</span><span class="sxs-lookup"><span data-stu-id="8a8b4-139">Rules</span></span>  
  
- <span data-ttu-id="8a8b4-140">**括号。**</span><span class="sxs-lookup"><span data-stu-id="8a8b4-140">**Parentheses.**</span></span> <span data-ttu-id="8a8b4-141">如果指定的参数列表，则必须将其括在括号中。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-141">If you specify a parameter list, you must enclose it in parentheses.</span></span> <span data-ttu-id="8a8b4-142">如果没有任何参数，仍可以使用括号内包含一个空列表。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-142">If there are no parameters, you can still use parentheses enclosing an empty list.</span></span> <span data-ttu-id="8a8b4-143">这将通过清晰化元素一个过程提高代码的可读性。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-143">This improves the readability of your code by clarifying that the element is a procedure.</span></span>  
  
- <span data-ttu-id="8a8b4-144">**可选参数。**</span><span class="sxs-lookup"><span data-stu-id="8a8b4-144">**Optional Parameters.**</span></span> <span data-ttu-id="8a8b4-145">如果您使用`Optional`参数的修饰符，列表中的所有后续参数也是可选和通过使用声明`Optional`修饰符。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-145">If you use the `Optional` modifier on a parameter, all subsequent parameters in the list must also be optional and be declared by using the `Optional` modifier.</span></span>  
  
     <span data-ttu-id="8a8b4-146">每个可选参数声明必须提供`defaultvalue`子句。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-146">Every optional parameter declaration must supply the `defaultvalue` clause.</span></span>  
  
     <span data-ttu-id="8a8b4-147">有关详细信息，请参阅[可选参数](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-147">For more information, see [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).</span></span>  
  
- <span data-ttu-id="8a8b4-148">**参数数组。**</span><span class="sxs-lookup"><span data-stu-id="8a8b4-148">**Parameter Arrays.**</span></span> <span data-ttu-id="8a8b4-149">必须指定`ByVal`为`ParamArray`参数。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-149">You must specify `ByVal` for a `ParamArray` parameter.</span></span>  
  
     <span data-ttu-id="8a8b4-150">不能使用两者`Optional`和`ParamArray`相同的参数列表中。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-150">You cannot use both `Optional` and `ParamArray` in the same parameter list.</span></span>  
  
     <span data-ttu-id="8a8b4-151">有关详细信息，请参阅[参数数组](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-151">For more information, see [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
- <span data-ttu-id="8a8b4-152">**传递机制。**</span><span class="sxs-lookup"><span data-stu-id="8a8b4-152">**Passing Mechanism.**</span></span> <span data-ttu-id="8a8b4-153">每个参数的默认机制是`ByVal`，这意味着该过程不能更改基础变量元素。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-153">The default mechanism for every argument is `ByVal`, which means the procedure cannot change the underlying variable element.</span></span> <span data-ttu-id="8a8b4-154">但是，如果元素是引用类型，该过程可以修改内容或成员的基础对象，即使它不能替换或重新分配对象本身。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-154">However, if the element is a reference type, the procedure can modify the contents or members of the underlying object, even though it cannot replace or reassign the object itself.</span></span>  
  
- <span data-ttu-id="8a8b4-155">**参数名称。**</span><span class="sxs-lookup"><span data-stu-id="8a8b4-155">**Parameter Names.**</span></span> <span data-ttu-id="8a8b4-156">如果参数的数据类型是一个数组，请按照`parametername`紧跟括号。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-156">If the parameter's data type is an array, follow `parametername` immediately by parentheses.</span></span> <span data-ttu-id="8a8b4-157">参数名称的详细信息，请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-157">For more information on parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a8b4-158">示例</span><span class="sxs-lookup"><span data-stu-id="8a8b4-158">Example</span></span>  
 <span data-ttu-id="8a8b4-159">下面的示例演示`Function`定义两个参数的过程。</span><span class="sxs-lookup"><span data-stu-id="8a8b4-159">The following example shows a `Function` procedure that defines two parameters.</span></span>  
  
 [!code-vb[VbVbalrStatements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="8a8b4-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a8b4-160">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="8a8b4-161">Function 语句</span><span class="sxs-lookup"><span data-stu-id="8a8b4-161">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="8a8b4-162">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="8a8b4-162">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="8a8b4-163">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="8a8b4-163">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="8a8b4-164">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="8a8b4-164">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="8a8b4-165">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="8a8b4-165">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="8a8b4-166">属性概述</span><span class="sxs-lookup"><span data-stu-id="8a8b4-166">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="8a8b4-167">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="8a8b4-167">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)

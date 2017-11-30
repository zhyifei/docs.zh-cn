---
title: "+ 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.+
helpviewer_keywords:
- arithmetic operators [Visual Basic], addition
- + operator
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
- sum operator [Visual Basic]
ms.assetid: 5694778f-0a2c-4539-8009-f66f318fb46d
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb0d66db2d777c046ccec69acc1f2069d21baf6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="614c3-102">+ 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="614c3-102">+ Operator (Visual Basic)</span></span>
<span data-ttu-id="614c3-103">将两个数相加或返回数值表达式的正数值。</span><span class="sxs-lookup"><span data-stu-id="614c3-103">Adds two numbers or returns the positive value of a numeric expression.</span></span> <span data-ttu-id="614c3-104">此外可以用于连接两个字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="614c3-104">Can also be used to concatenate two string expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="614c3-105">语法</span><span class="sxs-lookup"><span data-stu-id="614c3-105">Syntax</span></span>  
  
```  
      expression1 + expression2  
- or -  
+ expression1  
```  
  
## <a name="parts"></a><span data-ttu-id="614c3-106">部件</span><span class="sxs-lookup"><span data-stu-id="614c3-106">Parts</span></span>  
  
|<span data-ttu-id="614c3-107">术语</span><span class="sxs-lookup"><span data-stu-id="614c3-107">Term</span></span>|<span data-ttu-id="614c3-108">定义</span><span class="sxs-lookup"><span data-stu-id="614c3-108">Definition</span></span>|  
|---|---|  
|`expression1`|<span data-ttu-id="614c3-109">必需。</span><span class="sxs-lookup"><span data-stu-id="614c3-109">Required.</span></span> <span data-ttu-id="614c3-110">任何数值或字符串的表达式。</span><span class="sxs-lookup"><span data-stu-id="614c3-110">Any numeric or string expression.</span></span>|  
|`expression2`|<span data-ttu-id="614c3-111">必填，除非`+`运算符正在计算值为负。</span><span class="sxs-lookup"><span data-stu-id="614c3-111">Required unless the `+` operator is calculating a negative value.</span></span> <span data-ttu-id="614c3-112">任何数值或字符串的表达式。</span><span class="sxs-lookup"><span data-stu-id="614c3-112">Any numeric or string expression.</span></span>|  
  
## <a name="result"></a><span data-ttu-id="614c3-113">结果</span><span class="sxs-lookup"><span data-stu-id="614c3-113">Result</span></span>  
 <span data-ttu-id="614c3-114">如果`expression1`和`expression2`均为数值，则结果是它们的算术和。</span><span class="sxs-lookup"><span data-stu-id="614c3-114">If `expression1` and `expression2` are both numeric, the result is their arithmetic sum.</span></span>  
  
 <span data-ttu-id="614c3-115">如果`expression2`不存在，`+`运算符是*一元*恒等运算符的表达式的未更改值。</span><span class="sxs-lookup"><span data-stu-id="614c3-115">If `expression2` is absent, the `+` operator is the *unary* identity operator for the unchanged value of an expression.</span></span> <span data-ttu-id="614c3-116">在这个意义上来说，该操作包含的保留的符号`expression1`，因此结果为负如果`expression1`为负。</span><span class="sxs-lookup"><span data-stu-id="614c3-116">In this sense, the operation consists of retaining the sign of `expression1`, so the result is negative if `expression1` is negative.</span></span>  
  
 <span data-ttu-id="614c3-117">如果`expression1`和`expression2`都是字符串，则结果是其值的串联。</span><span class="sxs-lookup"><span data-stu-id="614c3-117">If `expression1` and `expression2` are both strings, the result is the concatenation of their values.</span></span>  
  
 <span data-ttu-id="614c3-118">如果`expression1`和`expression2`是混合类型的执行的操作取决于其类型，其内容和的设置[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="614c3-118">If `expression1` and `expression2` are of mixed types, the action taken depends on their types, their contents, and the setting of the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="614c3-119">有关详细信息，请参阅"备注。"中的表</span><span class="sxs-lookup"><span data-stu-id="614c3-119">For more information, see the tables in "Remarks."</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="614c3-120">支持的类型</span><span class="sxs-lookup"><span data-stu-id="614c3-120">Supported Types</span></span>  
 <span data-ttu-id="614c3-121">所有数值类型，包括未签名和浮点类型和`Decimal`，和`String`。</span><span class="sxs-lookup"><span data-stu-id="614c3-121">All numeric types, including the unsigned and floating-point types and `Decimal`, and `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="614c3-122">备注</span><span class="sxs-lookup"><span data-stu-id="614c3-122">Remarks</span></span>  
 <span data-ttu-id="614c3-123">一般情况下，`+`执行算术加法运算在可能的情况下，并将连接仅当两个表达式均为字符串时，才。</span><span class="sxs-lookup"><span data-stu-id="614c3-123">In general, `+` performs arithmetic addition when possible, and concatenates only when both expressions are strings.</span></span>  
  
 <span data-ttu-id="614c3-124">如果表达式都不是`Object`，Visual Basic 将采取以下措施。</span><span class="sxs-lookup"><span data-stu-id="614c3-124">If neither expression is an `Object`, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="614c3-125">表达式的数据类型</span><span class="sxs-lookup"><span data-stu-id="614c3-125">Data types of expressions</span></span>|<span data-ttu-id="614c3-126">由编译器的操作</span><span class="sxs-lookup"><span data-stu-id="614c3-126">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="614c3-127">两个表达式均数值数据类型 (`SByte`， `Byte`， `Short`， `UShort`， `Integer`， `UInteger`， `Long`， `ULong`， `Decimal`， `Single`，或`Double`)</span><span class="sxs-lookup"><span data-stu-id="614c3-127">Both expressions are numeric data types (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, or `Double`)</span></span>|<span data-ttu-id="614c3-128">添加。</span><span class="sxs-lookup"><span data-stu-id="614c3-128">Add.</span></span> <span data-ttu-id="614c3-129">结果数据类型为数值类型适用于数据类型的`expression1`和`expression2`。</span><span class="sxs-lookup"><span data-stu-id="614c3-129">The result data type is a numeric type appropriate for the data types of `expression1` and `expression2`.</span></span> <span data-ttu-id="614c3-130">请参阅中的"整数算法"表[运算符结果的数据类型的](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)。</span><span class="sxs-lookup"><span data-stu-id="614c3-130">See the "Integer Arithmetic" tables in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).</span></span>|  
|<span data-ttu-id="614c3-131">这两个表达式均为类型`String`</span><span class="sxs-lookup"><span data-stu-id="614c3-131">Both expressions are of type `String`</span></span>|<span data-ttu-id="614c3-132">串联在一起。</span><span class="sxs-lookup"><span data-stu-id="614c3-132">Concatenate.</span></span>|  
|<span data-ttu-id="614c3-133">一个表达式为数值数据类型，另一个是一个字符串</span><span class="sxs-lookup"><span data-stu-id="614c3-133">One expression is a numeric data type and the other is a string</span></span>|<span data-ttu-id="614c3-134">如果`Option Strict`是`On`，然后将生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="614c3-134">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="614c3-135">如果`Option Strict`是`Off`，隐式转换`String`到`Double`和添加。</span><span class="sxs-lookup"><span data-stu-id="614c3-135">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="614c3-136">如果`String`不能转换为`Double`，然后引发<xref:System.InvalidCastException>异常。</span><span class="sxs-lookup"><span data-stu-id="614c3-136">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="614c3-137">一个表达式为数值数据类型，而另一种是[执行任何操作](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="614c3-137">One expression is a numeric data type, and the other is [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|<span data-ttu-id="614c3-138">添加，请使用`Nothing`值为零。</span><span class="sxs-lookup"><span data-stu-id="614c3-138">Add, with `Nothing` valued as zero.</span></span>|  
|<span data-ttu-id="614c3-139">一个表达式是字符串，并且另一种是`Nothing`</span><span class="sxs-lookup"><span data-stu-id="614c3-139">One expression is a string, and the other is `Nothing`</span></span>|<span data-ttu-id="614c3-140">连接，与`Nothing`值为""。</span><span class="sxs-lookup"><span data-stu-id="614c3-140">Concatenate, with `Nothing` valued as "".</span></span>|  
  
 <span data-ttu-id="614c3-141">如果一个表达式为`Object`表达式，Visual Basic 将采取以下措施。</span><span class="sxs-lookup"><span data-stu-id="614c3-141">If one expression is an `Object` expression, Visual Basic takes the following actions.</span></span>  
  
|<span data-ttu-id="614c3-142">表达式的数据类型</span><span class="sxs-lookup"><span data-stu-id="614c3-142">Data types of expressions</span></span>|<span data-ttu-id="614c3-143">由编译器的操作</span><span class="sxs-lookup"><span data-stu-id="614c3-143">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="614c3-144">`Object`表达式包含的数字值，另一个是数值数据类型</span><span class="sxs-lookup"><span data-stu-id="614c3-144">`Object` expression holds a numeric value and the other is a numeric data type</span></span>|<span data-ttu-id="614c3-145">如果`Option Strict`是`On`，然后将生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="614c3-145">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="614c3-146">如果`Option Strict`是`Off`，然后添加。</span><span class="sxs-lookup"><span data-stu-id="614c3-146">If `Option Strict` is `Off`, then add.</span></span>|  
|<span data-ttu-id="614c3-147">`Object`表达式包含的数字值，另一个是类型的`String`</span><span class="sxs-lookup"><span data-stu-id="614c3-147">`Object` expression holds a numeric value and the other is of type `String`</span></span>|<span data-ttu-id="614c3-148">如果`Option Strict`是`On`，然后将生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="614c3-148">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="614c3-149">如果`Option Strict`是`Off`，隐式转换`String`到`Double`和添加。</span><span class="sxs-lookup"><span data-stu-id="614c3-149">If `Option Strict` is `Off`, then implicitly convert the `String` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="614c3-150">如果`String`不能转换为`Double`，然后引发<xref:System.InvalidCastException>异常。</span><span class="sxs-lookup"><span data-stu-id="614c3-150">If the `String` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="614c3-151">`Object`表达式包含一个字符串，另一个是数值数据类型</span><span class="sxs-lookup"><span data-stu-id="614c3-151">`Object` expression holds a string and the other is a numeric data type</span></span>|<span data-ttu-id="614c3-152">如果`Option Strict`是`On`，然后将生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="614c3-152">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="614c3-153">如果`Option Strict`是`Off`，然后将字符串隐式转换`Object`到`Double`和添加。</span><span class="sxs-lookup"><span data-stu-id="614c3-153">If `Option Strict` is `Off`, then implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="614c3-154">如果字符串`Object`不能转换为`Double`，然后引发<xref:System.InvalidCastException>异常。</span><span class="sxs-lookup"><span data-stu-id="614c3-154">If the string `Object` cannot be converted to `Double`, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
|<span data-ttu-id="614c3-155">`Object`表达式包含一个字符串，另一个是类型的`String`</span><span class="sxs-lookup"><span data-stu-id="614c3-155">`Object` expression holds a string and the other is of type `String`</span></span>|<span data-ttu-id="614c3-156">如果`Option Strict`是`On`，然后将生成编译器错误。</span><span class="sxs-lookup"><span data-stu-id="614c3-156">If `Option Strict` is `On`, then generate a compiler error.</span></span><br /><br /> <span data-ttu-id="614c3-157">如果`Option Strict`是`Off`，隐式转换`Object`到`String`并连接。</span><span class="sxs-lookup"><span data-stu-id="614c3-157">If `Option Strict` is `Off`, then implicitly convert `Object` to `String` and concatenate.</span></span>|  
  
 <span data-ttu-id="614c3-158">如果两个表达式均`Object`表达式，Visual Basic 将采取以下措施 (`Option Strict Off`仅)。</span><span class="sxs-lookup"><span data-stu-id="614c3-158">If both expressions are `Object` expressions, Visual Basic takes the following actions (`Option Strict Off` only).</span></span>  
  
|<span data-ttu-id="614c3-159">表达式的数据类型</span><span class="sxs-lookup"><span data-stu-id="614c3-159">Data types of expressions</span></span>|<span data-ttu-id="614c3-160">由编译器的操作</span><span class="sxs-lookup"><span data-stu-id="614c3-160">Action by compiler</span></span>|  
|---|---|  
|<span data-ttu-id="614c3-161">同时`Object`表达式保留数值</span><span class="sxs-lookup"><span data-stu-id="614c3-161">Both `Object` expressions hold numeric values</span></span>|<span data-ttu-id="614c3-162">添加。</span><span class="sxs-lookup"><span data-stu-id="614c3-162">Add.</span></span>|  
|<span data-ttu-id="614c3-163">同时`Object`表达式均为类型`String`</span><span class="sxs-lookup"><span data-stu-id="614c3-163">Both `Object` expressions are of type `String`</span></span>|<span data-ttu-id="614c3-164">串联在一起。</span><span class="sxs-lookup"><span data-stu-id="614c3-164">Concatenate.</span></span>|  
|<span data-ttu-id="614c3-165">一个`Object`表达式包含的数字值和其他包含字符串</span><span class="sxs-lookup"><span data-stu-id="614c3-165">One `Object` expression holds a numeric value and the other holds a string</span></span>|<span data-ttu-id="614c3-166">将字符串隐式转换`Object`到`Double`和添加。</span><span class="sxs-lookup"><span data-stu-id="614c3-166">Implicitly convert the string `Object` to `Double` and add.</span></span><br /><br /> <span data-ttu-id="614c3-167">如果字符串`Object`不能转换为数字值，然后引发<xref:System.InvalidCastException>异常。</span><span class="sxs-lookup"><span data-stu-id="614c3-167">If the string `Object` cannot be converted to a numeric value, then throw an <xref:System.InvalidCastException> exception.</span></span>|  
  
 <span data-ttu-id="614c3-168">如果任一`Object`表达式计算结果为[执行任何操作](../../../visual-basic/language-reference/nothing.md)或<xref:System.DBNull>、`+`运算符会将其视为`String`值为""。</span><span class="sxs-lookup"><span data-stu-id="614c3-168">If either `Object` expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md) or <xref:System.DBNull>, the `+` operator treats it as a `String` with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="614c3-169">当你使用`+`运算符，你可能不能以确定是否添加或字符串串联将出现。</span><span class="sxs-lookup"><span data-stu-id="614c3-169">When you use the `+` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="614c3-170">使用`&`的串联运算符，以消除多义性，并提供自说明代码。</span><span class="sxs-lookup"><span data-stu-id="614c3-170">Use the `&` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="614c3-171">重载</span><span class="sxs-lookup"><span data-stu-id="614c3-171">Overloading</span></span>  
 <span data-ttu-id="614c3-172">`+`运算符可以被*重载*，这意味着，一个类或结构可以重新定义其行为时，操作数的类或结构的类型。</span><span class="sxs-lookup"><span data-stu-id="614c3-172">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="614c3-173">如果你的代码使用此运算符对这样的类或结构，请确保你了解其重新定义的行为。</span><span class="sxs-lookup"><span data-stu-id="614c3-173">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="614c3-174">有关详细信息，请参阅[运算符过程](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="614c3-174">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="614c3-175">示例</span><span class="sxs-lookup"><span data-stu-id="614c3-175">Example</span></span>  
 <span data-ttu-id="614c3-176">下面的示例使用`+`运算符以添加数字。</span><span class="sxs-lookup"><span data-stu-id="614c3-176">The following example uses the `+` operator to add numbers.</span></span> <span data-ttu-id="614c3-177">如果操作数均为数值的同时，Visual Basic 将计算算术的结果。</span><span class="sxs-lookup"><span data-stu-id="614c3-177">If the operands are both numeric, Visual Basic computes the arithmetic result.</span></span> <span data-ttu-id="614c3-178">算术结果表示两个操作数之和。</span><span class="sxs-lookup"><span data-stu-id="614c3-178">The arithmetic result represents the sum of the two operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#6](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_1.vb)]  
  
 <span data-ttu-id="614c3-179">你还可以使用`+`运算符来连接字符串。</span><span class="sxs-lookup"><span data-stu-id="614c3-179">You can also use the `+` operator to concatenate strings.</span></span> <span data-ttu-id="614c3-180">如果操作数均为两个字符串，Visual Basic 将它们连接。</span><span class="sxs-lookup"><span data-stu-id="614c3-180">If the operands are both strings, Visual Basic concatenates them.</span></span> <span data-ttu-id="614c3-181">串联结果表示单个字符串依次排列包含的两个操作数的内容。</span><span class="sxs-lookup"><span data-stu-id="614c3-181">The concatenation result represents a single string consisting of the contents of the two operands one after the other.</span></span>  
  
 <span data-ttu-id="614c3-182">如果操作数都是混合类型，结果取决于的设置[Option Strict 语句](../../../visual-basic/language-reference/statements/option-strict-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="614c3-182">If the operands are of mixed types, the result depends on the setting of the [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span> <span data-ttu-id="614c3-183">下面的示例演示结果时`Option Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="614c3-183">The following example illustrates the result when `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbVbalrOperators#53](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_2.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#51](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_4.vb)]  
  
 <span data-ttu-id="614c3-184">下面的示例演示结果时`Option Strict`是`Off`。</span><span class="sxs-lookup"><span data-stu-id="614c3-184">The following example illustrates the result when `Option Strict` is `Off`.</span></span>  
  
 [!code-vb[VbVbalrOperators#54](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_5.vb)]  
  
 [!code-vb[VbVbalrOperators#50](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_3.vb)]  
[!code-vb[VbVbalrOperators#52](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-operator_6.vb)]  
  
 <span data-ttu-id="614c3-185">若要消除混淆，应使用`&`运算符而不是`+`的串联。</span><span class="sxs-lookup"><span data-stu-id="614c3-185">To eliminate ambiguity, you should use the `&` operator instead of `+` for concatenation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="614c3-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="614c3-186">See Also</span></span>  
 [<span data-ttu-id="614c3-187">& 运算符</span><span class="sxs-lookup"><span data-stu-id="614c3-187">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [<span data-ttu-id="614c3-188">串联运算符</span><span class="sxs-lookup"><span data-stu-id="614c3-188">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="614c3-189">算术运算符</span><span class="sxs-lookup"><span data-stu-id="614c3-189">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [<span data-ttu-id="614c3-190">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="614c3-190">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="614c3-191">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="614c3-191">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="614c3-192">在 Visual Basic 中的算术运算符</span><span class="sxs-lookup"><span data-stu-id="614c3-192">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="614c3-193">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="614c3-193">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)

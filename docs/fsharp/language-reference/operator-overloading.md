---
title: 运算符重载 (F#)
description: '了解如何重载算术运算符在类或记录类型，然后在 F # 中的全局级别。'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 45fcb4d2acce29caa6b38d08ae4f166884f20147
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="operator-overloading"></a><span data-ttu-id="e0960-103">运算符重载</span><span class="sxs-lookup"><span data-stu-id="e0960-103">Operator Overloading</span></span>

<span data-ttu-id="e0960-104">本主题介绍如何重载算术运算符在类或记录类型，并在全局级别。</span><span class="sxs-lookup"><span data-stu-id="e0960-104">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>


## <a name="syntax"></a><span data-ttu-id="e0960-105">语法</span><span class="sxs-lookup"><span data-stu-id="e0960-105">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="e0960-106">备注</span><span class="sxs-lookup"><span data-stu-id="e0960-106">Remarks</span></span>
<span data-ttu-id="e0960-107">在上述语法中，*运算符符号*是之一`+`， `-`， `*`， `/`， `=`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="e0960-107">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="e0960-108">*参数列表*指定操作数中的该运算符的常用语法中显示的顺序。</span><span class="sxs-lookup"><span data-stu-id="e0960-108">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="e0960-109">*方法体*构造生成的值。</span><span class="sxs-lookup"><span data-stu-id="e0960-109">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="e0960-110">运算符重载的运算符必须是静态的。</span><span class="sxs-lookup"><span data-stu-id="e0960-110">Operator overloads for operators must be static.</span></span> <span data-ttu-id="e0960-111">运算符重载的一元运算符，如`+`和`-`，必须使用波形符 (`~`) 中*运算符符号*指示运算符是一元运算符而不是二元运算符，如所示下面的声明。</span><span class="sxs-lookup"><span data-stu-id="e0960-111">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="e0960-112">下面的代码演示一个仅包含两个运算符的矢量类，其中的一个运算符用于一元负运算，而另一个运算符用于标量乘法运算。</span><span class="sxs-lookup"><span data-stu-id="e0960-112">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="e0960-113">在示例中，用于标量乘法运算的两个重载被必需的因为运算符必须工作而不考虑矢量和标量出现的顺序。</span><span class="sxs-lookup"><span data-stu-id="e0960-113">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="e0960-114">创建新的运算符</span><span class="sxs-lookup"><span data-stu-id="e0960-114">Creating New Operators</span></span>
<span data-ttu-id="e0960-115">您可以重载所有标准的运算符，但你还可以创建新的某些字符序列的运算符。</span><span class="sxs-lookup"><span data-stu-id="e0960-115">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="e0960-116">允许的运算符字符为`!`， `%`， `&`， `*`， `+`， `-`， `.`， `/`， `<`， `=`， `>`， `?`， `@`， `^`， `|`，和`~`。</span><span class="sxs-lookup"><span data-stu-id="e0960-116">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="e0960-117">`~`字符具有特殊含义的一元运算符，但不可运算符字符序列的一部分。</span><span class="sxs-lookup"><span data-stu-id="e0960-117">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="e0960-118">并非所有运算符可以都进行一元。</span><span class="sxs-lookup"><span data-stu-id="e0960-118">Not all operators can be made unary.</span></span>

<span data-ttu-id="e0960-119">具体取决于你使用的确切字符序列，你运算符将具有特定优先级和关联性。</span><span class="sxs-lookup"><span data-stu-id="e0960-119">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="e0960-120">关联性可以是处于到右还是从右到左且出现在不带括号的序列中的相同级别的优先级的运算符时，需要使用。</span><span class="sxs-lookup"><span data-stu-id="e0960-120">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="e0960-121">运算符字符`.`不会影响优先，这样，例如，如果你想要定义您自己的具有相同的优先级和结合性作为普通乘法的乘法版本，你可以创建运算符，例如`.*`.</span><span class="sxs-lookup"><span data-stu-id="e0960-121">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="e0960-122">只有运算符`?`和`?<-`可能会启动与`?`。</span><span class="sxs-lookup"><span data-stu-id="e0960-122">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="e0960-123">在找不到表，其中显示 F # 中的所有运算符的优先级[符号和运算符参考](symbol-and-operator-reference/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e0960-123">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](symbol-and-operator-reference/index.md).</span></span>


## <a name="overloaded-operator-names"></a><span data-ttu-id="e0960-124">重载的运算符名称</span><span class="sxs-lookup"><span data-stu-id="e0960-124">Overloaded Operator Names</span></span>
<span data-ttu-id="e0960-125">当 F # 编译器编译运算符表达式时，它将生成具有该运算符的编译器生成名称的方法。</span><span class="sxs-lookup"><span data-stu-id="e0960-125">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="e0960-126">这是显示在该方法的 Microsoft 中间语言 (MSIL) 中以及在反射和 IntelliSense 的名称。</span><span class="sxs-lookup"><span data-stu-id="e0960-126">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="e0960-127">通常不需要在 F # 代码中使用这些名称。</span><span class="sxs-lookup"><span data-stu-id="e0960-127">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="e0960-128">下表显示了标准运算符和其相应的生成名称。</span><span class="sxs-lookup"><span data-stu-id="e0960-128">The following table shows the standard operators and their corresponding generated names.</span></span>



|<span data-ttu-id="e0960-129">运算符</span><span class="sxs-lookup"><span data-stu-id="e0960-129">Operator</span></span>|<span data-ttu-id="e0960-130">生成的名称</span><span class="sxs-lookup"><span data-stu-id="e0960-130">Generated name</span></span>|
|--------|--------------|
|`[]`|`op_Nil`|
|`::`|`op_Cons`|
|`+`|`op_Addition`|
|`-`|`op_Subtraction`|
|`*`|`op_Multiply`|
|`/`|`op_Division`|
|`@`|`op_Append`|
|`^`|`op_Concatenate`|
|`%`|`op_Modulus`|
|`&&&`|`op_BitwiseAnd`|
|<code>&#124;&#124;&#124;</code>|`op_BitwiseOr`|
|`^^^`|`op_ExclusiveOr`|
|`<<<`|`op_LeftShift`|
|`~~~`|`op_LogicalNot`|
|`>>>`|`op_RightShift`|
|`~+`|`op_UnaryPlus`|
|`~-`|`op_UnaryNegation`|
|`=`|`op_Equality`|
|`<=`|`op_LessThanOrEqual`|
|`>=`|`op_GreaterThanOrEqual`|
|`<`|`op_LessThan`|
|`>`|`op_GreaterThan`|
|`?`|`op_Dynamic`|
|`?<-`|`op_DynamicAssignment`|
|<code>&#124;></code>|`op_PipeRight`|
|<code><&#124;</code>|`op_PipeLeft`|
|`!`|`op_Dereference`|
|`>>`|`op_ComposeRight`|
|`<<`|`op_ComposeLeft`|
|`<@ @>`|`op_Quotation`|
|`<@@ @@>`|`op_QuotationUntyped`|
|`+=`|`op_AdditionAssignment`|
|`-=`|`op_SubtractionAssignment`|
|`*=`|`op_MultiplyAssignment`|
|`/=`|`op_DivisionAssignment`|
|`..`|`op_Range`|
|`.. ..`|`op_RangeStep`|
<span data-ttu-id="e0960-131">未在此处列出的运算符字符的其他组合可以用作运算符，并具有通过串联名称下表中的每个字符组成的名称。</span><span class="sxs-lookup"><span data-stu-id="e0960-131">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="e0960-132">例如，+ ！</span><span class="sxs-lookup"><span data-stu-id="e0960-132">For example, +!</span></span> <span data-ttu-id="e0960-133">将成为`op_PlusBang`。</span><span class="sxs-lookup"><span data-stu-id="e0960-133">becomes `op_PlusBang`.</span></span>



|<span data-ttu-id="e0960-134">运算符字符</span><span class="sxs-lookup"><span data-stu-id="e0960-134">Operator character</span></span>|<span data-ttu-id="e0960-135">名称</span><span class="sxs-lookup"><span data-stu-id="e0960-135">Name</span></span>|
|------------------|----|
|`>`|`Greater`|
|`<`|`Less`|
|`+`|`Plus`|
|`-`|`Minus`|
|`*`|`Multiply`|
|`/`|`Divide`|
|`=`|`Equals`|
|`~`|`Twiddle`|
|`%`|`Percent`|
|`.`|`Dot`|
|`&`|`Amp`|
|<code>&#124;</code>|`Bar`|
|`@`|`At`|
|`^`|`Hat`|
|`!`|`Bang`|
|`?`|`Qmark`|
|`(`|`LParen`|
|`,`|`Comma`|
|`)`|`RParen`|
|`[`|`LBrack`|
|`]`|`RBrack`|

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="e0960-136">前缀和中缀运算符</span><span class="sxs-lookup"><span data-stu-id="e0960-136">Prefix and Infix Operators</span></span>
<span data-ttu-id="e0960-137">*前缀*运算符应放置之前操作数或多个操作数，类似于函数。</span><span class="sxs-lookup"><span data-stu-id="e0960-137">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="e0960-138">*中缀*运算符需要两个操作数之间放置。</span><span class="sxs-lookup"><span data-stu-id="e0960-138">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="e0960-139">只有某些运算符可以用作前缀运算符。</span><span class="sxs-lookup"><span data-stu-id="e0960-139">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="e0960-140">有些运算符始终是前缀运算符，其他人可能中缀或前缀，并且 rest 始终中缀运算符。</span><span class="sxs-lookup"><span data-stu-id="e0960-140">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="e0960-141">除了 `!` 之外，以 `!=` 开头的运算符以及运算符 `~` 或 `~` 的重复序列始终为前缀运算符。</span><span class="sxs-lookup"><span data-stu-id="e0960-141">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="e0960-142">运算符`+`， `-`， `+.`， `-.`， `&`， `&&`， `%`，和`%%`可以是前缀运算符或中缀运算符。</span><span class="sxs-lookup"><span data-stu-id="e0960-142">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="e0960-143">通过添加将这些运算符的前缀版本分开的中缀版本中，你`~`在定义了该前缀运算符开头。</span><span class="sxs-lookup"><span data-stu-id="e0960-143">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="e0960-144">`~`时仅在定义它时，才使用运算符，不使用。</span><span class="sxs-lookup"><span data-stu-id="e0960-144">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="e0960-145">示例</span><span class="sxs-lookup"><span data-stu-id="e0960-145">Example</span></span>

<span data-ttu-id="e0960-146">下面的代码演示如何使用运算符重载来实现部分类型。</span><span class="sxs-lookup"><span data-stu-id="e0960-146">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="e0960-147">表示一小部分为分子和分母。</span><span class="sxs-lookup"><span data-stu-id="e0960-147">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="e0960-148">该函数`hcf`用于确定最高常见因子，用于将用于减少分数 （竖式）。</span><span class="sxs-lookup"><span data-stu-id="e0960-148">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="e0960-149">**输出：**</span><span class="sxs-lookup"><span data-stu-id="e0960-149">**Output:**</span></span>

```
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="e0960-150">在全局级别的运算符</span><span class="sxs-lookup"><span data-stu-id="e0960-150">Operators at the Global Level</span></span>
<span data-ttu-id="e0960-151">你还可以定义在全局级别的运算符。</span><span class="sxs-lookup"><span data-stu-id="e0960-151">You can also define operators at the global level.</span></span> <span data-ttu-id="e0960-152">下面的代码定义一个运算符`+?`。</span><span class="sxs-lookup"><span data-stu-id="e0960-152">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="e0960-153">上面的代码的输出是`12`。</span><span class="sxs-lookup"><span data-stu-id="e0960-153">The output of the above code is `12`.</span></span>

<span data-ttu-id="e0960-154">因为 F # 的范围规则规定新定义的运算符，优先于内置运算符，您可以重新定义这种方式中的正则算术运算符。</span><span class="sxs-lookup"><span data-stu-id="e0960-154">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="e0960-155">关键字`inline`通常会与全局运算符，这通常是最好集成到调用代码的小函数使用。</span><span class="sxs-lookup"><span data-stu-id="e0960-155">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="e0960-156">进行运算符函数内联还使他们能够使用静态解析的类型参数，以生成静态解析的泛型代码。</span><span class="sxs-lookup"><span data-stu-id="e0960-156">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="e0960-157">有关详细信息，请参阅[内联函数](functions/inline-functions.md)和[静态解析的类型参数](generics/statically-resolved-type-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="e0960-157">For more information, see [Inline Functions](functions/inline-functions.md) and [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e0960-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0960-158">See Also</span></span>
[<span data-ttu-id="e0960-159">成员</span><span class="sxs-lookup"><span data-stu-id="e0960-159">Members</span></span>](members/index.md)

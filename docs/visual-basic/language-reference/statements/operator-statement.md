---
title: Operator 语句
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: aa6ae3977977ded05e47d12dabe72f09251f262d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353795"
---
# <a name="operator-statement"></a><span data-ttu-id="b1ced-102">Operator 语句</span><span class="sxs-lookup"><span data-stu-id="b1ced-102">Operator Statement</span></span>

<span data-ttu-id="b1ced-103">声明在类或结构上定义运算符过程的运算符符号、操作数和代码。</span><span class="sxs-lookup"><span data-stu-id="b1ced-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="b1ced-104">语法</span><span class="sxs-lookup"><span data-stu-id="b1ced-104">Syntax</span></span>

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a><span data-ttu-id="b1ced-105">部件</span><span class="sxs-lookup"><span data-stu-id="b1ced-105">Parts</span></span>

`attrlist`  
<span data-ttu-id="b1ced-106">可选。</span><span class="sxs-lookup"><span data-stu-id="b1ced-106">Optional.</span></span> <span data-ttu-id="b1ced-107">请参阅[特性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="b1ced-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

`Public`  
<span data-ttu-id="b1ced-108">必需。</span><span class="sxs-lookup"><span data-stu-id="b1ced-108">Required.</span></span> <span data-ttu-id="b1ced-109">指示此运算符过程具有[公共](../../../visual-basic/language-reference/modifiers/public.md)访问权限。</span><span class="sxs-lookup"><span data-stu-id="b1ced-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>

`Overloads`  
<span data-ttu-id="b1ced-110">可选。</span><span class="sxs-lookup"><span data-stu-id="b1ced-110">Optional.</span></span> <span data-ttu-id="b1ced-111">请参阅[重载](../../../visual-basic/language-reference/modifiers/overloads.md)。</span><span class="sxs-lookup"><span data-stu-id="b1ced-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>

`Shared`  
<span data-ttu-id="b1ced-112">必需。</span><span class="sxs-lookup"><span data-stu-id="b1ced-112">Required.</span></span> <span data-ttu-id="b1ced-113">指示此运算符过程是一个[共享](../../../visual-basic/language-reference/modifiers/shared.md)过程。</span><span class="sxs-lookup"><span data-stu-id="b1ced-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>

`Shadows`  
<span data-ttu-id="b1ced-114">可选。</span><span class="sxs-lookup"><span data-stu-id="b1ced-114">Optional.</span></span> <span data-ttu-id="b1ced-115">请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。</span><span class="sxs-lookup"><span data-stu-id="b1ced-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

`Widening`  
<span data-ttu-id="b1ced-116">对于转换运算符是必需的，除非指定 `Narrowing`。</span><span class="sxs-lookup"><span data-stu-id="b1ced-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="b1ced-117">指示此运算符过程定义[扩大](../../../visual-basic/language-reference/modifiers/widening.md)转换。</span><span class="sxs-lookup"><span data-stu-id="b1ced-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="b1ced-118">请参阅此帮助页上的 "扩大和收缩转换"。</span><span class="sxs-lookup"><span data-stu-id="b1ced-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`Narrowing`  
<span data-ttu-id="b1ced-119">对于转换运算符是必需的，除非指定 `Widening`。</span><span class="sxs-lookup"><span data-stu-id="b1ced-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="b1ced-120">指示此运算符过程定义[收缩](../../../visual-basic/language-reference/modifiers/narrowing.md)转换。</span><span class="sxs-lookup"><span data-stu-id="b1ced-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="b1ced-121">请参阅此帮助页上的 "扩大和收缩转换"。</span><span class="sxs-lookup"><span data-stu-id="b1ced-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>

`operatorsymbol`  
<span data-ttu-id="b1ced-122">必需。</span><span class="sxs-lookup"><span data-stu-id="b1ced-122">Required.</span></span> <span data-ttu-id="b1ced-123">此运算符过程所定义的运算符的符号或标识符。</span><span class="sxs-lookup"><span data-stu-id="b1ced-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>

`operand1`  
<span data-ttu-id="b1ced-124">必需。</span><span class="sxs-lookup"><span data-stu-id="b1ced-124">Required.</span></span> <span data-ttu-id="b1ced-125">一元运算符的单个操作数的名称和类型（包括转换运算符）或二元运算符的左操作数。</span><span class="sxs-lookup"><span data-stu-id="b1ced-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>

`operand2`  
<span data-ttu-id="b1ced-126">对于二元运算符是必需的。</span><span class="sxs-lookup"><span data-stu-id="b1ced-126">Required for binary operators.</span></span> <span data-ttu-id="b1ced-127">二元运算符的右操作数的名称和类型。</span><span class="sxs-lookup"><span data-stu-id="b1ced-127">The name and type of the right operand of a binary operator.</span></span>

<span data-ttu-id="b1ced-128">`operand1` 和 `operand2` 具有以下语法和部分：</span><span class="sxs-lookup"><span data-stu-id="b1ced-128">`operand1` and `operand2` have the following syntax and parts:</span></span>

`[ ByVal ] operandname [ As operandtype ]`

|<span data-ttu-id="b1ced-129">部件</span><span class="sxs-lookup"><span data-stu-id="b1ced-129">Part</span></span>|<span data-ttu-id="b1ced-130">说明</span><span class="sxs-lookup"><span data-stu-id="b1ced-130">Description</span></span>|
|----------|-----------------|
|`ByVal`|<span data-ttu-id="b1ced-131">可选，但传递机制必须是[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="b1ced-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|
|`operandname`|<span data-ttu-id="b1ced-132">必需。</span><span class="sxs-lookup"><span data-stu-id="b1ced-132">Required.</span></span> <span data-ttu-id="b1ced-133">表示此操作数的变量的名称。</span><span class="sxs-lookup"><span data-stu-id="b1ced-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="b1ced-134">请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="b1ced-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
|`operandtype`|<span data-ttu-id="b1ced-135">除非 `On``Option Strict`，否则为可选。</span><span class="sxs-lookup"><span data-stu-id="b1ced-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="b1ced-136">此操作数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b1ced-136">Data type of this operand.</span></span>|

`type`  
<span data-ttu-id="b1ced-137">除非 `On``Option Strict`，否则为可选。</span><span class="sxs-lookup"><span data-stu-id="b1ced-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="b1ced-138">运算符过程返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b1ced-138">Data type of the value the operator procedure returns.</span></span>

`statements`  
<span data-ttu-id="b1ced-139">可选。</span><span class="sxs-lookup"><span data-stu-id="b1ced-139">Optional.</span></span> <span data-ttu-id="b1ced-140">运算符过程运行的语句块。</span><span class="sxs-lookup"><span data-stu-id="b1ced-140">Block of statements that the operator procedure runs.</span></span>

`returnvalue`  
<span data-ttu-id="b1ced-141">必需。</span><span class="sxs-lookup"><span data-stu-id="b1ced-141">Required.</span></span> <span data-ttu-id="b1ced-142">运算符过程返回到调用代码的值。</span><span class="sxs-lookup"><span data-stu-id="b1ced-142">The value that the operator procedure returns to the calling code.</span></span>

<span data-ttu-id="b1ced-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="b1ced-143">`End` `Operator`</span></span>  
<span data-ttu-id="b1ced-144">必需。</span><span class="sxs-lookup"><span data-stu-id="b1ced-144">Required.</span></span> <span data-ttu-id="b1ced-145">终止此运算符过程的定义。</span><span class="sxs-lookup"><span data-stu-id="b1ced-145">Terminates the definition of this operator procedure.</span></span>

## <a name="remarks"></a><span data-ttu-id="b1ced-146">备注</span><span class="sxs-lookup"><span data-stu-id="b1ced-146">Remarks</span></span>

<span data-ttu-id="b1ced-147">只能在类或结构中使用 `Operator`。</span><span class="sxs-lookup"><span data-stu-id="b1ced-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="b1ced-148">这意味着运算符的*声明上下文*不能是源文件、命名空间、模块、接口、过程或块。</span><span class="sxs-lookup"><span data-stu-id="b1ced-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="b1ced-149">有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="b1ced-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="b1ced-150">所有运算符都必须 `Public Shared`。</span><span class="sxs-lookup"><span data-stu-id="b1ced-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="b1ced-151">不能为任一操作数指定 `ByRef`、`Optional`或 `ParamArray`。</span><span class="sxs-lookup"><span data-stu-id="b1ced-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>

<span data-ttu-id="b1ced-152">不能使用运算符符号或标识符来保存返回值。</span><span class="sxs-lookup"><span data-stu-id="b1ced-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="b1ced-153">必须使用 `Return` 语句，并且必须指定一个值。</span><span class="sxs-lookup"><span data-stu-id="b1ced-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="b1ced-154">任意数量的 `Return` 语句可以出现在过程中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="b1ced-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>

<span data-ttu-id="b1ced-155">以这种方式定义运算符称为*运算符重载*，无论是否使用 `Overloads` 关键字。</span><span class="sxs-lookup"><span data-stu-id="b1ced-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="b1ced-156">下表列出了可定义的运算符。</span><span class="sxs-lookup"><span data-stu-id="b1ced-156">The following table lists the operators you can define.</span></span>

|<span data-ttu-id="b1ced-157">类型</span><span class="sxs-lookup"><span data-stu-id="b1ced-157">Type</span></span>|<span data-ttu-id="b1ced-158">运算符</span><span class="sxs-lookup"><span data-stu-id="b1ced-158">Operators</span></span>|
|----------|---------------|
|<span data-ttu-id="b1ced-159">一元</span><span class="sxs-lookup"><span data-stu-id="b1ced-159">Unary</span></span>|<span data-ttu-id="b1ced-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="b1ced-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|
|<span data-ttu-id="b1ced-161">Binary</span><span class="sxs-lookup"><span data-stu-id="b1ced-161">Binary</span></span>|<span data-ttu-id="b1ced-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="b1ced-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|
|<span data-ttu-id="b1ced-163">转换（一元）</span><span class="sxs-lookup"><span data-stu-id="b1ced-163">Conversion (unary)</span></span>|`CType`|

<span data-ttu-id="b1ced-164">请注意，二元列表中的 `=` 运算符是比较运算符，而不是赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="b1ced-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>

<span data-ttu-id="b1ced-165">在定义 `CType`时，必须指定 `Widening` 或 `Narrowing`。</span><span class="sxs-lookup"><span data-stu-id="b1ced-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>

## <a name="matched-pairs"></a><span data-ttu-id="b1ced-166">匹配对</span><span class="sxs-lookup"><span data-stu-id="b1ced-166">Matched Pairs</span></span>

<span data-ttu-id="b1ced-167">必须将某些运算符定义为匹配对。</span><span class="sxs-lookup"><span data-stu-id="b1ced-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="b1ced-168">如果定义此类对的任一运算符，则还必须定义其他运算符。</span><span class="sxs-lookup"><span data-stu-id="b1ced-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="b1ced-169">匹配对如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1ced-169">The matched pairs are the following:</span></span>

- <span data-ttu-id="b1ced-170">`=` 和 `<>`</span><span class="sxs-lookup"><span data-stu-id="b1ced-170">`=` and `<>`</span></span>

- <span data-ttu-id="b1ced-171">`>` 和 `<`</span><span class="sxs-lookup"><span data-stu-id="b1ced-171">`>` and `<`</span></span>

- <span data-ttu-id="b1ced-172">`>=` 和 `<=`</span><span class="sxs-lookup"><span data-stu-id="b1ced-172">`>=` and `<=`</span></span>

- <span data-ttu-id="b1ced-173">`IsTrue` 和 `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="b1ced-173">`IsTrue` and `IsFalse`</span></span>

## <a name="data-type-restrictions"></a><span data-ttu-id="b1ced-174">数据类型限制</span><span class="sxs-lookup"><span data-stu-id="b1ced-174">Data Type Restrictions</span></span>

<span data-ttu-id="b1ced-175">你定义的每个运算符都必须涉及你定义它的类或结构。</span><span class="sxs-lookup"><span data-stu-id="b1ced-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="b1ced-176">这意味着，类或结构必须显示为以下类型的数据类型：</span><span class="sxs-lookup"><span data-stu-id="b1ced-176">This means that the class or structure must appear as the data type of the following:</span></span>

- <span data-ttu-id="b1ced-177">一元运算符的操作数。</span><span class="sxs-lookup"><span data-stu-id="b1ced-177">The operand of a unary operator.</span></span>

- <span data-ttu-id="b1ced-178">二元运算符的至少一个操作数。</span><span class="sxs-lookup"><span data-stu-id="b1ced-178">At least one of the operands of a binary operator.</span></span>

- <span data-ttu-id="b1ced-179">转换运算符的操作数或返回类型。</span><span class="sxs-lookup"><span data-stu-id="b1ced-179">Either the operand or the return type of a conversion operator.</span></span>

 <span data-ttu-id="b1ced-180">某些运算符具有额外的数据类型限制，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b1ced-180">Certain operators have additional data type restrictions, as follows:</span></span>

- <span data-ttu-id="b1ced-181">如果定义 `IsTrue` 和 `IsFalse` 运算符，则它们必须返回 `Boolean` 类型。</span><span class="sxs-lookup"><span data-stu-id="b1ced-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>

- <span data-ttu-id="b1ced-182">如果定义 `<<` 和 `>>` 运算符，则它们必须为 `operand2`的 `operandtype` 指定 `Integer` 类型。</span><span class="sxs-lookup"><span data-stu-id="b1ced-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>

<span data-ttu-id="b1ced-183">返回类型不一定对应于任一操作数的类型。</span><span class="sxs-lookup"><span data-stu-id="b1ced-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="b1ced-184">例如，即使两个操作数都不 `Boolean`，`=` 或 `<>` 这样的比较运算符也可能返回 `Boolean`。</span><span class="sxs-lookup"><span data-stu-id="b1ced-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>

## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="b1ced-185">逻辑运算符和位运算符</span><span class="sxs-lookup"><span data-stu-id="b1ced-185">Logical and Bitwise Operators</span></span>

<span data-ttu-id="b1ced-186">`And`、`Or`、`Not`和 `Xor` 运算符可在 Visual Basic 中执行逻辑或按位运算。</span><span class="sxs-lookup"><span data-stu-id="b1ced-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="b1ced-187">但是，如果在类或结构上定义这些运算符之一，则只能定义其按位运算。</span><span class="sxs-lookup"><span data-stu-id="b1ced-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>

<span data-ttu-id="b1ced-188">不能使用 `Operator` 语句直接定义 `AndAlso` 运算符。</span><span class="sxs-lookup"><span data-stu-id="b1ced-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="b1ced-189">不过，如果已满足以下条件，则可以使用 `AndAlso`：</span><span class="sxs-lookup"><span data-stu-id="b1ced-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>

- <span data-ttu-id="b1ced-190">已在要用于 `AndAlso`的相同操作数类型上定义 `And`。</span><span class="sxs-lookup"><span data-stu-id="b1ced-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>

- <span data-ttu-id="b1ced-191">`And` 的定义返回的类型与定义它的类或结构的类型相同。</span><span class="sxs-lookup"><span data-stu-id="b1ced-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>

- <span data-ttu-id="b1ced-192">您已在定义了 `And`的类或结构上定义 `IsFalse` 运算符。</span><span class="sxs-lookup"><span data-stu-id="b1ced-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>

<span data-ttu-id="b1ced-193">同样，如果已使用类或结构的返回类型在同一操作数上定义了 `Or`，并且已在类或结构上定义了 `IsTrue`，则可以使用 `OrElse`。</span><span class="sxs-lookup"><span data-stu-id="b1ced-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>

## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="b1ced-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="b1ced-194">Widening and Narrowing Conversions</span></span>

<span data-ttu-id="b1ced-195">在运行时，*扩大转换*始终会成功，而*收缩转换*可能会在运行时失败。</span><span class="sxs-lookup"><span data-stu-id="b1ced-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="b1ced-196">有关详细信息，请参阅 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="b1ced-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="b1ced-197">如果声明要 `Widening`的转换过程，则过程代码不得生成任何失败。</span><span class="sxs-lookup"><span data-stu-id="b1ced-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="b1ced-198">这意味着：</span><span class="sxs-lookup"><span data-stu-id="b1ced-198">This means the following:</span></span>

- <span data-ttu-id="b1ced-199">它必须始终返回 `type`类型的有效值。</span><span class="sxs-lookup"><span data-stu-id="b1ced-199">It must always return a valid value of type `type`.</span></span>

- <span data-ttu-id="b1ced-200">它必须处理所有可能的异常和其他错误情况。</span><span class="sxs-lookup"><span data-stu-id="b1ced-200">It must handle all possible exceptions and other error conditions.</span></span>

- <span data-ttu-id="b1ced-201">它必须处理它所调用的任何过程中的任何错误。</span><span class="sxs-lookup"><span data-stu-id="b1ced-201">It must handle any error returns from any procedures it calls.</span></span>

<span data-ttu-id="b1ced-202">如果转换过程可能会失败或可能导致未经处理的异常，则必须将其声明为 `Narrowing`。</span><span class="sxs-lookup"><span data-stu-id="b1ced-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>

## <a name="example"></a><span data-ttu-id="b1ced-203">示例</span><span class="sxs-lookup"><span data-stu-id="b1ced-203">Example</span></span>

<span data-ttu-id="b1ced-204">下面的代码示例使用 `Operator` 语句来定义结构的轮廓，其中包括 `And`、`Or`、`IsFalse`和 `IsTrue` 运算符的运算符过程。</span><span class="sxs-lookup"><span data-stu-id="b1ced-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="b1ced-205">`And` 和 `Or` 每个都采用类型 `abc` 和返回类型 `abc`两个操作数。</span><span class="sxs-lookup"><span data-stu-id="b1ced-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="b1ced-206">`IsFalse` 和 `IsTrue` 每个都采用 `abc` 类型的单个操作数并返回 `Boolean`。</span><span class="sxs-lookup"><span data-stu-id="b1ced-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="b1ced-207">这些定义允许调用代码将 `And`、`AndAlso`、`Or`和 `OrElse` 与 `abc`类型的操作数一起使用。</span><span class="sxs-lookup"><span data-stu-id="b1ced-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a><span data-ttu-id="b1ced-208">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1ced-208">See also</span></span>

- [<span data-ttu-id="b1ced-209">IsFalse 运算符</span><span class="sxs-lookup"><span data-stu-id="b1ced-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [<span data-ttu-id="b1ced-210">IsTrue 运算符</span><span class="sxs-lookup"><span data-stu-id="b1ced-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [<span data-ttu-id="b1ced-211">Widening</span><span class="sxs-lookup"><span data-stu-id="b1ced-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)
- [<span data-ttu-id="b1ced-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="b1ced-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="b1ced-213">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="b1ced-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="b1ced-214">运算符过程</span><span class="sxs-lookup"><span data-stu-id="b1ced-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="b1ced-215">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="b1ced-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="b1ced-216">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="b1ced-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="b1ced-217">如何：调用运算符过程</span><span class="sxs-lookup"><span data-stu-id="b1ced-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [<span data-ttu-id="b1ced-218">如何：使用定义运算符的类</span><span class="sxs-lookup"><span data-stu-id="b1ced-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)

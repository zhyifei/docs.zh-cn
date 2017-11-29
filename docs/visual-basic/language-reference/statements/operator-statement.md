---
title: Operator Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.operator
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
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1b6be45fd0a606f43c14d57f3f8ae0955f256ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="operator-statement"></a><span data-ttu-id="dba1d-102">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="dba1d-102">Operator Statement</span></span>
<span data-ttu-id="dba1d-103">声明运算符，操作数，并在类或结构定义运算符过程的代码。</span><span class="sxs-lookup"><span data-stu-id="dba1d-103">Declares the operator symbol, operands, and code that define an operator procedure on a class or structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dba1d-104">语法</span><span class="sxs-lookup"><span data-stu-id="dba1d-104">Syntax</span></span>  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a><span data-ttu-id="dba1d-105">部件</span><span class="sxs-lookup"><span data-stu-id="dba1d-105">Parts</span></span>  
 `attrlist`  
 <span data-ttu-id="dba1d-106">可选。</span><span class="sxs-lookup"><span data-stu-id="dba1d-106">Optional.</span></span> <span data-ttu-id="dba1d-107">请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="dba1d-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `Public`  
 <span data-ttu-id="dba1d-108">必需。</span><span class="sxs-lookup"><span data-stu-id="dba1d-108">Required.</span></span> <span data-ttu-id="dba1d-109">指示此运算符过程具有[公共](../../../visual-basic/language-reference/modifiers/public.md)访问。</span><span class="sxs-lookup"><span data-stu-id="dba1d-109">Indicates that this operator procedure has [Public](../../../visual-basic/language-reference/modifiers/public.md) access.</span></span>  
  
 `Overloads`  
 <span data-ttu-id="dba1d-110">可选。</span><span class="sxs-lookup"><span data-stu-id="dba1d-110">Optional.</span></span> <span data-ttu-id="dba1d-111">请参阅[重载](../../../visual-basic/language-reference/modifiers/overloads.md)。</span><span class="sxs-lookup"><span data-stu-id="dba1d-111">See [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).</span></span>  
  
 `Shared`  
 <span data-ttu-id="dba1d-112">必需。</span><span class="sxs-lookup"><span data-stu-id="dba1d-112">Required.</span></span> <span data-ttu-id="dba1d-113">指示此运算符过程是[共享](../../../visual-basic/language-reference/modifiers/shared.md)过程。</span><span class="sxs-lookup"><span data-stu-id="dba1d-113">Indicates that this operator procedure is a [Shared](../../../visual-basic/language-reference/modifiers/shared.md) procedure.</span></span>  
  
 `Shadows`  
 <span data-ttu-id="dba1d-114">可选。</span><span class="sxs-lookup"><span data-stu-id="dba1d-114">Optional.</span></span> <span data-ttu-id="dba1d-115">请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。</span><span class="sxs-lookup"><span data-stu-id="dba1d-115">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `Widening`  
 <span data-ttu-id="dba1d-116">除非另行指定，所需的转换运算符`Narrowing`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-116">Required for a conversion operator unless you specify `Narrowing`.</span></span> <span data-ttu-id="dba1d-117">指示此运算符过程定义[Widening](../../../visual-basic/language-reference/modifiers/widening.md)转换。</span><span class="sxs-lookup"><span data-stu-id="dba1d-117">Indicates that this operator procedure defines a [Widening](../../../visual-basic/language-reference/modifiers/widening.md) conversion.</span></span> <span data-ttu-id="dba1d-118">此帮助页上，请参见"扩大转换和收缩转换"。</span><span class="sxs-lookup"><span data-stu-id="dba1d-118">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `Narrowing`  
 <span data-ttu-id="dba1d-119">除非另行指定，所需的转换运算符`Widening`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-119">Required for a conversion operator unless you specify `Widening`.</span></span> <span data-ttu-id="dba1d-120">指示此运算符过程定义[Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)转换。</span><span class="sxs-lookup"><span data-stu-id="dba1d-120">Indicates that this operator procedure defines a [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) conversion.</span></span> <span data-ttu-id="dba1d-121">此帮助页上，请参见"扩大转换和收缩转换"。</span><span class="sxs-lookup"><span data-stu-id="dba1d-121">See "Widening and Narrowing Conversions" on this Help page.</span></span>  
  
 `operatorsymbol`  
 <span data-ttu-id="dba1d-122">必需。</span><span class="sxs-lookup"><span data-stu-id="dba1d-122">Required.</span></span> <span data-ttu-id="dba1d-123">符号或运算符的此运算符过程所定义的标识符。</span><span class="sxs-lookup"><span data-stu-id="dba1d-123">The symbol or identifier of the operator that this operator procedure defines.</span></span>  
  
 `operand1`  
 <span data-ttu-id="dba1d-124">必需。</span><span class="sxs-lookup"><span data-stu-id="dba1d-124">Required.</span></span> <span data-ttu-id="dba1d-125">名称和的一元运算符 （包括转换运算符） 的单个操作数或二元运算符的左的操作数的类型。</span><span class="sxs-lookup"><span data-stu-id="dba1d-125">The name and type of the single operand of a unary operator (including a conversion operator) or the left operand of a binary operator.</span></span>  
  
 `operand2`  
 <span data-ttu-id="dba1d-126">所需的二元运算符。</span><span class="sxs-lookup"><span data-stu-id="dba1d-126">Required for binary operators.</span></span> <span data-ttu-id="dba1d-127">名称和二元运算符的右操作数的类型。</span><span class="sxs-lookup"><span data-stu-id="dba1d-127">The name and type of the right operand of a binary operator.</span></span>  
  
 <span data-ttu-id="dba1d-128">`operand1`和`operand2`具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="dba1d-128">`operand1` and `operand2` have the following syntax and parts:</span></span>  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|<span data-ttu-id="dba1d-129">部件</span><span class="sxs-lookup"><span data-stu-id="dba1d-129">Part</span></span>|<span data-ttu-id="dba1d-130">描述</span><span class="sxs-lookup"><span data-stu-id="dba1d-130">Description</span></span>|  
|----------|-----------------|  
|`ByVal`|<span data-ttu-id="dba1d-131">可选，但的传递机制必须[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="dba1d-131">Optional, but the passing mechanism must be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>|  
|`operandname`|<span data-ttu-id="dba1d-132">必需。</span><span class="sxs-lookup"><span data-stu-id="dba1d-132">Required.</span></span> <span data-ttu-id="dba1d-133">表示此操作数的变量的名称。</span><span class="sxs-lookup"><span data-stu-id="dba1d-133">Name of the variable representing this operand.</span></span> <span data-ttu-id="dba1d-134">请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="dba1d-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`operandtype`|<span data-ttu-id="dba1d-135">可选除非`Option Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-135">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="dba1d-136">此操作数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="dba1d-136">Data type of this operand.</span></span>|  
  
 `type`  
 <span data-ttu-id="dba1d-137">可选除非`Option Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-137">Optional unless `Option Strict` is `On`.</span></span> <span data-ttu-id="dba1d-138">运算符过程的值的数据类型返回。</span><span class="sxs-lookup"><span data-stu-id="dba1d-138">Data type of the value the operator procedure returns.</span></span>  
  
 `statements`  
 <span data-ttu-id="dba1d-139">可选。</span><span class="sxs-lookup"><span data-stu-id="dba1d-139">Optional.</span></span> <span data-ttu-id="dba1d-140">运算符过程运行的语句块。</span><span class="sxs-lookup"><span data-stu-id="dba1d-140">Block of statements that the operator procedure runs.</span></span>  
  
 `returnvalue`  
 <span data-ttu-id="dba1d-141">必需。</span><span class="sxs-lookup"><span data-stu-id="dba1d-141">Required.</span></span> <span data-ttu-id="dba1d-142">运算符过程返回到调用代码的值。</span><span class="sxs-lookup"><span data-stu-id="dba1d-142">The value that the operator procedure returns to the calling code.</span></span>  
  
 <span data-ttu-id="dba1d-143">`End` `Operator`</span><span class="sxs-lookup"><span data-stu-id="dba1d-143">`End` `Operator`</span></span>  
 <span data-ttu-id="dba1d-144">必需。</span><span class="sxs-lookup"><span data-stu-id="dba1d-144">Required.</span></span> <span data-ttu-id="dba1d-145">终止此运算符过程的定义。</span><span class="sxs-lookup"><span data-stu-id="dba1d-145">Terminates the definition of this operator procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dba1d-146">备注</span><span class="sxs-lookup"><span data-stu-id="dba1d-146">Remarks</span></span>  
 <span data-ttu-id="dba1d-147">你可以使用`Operator`只能在类或结构中。</span><span class="sxs-lookup"><span data-stu-id="dba1d-147">You can use `Operator` only in a class or structure.</span></span> <span data-ttu-id="dba1d-148">这意味着*声明上下文*运算符不能是源文件、 命名空间、 模块、 接口、 过程或块。</span><span class="sxs-lookup"><span data-stu-id="dba1d-148">This means the *declaration context* for an operator cannot be a source file, namespace, module, interface, procedure, or block.</span></span> <span data-ttu-id="dba1d-149">有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="dba1d-149">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="dba1d-150">所有运算符必须都是`Public Shared`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-150">All operators must be `Public Shared`.</span></span> <span data-ttu-id="dba1d-151">不能指定`ByRef`， `Optional`，或`ParamArray`为其中一个操作数。</span><span class="sxs-lookup"><span data-stu-id="dba1d-151">You cannot specify `ByRef`, `Optional`, or `ParamArray` for either operand.</span></span>  
  
 <span data-ttu-id="dba1d-152">不能使用运算符或标识符保留返回值。</span><span class="sxs-lookup"><span data-stu-id="dba1d-152">You cannot use the operator symbol or identifier to hold a return value.</span></span> <span data-ttu-id="dba1d-153">必须使用`Return`语句，并且它必须指定一个值。</span><span class="sxs-lookup"><span data-stu-id="dba1d-153">You must use the `Return` statement, and it must specify a value.</span></span> <span data-ttu-id="dba1d-154">任意数量的`Return`语句可以在过程中任何位置显示。</span><span class="sxs-lookup"><span data-stu-id="dba1d-154">Any number of `Return` statements can appear anywhere in the procedure.</span></span>  
  
 <span data-ttu-id="dba1d-155">以这种方式定义一个运算符调用*运算符重载*，而无论你使用`Overloads`关键字。</span><span class="sxs-lookup"><span data-stu-id="dba1d-155">Defining an operator in this way is called *operator overloading*, whether or not you use the `Overloads` keyword.</span></span> <span data-ttu-id="dba1d-156">下表列出了可定义的运算符。</span><span class="sxs-lookup"><span data-stu-id="dba1d-156">The following table lists the operators you can define.</span></span>  
  
|<span data-ttu-id="dba1d-157">类型</span><span class="sxs-lookup"><span data-stu-id="dba1d-157">Type</span></span>|<span data-ttu-id="dba1d-158">运算符</span><span class="sxs-lookup"><span data-stu-id="dba1d-158">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="dba1d-159">一元</span><span class="sxs-lookup"><span data-stu-id="dba1d-159">Unary</span></span>|<span data-ttu-id="dba1d-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="dba1d-160">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="dba1d-161">二进制</span><span class="sxs-lookup"><span data-stu-id="dba1d-161">Binary</span></span>|<span data-ttu-id="dba1d-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="dba1d-162">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="dba1d-163">转换（一元）</span><span class="sxs-lookup"><span data-stu-id="dba1d-163">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="dba1d-164">请注意，`=`二元列表中的运算符是比较运算符，而不是赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="dba1d-164">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="dba1d-165">在定义`CType`，您必须指定`Widening`或`Narrowing`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-165">When you define `CType`, you must specify either `Widening` or `Narrowing`.</span></span>  
  
## <a name="matched-pairs"></a><span data-ttu-id="dba1d-166">匹配的对</span><span class="sxs-lookup"><span data-stu-id="dba1d-166">Matched Pairs</span></span>  
 <span data-ttu-id="dba1d-167">你必须定义匹配对某些运算符。</span><span class="sxs-lookup"><span data-stu-id="dba1d-167">You must define certain operators as matched pairs.</span></span> <span data-ttu-id="dba1d-168">如果定义此类对任一运算符时，必须定义对其他。</span><span class="sxs-lookup"><span data-stu-id="dba1d-168">If you define either operator of such a pair, you must define the other as well.</span></span> <span data-ttu-id="dba1d-169">匹配的对如下所示：</span><span class="sxs-lookup"><span data-stu-id="dba1d-169">The matched pairs are the following:</span></span>  
  
-   <span data-ttu-id="dba1d-170">`=` 和 `<>`</span><span class="sxs-lookup"><span data-stu-id="dba1d-170">`=` and `<>`</span></span>  
  
-   <span data-ttu-id="dba1d-171">`>` 和 `<`</span><span class="sxs-lookup"><span data-stu-id="dba1d-171">`>` and `<`</span></span>  
  
-   <span data-ttu-id="dba1d-172">`>=` 和 `<=`</span><span class="sxs-lookup"><span data-stu-id="dba1d-172">`>=` and `<=`</span></span>  
  
-   <span data-ttu-id="dba1d-173">`IsTrue` 和 `IsFalse`</span><span class="sxs-lookup"><span data-stu-id="dba1d-173">`IsTrue` and `IsFalse`</span></span>  
  
## <a name="data-type-restrictions"></a><span data-ttu-id="dba1d-174">数据类型限制</span><span class="sxs-lookup"><span data-stu-id="dba1d-174">Data Type Restrictions</span></span>  
 <span data-ttu-id="dba1d-175">你定义每个运算符必须包含在其上定义的类或结构。</span><span class="sxs-lookup"><span data-stu-id="dba1d-175">Every operator you define must involve the class or structure on which you define it.</span></span> <span data-ttu-id="dba1d-176">这意味着类或结构必须显示为以下数据类型：</span><span class="sxs-lookup"><span data-stu-id="dba1d-176">This means that the class or structure must appear as the data type of the following:</span></span>  
  
-   <span data-ttu-id="dba1d-177">一元运算符的操作数。</span><span class="sxs-lookup"><span data-stu-id="dba1d-177">The operand of a unary operator.</span></span>  
  
-   <span data-ttu-id="dba1d-178">至少一个二元运算符的操作数。</span><span class="sxs-lookup"><span data-stu-id="dba1d-178">At least one of the operands of a binary operator.</span></span>  
  
-   <span data-ttu-id="dba1d-179">操作数或转换运算符的返回类型。</span><span class="sxs-lookup"><span data-stu-id="dba1d-179">Either the operand or the return type of a conversion operator.</span></span>  
  
 <span data-ttu-id="dba1d-180">某些运算符具有额外的数据类型限制，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dba1d-180">Certain operators have additional data type restrictions, as follows:</span></span>  
  
-   <span data-ttu-id="dba1d-181">如果你定义`IsTrue`和`IsFalse`运算符，它们必须都返回`Boolean`类型。</span><span class="sxs-lookup"><span data-stu-id="dba1d-181">If you define the `IsTrue` and `IsFalse` operators, they must both return the `Boolean` type.</span></span>  
  
-   <span data-ttu-id="dba1d-182">如果你定义`<<`和`>>`运算符，它们必须同时指定`Integer`键入`operandtype`的`operand2`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-182">If you define the `<<` and `>>` operators, they must both specify the `Integer` type for the `operandtype` of `operand2`.</span></span>  
  
 <span data-ttu-id="dba1d-183">返回类型没有对应于其中一个操作数的类型。</span><span class="sxs-lookup"><span data-stu-id="dba1d-183">The return type does not have to correspond to the type of either operand.</span></span> <span data-ttu-id="dba1d-184">例如，如一个比较运算符`=`或`<>`可以返回`Boolean`即使两个操作数是`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-184">For example, a comparison operator such as `=` or `<>` can return `Boolean` even if neither operand is `Boolean`.</span></span>  
  
## <a name="logical-and-bitwise-operators"></a><span data-ttu-id="dba1d-185">逻辑和按位运算符</span><span class="sxs-lookup"><span data-stu-id="dba1d-185">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="dba1d-186">`And`， `Or`， `Not`，和`Xor`运算符可以在 Visual Basic 中执行逻辑或位运算。</span><span class="sxs-lookup"><span data-stu-id="dba1d-186">The `And`, `Or`, `Not`, and `Xor` operators can perform either logical or bitwise operations in Visual Basic.</span></span> <span data-ttu-id="dba1d-187">但是，如果你在类或结构上定义这些运算符之一，你可以定义仅其按位运算。</span><span class="sxs-lookup"><span data-stu-id="dba1d-187">However, if you define one of these operators on a class or structure, you can define only its bitwise operation.</span></span>  
  
 <span data-ttu-id="dba1d-188">不能定义`AndAlso`直接与运算符`Operator`语句。</span><span class="sxs-lookup"><span data-stu-id="dba1d-188">You cannot define the `AndAlso` operator directly with an `Operator` statement.</span></span> <span data-ttu-id="dba1d-189">但是，你可以使用`AndAlso`如果你已满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="dba1d-189">However, you can use `AndAlso` if you have fulfilled the following conditions:</span></span>  
  
-   <span data-ttu-id="dba1d-190">已定义`And`在你想要用于对同一操作数类型`AndAlso`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-190">You have defined `And` on the same operand types you want to use for `AndAlso`.</span></span>  
  
-   <span data-ttu-id="dba1d-191">你定义`And`返回与在其上定义它的类或结构相同的类型。</span><span class="sxs-lookup"><span data-stu-id="dba1d-191">Your definition of `And` returns the same type as the class or structure on which you have defined it.</span></span>  
  
-   <span data-ttu-id="dba1d-192">已定义`IsFalse`运算符在其上具有定义的类或结构`And`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-192">You have defined the `IsFalse` operator on the class or structure on which you have defined `And`.</span></span>  
  
 <span data-ttu-id="dba1d-193">同样，你可以使用`OrElse`如果已定义`Or`对相同的操作数与返回类型的类或结构，并且你已定义`IsTrue`在类或结构上。</span><span class="sxs-lookup"><span data-stu-id="dba1d-193">Similarly, you can use `OrElse` if you have defined `Or` on the same operands, with the return type of the class or structure, and you have defined `IsTrue` on the class or structure.</span></span>  
  
## <a name="widening-and-narrowing-conversions"></a><span data-ttu-id="dba1d-194">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="dba1d-194">Widening and Narrowing Conversions</span></span>  
 <span data-ttu-id="dba1d-195">A*扩大转换*在运行时，始终成功时*收缩转换*可以在运行时失败。</span><span class="sxs-lookup"><span data-stu-id="dba1d-195">A *widening conversion* always succeeds at run time, while a *narrowing conversion* can fail at run time.</span></span> <span data-ttu-id="dba1d-196">有关详细信息，请参阅 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="dba1d-196">For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
 <span data-ttu-id="dba1d-197">如果声明转换过程要`Widening`，过程代码一定不会产生任何故障。</span><span class="sxs-lookup"><span data-stu-id="dba1d-197">If you declare a conversion procedure to be `Widening`, your procedure code must not generate any failures.</span></span> <span data-ttu-id="dba1d-198">这意味着：</span><span class="sxs-lookup"><span data-stu-id="dba1d-198">This means the following:</span></span>  
  
-   <span data-ttu-id="dba1d-199">它必须始终返回类型的有效值`type`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-199">It must always return a valid value of type `type`.</span></span>  
  
-   <span data-ttu-id="dba1d-200">它必须处理所有可能的异常和其他错误条件。</span><span class="sxs-lookup"><span data-stu-id="dba1d-200">It must handle all possible exceptions and other error conditions.</span></span>  
  
-   <span data-ttu-id="dba1d-201">它必须处理从它调用任何过程返回的任何错误。</span><span class="sxs-lookup"><span data-stu-id="dba1d-201">It must handle any error returns from any procedures it calls.</span></span>  
  
 <span data-ttu-id="dba1d-202">如果没有任何可能转换过程可能不成功，或者它可能会导致未经处理的异常，必须将其声明`Narrowing`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-202">If there is any possibility that a conversion procedure might not succeed, or that it might cause an unhandled exception, you must declare it to be `Narrowing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dba1d-203">示例</span><span class="sxs-lookup"><span data-stu-id="dba1d-203">Example</span></span>  
 <span data-ttu-id="dba1d-204">下面的代码示例使用`Operator`语句以定义一个结构，其中包括运算符的过程的轮廓`And`， `Or`， `IsFalse`，和`IsTrue`运算符。</span><span class="sxs-lookup"><span data-stu-id="dba1d-204">The following code example uses the `Operator` statement to define the outline of a structure that includes operator procedures for the `And`, `Or`, `IsFalse`, and `IsTrue` operators.</span></span> <span data-ttu-id="dba1d-205">`And`和`Or`每个都采用类型的两个操作数`abc`和返回类型`abc`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-205">`And` and `Or` each take two operands of type `abc` and return type `abc`.</span></span> <span data-ttu-id="dba1d-206">`IsFalse`和`IsTrue`个各自采用单个类型的操作数的`abc`并返回`Boolean`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-206">`IsFalse` and `IsTrue` each take a single operand of type `abc` and return `Boolean`.</span></span> <span data-ttu-id="dba1d-207">这些定义使调用代码以使用`And`， `AndAlso`， `Or`，和`OrElse`类型操作数`abc`。</span><span class="sxs-lookup"><span data-stu-id="dba1d-207">These definitions allow the calling code to use `And`, `AndAlso`, `Or`, and `OrElse` with operands of type `abc`.</span></span>  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="dba1d-208">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dba1d-208">See Also</span></span>  
 [<span data-ttu-id="dba1d-209">IsFalse 运算符</span><span class="sxs-lookup"><span data-stu-id="dba1d-209">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="dba1d-210">IsTrue 运算符</span><span class="sxs-lookup"><span data-stu-id="dba1d-210">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="dba1d-211">Widening</span><span class="sxs-lookup"><span data-stu-id="dba1d-211">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="dba1d-212">Narrowing</span><span class="sxs-lookup"><span data-stu-id="dba1d-212">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="dba1d-213">扩大转换和收缩转换</span><span class="sxs-lookup"><span data-stu-id="dba1d-213">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="dba1d-214">运算符过程</span><span class="sxs-lookup"><span data-stu-id="dba1d-214">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="dba1d-215">如何：定义运算符</span><span class="sxs-lookup"><span data-stu-id="dba1d-215">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="dba1d-216">如何：定义转换运算符</span><span class="sxs-lookup"><span data-stu-id="dba1d-216">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="dba1d-217">如何：调用运算符过程</span><span class="sxs-lookup"><span data-stu-id="dba1d-217">How to: Call an Operator Procedure</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="dba1d-218">如何：使用定义运算符的类</span><span class="sxs-lookup"><span data-stu-id="dba1d-218">How to: Use a Class that Defines Operators</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)

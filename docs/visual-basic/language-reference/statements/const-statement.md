---
title: Const 语句 (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Const
helpviewer_keywords:
- Const statement [Visual Basic]
ms.assetid: 495b318d-b7c5-4198-94f8-0790a541b07a
ms.openlocfilehash: 089c2dca99373f379e1eff319cf8c41242e5f135
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835305"
---
# <a name="const-statement-visual-basic"></a><span data-ttu-id="b899a-102">Const 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b899a-102">Const Statement (Visual Basic)</span></span>
<span data-ttu-id="b899a-103">声明和定义一个或多个常量。</span><span class="sxs-lookup"><span data-stu-id="b899a-103">Declares and defines one or more constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b899a-104">语法</span><span class="sxs-lookup"><span data-stu-id="b899a-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ]   
Const constantlist  
```  
  
## <a name="parts"></a><span data-ttu-id="b899a-105">部件</span><span class="sxs-lookup"><span data-stu-id="b899a-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="b899a-106">可选。</span><span class="sxs-lookup"><span data-stu-id="b899a-106">Optional.</span></span> <span data-ttu-id="b899a-107">此语句中声明的属性适用于所有常量的列表。</span><span class="sxs-lookup"><span data-stu-id="b899a-107">List of attributes that apply to all the constants declared in this statement.</span></span> <span data-ttu-id="b899a-108">请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)括进尖括号 ("`<`"和"`>`")。</span><span class="sxs-lookup"><span data-stu-id="b899a-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="b899a-109">可选。</span><span class="sxs-lookup"><span data-stu-id="b899a-109">Optional.</span></span> <span data-ttu-id="b899a-110">用于指定哪些代码可以访问这些常量。</span><span class="sxs-lookup"><span data-stu-id="b899a-110">Use this to specify what code can access these constants.</span></span> <span data-ttu-id="b899a-111">可以是[公共](../../../visual-basic/language-reference/modifiers/public.md)，[受保护](../../../visual-basic/language-reference/modifiers/protected.md)，[友元](../../../visual-basic/language-reference/modifiers/friend.md)， [Protected Friend](../modifiers/protected-friend.md)，[专用](../../../visual-basic/language-reference/modifiers/private.md)，或[专用受保护](../../language-reference/modifiers/private-protected.md)。</span><span class="sxs-lookup"><span data-stu-id="b899a-111">Can be [Public](../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../visual-basic/language-reference/modifiers/friend.md), [Protected Friend](../modifiers/protected-friend.md), [Private](../../../visual-basic/language-reference/modifiers/private.md), or [Private Protected](../../language-reference/modifiers/private-protected.md).</span></span>
  
 `Shadows`  
 <span data-ttu-id="b899a-112">可选。</span><span class="sxs-lookup"><span data-stu-id="b899a-112">Optional.</span></span> <span data-ttu-id="b899a-113">使用此方法将重新声明并隐藏基类中的编程元素。</span><span class="sxs-lookup"><span data-stu-id="b899a-113">Use this to redeclare and hide a programming element in a base class.</span></span> <span data-ttu-id="b899a-114">请参阅[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)。</span><span class="sxs-lookup"><span data-stu-id="b899a-114">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
 `constantlist`  
 <span data-ttu-id="b899a-115">必需。</span><span class="sxs-lookup"><span data-stu-id="b899a-115">Required.</span></span> <span data-ttu-id="b899a-116">此语句中声明的常量的列表。</span><span class="sxs-lookup"><span data-stu-id="b899a-116">List of constants being declared in this statement.</span></span>  
  
 <span data-ttu-id="b899a-117">`constant` `[ ,` `constant` `... ]`</span><span class="sxs-lookup"><span data-stu-id="b899a-117">`constant` `[ ,` `constant` `... ]`</span></span>  
  
 <span data-ttu-id="b899a-118">每个 `constant` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="b899a-118">Each `constant` has the following syntax and parts:</span></span>  
  
 <span data-ttu-id="b899a-119">`constantname` `[ As` `datatype` `] =` `initializer`</span><span class="sxs-lookup"><span data-stu-id="b899a-119">`constantname` `[ As` `datatype` `] =` `initializer`</span></span>  
  
|<span data-ttu-id="b899a-120">部件</span><span class="sxs-lookup"><span data-stu-id="b899a-120">Part</span></span>|<span data-ttu-id="b899a-121">描述</span><span class="sxs-lookup"><span data-stu-id="b899a-121">Description</span></span>|  
|----------|-----------------|  
|`constantname`|<span data-ttu-id="b899a-122">必需。</span><span class="sxs-lookup"><span data-stu-id="b899a-122">Required.</span></span> <span data-ttu-id="b899a-123">常数的名称。</span><span class="sxs-lookup"><span data-stu-id="b899a-123">Name of the constant.</span></span> <span data-ttu-id="b899a-124">请参阅 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="b899a-124">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`datatype`|<span data-ttu-id="b899a-125">需要`Option Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="b899a-125">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="b899a-126">常量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b899a-126">Data type of the constant.</span></span>|  
|`initializer`|<span data-ttu-id="b899a-127">必需。</span><span class="sxs-lookup"><span data-stu-id="b899a-127">Required.</span></span> <span data-ttu-id="b899a-128">在编译时计算和分配给常量的表达式。</span><span class="sxs-lookup"><span data-stu-id="b899a-128">Expression that is evaluated at compile time and assigned to the constant.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b899a-129">备注</span><span class="sxs-lookup"><span data-stu-id="b899a-129">Remarks</span></span>  
 <span data-ttu-id="b899a-130">如果在应用程序中有一个值，永远不会更改，可以定义一个命名的常量和用它代替文字值。</span><span class="sxs-lookup"><span data-stu-id="b899a-130">If you have a value that never changes in your application, you can define a named constant and use it in place of a literal value.</span></span> <span data-ttu-id="b899a-131">系统会更容易记忆于值名称。</span><span class="sxs-lookup"><span data-stu-id="b899a-131">A name is easier to remember than a value.</span></span> <span data-ttu-id="b899a-132">您可以只需一次定义常量和在代码中在多个位置使用它。</span><span class="sxs-lookup"><span data-stu-id="b899a-132">You can define the constant just once and use it in many places in your code.</span></span> <span data-ttu-id="b899a-133">如果需要更高版本中重新定义的值，`Const`语句是您需要进行更改的唯一位置。</span><span class="sxs-lookup"><span data-stu-id="b899a-133">If in a later version you need to redefine the value, the `Const` statement is the only place you need to make a change.</span></span>  
  
 <span data-ttu-id="b899a-134">可以使用`Const`仅在模块或过程的级别。</span><span class="sxs-lookup"><span data-stu-id="b899a-134">You can use `Const` only at module or procedure level.</span></span> <span data-ttu-id="b899a-135">这意味着*声明上下文*变量必须是类、 结构、 模块、 过程或块，并且不能是源文件、 命名空间或接口。</span><span class="sxs-lookup"><span data-stu-id="b899a-135">This means the *declaration context* for a variable must be a class, structure, module, procedure, or block, and cannot be a source file, namespace, or interface.</span></span> <span data-ttu-id="b899a-136">有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="b899a-136">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="b899a-137">局部常量 （在对过程） 默认为公共访问权限，并且您不能对其使用任何访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="b899a-137">Local constants (inside a procedure) default to public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="b899a-138">类和模块成员 （任何过程之外） 的常量默认为私有访问和结构成员常量默认为公共访问权限。</span><span class="sxs-lookup"><span data-stu-id="b899a-138">Class and module member constants (outside any procedure) default to private access, and structure member constants default to public access.</span></span> <span data-ttu-id="b899a-139">您可以调整其访问级别和访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="b899a-139">You can adjust their access levels with the access modifiers.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b899a-140">规则</span><span class="sxs-lookup"><span data-stu-id="b899a-140">Rules</span></span>  
  
-   <span data-ttu-id="b899a-141">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="b899a-141">**Declaration Context.**</span></span> <span data-ttu-id="b899a-142">常量是在模块级别，在任何过程中，外部声明*成员常量*; 它是类、 结构的成员或声明其模块。</span><span class="sxs-lookup"><span data-stu-id="b899a-142">A constant declared at module level, outside any procedure, is a *member constant*; it is a member of the class, structure, or module that declares it.</span></span>  
  
     <span data-ttu-id="b899a-143">在过程级别声明的常量是*的局部常量*; 它是本地的过程或声明它的块。</span><span class="sxs-lookup"><span data-stu-id="b899a-143">A constant declared at procedure level is a *local constant*; it is local to the procedure or block that declares it.</span></span>  
  
-   <span data-ttu-id="b899a-144">**特性。**</span><span class="sxs-lookup"><span data-stu-id="b899a-144">**Attributes.**</span></span> <span data-ttu-id="b899a-145">可以将特性应用于成员常数上，而不是局部常量。</span><span class="sxs-lookup"><span data-stu-id="b899a-145">You can apply attributes only to member constants, not to local constants.</span></span> <span data-ttu-id="b899a-146">特性提供信息对程序集的元数据，这并无意义的局部常量如临时存储。</span><span class="sxs-lookup"><span data-stu-id="b899a-146">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local constants.</span></span>  
  
-   <span data-ttu-id="b899a-147">**修饰符。**</span><span class="sxs-lookup"><span data-stu-id="b899a-147">**Modifiers.**</span></span> <span data-ttu-id="b899a-148">默认情况下，所有常量都均`Shared`， `Static`，和`ReadOnly`。</span><span class="sxs-lookup"><span data-stu-id="b899a-148">By default, all constants are `Shared`, `Static`, and `ReadOnly`.</span></span> <span data-ttu-id="b899a-149">声明常量时，不能使用任何这些关键字。</span><span class="sxs-lookup"><span data-stu-id="b899a-149">You cannot use any of these keywords when declaring a constant.</span></span>  
  
     <span data-ttu-id="b899a-150">在过程级别不能使用`Shadows`或任何访问修饰符来声明局部常量。</span><span class="sxs-lookup"><span data-stu-id="b899a-150">At procedure level, you cannot use `Shadows` or any access modifiers to declare local constants.</span></span>  
  
-   <span data-ttu-id="b899a-151">**多个常量。**</span><span class="sxs-lookup"><span data-stu-id="b899a-151">**Multiple Constants.**</span></span> <span data-ttu-id="b899a-152">您可以声明多个常量在相同的声明语句中，指定`constantname`为每个部分。</span><span class="sxs-lookup"><span data-stu-id="b899a-152">You can declare several constants in the same declaration statement, specifying the `constantname` part for each one.</span></span> <span data-ttu-id="b899a-153">由逗号分隔多个常量。</span><span class="sxs-lookup"><span data-stu-id="b899a-153">Multiple constants are separated by commas.</span></span>  
  
## <a name="data-type-rules"></a><span data-ttu-id="b899a-154">数据类型的规则</span><span class="sxs-lookup"><span data-stu-id="b899a-154">Data Type Rules</span></span>  
  
-   <span data-ttu-id="b899a-155">**数据类型。**</span><span class="sxs-lookup"><span data-stu-id="b899a-155">**Data Types.**</span></span> <span data-ttu-id="b899a-156">`Const`语句可以声明一个变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b899a-156">The `Const` statement can declare the data type of a variable.</span></span> <span data-ttu-id="b899a-157">您可以指定任何数据类型或枚举的名称。</span><span class="sxs-lookup"><span data-stu-id="b899a-157">You can specify any data type or the name of an enumeration.</span></span>  
  
-   <span data-ttu-id="b899a-158">**默认类型。**</span><span class="sxs-lookup"><span data-stu-id="b899a-158">**Default Type.**</span></span> <span data-ttu-id="b899a-159">如果未指定`datatype`，该常量将的数据类型`initializer`。</span><span class="sxs-lookup"><span data-stu-id="b899a-159">If you do not specify `datatype`, the constant takes the data type of `initializer`.</span></span> <span data-ttu-id="b899a-160">如果同时指定`datatype`并`initializer`的数据类型`initializer`必须可转换为`datatype`。</span><span class="sxs-lookup"><span data-stu-id="b899a-160">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="b899a-161">如果既没有`datatype`也不`initializer`存在，则数据类型默认为`Object`。</span><span class="sxs-lookup"><span data-stu-id="b899a-161">If neither `datatype` nor `initializer` is present, the data type defaults to `Object`.</span></span>  
  
-   <span data-ttu-id="b899a-162">**不同类型。**</span><span class="sxs-lookup"><span data-stu-id="b899a-162">**Different Types.**</span></span> <span data-ttu-id="b899a-163">可以通过使用单独指定不同的数据类型为不同的常量`As`子句为每个声明的变量。</span><span class="sxs-lookup"><span data-stu-id="b899a-163">You can specify different data types for different constants by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="b899a-164">但是，不能声明为相同类型的通过使用一种常见的多个常量`As`子句。</span><span class="sxs-lookup"><span data-stu-id="b899a-164">However, you cannot declare several constants to be of the same type by using a common `As` clause.</span></span>  
  
-   <span data-ttu-id="b899a-165">**初始化。**</span><span class="sxs-lookup"><span data-stu-id="b899a-165">**Initialization.**</span></span> <span data-ttu-id="b899a-166">必须初始化中的每个常量的值`constantlist`。</span><span class="sxs-lookup"><span data-stu-id="b899a-166">You must initialize the value of every constant in `constantlist`.</span></span> <span data-ttu-id="b899a-167">您使用`initializer`来提供要分配给常量的表达式。</span><span class="sxs-lookup"><span data-stu-id="b899a-167">You use `initializer` to supply an expression to be assigned to the constant.</span></span> <span data-ttu-id="b899a-168">表达式可以是文本、 其他已定义的常量和枚举成员的已定义的任意组合。</span><span class="sxs-lookup"><span data-stu-id="b899a-168">The expression can be any combination of literals, other constants that are already defined, and enumeration members that are already defined.</span></span> <span data-ttu-id="b899a-169">可以使用算术和逻辑运算符来组合这些元素。</span><span class="sxs-lookup"><span data-stu-id="b899a-169">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
     <span data-ttu-id="b899a-170">不能使用变量或函数中的`initializer`。</span><span class="sxs-lookup"><span data-stu-id="b899a-170">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="b899a-171">但是，可以使用转换关键字如`CByte`和`CShort`。</span><span class="sxs-lookup"><span data-stu-id="b899a-171">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="b899a-172">此外可以使用`AscW`如果调用与常量`String`或`Char`参数，因为可以在编译时计算。</span><span class="sxs-lookup"><span data-stu-id="b899a-172">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="b899a-173">行为</span><span class="sxs-lookup"><span data-stu-id="b899a-173">Behavior</span></span>  
  
-   <span data-ttu-id="b899a-174">**作用域。**</span><span class="sxs-lookup"><span data-stu-id="b899a-174">**Scope.**</span></span> <span data-ttu-id="b899a-175">局部常量仅从内部来访问它们的过程或块。</span><span class="sxs-lookup"><span data-stu-id="b899a-175">Local constants are accessible only from within their procedure or block.</span></span> <span data-ttu-id="b899a-176">成员常量是可从其类、 结构或模块内任意位置访问。</span><span class="sxs-lookup"><span data-stu-id="b899a-176">Member constants are accessible from anywhere within their class, structure, or module.</span></span>  
  
-   <span data-ttu-id="b899a-177">**限定。**</span><span class="sxs-lookup"><span data-stu-id="b899a-177">**Qualification.**</span></span> <span data-ttu-id="b899a-178">代码类之外，结构或模块必须限定成员常量的名称，并且该类、 结构或模块的名称。</span><span class="sxs-lookup"><span data-stu-id="b899a-178">Code outside a class, structure, or module must qualify a member constant's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="b899a-179">过程或块不能引用在该过程或块中任何局部常量之外的代码。</span><span class="sxs-lookup"><span data-stu-id="b899a-179">Code outside a procedure or block cannot refer to any local constants within that procedure or block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b899a-180">示例</span><span class="sxs-lookup"><span data-stu-id="b899a-180">Example</span></span>  
 <span data-ttu-id="b899a-181">下面的示例使用`Const`语句声明用于代替文字值的常量。</span><span class="sxs-lookup"><span data-stu-id="b899a-181">The following example uses the `Const` statement to declare constants for use in place of literal values.</span></span>  
  
 [!code-vb[VbVbalrStatements#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#13)]  
  
## <a name="example"></a><span data-ttu-id="b899a-182">示例</span><span class="sxs-lookup"><span data-stu-id="b899a-182">Example</span></span>  
 <span data-ttu-id="b899a-183">如果数据类型定义一个常量`Object`，Visual Basic 编译器为其提供的类型`initializer`，而不是`Object`。</span><span class="sxs-lookup"><span data-stu-id="b899a-183">If you define a constant with data type `Object`, the Visual Basic compiler gives it the type of `initializer`, instead of `Object`.</span></span> <span data-ttu-id="b899a-184">在下面的示例中，常量`naturalLogBase`具有运行时类型`Decimal`。</span><span class="sxs-lookup"><span data-stu-id="b899a-184">In the following example, the constant `naturalLogBase` has the run-time type `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrStatements#87](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#87)]  
  
 <span data-ttu-id="b899a-185">前面的示例使用<xref:System.Type.ToString%2A>方法<xref:System.Type>返回的对象[GetType 运算符](../../../visual-basic/language-reference/operators/gettype-operator.md)，这是因为<xref:System.Type>无法转换为`String`使用`CStr`。</span><span class="sxs-lookup"><span data-stu-id="b899a-185">The preceding example uses the <xref:System.Type.ToString%2A> method on the <xref:System.Type> object returned by the [GetType Operator](../../../visual-basic/language-reference/operators/gettype-operator.md), because <xref:System.Type> cannot be converted to `String` using `CStr`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b899a-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="b899a-186">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [<span data-ttu-id="b899a-187">Enum 语句</span><span class="sxs-lookup"><span data-stu-id="b899a-187">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="b899a-188">#Const 指令</span><span class="sxs-lookup"><span data-stu-id="b899a-188">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="b899a-189">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="b899a-189">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="b899a-190">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="b899a-190">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="b899a-191">隐式转换和显式转换</span><span class="sxs-lookup"><span data-stu-id="b899a-191">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="b899a-192">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="b899a-192">Constants and Enumerations</span></span>](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)
- [<span data-ttu-id="b899a-193">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="b899a-193">Constants and Enumerations</span></span>](../../../visual-basic/language-reference/constants-and-enumerations.md)
- [<span data-ttu-id="b899a-194">类型转换函数</span><span class="sxs-lookup"><span data-stu-id="b899a-194">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)

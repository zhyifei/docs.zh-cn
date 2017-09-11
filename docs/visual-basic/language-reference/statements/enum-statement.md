---
title: "Enum 语句 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Enum
dev_langs:
- VB
helpviewer_keywords:
- enumerated constants
- Enum statement
- Private keyword, Enum statements
- Public keyword, in Enum statement
- variables [Visual Basic], enumeration
- constants, enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
caps.latest.revision: 44
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ff075349756bd4c568833d049b50b3c3721d1b08
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="enum-statement-visual-basic"></a><span data-ttu-id="e553b-102">Enum 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e553b-102">Enum Statement (Visual Basic)</span></span>
<span data-ttu-id="e553b-103">声明枚举并定义其成员的值。</span><span class="sxs-lookup"><span data-stu-id="e553b-103">Declares an enumeration and defines the values of its members.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e553b-104">语法</span><span class="sxs-lookup"><span data-stu-id="e553b-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]   
Enum enumerationname [ As datatype ]   
   memberlist  
End Enum  
```  
  
## <a name="parts"></a><span data-ttu-id="e553b-105">部件</span><span class="sxs-lookup"><span data-stu-id="e553b-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="e553b-106">可选。</span><span class="sxs-lookup"><span data-stu-id="e553b-106">Optional.</span></span> <span data-ttu-id="e553b-107">应用于此枚举的属性列表。</span><span class="sxs-lookup"><span data-stu-id="e553b-107">List of attributes that apply to this enumeration.</span></span> <span data-ttu-id="e553b-108">必须将括[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)在尖括号 ("`<`"和"`>`")。</span><span class="sxs-lookup"><span data-stu-id="e553b-108">You must enclose the [attribute list](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>  
  
     <span data-ttu-id="e553b-109"><xref:System.FlagsAttribute>属性指示的值的枚举的实例可以包含多个枚举成员，并且每个成员表示中的枚举值的位域。</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="e553b-109">The <xref:System.FlagsAttribute> attribute indicates that the value of an instance of the enumeration can include multiple enumeration members, and that each member represents a bit field in the enumeration value.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="e553b-110">可选。</span><span class="sxs-lookup"><span data-stu-id="e553b-110">Optional.</span></span> <span data-ttu-id="e553b-111">指定哪些代码可以访问此枚举。</span><span class="sxs-lookup"><span data-stu-id="e553b-111">Specifies what code can access this enumeration.</span></span> <span data-ttu-id="e553b-112">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="e553b-112">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="e553b-113">Public</span><span class="sxs-lookup"><span data-stu-id="e553b-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="e553b-114">Protected</span><span class="sxs-lookup"><span data-stu-id="e553b-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="e553b-115">Friend</span><span class="sxs-lookup"><span data-stu-id="e553b-115">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="e553b-116">Private</span><span class="sxs-lookup"><span data-stu-id="e553b-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
     <span data-ttu-id="e553b-117">您可以指定`Protected``Friend`以允许从枚举的类，派生的类中或同一程序集中的代码中进行访问。</span><span class="sxs-lookup"><span data-stu-id="e553b-117">You can specify `Protected``Friend` to allow access from code within the enumeration's class, a derived class, or the same assembly.</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="e553b-118">可选。</span><span class="sxs-lookup"><span data-stu-id="e553b-118">Optional.</span></span> <span data-ttu-id="e553b-119">指定此枚举重新声明，并隐藏一个同名的编程元素或一组重载元素，在基类中。</span><span class="sxs-lookup"><span data-stu-id="e553b-119">Specifies that this enumeration redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="e553b-120">您可以指定[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)仅限于在枚举本身，不在它的任何成员。</span><span class="sxs-lookup"><span data-stu-id="e553b-120">You can specify [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) only on the enumeration itself, not on any of its members.</span></span>  
  
-   `enumerationname`  
  
     <span data-ttu-id="e553b-121">必需。</span><span class="sxs-lookup"><span data-stu-id="e553b-121">Required.</span></span> <span data-ttu-id="e553b-122">枚举的名称。</span><span class="sxs-lookup"><span data-stu-id="e553b-122">Name of the enumeration.</span></span> <span data-ttu-id="e553b-123">有关有效的名称的信息，请参阅[声明元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="e553b-123">For information on valid names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `datatype`  
  
     <span data-ttu-id="e553b-124">可选。</span><span class="sxs-lookup"><span data-stu-id="e553b-124">Optional.</span></span> <span data-ttu-id="e553b-125">枚举及其所有成员的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e553b-125">Data type of the enumeration and all its members.</span></span>  
  
-   `memberlist`  
  
     <span data-ttu-id="e553b-126">必需。</span><span class="sxs-lookup"><span data-stu-id="e553b-126">Required.</span></span> <span data-ttu-id="e553b-127">此语句中声明的成员常量的列表。</span><span class="sxs-lookup"><span data-stu-id="e553b-127">List of member constants being declared in this statement.</span></span> <span data-ttu-id="e553b-128">在单个源代码行上显示多个成员。</span><span class="sxs-lookup"><span data-stu-id="e553b-128">Multiple members appear on individual source code lines.</span></span>  
  
     <span data-ttu-id="e553b-129">每个`member`具有以下语法和部分︰`[<attribute list>] member name [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="e553b-129">Each `member` has the following syntax and parts: `[<attribute list>] member name [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="e553b-130">部件</span><span class="sxs-lookup"><span data-stu-id="e553b-130">Part</span></span>|<span data-ttu-id="e553b-131">描述</span><span class="sxs-lookup"><span data-stu-id="e553b-131">Description</span></span>|  
    |---|---|  
    |`membername`|<span data-ttu-id="e553b-132">必需。</span><span class="sxs-lookup"><span data-stu-id="e553b-132">Required.</span></span> <span data-ttu-id="e553b-133">此成员的名称。</span><span class="sxs-lookup"><span data-stu-id="e553b-133">Name of this member.</span></span>|  
    |`initializer`|<span data-ttu-id="e553b-134">可选。</span><span class="sxs-lookup"><span data-stu-id="e553b-134">Optional.</span></span> <span data-ttu-id="e553b-135">在编译时计算并将其分配给此成员的表达式。</span><span class="sxs-lookup"><span data-stu-id="e553b-135">Expression that is evaluated at compile time and assigned to this member.</span></span>|  
  
-   <span data-ttu-id="e553b-136">`End` `Enum`</span><span class="sxs-lookup"><span data-stu-id="e553b-136">`End` `Enum`</span></span>  
  
     <span data-ttu-id="e553b-137">终止 `Enum` 块。</span><span class="sxs-lookup"><span data-stu-id="e553b-137">Terminates the `Enum` block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e553b-138">备注</span><span class="sxs-lookup"><span data-stu-id="e553b-138">Remarks</span></span>  
 <span data-ttu-id="e553b-139">如果您有一组在逻辑上彼此相关的不变值，您可以在枚举中一起定义它们。</span><span class="sxs-lookup"><span data-stu-id="e553b-139">If you have a set of unchanging values that are logically related to each other, you can define them together in an enumeration.</span></span> <span data-ttu-id="e553b-140">这提供了为枚举和它们的值比更容易记住其成员有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="e553b-140">This provides meaningful names for the enumeration and its members, which are easier to remember than their values.</span></span> <span data-ttu-id="e553b-141">然后可以在代码中，在多个位置中使用的枚举成员。</span><span class="sxs-lookup"><span data-stu-id="e553b-141">You can then use the enumeration members in many places in your code.</span></span>  
  
 <span data-ttu-id="e553b-142">使用枚举的好处包括︰</span><span class="sxs-lookup"><span data-stu-id="e553b-142">The benefits of using enumerations include the following:</span></span>  
  
-   <span data-ttu-id="e553b-143">这样可以减少错误引起的转置或键入数字。</span><span class="sxs-lookup"><span data-stu-id="e553b-143">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="e553b-144">便于在以后更改值。</span><span class="sxs-lookup"><span data-stu-id="e553b-144">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="e553b-145">使代码易于阅读，这意味着它不太可能会引入错误。</span><span class="sxs-lookup"><span data-stu-id="e553b-145">Makes code easier to read, which means it is less likely that errors will be introduced.</span></span>  
  
-   <span data-ttu-id="e553b-146">确保向前兼容性。</span><span class="sxs-lookup"><span data-stu-id="e553b-146">Ensures forward compatibility.</span></span> <span data-ttu-id="e553b-147">如果您使用枚举，您的代码就很难，如果有人在将来更改的成员名称所对应的值失败。</span><span class="sxs-lookup"><span data-stu-id="e553b-147">If you use enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
 <span data-ttu-id="e553b-148">枚举具有名称、 基础的数据类型和一组的成员。</span><span class="sxs-lookup"><span data-stu-id="e553b-148">An enumeration has a name, an underlying data type, and a set of members.</span></span> <span data-ttu-id="e553b-149">每个成员表示一个常量。</span><span class="sxs-lookup"><span data-stu-id="e553b-149">Each member represents a constant.</span></span>  
  
 <span data-ttu-id="e553b-150">枚举在类、 结构、 模块或接口级别，任何过程之外，声明是*成员枚举*。</span><span class="sxs-lookup"><span data-stu-id="e553b-150">An enumeration declared at class, structure, module, or interface level, outside any procedure, is a *member enumeration*.</span></span> <span data-ttu-id="e553b-151">它是类、 结构、 模块或接口声明它的成员。</span><span class="sxs-lookup"><span data-stu-id="e553b-151">It is a member of the class, structure, module, or interface that declares it.</span></span>  
  
 <span data-ttu-id="e553b-152">成员枚举可以是从任何位置访问其类、 结构、 模块或接口。</span><span class="sxs-lookup"><span data-stu-id="e553b-152">Member enumerations can be accessed from anywhere within their class, structure, module, or interface.</span></span> <span data-ttu-id="e553b-153">代码类之外，结构或模块必须限定成员枚举的名称替换该类、 结构或模块的名称。</span><span class="sxs-lookup"><span data-stu-id="e553b-153">Code outside a class, structure, or module must qualify a member enumeration's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="e553b-154">您可以避免需要通过添加使用完全限定的名[导入](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)到源代码文件的语句。</span><span class="sxs-lookup"><span data-stu-id="e553b-154">You can avoid the need to use fully qualified names by adding an [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statement to the source file.</span></span>  
  
 <span data-ttu-id="e553b-155">枚举声明的命名空间级别之外任何类、 结构、 模块或接口，是它在其中出现的命名空间的成员。</span><span class="sxs-lookup"><span data-stu-id="e553b-155">An enumeration declared at namespace level, outside any class, structure, module, or interface, is a member of the namespace in which it appears.</span></span>  
  
 <span data-ttu-id="e553b-156">*声明上下文*供枚举必须源文件、 命名空间、 类、 结构、 模块或接口，并且不能为一个过程。</span><span class="sxs-lookup"><span data-stu-id="e553b-156">The *declaration context* for an enumeration must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure.</span></span> <span data-ttu-id="e553b-157">有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="e553b-157">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="e553b-158">您可以将特性应用到枚举作为一个整体，但不是属于其成员分别。</span><span class="sxs-lookup"><span data-stu-id="e553b-158">You can apply attributes to an enumeration as a whole, but not to its members individually.</span></span> <span data-ttu-id="e553b-159">属性提供对该程序集的元数据的信息。</span><span class="sxs-lookup"><span data-stu-id="e553b-159">An attribute contributes information to the assembly's metadata.</span></span>  
  
## <a name="data-type"></a><span data-ttu-id="e553b-160">数据类型</span><span class="sxs-lookup"><span data-stu-id="e553b-160">Data Type</span></span>  
 <span data-ttu-id="e553b-161">`Enum`语句可以声明一个枚举的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e553b-161">The `Enum` statement can declare the data type of an enumeration.</span></span> <span data-ttu-id="e553b-162">每个成员采用枚举的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e553b-162">Each member takes the enumeration's data type.</span></span> <span data-ttu-id="e553b-163">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span><span class="sxs-lookup"><span data-stu-id="e553b-163">You can specify `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort`.</span></span>  
  
 <span data-ttu-id="e553b-164">如果未指定`datatype`枚举时，对于每个成员进行的数据类型及其`initializer`。</span><span class="sxs-lookup"><span data-stu-id="e553b-164">If you do not specify `datatype` for the enumeration, each member takes the data type of its `initializer`.</span></span> <span data-ttu-id="e553b-165">如果同时指定了`datatype`和`initializer`的数据类型`initializer`必须可转换为`datatype`。</span><span class="sxs-lookup"><span data-stu-id="e553b-165">If you specify both `datatype` and `initializer`, the data type of `initializer` must be convertible to `datatype`.</span></span> <span data-ttu-id="e553b-166">如果既没有`datatype`，也不`initializer`不存在，则数据类型为默认`Integer`。</span><span class="sxs-lookup"><span data-stu-id="e553b-166">If neither `datatype` nor `initializer` is present, the data type defaults to `Integer`.</span></span>  
  
## <a name="initializing-members"></a><span data-ttu-id="e553b-167">初始化成员</span><span class="sxs-lookup"><span data-stu-id="e553b-167">Initializing Members</span></span>  
 <span data-ttu-id="e553b-168">`Enum`语句可以初始化中的选定成员的内容`memberlist`。</span><span class="sxs-lookup"><span data-stu-id="e553b-168">The `Enum` statement can initialize the contents of selected members in `memberlist`.</span></span> <span data-ttu-id="e553b-169">您使用`initializer`来提供要分配给该成员的表达式。</span><span class="sxs-lookup"><span data-stu-id="e553b-169">You use `initializer` to supply an expression to be assigned to the member.</span></span>  
  
 <span data-ttu-id="e553b-170">如果未指定`initializer`对于成员，Visual Basic 对其进行初始化为零 (如果它是第一个`member`中`memberlist`)，或为大&1; 相比，紧靠前的值`member`。</span><span class="sxs-lookup"><span data-stu-id="e553b-170">If you do not specify `initializer` for a member, Visual Basic initializes it either to zero (if it is the first `member` in `memberlist`), or to a value greater by one than that of the immediately preceding `member`.</span></span>  
  
 <span data-ttu-id="e553b-171">在每个提供的表达式`initializer`可以是文本、 已定义，其他常量和已定义，包括以前此枚举的成员的枚举成员的任意组合。</span><span class="sxs-lookup"><span data-stu-id="e553b-171">The expression supplied in each `initializer` can be any combination of literals, other constants that are already defined, and enumeration members that are already defined, including a previous member of this enumeration.</span></span> <span data-ttu-id="e553b-172">您可以使用算术和逻辑运算符来组合这些元素。</span><span class="sxs-lookup"><span data-stu-id="e553b-172">You can use arithmetic and logical operators to combine such elements.</span></span>  
  
 <span data-ttu-id="e553b-173">不能使用变量或函数中的`initializer`。</span><span class="sxs-lookup"><span data-stu-id="e553b-173">You cannot use variables or functions in `initializer`.</span></span> <span data-ttu-id="e553b-174">但是，可以使用转换关键字如`CByte`和`CShort`。</span><span class="sxs-lookup"><span data-stu-id="e553b-174">However, you can use conversion keywords such as `CByte` and `CShort`.</span></span> <span data-ttu-id="e553b-175">您还可以使用`AscW`如果用一个常量调用`String`或`Char`参数，因为在编译时可计算。</span><span class="sxs-lookup"><span data-stu-id="e553b-175">You can also use `AscW` if you call it with a constant `String` or `Char` argument, since that can be evaluated at compile time.</span></span>  
  
 <span data-ttu-id="e553b-176">枚举不能具有浮点值。</span><span class="sxs-lookup"><span data-stu-id="e553b-176">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="e553b-177">如果一名成员分配一个浮点值和`Option Strict`被设置为 on，会发生编译错误。</span><span class="sxs-lookup"><span data-stu-id="e553b-177">If a member is assigned a floating-point value and `Option Strict` is set to on, a compiler error occurs.</span></span> <span data-ttu-id="e553b-178">如果`Option Strict`处于关闭状态，则这会自动转换为`Enum`类型。</span><span class="sxs-lookup"><span data-stu-id="e553b-178">If `Option Strict` is off, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="e553b-179">如果某个成员的值超出了允许的范围为基础的数据类型，或如果初始化到基础数据类型允许的最大值的任何成员，则编译器会报告错误。</span><span class="sxs-lookup"><span data-stu-id="e553b-179">If the value of a member exceeds the allowable range for the underlying data type, or if you initialize any member to the maximum value allowed by the underlying data type, the compiler reports an error.</span></span>  
  
## <a name="modifiers"></a><span data-ttu-id="e553b-180">修饰符</span><span class="sxs-lookup"><span data-stu-id="e553b-180">Modifiers</span></span>  
 <span data-ttu-id="e553b-181">类、 结构、 模块和接口成员的枚举默认值为公共访问。</span><span class="sxs-lookup"><span data-stu-id="e553b-181">Class, structure, module, and interface member enumerations default to public access.</span></span> <span data-ttu-id="e553b-182">您可以调整它们的访问级别使用的访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="e553b-182">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="e553b-183">Namespace 成员枚举默认为友元访问权限。</span><span class="sxs-lookup"><span data-stu-id="e553b-183">Namespace member enumerations default to friend access.</span></span> <span data-ttu-id="e553b-184">您可以调整它们公共的但无法访问私有或受保护的访问级别。</span><span class="sxs-lookup"><span data-stu-id="e553b-184">You can adjust their access levels to public, but not to private or protected.</span></span> <span data-ttu-id="e553b-185">有关详细信息，请参阅[Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="e553b-185">For more information, see [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="e553b-186">所有枚举成员都具有公共访问权限，并且不能对其使用任何访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="e553b-186">All enumeration members have public access, and you cannot use any access modifiers on them.</span></span> <span data-ttu-id="e553b-187">但是，如果枚举本身具有更受限制的访问级别，指定的枚举访问级别优先。</span><span class="sxs-lookup"><span data-stu-id="e553b-187">However, if the enumeration itself has a more restricted access level, the specified enumeration access level takes precedence.</span></span>  
  
 <span data-ttu-id="e553b-188">默认情况下，所有枚举都是类型，其字段都是常量。</span><span class="sxs-lookup"><span data-stu-id="e553b-188">By default, all enumerations are types and their fields are constants.</span></span> <span data-ttu-id="e553b-189">因此`Shared`， `Static`，和`ReadOnly`声明枚举或它的成员时，不能使用关键字。</span><span class="sxs-lookup"><span data-stu-id="e553b-189">Therefore the `Shared`, `Static`, and `ReadOnly` keywords cannot be used when declaring an enumeration or its members.</span></span>  
  
## <a name="assigning-multiple-values"></a><span data-ttu-id="e553b-190">分配多个值</span><span class="sxs-lookup"><span data-stu-id="e553b-190">Assigning Multiple Values</span></span>  
 <span data-ttu-id="e553b-191">枚举通常表示互斥的值。</span><span class="sxs-lookup"><span data-stu-id="e553b-191">Enumerations typically represent mutually exclusive values.</span></span> <span data-ttu-id="e553b-192">通过包括<xref:System.FlagsAttribute>属性中`Enum`声明中，您可以改为分配多个值的枚举的实例。</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="e553b-192">By including the <xref:System.FlagsAttribute> attribute in the `Enum` declaration, you can instead assign multiple values to an instance of the enumeration.</span></span> <span data-ttu-id="e553b-193"><xref:System.FlagsAttribute>属性指定枚举视为位字段，即一组标志。</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="e553b-193">The <xref:System.FlagsAttribute> attribute specifies that the enumeration be treated as a bit field, that is, a set of flags.</span></span> <span data-ttu-id="e553b-194">这些应用程序称为*位*枚举。</span><span class="sxs-lookup"><span data-stu-id="e553b-194">These are called *bitwise* enumerations.</span></span>  
  
 <span data-ttu-id="e553b-195">当使用声明枚举<xref:System.FlagsAttribute>属性中，我们建议您使用的 2，这是、 1、 2、 4、 8、 16 和等等，幂的值。</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="e553b-195">When you declare an enumeration by using the <xref:System.FlagsAttribute> attribute, we recommend that you use powers of 2, that is, 1, 2, 4, 8, 16, and so on, for the values.</span></span> <span data-ttu-id="e553b-196">我们还建议"None"是其值为 0 的成员的名称。</span><span class="sxs-lookup"><span data-stu-id="e553b-196">We also recommend that "None" be the name of a member whose value is 0.</span></span> <span data-ttu-id="e553b-197">有关其他指南，请参阅<xref:System.FlagsAttribute>和<xref:System.Enum>。</xref:System.Enum> </xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="e553b-197">For additional guidelines, see <xref:System.FlagsAttribute> and <xref:System.Enum>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e553b-198">示例</span><span class="sxs-lookup"><span data-stu-id="e553b-198">Example</span></span>  
 <span data-ttu-id="e553b-199">下面的示例演示如何使用`Enum`语句。</span><span class="sxs-lookup"><span data-stu-id="e553b-199">The following example shows how to use the `Enum` statement.</span></span> <span data-ttu-id="e553b-200">请注意，该成员被称为`EggSizeEnum.Medium`，而不是作为`Medium`。</span><span class="sxs-lookup"><span data-stu-id="e553b-200">Note that the member is referred to as `EggSizeEnum.Medium`, and not as `Medium`.</span></span>  
  
 <span data-ttu-id="e553b-201">[!code-vb[VbEnumsTask #&41;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e553b-201">[!code-vb[VbEnumsTask#41](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e553b-202">示例</span><span class="sxs-lookup"><span data-stu-id="e553b-202">Example</span></span>  
 <span data-ttu-id="e553b-203">下面的示例中的方法之外，则`Egg`类。</span><span class="sxs-lookup"><span data-stu-id="e553b-203">The method in the following example is outside the `Egg` class.</span></span> <span data-ttu-id="e553b-204">因此，`EggSizeEnum`是作为完全限定的`Egg.EggSizeEnum`。</span><span class="sxs-lookup"><span data-stu-id="e553b-204">Therefore, `EggSizeEnum` is fully qualified as `Egg.EggSizeEnum`.</span></span>  
  
 <span data-ttu-id="e553b-205">[!code-vb[VbEnumsTask #&42;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e553b-205">[!code-vb[VbEnumsTask#42](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e553b-206">示例</span><span class="sxs-lookup"><span data-stu-id="e553b-206">Example</span></span>  
 <span data-ttu-id="e553b-207">下面的示例使用`Enum`语句来定义一组相关的命名的常量值。</span><span class="sxs-lookup"><span data-stu-id="e553b-207">The following example uses the `Enum` statement to define a related set of named constant values.</span></span> <span data-ttu-id="e553b-208">在这种情况下，值是您可能选择用来设计数据库的数据输入窗体颜色。</span><span class="sxs-lookup"><span data-stu-id="e553b-208">In this case, the values are colors you might choose to design data entry forms for a database.</span></span>  
  
 <span data-ttu-id="e553b-209">[!code-vb[VbEnumsTask #&30;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e553b-209">[!code-vb[VbEnumsTask#30](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e553b-210">示例</span><span class="sxs-lookup"><span data-stu-id="e553b-210">Example</span></span>  
 <span data-ttu-id="e553b-211">下面的示例演示包括正和负号的值。</span><span class="sxs-lookup"><span data-stu-id="e553b-211">The following example shows values that include both positive and negative numbers.</span></span>  
  
 <span data-ttu-id="e553b-212">[!code-vb[VbEnumsTask #&31;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="e553b-212">[!code-vb[VbEnumsTask#31](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e553b-213">示例</span><span class="sxs-lookup"><span data-stu-id="e553b-213">Example</span></span>  
 <span data-ttu-id="e553b-214">在下面的示例中，`As`子句用于指定`datatype`的枚举。</span><span class="sxs-lookup"><span data-stu-id="e553b-214">In the following example, an `As` clause is used to specify the `datatype` of an enumeration.</span></span>  
  
 <span data-ttu-id="e553b-215">[!code-vb[VbEnumsTask #&6;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="e553b-215">[!code-vb[VbEnumsTask#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_5.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e553b-216">示例</span><span class="sxs-lookup"><span data-stu-id="e553b-216">Example</span></span>  
 <span data-ttu-id="e553b-217">下面的示例演示如何使用按位枚举。</span><span class="sxs-lookup"><span data-stu-id="e553b-217">The following example shows how to use a bitwise enumeration.</span></span> <span data-ttu-id="e553b-218">多个值可以分配给一个按位枚举的一个实例。</span><span class="sxs-lookup"><span data-stu-id="e553b-218">Multiple values can be assigned to an instance of a bitwise enumeration.</span></span> <span data-ttu-id="e553b-219">`Enum`声明包含<xref:System.FlagsAttribute>属性，指示可以将枚举视为一组标志。</xref:System.FlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="e553b-219">The `Enum` declaration includes the <xref:System.FlagsAttribute> attribute, which indicates that the enumeration can be treated as a set of flags.</span></span>  
  
 <span data-ttu-id="e553b-220">[!code-vb[VbEnumsTask #&61;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="e553b-220">[!code-vb[VbEnumsTask#61](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_6.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="e553b-221">示例</span><span class="sxs-lookup"><span data-stu-id="e553b-221">Example</span></span>  
 <span data-ttu-id="e553b-222">下面的示例循环访问枚举。</span><span class="sxs-lookup"><span data-stu-id="e553b-222">The following example iterates through an enumeration.</span></span> <span data-ttu-id="e553b-223">它使用<xref:System.Enum.GetNames%2A>方法来检索的枚举成员名称的数组和<xref:System.Enum.GetValues%2A>检索成员值的数组。</xref:System.Enum.GetValues%2A> </xref:System.Enum.GetNames%2A></span><span class="sxs-lookup"><span data-stu-id="e553b-223">It uses the <xref:System.Enum.GetNames%2A> method to retrieve an array of member names from the enumeration, and <xref:System.Enum.GetValues%2A> to retrieve an array of member values.</span></span>  
  
 <span data-ttu-id="e553b-224">[!code-vb[VbEnumsTask #&51;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="e553b-224">[!code-vb[VbEnumsTask#51](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enum-statement_7.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e553b-225">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e553b-225">See Also</span></span>  
 <span data-ttu-id="e553b-226"><xref:System.Enum></xref:System.Enum></span><span class="sxs-lookup"><span data-stu-id="e553b-226"><xref:System.Enum></span></span>   
 <span data-ttu-id="e553b-227"><xref:Microsoft.VisualBasic.Strings.AscW%2A></xref:Microsoft.VisualBasic.Strings.AscW%2A></span><span class="sxs-lookup"><span data-stu-id="e553b-227"><xref:Microsoft.VisualBasic.Strings.AscW%2A></span></span>   
<span data-ttu-id="e553b-228"> [Const 语句](../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e553b-228"> [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="e553b-229"> [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e553b-229"> [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="e553b-230"> [隐式和显式转换](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="e553b-230"> [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="e553b-231"> [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="e553b-231"> [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="e553b-232"> [常量和枚举](../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="e553b-232"> [Constants and Enumerations](../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>

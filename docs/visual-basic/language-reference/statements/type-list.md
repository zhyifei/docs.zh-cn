---
title: 类型列表 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- StructureConstraint
- vb.StructureConstraint
- ClassConstraint
- vb.ClassConstraint
helpviewer_keywords:
- class constraint
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- generics [Visual Basic], type list
- structure constraint
- constraints, in type parameters
- generics [Visual Basic], generic types
- parameters [Visual Basic], type
- constraints, Structure keyword
- type parameters [Visual Basic], constraints
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- generics [Visual Basic], type parameters
- type parameters
- constraints, Class keyword
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
ms.openlocfilehash: dd50435b7cbb5d3d25c0e30618e8733b4eddfe91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655070"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="72dc0-102">类型列表 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72dc0-102">Type List (Visual Basic)</span></span>
<span data-ttu-id="72dc0-103">指定*类型参数*有关*泛型*编程元素。</span><span class="sxs-lookup"><span data-stu-id="72dc0-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="72dc0-104">由逗号分隔多个参数。</span><span class="sxs-lookup"><span data-stu-id="72dc0-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="72dc0-105">下面是一个类型参数的语法。</span><span class="sxs-lookup"><span data-stu-id="72dc0-105">Following is the syntax for one type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72dc0-106">语法</span><span class="sxs-lookup"><span data-stu-id="72dc0-106">Syntax</span></span>  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a><span data-ttu-id="72dc0-107">部件</span><span class="sxs-lookup"><span data-stu-id="72dc0-107">Parts</span></span>  
  
|<span data-ttu-id="72dc0-108">术语</span><span class="sxs-lookup"><span data-stu-id="72dc0-108">Term</span></span>|<span data-ttu-id="72dc0-109">定义</span><span class="sxs-lookup"><span data-stu-id="72dc0-109">Definition</span></span>|  
|---|---|  
|`genericmodifier`|<span data-ttu-id="72dc0-110">可选。</span><span class="sxs-lookup"><span data-stu-id="72dc0-110">Optional.</span></span> <span data-ttu-id="72dc0-111">可以仅在泛型接口和委托中使用。</span><span class="sxs-lookup"><span data-stu-id="72dc0-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="72dc0-112">您可以将类型声明协变通过使用[出](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)关键字或通过使用逆变[中](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="72dc0-112">You can declare a type covariant by using the [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="72dc0-113">请参阅 [协变和逆变](../../programming-guide/concepts/covariance-contravariance/index.md)。</span><span class="sxs-lookup"><span data-stu-id="72dc0-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|  
|`typename`|<span data-ttu-id="72dc0-114">必需。</span><span class="sxs-lookup"><span data-stu-id="72dc0-114">Required.</span></span> <span data-ttu-id="72dc0-115">类型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="72dc0-115">Name of the type parameter.</span></span> <span data-ttu-id="72dc0-116">这是一个占位符，将替换为已定义的类型提供的相应类型参数。</span><span class="sxs-lookup"><span data-stu-id="72dc0-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|  
|`constraintlist`|<span data-ttu-id="72dc0-117">可选。</span><span class="sxs-lookup"><span data-stu-id="72dc0-117">Optional.</span></span> <span data-ttu-id="72dc0-118">约束可以为提供的数据类型的要求列表`typename`。</span><span class="sxs-lookup"><span data-stu-id="72dc0-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="72dc0-119">如果有多个约束，则将它们括在大括号中 (`{ }`)，并用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="72dc0-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="72dc0-120">您必须引入的约束列表[作为](../../../visual-basic/language-reference/statements/as-clause.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="72dc0-120">You must introduce the constraint list with the [As](../../../visual-basic/language-reference/statements/as-clause.md) keyword.</span></span> <span data-ttu-id="72dc0-121">您使用`As`仅一次，在列表的开头。</span><span class="sxs-lookup"><span data-stu-id="72dc0-121">You use `As` only once, at the beginning of the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72dc0-122">备注</span><span class="sxs-lookup"><span data-stu-id="72dc0-122">Remarks</span></span>  
 <span data-ttu-id="72dc0-123">每个泛型编程元素必须采用至少一个类型参数。</span><span class="sxs-lookup"><span data-stu-id="72dc0-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="72dc0-124">类型参数是特定类型的占位符 (*构造的元素*) 客户端代码在创建泛型类型的实例时指定。</span><span class="sxs-lookup"><span data-stu-id="72dc0-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="72dc0-125">可以定义一个泛型类、 结构、 接口、 过程或委托。</span><span class="sxs-lookup"><span data-stu-id="72dc0-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>  
  
 <span data-ttu-id="72dc0-126">有关何时定义泛型类型的详细信息，请参阅[在 Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)。</span><span class="sxs-lookup"><span data-stu-id="72dc0-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="72dc0-127">类型参数名称的详细信息，请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="72dc0-127">For more information on type parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="72dc0-128">规则</span><span class="sxs-lookup"><span data-stu-id="72dc0-128">Rules</span></span>  
  
-   <span data-ttu-id="72dc0-129">**括号。**</span><span class="sxs-lookup"><span data-stu-id="72dc0-129">**Parentheses.**</span></span> <span data-ttu-id="72dc0-130">如果您提供类型参数列表，则必须将其括在括号中，并且必须引入与列表[的](../../../visual-basic/language-reference/statements/of-clause.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="72dc0-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword.</span></span> <span data-ttu-id="72dc0-131">您使用`Of`仅一次，在列表的开头。</span><span class="sxs-lookup"><span data-stu-id="72dc0-131">You use `Of` only once, at the beginning of the list.</span></span>  
  
-   <span data-ttu-id="72dc0-132">**约束。**</span><span class="sxs-lookup"><span data-stu-id="72dc0-132">**Constraints.**</span></span> <span data-ttu-id="72dc0-133">一系列*约束*对类型参数可以包括以下各项的任意组合：</span><span class="sxs-lookup"><span data-stu-id="72dc0-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>  
  
    -   <span data-ttu-id="72dc0-134">任意数量的接口。</span><span class="sxs-lookup"><span data-stu-id="72dc0-134">Any number of interfaces.</span></span> <span data-ttu-id="72dc0-135">此列表中，所提供的类型必须实现的每个接口。</span><span class="sxs-lookup"><span data-stu-id="72dc0-135">The supplied type must implement every interface in this list.</span></span>  
  
    -   <span data-ttu-id="72dc0-136">最多一个类。</span><span class="sxs-lookup"><span data-stu-id="72dc0-136">At most one class.</span></span> <span data-ttu-id="72dc0-137">所提供的类型必须继承自该类的类。</span><span class="sxs-lookup"><span data-stu-id="72dc0-137">The supplied type must inherit from that class.</span></span>  
  
    -   <span data-ttu-id="72dc0-138">`New` 关键字。</span><span class="sxs-lookup"><span data-stu-id="72dc0-138">The `New` keyword.</span></span> <span data-ttu-id="72dc0-139">所提供的类型必须公开泛型类型可以访问的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="72dc0-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="72dc0-140">这是限制由一个或多个接口的类型参数的情况下很有用。</span><span class="sxs-lookup"><span data-stu-id="72dc0-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="72dc0-141">实现接口的类型不一定是公开一个构造函数，并根据构造函数的访问级别，可能无法再对其进行访问的泛型类型中的代码。</span><span class="sxs-lookup"><span data-stu-id="72dc0-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>  
  
    -   <span data-ttu-id="72dc0-142">任一`Class`关键字或`Structure`关键字。</span><span class="sxs-lookup"><span data-stu-id="72dc0-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="72dc0-143">`Class`关键字约束泛型类型形参以要求传递给它的任何类型参数是引用类型，例如字符串、 数组或委托，或从类创建对象。</span><span class="sxs-lookup"><span data-stu-id="72dc0-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="72dc0-144">`Structure`关键字约束泛型类型形参，以要求传递给它的任何类型参数是值类型，例如结构、 枚举或基本数据类型。</span><span class="sxs-lookup"><span data-stu-id="72dc0-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="72dc0-145">不能同时包括`Class`并`Structure`在同一个`constraintlist`。</span><span class="sxs-lookup"><span data-stu-id="72dc0-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>  
  
     <span data-ttu-id="72dc0-146">所提供的类型必须满足每个要求中包括`constraintlist`。</span><span class="sxs-lookup"><span data-stu-id="72dc0-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>  
  
     <span data-ttu-id="72dc0-147">在每个类型参数约束均独立于其他类型参数的约束。</span><span class="sxs-lookup"><span data-stu-id="72dc0-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="72dc0-148">行为</span><span class="sxs-lookup"><span data-stu-id="72dc0-148">Behavior</span></span>  
  
-   <span data-ttu-id="72dc0-149">**编译时替换。**</span><span class="sxs-lookup"><span data-stu-id="72dc0-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="72dc0-150">从通用的编程元素创建构造的类型时，你提供每个类型参数定义的的类型。</span><span class="sxs-lookup"><span data-stu-id="72dc0-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="72dc0-151">Visual Basic 编译器就会替换该类型提供的每个匹配项`typename`泛型元素内。</span><span class="sxs-lookup"><span data-stu-id="72dc0-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>  
  
-   <span data-ttu-id="72dc0-152">**不是存在的约束。**</span><span class="sxs-lookup"><span data-stu-id="72dc0-152">**Absence of Constraints.**</span></span> <span data-ttu-id="72dc0-153">如果不指定任何约束类型参数上的，你的代码仅限于运算和成员受[Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md)为该类型形参。</span><span class="sxs-lookup"><span data-stu-id="72dc0-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) for that type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72dc0-154">示例</span><span class="sxs-lookup"><span data-stu-id="72dc0-154">Example</span></span>  
 <span data-ttu-id="72dc0-155">下面的示例演示泛型字典类，包括将新项添加到字典中的主干函数的主干定义。</span><span class="sxs-lookup"><span data-stu-id="72dc0-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="72dc0-156">示例</span><span class="sxs-lookup"><span data-stu-id="72dc0-156">Example</span></span>  
 <span data-ttu-id="72dc0-157">因为`dictionary`是泛型类型，使用它的代码，可以创建多个对象，每个具有相同的功能，但却作用于不同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="72dc0-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="72dc0-158">下面的示例演示创建的代码行`dictionary`对象使用`String`条目和`Integer`密钥。</span><span class="sxs-lookup"><span data-stu-id="72dc0-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="72dc0-159">示例</span><span class="sxs-lookup"><span data-stu-id="72dc0-159">Example</span></span>  
 <span data-ttu-id="72dc0-160">下面的示例演示由前面的示例生成等效的主干定义。</span><span class="sxs-lookup"><span data-stu-id="72dc0-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="72dc0-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="72dc0-161">See also</span></span>
- [<span data-ttu-id="72dc0-162">Of</span><span class="sxs-lookup"><span data-stu-id="72dc0-162">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)
- [<span data-ttu-id="72dc0-163">New 运算符</span><span class="sxs-lookup"><span data-stu-id="72dc0-163">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)
- [<span data-ttu-id="72dc0-164">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="72dc0-164">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="72dc0-165">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="72dc0-165">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="72dc0-166">Function 语句</span><span class="sxs-lookup"><span data-stu-id="72dc0-166">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="72dc0-167">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="72dc0-167">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="72dc0-168">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="72dc0-168">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="72dc0-169">如何：使用泛型类</span><span class="sxs-lookup"><span data-stu-id="72dc0-169">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [<span data-ttu-id="72dc0-170">协变和逆变</span><span class="sxs-lookup"><span data-stu-id="72dc0-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)
- [<span data-ttu-id="72dc0-171">In</span><span class="sxs-lookup"><span data-stu-id="72dc0-171">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="72dc0-172">Out</span><span class="sxs-lookup"><span data-stu-id="72dc0-172">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)

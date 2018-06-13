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
ms.openlocfilehash: 5fbb07154fce27feb257b431c1726446b42fbfe0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605285"
---
# <a name="type-list-visual-basic"></a><span data-ttu-id="5efaa-102">类型列表 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5efaa-102">Type List (Visual Basic)</span></span>
<span data-ttu-id="5efaa-103">指定*类型参数*为*泛型*编程元素。</span><span class="sxs-lookup"><span data-stu-id="5efaa-103">Specifies the *type parameters* for a *generic* programming element.</span></span> <span data-ttu-id="5efaa-104">用逗号分隔多个参数。</span><span class="sxs-lookup"><span data-stu-id="5efaa-104">Multiple parameters are separated by commas.</span></span> <span data-ttu-id="5efaa-105">下面是一个类型参数的语法。</span><span class="sxs-lookup"><span data-stu-id="5efaa-105">Following is the syntax for one type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5efaa-106">语法</span><span class="sxs-lookup"><span data-stu-id="5efaa-106">Syntax</span></span>  
  
```  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## <a name="parts"></a><span data-ttu-id="5efaa-107">部件</span><span class="sxs-lookup"><span data-stu-id="5efaa-107">Parts</span></span>  
  
|<span data-ttu-id="5efaa-108">术语</span><span class="sxs-lookup"><span data-stu-id="5efaa-108">Term</span></span>|<span data-ttu-id="5efaa-109">定义</span><span class="sxs-lookup"><span data-stu-id="5efaa-109">Definition</span></span>|  
|---|---|  
|`genericmodifier`|<span data-ttu-id="5efaa-110">可选。</span><span class="sxs-lookup"><span data-stu-id="5efaa-110">Optional.</span></span> <span data-ttu-id="5efaa-111">可仅在泛型接口和委托。</span><span class="sxs-lookup"><span data-stu-id="5efaa-111">Can be used only in generic interfaces and delegates.</span></span> <span data-ttu-id="5efaa-112">你可以声明类型协变使用[出](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)关键字或通过使用逆变[中](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="5efaa-112">You can declare a type covariant by using the [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md) keyword or contravariant by using the [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) keyword.</span></span> <span data-ttu-id="5efaa-113">请参阅 [协变和逆变](../../programming-guide/concepts/covariance-contravariance/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5efaa-113">See [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>|  
|`typename`|<span data-ttu-id="5efaa-114">必须的。</span><span class="sxs-lookup"><span data-stu-id="5efaa-114">Required.</span></span> <span data-ttu-id="5efaa-115">类型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="5efaa-115">Name of the type parameter.</span></span> <span data-ttu-id="5efaa-116">这是一个占位符，将替换为相应类型参数所提供的定义类型。</span><span class="sxs-lookup"><span data-stu-id="5efaa-116">This is a placeholder, to be replaced by a defined type supplied by the corresponding type argument.</span></span>|  
|`constraintlist`|<span data-ttu-id="5efaa-117">可选。</span><span class="sxs-lookup"><span data-stu-id="5efaa-117">Optional.</span></span> <span data-ttu-id="5efaa-118">约束可以为提供的数据类型的要求列表`typename`。</span><span class="sxs-lookup"><span data-stu-id="5efaa-118">List of requirements that constrain the data type that can be supplied for `typename`.</span></span> <span data-ttu-id="5efaa-119">如果你有多个约束，则将它们括在大括号中 (`{ }`)，并用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="5efaa-119">If you have multiple constraints, enclose them in curly braces (`{ }`) and separate them with commas.</span></span> <span data-ttu-id="5efaa-120">你必须使用引入此约束列表[作为](../../../visual-basic/language-reference/statements/as-clause.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="5efaa-120">You must introduce the constraint list with the [As](../../../visual-basic/language-reference/statements/as-clause.md) keyword.</span></span> <span data-ttu-id="5efaa-121">你使用`As`一次，在列表的开头。</span><span class="sxs-lookup"><span data-stu-id="5efaa-121">You use `As` only once, at the beginning of the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5efaa-122">备注</span><span class="sxs-lookup"><span data-stu-id="5efaa-122">Remarks</span></span>  
 <span data-ttu-id="5efaa-123">每个泛型的编程元素必须采用至少一个类型参数。</span><span class="sxs-lookup"><span data-stu-id="5efaa-123">Every generic programming element must take at least one type parameter.</span></span> <span data-ttu-id="5efaa-124">类型参数是为特定类型的占位符 (*构造的元素*) 客户端代码在创建泛型类型的实例时指定。</span><span class="sxs-lookup"><span data-stu-id="5efaa-124">A type parameter is a placeholder for a specific type (a *constructed element*) that client code specifies when it creates an instance of the generic type.</span></span> <span data-ttu-id="5efaa-125">你可以定义的泛型类、 结构、 接口、 过程或委托。</span><span class="sxs-lookup"><span data-stu-id="5efaa-125">You can define a generic class, structure, interface, procedure, or delegate.</span></span>  
  
 <span data-ttu-id="5efaa-126">有关何时定义泛型类型的详细信息，请参阅[Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)。</span><span class="sxs-lookup"><span data-stu-id="5efaa-126">For more information on when to define a generic type, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span> <span data-ttu-id="5efaa-127">对类型参数名称的详细信息，请参阅[声明元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="5efaa-127">For more information on type parameter names, see [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="5efaa-128">规则</span><span class="sxs-lookup"><span data-stu-id="5efaa-128">Rules</span></span>  
  
-   <span data-ttu-id="5efaa-129">**括号。**</span><span class="sxs-lookup"><span data-stu-id="5efaa-129">**Parentheses.**</span></span> <span data-ttu-id="5efaa-130">如果提供类型参数列表，则必须将它括在括号内，并且你必须使用引入列表[的](../../../visual-basic/language-reference/statements/of-clause.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="5efaa-130">If you supply a type parameter list, you must enclose it in parentheses, and you must introduce the list with the [Of](../../../visual-basic/language-reference/statements/of-clause.md) keyword.</span></span> <span data-ttu-id="5efaa-131">你使用`Of`一次，在列表的开头。</span><span class="sxs-lookup"><span data-stu-id="5efaa-131">You use `Of` only once, at the beginning of the list.</span></span>  
  
-   <span data-ttu-id="5efaa-132">**约束。**</span><span class="sxs-lookup"><span data-stu-id="5efaa-132">**Constraints.**</span></span> <span data-ttu-id="5efaa-133">一份*约束*的类型参数可以在任意组合中包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="5efaa-133">A list of *constraints* on a type parameter can include the following items in any combination:</span></span>  
  
    -   <span data-ttu-id="5efaa-134">任意数量的接口。</span><span class="sxs-lookup"><span data-stu-id="5efaa-134">Any number of interfaces.</span></span> <span data-ttu-id="5efaa-135">提供的类型必须实现每个接口，此列表中。</span><span class="sxs-lookup"><span data-stu-id="5efaa-135">The supplied type must implement every interface in this list.</span></span>  
  
    -   <span data-ttu-id="5efaa-136">最多一个类。</span><span class="sxs-lookup"><span data-stu-id="5efaa-136">At most one class.</span></span> <span data-ttu-id="5efaa-137">提供的类型必须从该类继承。</span><span class="sxs-lookup"><span data-stu-id="5efaa-137">The supplied type must inherit from that class.</span></span>  
  
    -   <span data-ttu-id="5efaa-138">`New` 关键字。</span><span class="sxs-lookup"><span data-stu-id="5efaa-138">The `New` keyword.</span></span> <span data-ttu-id="5efaa-139">提供的类型必须公开一个泛型类型可以访问的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="5efaa-139">The supplied type must expose a parameterless constructor that your generic type can access.</span></span> <span data-ttu-id="5efaa-140">这是你将通过一个或多个接口的类型参数约束的情况下很有用。</span><span class="sxs-lookup"><span data-stu-id="5efaa-140">This is useful if you constrain a type parameter by one or more interfaces.</span></span> <span data-ttu-id="5efaa-141">实现接口的类型不一定会公开一个构造函数，，具体取决于构造函数的访问级别，泛型类型中的代码可能不能访问它。</span><span class="sxs-lookup"><span data-stu-id="5efaa-141">A type that implements interfaces does not necessarily expose a constructor, and depending on the access level of a constructor, the code within the generic type might not be able to access it.</span></span>  
  
    -   <span data-ttu-id="5efaa-142">任一`Class`关键字或`Structure`关键字。</span><span class="sxs-lookup"><span data-stu-id="5efaa-142">Either the `Class` keyword or the `Structure` keyword.</span></span> <span data-ttu-id="5efaa-143">`Class`关键字约束用于需要传递给它的任何类型自变量是引用类型，例如字符串、 数组或委托，或从类创建对象的泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="5efaa-143">The `Class` keyword constrains a generic type parameter to require that any type argument passed to it be a reference type, for example a string, array, or delegate, or an object created from a class.</span></span> <span data-ttu-id="5efaa-144">`Structure`关键字约束的泛型类型参数要求传递给它的任何类型自变量是值类型，例如结构、 枚举或基本数据类型。</span><span class="sxs-lookup"><span data-stu-id="5efaa-144">The `Structure` keyword constrains a generic type parameter to require that any type argument passed to it be a value type, for example a structure, enumeration, or elementary data type.</span></span> <span data-ttu-id="5efaa-145">不能同时包含这两者`Class`和`Structure`在同一个`constraintlist`。</span><span class="sxs-lookup"><span data-stu-id="5efaa-145">You cannot include both `Class` and `Structure` in the same `constraintlist`.</span></span>  
  
     <span data-ttu-id="5efaa-146">提供的类型必须满足中包括每个要求`constraintlist`。</span><span class="sxs-lookup"><span data-stu-id="5efaa-146">The supplied type must satisfy every requirement you include in `constraintlist`.</span></span>  
  
     <span data-ttu-id="5efaa-147">每个类型参数约束均独立于其他类型参数的约束。</span><span class="sxs-lookup"><span data-stu-id="5efaa-147">Constraints on each type parameter are independent of constraints on other type parameters.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="5efaa-148">行为</span><span class="sxs-lookup"><span data-stu-id="5efaa-148">Behavior</span></span>  
  
-   <span data-ttu-id="5efaa-149">**编译时替换。**</span><span class="sxs-lookup"><span data-stu-id="5efaa-149">**Compile-Time Substitution.**</span></span> <span data-ttu-id="5efaa-150">时从泛型的编程元素创建构造的类型，提供每个类型参数已定义的类型。</span><span class="sxs-lookup"><span data-stu-id="5efaa-150">When you create a constructed type from a generic programming element, you supply a defined type for each type parameter.</span></span> <span data-ttu-id="5efaa-151">Visual Basic 编译器就会替换该类型提供的每个匹配项`typename`泛型元素内。</span><span class="sxs-lookup"><span data-stu-id="5efaa-151">The Visual Basic compiler substitutes that supplied type for every occurrence of `typename` within the generic element.</span></span>  
  
-   <span data-ttu-id="5efaa-152">**没有约束。**</span><span class="sxs-lookup"><span data-stu-id="5efaa-152">**Absence of Constraints.**</span></span> <span data-ttu-id="5efaa-153">如果不指定任何类型参数上的约束，你的代码仅限于运算和成员受[Object 数据类型](../../../visual-basic/language-reference/data-types/object-data-type.md)为该类型参数。</span><span class="sxs-lookup"><span data-stu-id="5efaa-153">If you do not specify any constraints on a type parameter, your code is limited to the operations and members supported by the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) for that type parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5efaa-154">示例</span><span class="sxs-lookup"><span data-stu-id="5efaa-154">Example</span></span>  
 <span data-ttu-id="5efaa-155">下面的示例演示一个泛型字典类，包括将新项添加到字典中的主干函数的主干定义。</span><span class="sxs-lookup"><span data-stu-id="5efaa-155">The following example shows a skeleton definition of a generic dictionary class, including a skeleton function to add a new entry to the dictionary.</span></span>  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="5efaa-156">示例</span><span class="sxs-lookup"><span data-stu-id="5efaa-156">Example</span></span>  
 <span data-ttu-id="5efaa-157">因为`dictionary`是泛型类型，使用它的代码，可以创建多个对象，每个具有相同的功能，但作用于不同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5efaa-157">Because `dictionary` is generic, the code that uses it can create a variety of objects from it, each having the same functionality but acting on a different data type.</span></span> <span data-ttu-id="5efaa-158">下面的示例演示的创建的代码行`dictionary`对象`String`条目和`Integer`密钥。</span><span class="sxs-lookup"><span data-stu-id="5efaa-158">The following example shows a line of code that creates a `dictionary` object with `String` entries and `Integer` keys.</span></span>  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="5efaa-159">示例</span><span class="sxs-lookup"><span data-stu-id="5efaa-159">Example</span></span>  
 <span data-ttu-id="5efaa-160">下面的示例演示了由前面的示例生成等效的主干定义。</span><span class="sxs-lookup"><span data-stu-id="5efaa-160">The following example shows the equivalent skeleton definition generated by the preceding example.</span></span>  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5efaa-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="5efaa-161">See Also</span></span>  
 [<span data-ttu-id="5efaa-162">Of</span><span class="sxs-lookup"><span data-stu-id="5efaa-162">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
 [<span data-ttu-id="5efaa-163">New 运算符</span><span class="sxs-lookup"><span data-stu-id="5efaa-163">New Operator</span></span>](../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="5efaa-164">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="5efaa-164">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="5efaa-165">Object 数据类型</span><span class="sxs-lookup"><span data-stu-id="5efaa-165">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="5efaa-166">Function 语句</span><span class="sxs-lookup"><span data-stu-id="5efaa-166">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="5efaa-167">Structure 语句</span><span class="sxs-lookup"><span data-stu-id="5efaa-167">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="5efaa-168">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="5efaa-168">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="5efaa-169">如何：使用泛型类</span><span class="sxs-lookup"><span data-stu-id="5efaa-169">How to: Use a Generic Class</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="5efaa-170">协变和逆变</span><span class="sxs-lookup"><span data-stu-id="5efaa-170">Covariance and Contravariance</span></span>](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [<span data-ttu-id="5efaa-171">In</span><span class="sxs-lookup"><span data-stu-id="5efaa-171">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [<span data-ttu-id="5efaa-172">Out</span><span class="sxs-lookup"><span data-stu-id="5efaa-172">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)

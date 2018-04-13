---
title: 对象初始值设定项：命名类型和匿名类型 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ObjectInitializer
helpviewer_keywords:
- object initializers [Visual Basic]
- anonymous types [Visual Basic], object initializers
- initializing properties [Visual Basic]
- initializers [Visual Basic]
- named types [Visual Basic]
ms.assetid: e2df3807-a70f-49dd-ac94-f1e07f472b1b
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 349e4f7b4902eb18845fee7cb4d01b217849a4d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a><span data-ttu-id="c3a80-102">对象初始值设定项：命名类型和匿名类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3a80-102">Object Initializers: Named and Anonymous Types (Visual Basic)</span></span>
<span data-ttu-id="c3a80-103">对象初始值设定项，可以通过使用单个表达式指定一个复杂对象的属性。</span><span class="sxs-lookup"><span data-stu-id="c3a80-103">Object initializers enable you to specify properties for a complex object by using a single expression.</span></span> <span data-ttu-id="c3a80-104">它们可以用于创建实例的命名类型和匿名类型。</span><span class="sxs-lookup"><span data-stu-id="c3a80-104">They can be used to create instances of named types and of anonymous types.</span></span>  
  
## <a name="declarations"></a><span data-ttu-id="c3a80-105">声明</span><span class="sxs-lookup"><span data-stu-id="c3a80-105">Declarations</span></span>  
 <span data-ttu-id="c3a80-106">声明命名类型和匿名类型的实例可以看起来几乎完全相同，但其效果并不相同。</span><span class="sxs-lookup"><span data-stu-id="c3a80-106">Declarations of instances of named and anonymous types can look almost identical, but their effects are not the same.</span></span> <span data-ttu-id="c3a80-107">每个类别都有其自己的功能和限制。</span><span class="sxs-lookup"><span data-stu-id="c3a80-107">Each category has abilities and restrictions of its own.</span></span> <span data-ttu-id="c3a80-108">下面的示例演示一种简便方式声明和初始化命名类的实例`Customer`，通过使用对象初始值设定项列表。</span><span class="sxs-lookup"><span data-stu-id="c3a80-108">The following example shows a convenient way to declare and initialize an instance of a named class, `Customer`, by using an object initializer list.</span></span> <span data-ttu-id="c3a80-109">请注意，在关键字后指定的类名称是`New`。</span><span class="sxs-lookup"><span data-stu-id="c3a80-109">Notice that the name of the class is specified after the keyword `New`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#1](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]  
  
 <span data-ttu-id="c3a80-110">一个匿名类型有没有可用的名称。</span><span class="sxs-lookup"><span data-stu-id="c3a80-110">An anonymous type has no usable name.</span></span> <span data-ttu-id="c3a80-111">因此实例化的匿名类型不能包含的类名称。</span><span class="sxs-lookup"><span data-stu-id="c3a80-111">Therefore an instantiation of an anonymous type cannot include a class name.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
 <span data-ttu-id="c3a80-112">要求和的两个声明的结果并不相同。</span><span class="sxs-lookup"><span data-stu-id="c3a80-112">The requirements and results of the two declarations are not the same.</span></span> <span data-ttu-id="c3a80-113">有关`namedCust`、`Customer`具有类`Name`属性必须已经存在，并且声明会创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="c3a80-113">For `namedCust`, a `Customer` class that has a `Name` property must already exist, and the declaration creates an instance of that class.</span></span> <span data-ttu-id="c3a80-114">有关`anonymousCust`，编译器定义了一个新的类具有一个属性，一个字符串称为`Name`，并创建此类的新实例。</span><span class="sxs-lookup"><span data-stu-id="c3a80-114">For `anonymousCust`, the compiler defines a new class that has one property, a string called `Name`, and creates a new instance of that class.</span></span>  
  
## <a name="named-types"></a><span data-ttu-id="c3a80-115">命名的类型</span><span class="sxs-lookup"><span data-stu-id="c3a80-115">Named Types</span></span>  
 <span data-ttu-id="c3a80-116">对象初始值设定项提供一种简单的方法来调用一种类型的构造函数，然后在单个语句中设置某些或所有属性的值。</span><span class="sxs-lookup"><span data-stu-id="c3a80-116">Object initializers provide a simple way to call the constructor of a type and then set the values of some or all properties in a single statement.</span></span> <span data-ttu-id="c3a80-117">编译器将调用该语句的适当构造函数： 如果未不提供任何参数，默认构造函数或参数化构造函数，如果发送一个或多个自变量。</span><span class="sxs-lookup"><span data-stu-id="c3a80-117">The compiler invokes the appropriate constructor for the statement: the default constructor if no arguments are presented, or a parameterized constructor if one or more arguments are sent.</span></span> <span data-ttu-id="c3a80-118">之后，以在初始值设定项列表中出现的顺序进行初始化的指定的属性。</span><span class="sxs-lookup"><span data-stu-id="c3a80-118">After that, the specified properties are initialized in the order in which they are presented in the initializer list.</span></span>  
  
 <span data-ttu-id="c3a80-119">初始值设定项列表中的每个初始化包含的类的成员的初始值分配。</span><span class="sxs-lookup"><span data-stu-id="c3a80-119">Each initialization in the initializer list consists of the assignment of an initial value to a member of the class.</span></span> <span data-ttu-id="c3a80-120">定义类时确定的名称和数据类型的成员。</span><span class="sxs-lookup"><span data-stu-id="c3a80-120">The names and data types of the members are determined when the class is defined.</span></span> <span data-ttu-id="c3a80-121">在以下示例中，`Customer`类必须存在，并且必须具有成员命名`Name`和`City`，可以接受字符串值。</span><span class="sxs-lookup"><span data-stu-id="c3a80-121">In the following examples, the `Customer` class must exist, and must have members named `Name` and `City` that can accept string values.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#3](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]  
  
 <span data-ttu-id="c3a80-122">或者，你可以通过使用下面的代码来获取相同的结果：</span><span class="sxs-lookup"><span data-stu-id="c3a80-122">Alternatively, you can obtain the same result by using the following code:</span></span>  
  
 [!code-vb[VbVbalrObjectInit#4](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]  
  
 <span data-ttu-id="c3a80-123">每个这些声明是等效于以下示例中，这将创建`Customer`通过使用默认构造函数中，对象，然后指定初始值`Name`和`City`属性使用`With`语句。</span><span class="sxs-lookup"><span data-stu-id="c3a80-123">Each of these declarations is equivalent to the following example, which creates a `Customer` object by using the default constructor, and then specifies initial values for the `Name` and `City` properties by using a `With` statement.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#5](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]  
  
 <span data-ttu-id="c3a80-124">如果`Customer`类包含使你能够发送中的值的参数化构造函数`Name`，例如，你可以声明和初始化`Customer`对象通过以下方式：</span><span class="sxs-lookup"><span data-stu-id="c3a80-124">If the `Customer` class contains a parameterized constructor that enables you to send in a value for `Name`, for example, you can also declare and initialize a `Customer` object in the following ways:</span></span>  
  
 [!code-vb[VbVbalrObjectInit#6](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]  
  
 <span data-ttu-id="c3a80-125">无需初始化所有属性，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="c3a80-125">You do not have to initialize all properties, as the following code shows.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#7](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]  
  
 <span data-ttu-id="c3a80-126">但是，初始化列表不能为空。</span><span class="sxs-lookup"><span data-stu-id="c3a80-126">However, the initialization list cannot be empty.</span></span> <span data-ttu-id="c3a80-127">未初始化的属性保留其默认值。</span><span class="sxs-lookup"><span data-stu-id="c3a80-127">Uninitialized properties retain their default values.</span></span>  
  
### <a name="type-inference-with-named-types"></a><span data-ttu-id="c3a80-128">命名类型的类型推理</span><span class="sxs-lookup"><span data-stu-id="c3a80-128">Type Inference with Named Types</span></span>  
 <span data-ttu-id="c3a80-129">你可以缩短的声明的代码`cust1`通过组合使用对象初始值设定项和局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="c3a80-129">You can shorten the code for the declaration of `cust1` by combining object initializers and local type inference.</span></span> <span data-ttu-id="c3a80-130">这允许你忽略`As`在变量声明中的子句。</span><span class="sxs-lookup"><span data-stu-id="c3a80-130">This enables you to omit the `As` clause in the variable declaration.</span></span> <span data-ttu-id="c3a80-131">变量的数据类型是从创建的分配的对象的类型推断出。</span><span class="sxs-lookup"><span data-stu-id="c3a80-131">The data type of the variable is inferred from the type of the object that is created by the assignment.</span></span> <span data-ttu-id="c3a80-132">在下面的示例中的一种`cust6`是`Customer`。</span><span class="sxs-lookup"><span data-stu-id="c3a80-132">In the following example, the type of `cust6` is `Customer`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#8](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]  
  
### <a name="remarks-about-named-types"></a><span data-ttu-id="c3a80-133">有关命名类型的备注</span><span class="sxs-lookup"><span data-stu-id="c3a80-133">Remarks About Named Types</span></span>  
  
-   <span data-ttu-id="c3a80-134">不止一次在对象初始值设定项列表中，不能初始化类成员。</span><span class="sxs-lookup"><span data-stu-id="c3a80-134">A class member cannot be initialized more than one time in the object initializer list.</span></span> <span data-ttu-id="c3a80-135">声明`cust7`会导致错误。</span><span class="sxs-lookup"><span data-stu-id="c3a80-135">The declaration of `cust7` causes an error.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#9](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]  
  
-   <span data-ttu-id="c3a80-136">成员可以用来初始化自身或另一个字段。</span><span class="sxs-lookup"><span data-stu-id="c3a80-136">A member can be used to initialize itself or another field.</span></span> <span data-ttu-id="c3a80-137">如果在被初始化，如下所示的以下声明之前访问成员，则`cust8`，将使用默认值。</span><span class="sxs-lookup"><span data-stu-id="c3a80-137">If a member is accessed before it has been initialized, as in the following declaration for `cust8`, the default value will be used.</span></span> <span data-ttu-id="c3a80-138">请记住，使用对象初始值设定项的声明，处理时，第一件事是，都会调用适当的构造函数。</span><span class="sxs-lookup"><span data-stu-id="c3a80-138">Remember that when a declaration that uses an object initializer is processed, the first thing that happens is that the appropriate constructor is invoked.</span></span> <span data-ttu-id="c3a80-139">之后，将初始化初始值设定项列表中的各个字段。</span><span class="sxs-lookup"><span data-stu-id="c3a80-139">After that, the individual fields in the initializer list are initialized.</span></span> <span data-ttu-id="c3a80-140">在以下示例中，默认值为`Name`分配为`cust8`，并且初始化的值分配中`cust9`。</span><span class="sxs-lookup"><span data-stu-id="c3a80-140">In the following examples, the default value for `Name` is assigned for `cust8`, and an initialized value is assigned in `cust9`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#10](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]  
  
     <span data-ttu-id="c3a80-141">下面的示例使用参数化构造函数从`cust3`和`cust4`声明和初始化`cust10`和`cust11`。</span><span class="sxs-lookup"><span data-stu-id="c3a80-141">The following example uses the parameterized constructor from `cust3` and `cust4` to declare and initialize `cust10` and `cust11`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#11](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]  
  
-   <span data-ttu-id="c3a80-142">可以嵌套对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="c3a80-142">Object initializers can be nested.</span></span> <span data-ttu-id="c3a80-143">在下面的示例中，`AddressClass`是具有两个属性的类`City`和`State`，和`Customer`类具有`Address`是的一个实例的属性`AddressClass`。</span><span class="sxs-lookup"><span data-stu-id="c3a80-143">In the following example, `AddressClass` is a class that has two properties, `City` and `State`, and the `Customer` class has an `Address` property that is an instance of `AddressClass`.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#12](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]  
  
-   <span data-ttu-id="c3a80-144">初始化列表不能为空。</span><span class="sxs-lookup"><span data-stu-id="c3a80-144">The initialization list cannot be empty.</span></span>  
  
-   <span data-ttu-id="c3a80-145">正在初始化的实例不能是类型对象。</span><span class="sxs-lookup"><span data-stu-id="c3a80-145">The instance being initialized cannot be of type Object.</span></span>  
  
-   <span data-ttu-id="c3a80-146">正在初始化的类成员不能共享的成员、 只读成员、 常量或方法调用。</span><span class="sxs-lookup"><span data-stu-id="c3a80-146">Class members being initialized cannot be shared members, read-only members, constants, or method calls.</span></span>  
  
-   <span data-ttu-id="c3a80-147">正在初始化的类成员无法编制索引，或可以限定。</span><span class="sxs-lookup"><span data-stu-id="c3a80-147">Class members being initialized cannot be indexed or qualified.</span></span> <span data-ttu-id="c3a80-148">下面的示例将引发编译器错误：</span><span class="sxs-lookup"><span data-stu-id="c3a80-148">The following examples raise compiler errors:</span></span>  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a><span data-ttu-id="c3a80-149">匿名类型</span><span class="sxs-lookup"><span data-stu-id="c3a80-149">Anonymous Types</span></span>  
 <span data-ttu-id="c3a80-150">匿名类型使用对象初始值设定项来创建未显式定义的新类型和名称的实例。</span><span class="sxs-lookup"><span data-stu-id="c3a80-150">Anonymous types use object initializers to create instances of new types that you do not explicitly define and name.</span></span> <span data-ttu-id="c3a80-151">此时，编译器将根据你指定的属性的类型生成在对象初始值设定项列表中。</span><span class="sxs-lookup"><span data-stu-id="c3a80-151">Instead, the compiler generates a type according to the properties you designate in the object initializer list.</span></span> <span data-ttu-id="c3a80-152">由于未指定类型的名称，因此将它称为*匿名类型*。</span><span class="sxs-lookup"><span data-stu-id="c3a80-152">Because the name of the type is not specified, it is referred to as an *anonymous type*.</span></span> <span data-ttu-id="c3a80-153">例如，比较和更早版本的以下声明`cust6`。</span><span class="sxs-lookup"><span data-stu-id="c3a80-153">For example, compare the following declaration to the earlier one for `cust6`.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#13](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]  
  
 <span data-ttu-id="c3a80-154">唯一的区别语法是后未指定任何名称`New`数据类型。</span><span class="sxs-lookup"><span data-stu-id="c3a80-154">The only difference syntactically is that no name is specified after `New` for the data type.</span></span> <span data-ttu-id="c3a80-155">但是，会发生什么情况是有很大差异。</span><span class="sxs-lookup"><span data-stu-id="c3a80-155">However, what happens is quite different.</span></span> <span data-ttu-id="c3a80-156">编译器将定义新的匿名类型具有两个属性，`Name`和`City`，并使用指定的值创建它的实例。</span><span class="sxs-lookup"><span data-stu-id="c3a80-156">The compiler defines a new anonymous type that has two properties, `Name` and `City`, and creates an instance of it with the specified values.</span></span> <span data-ttu-id="c3a80-157">类型推理确定类型的`Name`和`City`在示例中为字符串。</span><span class="sxs-lookup"><span data-stu-id="c3a80-157">Type inference determines the types of `Name` and `City` in the example to be strings.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="c3a80-158">匿名类型的名称由编译器，生成和编译的不同而有所不同。</span><span class="sxs-lookup"><span data-stu-id="c3a80-158">The name of the anonymous type is generated by the compiler, and may vary from compilation to compilation.</span></span> <span data-ttu-id="c3a80-159">你的代码不应使用或依赖于匿名类型的名称。</span><span class="sxs-lookup"><span data-stu-id="c3a80-159">Your code should not use or rely on the name of an anonymous type.</span></span>  
  
 <span data-ttu-id="c3a80-160">类型的名称不可用，因为不能使用`As`子句来声明`cust13`。</span><span class="sxs-lookup"><span data-stu-id="c3a80-160">Because the name of the type is not available, you cannot use an `As` clause to declare `cust13`.</span></span> <span data-ttu-id="c3a80-161">必须推断其类型。</span><span class="sxs-lookup"><span data-stu-id="c3a80-161">Its type must be inferred.</span></span> <span data-ttu-id="c3a80-162">如果不使用后期绑定，这将限制到本地变量的匿名类型的使用。</span><span class="sxs-lookup"><span data-stu-id="c3a80-162">Without using late binding, this limits the use of anonymous types to local variables.</span></span>  
  
 <span data-ttu-id="c3a80-163">匿名类型提供对关键支持[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="c3a80-163">Anonymous types provide critical support for [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="c3a80-164">有关使用查询中的匿名类型的详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)和[Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="c3a80-164">For more information about the use of anonymous types in queries, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).</span></span>  
  
### <a name="remarks-about-anonymous-types"></a><span data-ttu-id="c3a80-165">有关匿名类型的备注</span><span class="sxs-lookup"><span data-stu-id="c3a80-165">Remarks About Anonymous Types</span></span>  
  
-   <span data-ttu-id="c3a80-166">通常情况下，所有或大多数匿名类型声明中的属性将键属性，通过键入关键字指示`Key`属性名称的前面。</span><span class="sxs-lookup"><span data-stu-id="c3a80-166">Typically, all or most of the properties in an anonymous type declaration will be key properties, which are indicated by typing the keyword `Key` in front of the property name.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#14](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]  
  
     <span data-ttu-id="c3a80-167">有关密钥属性的详细信息，请参阅[密钥](../../../../visual-basic/language-reference/modifiers/key.md)。</span><span class="sxs-lookup"><span data-stu-id="c3a80-167">For more information about key properties, see [Key](../../../../visual-basic/language-reference/modifiers/key.md).</span></span>  
  
-   <span data-ttu-id="c3a80-168">对于匿名类型定义必须声明至少一个属性，如命名类型，初始值设定项列表。</span><span class="sxs-lookup"><span data-stu-id="c3a80-168">Like named types, initializer lists for anonymous type definitions must declare at least one property.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]  
  
-   <span data-ttu-id="c3a80-169">当声明匿名类型的实例时，编译器将生成匹配的匿名类型定义。</span><span class="sxs-lookup"><span data-stu-id="c3a80-169">When an instance of an anonymous type is declared, the compiler generates a matching anonymous type definition.</span></span> <span data-ttu-id="c3a80-170">名称和数据类型的属性，将实例声明中，从包括以及中定义的编译器。</span><span class="sxs-lookup"><span data-stu-id="c3a80-170">The names and data types of the properties are taken from the instance declaration, and are included by the compiler in the definition.</span></span> <span data-ttu-id="c3a80-171">属性不是名为，并且它们必须命名类型定义，请提前。</span><span class="sxs-lookup"><span data-stu-id="c3a80-171">The properties are not named and defined in advance, as they would be for a named type.</span></span> <span data-ttu-id="c3a80-172">其类型会被推断。</span><span class="sxs-lookup"><span data-stu-id="c3a80-172">Their types are inferred.</span></span> <span data-ttu-id="c3a80-173">不能通过使用指定的属性的数据类型`As`子句。</span><span class="sxs-lookup"><span data-stu-id="c3a80-173">You cannot specify the data types of the properties by using an `As` clause.</span></span>  
  
-   <span data-ttu-id="c3a80-174">匿名类型还可以建立的名称和值的属性在其他几种方式。</span><span class="sxs-lookup"><span data-stu-id="c3a80-174">Anonymous types can also establish the names and values of their properties in several other ways.</span></span> <span data-ttu-id="c3a80-175">例如，名称和变量，或名称的值和其他对象的属性的值，可能需要一个匿名类型属性。</span><span class="sxs-lookup"><span data-stu-id="c3a80-175">For example, an anonymous type property can take both the name and the value of a variable, or the name and value of a property of another object.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#15](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]  
  
     <span data-ttu-id="c3a80-176">有关在匿名类型中定义属性的选项的详细信息，请参阅[如何： 推断属性名和匿名类型声明中的类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)。</span><span class="sxs-lookup"><span data-stu-id="c3a80-176">For more information about the options for defining properties in anonymous types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3a80-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3a80-177">See Also</span></span>  
 [<span data-ttu-id="c3a80-178">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="c3a80-178">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="c3a80-179">匿名类型</span><span class="sxs-lookup"><span data-stu-id="c3a80-179">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="c3a80-180">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="c3a80-180">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="c3a80-181">如何：推断匿名类型声明中的属性名和类型</span><span class="sxs-lookup"><span data-stu-id="c3a80-181">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [<span data-ttu-id="c3a80-182">Key</span><span class="sxs-lookup"><span data-stu-id="c3a80-182">Key</span></span>](../../../../visual-basic/language-reference/modifiers/key.md)  
 [<span data-ttu-id="c3a80-183">如何：使用对象初始值设定项声明对象</span><span class="sxs-lookup"><span data-stu-id="c3a80-183">How to: Declare an Object by Using an Object Initializer</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)

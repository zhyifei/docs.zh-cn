---
title: "对象初始值设定项︰ 命名类型和匿名类型 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ObjectInitializer
dev_langs:
- VB
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d3c89fb0a7b7c535f1b46c208ac47f58513208ba
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="object-initializers-named-and-anonymous-types-visual-basic"></a><span data-ttu-id="49e29-102">对象初始值设定项：命名类型和匿名类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49e29-102">Object Initializers: Named and Anonymous Types (Visual Basic)</span></span>
<span data-ttu-id="49e29-103">对象初始值设定项，可以通过使用单个表达式中指定的复杂对象的属性。</span><span class="sxs-lookup"><span data-stu-id="49e29-103">Object initializers enable you to specify properties for a complex object by using a single expression.</span></span> <span data-ttu-id="49e29-104">可以使用它们来创建命名类型和匿名类型的实例。</span><span class="sxs-lookup"><span data-stu-id="49e29-104">They can be used to create instances of named types and of anonymous types.</span></span>  
  
## <a name="declarations"></a><span data-ttu-id="49e29-105">声明</span><span class="sxs-lookup"><span data-stu-id="49e29-105">Declarations</span></span>  
 <span data-ttu-id="49e29-106">命名和匿名类型的实例的声明可以看起来几乎完全相同，但它们的效果并不相同。</span><span class="sxs-lookup"><span data-stu-id="49e29-106">Declarations of instances of named and anonymous types can look almost identical, but their effects are not the same.</span></span> <span data-ttu-id="49e29-107">每个类别都有其自己的功能和限制。</span><span class="sxs-lookup"><span data-stu-id="49e29-107">Each category has abilities and restrictions of its own.</span></span> <span data-ttu-id="49e29-108">下面的示例演示如何声明和初始化命名类的实例的捷径`Customer`，通过使用对象初始值设定项列表。</span><span class="sxs-lookup"><span data-stu-id="49e29-108">The following example shows a convenient way to declare and initialize an instance of a named class, `Customer`, by using an object initializer list.</span></span> <span data-ttu-id="49e29-109">请注意，在关键字后指定的类名称是`New`。</span><span class="sxs-lookup"><span data-stu-id="49e29-109">Notice that the name of the class is specified after the keyword `New`.</span></span>  
  
 <span data-ttu-id="49e29-110">[!code-vb[VbVbalrObjectInit #&1;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-110">[!code-vb[VbVbalrObjectInit#1](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_1.vb)]</span></span>  
  
 <span data-ttu-id="49e29-111">匿名类型有没有可用的名称。</span><span class="sxs-lookup"><span data-stu-id="49e29-111">An anonymous type has no usable name.</span></span> <span data-ttu-id="49e29-112">因此匿名类型的实例化不能包含类名。</span><span class="sxs-lookup"><span data-stu-id="49e29-112">Therefore an instantiation of an anonymous type cannot include a class name.</span></span>  
  
 <span data-ttu-id="49e29-113">[!code-vb[VbVbalrObjectInit #&2;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-113">[!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]</span></span>  
  
 <span data-ttu-id="49e29-114">要求和结果的两个声明都不相同。</span><span class="sxs-lookup"><span data-stu-id="49e29-114">The requirements and results of the two declarations are not the same.</span></span> <span data-ttu-id="49e29-115">有关`namedCust`、`Customer`类，该类具有`Name`属性必须已经存在，并且声明会创建此类的实例。</span><span class="sxs-lookup"><span data-stu-id="49e29-115">For `namedCust`, a `Customer` class that has a `Name` property must already exist, and the declaration creates an instance of that class.</span></span> <span data-ttu-id="49e29-116">有关`anonymousCust`，编译器会定义一个新类，具有一个属性，它是一个字符串称为`Name`，并创建此类的新实例。</span><span class="sxs-lookup"><span data-stu-id="49e29-116">For `anonymousCust`, the compiler defines a new class that has one property, a string called `Name`, and creates a new instance of that class.</span></span>  
  
## <a name="named-types"></a><span data-ttu-id="49e29-117">命名的类型</span><span class="sxs-lookup"><span data-stu-id="49e29-117">Named Types</span></span>  
 <span data-ttu-id="49e29-118">对象初始值设定项提供了一种简单方法调用一种类型的构造函数，然后在单个语句中设置某些或所有属性的值。</span><span class="sxs-lookup"><span data-stu-id="49e29-118">Object initializers provide a simple way to call the constructor of a type and then set the values of some or all properties in a single statement.</span></span> <span data-ttu-id="49e29-119">编译器将调用适当的构造函数的语句︰ 如果未不提供任何参数，该默认构造函数或参数化构造函数，如果将发送一个或多个参数。</span><span class="sxs-lookup"><span data-stu-id="49e29-119">The compiler invokes the appropriate constructor for the statement: the default constructor if no arguments are presented, or a parameterized constructor if one or more arguments are sent.</span></span> <span data-ttu-id="49e29-120">此后，初始值设定项列表中出现的顺序初始化指定的属性。</span><span class="sxs-lookup"><span data-stu-id="49e29-120">After that, the specified properties are initialized in the order in which they are presented in the initializer list.</span></span>  
  
 <span data-ttu-id="49e29-121">每个初始值设定项列表初始化包括分配给类的成员初始值。</span><span class="sxs-lookup"><span data-stu-id="49e29-121">Each initialization in the initializer list consists of the assignment of an initial value to a member of the class.</span></span> <span data-ttu-id="49e29-122">定义类时确定的名称和数据类型的成员。</span><span class="sxs-lookup"><span data-stu-id="49e29-122">The names and data types of the members are determined when the class is defined.</span></span> <span data-ttu-id="49e29-123">在下面的示例中，`Customer`类必须存在，并且必须命名成员`Name`和`City`，可以接受字符串值。</span><span class="sxs-lookup"><span data-stu-id="49e29-123">In the following examples, the `Customer` class must exist, and must have members named `Name` and `City` that can accept string values.</span></span>  
  
 <span data-ttu-id="49e29-124">[!code-vb[VbVbalrObjectInit #&3;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-124">[!code-vb[VbVbalrObjectInit#3](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_3.vb)]</span></span>  
  
 <span data-ttu-id="49e29-125">或者，您可以通过使用下面的代码来获取相同的结果︰</span><span class="sxs-lookup"><span data-stu-id="49e29-125">Alternatively, you can obtain the same result by using the following code:</span></span>  
  
 <span data-ttu-id="49e29-126">[!code-vb[VbVbalrObjectInit #&4;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-126">[!code-vb[VbVbalrObjectInit#4](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_4.vb)]</span></span>  
  
 <span data-ttu-id="49e29-127">这些声明的每个等效于以下示例中，这将创建`Customer`通过使用默认构造函数中，对象，然后指定初始值`Name`和`City`属性使用`With`语句。</span><span class="sxs-lookup"><span data-stu-id="49e29-127">Each of these declarations is equivalent to the following example, which creates a `Customer` object by using the default constructor, and then specifies initial values for the `Name` and `City` properties by using a `With` statement.</span></span>  
  
 <span data-ttu-id="49e29-128">[!code-vb[VbVbalrObjectInit #&5;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-128">[!code-vb[VbVbalrObjectInit#5](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_5.vb)]</span></span>  
  
 <span data-ttu-id="49e29-129">如果`Customer`类包含的参数化构造函数，使您可以为输入值发送`Name`，例如，您可以声明和初始化`Customer`对象通过以下方式︰</span><span class="sxs-lookup"><span data-stu-id="49e29-129">If the `Customer` class contains a parameterized constructor that enables you to send in a value for `Name`, for example, you can also declare and initialize a `Customer` object in the following ways:</span></span>  
  
 <span data-ttu-id="49e29-130">[!code-vb[VbVbalrObjectInit #&6;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-130">[!code-vb[VbVbalrObjectInit#6](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_6.vb)]</span></span>  
  
 <span data-ttu-id="49e29-131">不需要初始化所有属性，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="49e29-131">You do not have to initialize all properties, as the following code shows.</span></span>  
  
 <span data-ttu-id="49e29-132">[!code-vb[VbVbalrObjectInit #&7;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-132">[!code-vb[VbVbalrObjectInit#7](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_7.vb)]</span></span>  
  
 <span data-ttu-id="49e29-133">但是，初始化列表不能为空。</span><span class="sxs-lookup"><span data-stu-id="49e29-133">However, the initialization list cannot be empty.</span></span> <span data-ttu-id="49e29-134">未初始化的属性保留其默认值。</span><span class="sxs-lookup"><span data-stu-id="49e29-134">Uninitialized properties retain their default values.</span></span>  
  
### <a name="type-inference-with-named-types"></a><span data-ttu-id="49e29-135">命名类型的类型推理</span><span class="sxs-lookup"><span data-stu-id="49e29-135">Type Inference with Named Types</span></span>  
 <span data-ttu-id="49e29-136">您可以缩短的声明的代码`cust1`通过组合对象初始值设定项和局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="49e29-136">You can shorten the code for the declaration of `cust1` by combining object initializers and local type inference.</span></span> <span data-ttu-id="49e29-137">这使您可以省略`As`在变量声明中的子句。</span><span class="sxs-lookup"><span data-stu-id="49e29-137">This enables you to omit the `As` clause in the variable declaration.</span></span> <span data-ttu-id="49e29-138">该变量的数据类型是从创建进行的赋值的对象的类型推断出的。</span><span class="sxs-lookup"><span data-stu-id="49e29-138">The data type of the variable is inferred from the type of the object that is created by the assignment.</span></span> <span data-ttu-id="49e29-139">在下面的示例的一种`cust6`是`Customer`。</span><span class="sxs-lookup"><span data-stu-id="49e29-139">In the following example, the type of `cust6` is `Customer`.</span></span>  
  
 <span data-ttu-id="49e29-140">[!code-vb[VbVbalrObjectInit #&8;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-140">[!code-vb[VbVbalrObjectInit#8](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_8.vb)]</span></span>  
  
### <a name="remarks-about-named-types"></a><span data-ttu-id="49e29-141">有关命名类型的备注</span><span class="sxs-lookup"><span data-stu-id="49e29-141">Remarks About Named Types</span></span>  
  
-   <span data-ttu-id="49e29-142">不止一次在对象初始值设定项列表中，无法初始化类成员。</span><span class="sxs-lookup"><span data-stu-id="49e29-142">A class member cannot be initialized more than one time in the object initializer list.</span></span> <span data-ttu-id="49e29-143">声明`cust7`将导致错误。</span><span class="sxs-lookup"><span data-stu-id="49e29-143">The declaration of `cust7` causes an error.</span></span>  
  
     <span data-ttu-id="49e29-144">[!code-vb[VbVbalrObjectInit #&9;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-144">[!code-vb[VbVbalrObjectInit#9](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_9.vb)]</span></span>  
  
-   <span data-ttu-id="49e29-145">成员可以用来初始化自身或另一个字段。</span><span class="sxs-lookup"><span data-stu-id="49e29-145">A member can be used to initialize itself or another field.</span></span> <span data-ttu-id="49e29-146">如果之前尚未初始化，如下所示的以下声明访问成员`cust8`，将使用默认值。</span><span class="sxs-lookup"><span data-stu-id="49e29-146">If a member is accessed before it has been initialized, as in the following declaration for `cust8`, the default value will be used.</span></span> <span data-ttu-id="49e29-147">请记住，使用对象初始值设定项的声明，处理时，第一件事是调用适当的构造函数。</span><span class="sxs-lookup"><span data-stu-id="49e29-147">Remember that when a declaration that uses an object initializer is processed, the first thing that happens is that the appropriate constructor is invoked.</span></span> <span data-ttu-id="49e29-148">之后，将初始化初始值设定项列表中的各个字段。</span><span class="sxs-lookup"><span data-stu-id="49e29-148">After that, the individual fields in the initializer list are initialized.</span></span> <span data-ttu-id="49e29-149">在下面的示例中，默认值为`Name`为分配`cust8`，并将其初始化的值分配在`cust9`。</span><span class="sxs-lookup"><span data-stu-id="49e29-149">In the following examples, the default value for `Name` is assigned for `cust8`, and an initialized value is assigned in `cust9`.</span></span>  
  
     <span data-ttu-id="49e29-150">[!code-vb[VbVbalrObjectInit #&10;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-150">[!code-vb[VbVbalrObjectInit#10](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_10.vb)]</span></span>  
  
     <span data-ttu-id="49e29-151">下面的示例使用参数化构造函数从`cust3`和`cust4`如何声明和初始化`cust10`和`cust11`。</span><span class="sxs-lookup"><span data-stu-id="49e29-151">The following example uses the parameterized constructor from `cust3` and `cust4` to declare and initialize `cust10` and `cust11`.</span></span>  
  
     <span data-ttu-id="49e29-152">[!code-vb[VbVbalrObjectInit #&11;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-152">[!code-vb[VbVbalrObjectInit#11](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_11.vb)]</span></span>  
  
-   <span data-ttu-id="49e29-153">可以嵌套对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="49e29-153">Object initializers can be nested.</span></span> <span data-ttu-id="49e29-154">在下面的示例中，`AddressClass`是具有两个属性的类`City`和`State`，和`Customer`类具有`Address`的一个实例的属性`AddressClass`。</span><span class="sxs-lookup"><span data-stu-id="49e29-154">In the following example, `AddressClass` is a class that has two properties, `City` and `State`, and the `Customer` class has an `Address` property that is an instance of `AddressClass`.</span></span>  
  
     <span data-ttu-id="49e29-155">[!code-vb[VbVbalrObjectInit #&12;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-155">[!code-vb[VbVbalrObjectInit#12](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_12.vb)]</span></span>  
  
-   <span data-ttu-id="49e29-156">初始化列表不能为空。</span><span class="sxs-lookup"><span data-stu-id="49e29-156">The initialization list cannot be empty.</span></span>  
  
-   <span data-ttu-id="49e29-157">正在初始化的实例不能是类型对象。</span><span class="sxs-lookup"><span data-stu-id="49e29-157">The instance being initialized cannot be of type Object.</span></span>  
  
-   <span data-ttu-id="49e29-158">正在初始化的类成员不能为共享的成员、 只读成员、 常量或方法调用。</span><span class="sxs-lookup"><span data-stu-id="49e29-158">Class members being initialized cannot be shared members, read-only members, constants, or method calls.</span></span>  
  
-   <span data-ttu-id="49e29-159">无法索引或限定正在初始化的类成员。</span><span class="sxs-lookup"><span data-stu-id="49e29-159">Class members being initialized cannot be indexed or qualified.</span></span> <span data-ttu-id="49e29-160">下面的示例会产生编译器错误︰</span><span class="sxs-lookup"><span data-stu-id="49e29-160">The following examples raise compiler errors:</span></span>  
  
     `'' Not valid.`  
  
     `' Dim c1 = New Customer With {.OrderNumbers(0) = 148662}`  
  
     `' Dim c2 = New Customer with {.Address.City = "Springfield"}`  
  
## <a name="anonymous-types"></a><span data-ttu-id="49e29-161">匿名类型</span><span class="sxs-lookup"><span data-stu-id="49e29-161">Anonymous Types</span></span>  
 <span data-ttu-id="49e29-162">匿名类型使用对象初始值设定项来创建未显式定义的新类型和名称的实例。</span><span class="sxs-lookup"><span data-stu-id="49e29-162">Anonymous types use object initializers to create instances of new types that you do not explicitly define and name.</span></span> <span data-ttu-id="49e29-163">相反，编译器将生成一种类型根据指定的属性在对象初始值设定项列表中。</span><span class="sxs-lookup"><span data-stu-id="49e29-163">Instead, the compiler generates a type according to the properties you designate in the object initializer list.</span></span> <span data-ttu-id="49e29-164">由于未指定类型的名称，它被称为*匿名类型*。</span><span class="sxs-lookup"><span data-stu-id="49e29-164">Because the name of the type is not specified, it is referred to as an *anonymous type*.</span></span> <span data-ttu-id="49e29-165">例如，将比较以下声明与上一为`cust6`。</span><span class="sxs-lookup"><span data-stu-id="49e29-165">For example, compare the following declaration to the earlier one for `cust6`.</span></span>  
  
 <span data-ttu-id="49e29-166">[!code-vb[VbVbalrObjectInit #&13;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-166">[!code-vb[VbVbalrObjectInit#13](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_13.vb)]</span></span>  
  
 <span data-ttu-id="49e29-167">唯一的区别在语法上是后未指定任何名称`New`数据类型。</span><span class="sxs-lookup"><span data-stu-id="49e29-167">The only difference syntactically is that no name is specified after `New` for the data type.</span></span> <span data-ttu-id="49e29-168">但是，会发生什么情况却截然不同。</span><span class="sxs-lookup"><span data-stu-id="49e29-168">However, what happens is quite different.</span></span> <span data-ttu-id="49e29-169">编译器会定义具有两个属性的新匿名类型`Name`和`City`，并使用指定的值创建它的一个实例。</span><span class="sxs-lookup"><span data-stu-id="49e29-169">The compiler defines a new anonymous type that has two properties, `Name` and `City`, and creates an instance of it with the specified values.</span></span> <span data-ttu-id="49e29-170">类型推导用于确定类型的`Name`和`City`在示例中为字符串。</span><span class="sxs-lookup"><span data-stu-id="49e29-170">Type inference determines the types of `Name` and `City` in the example to be strings.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="49e29-171">匿名类型的名称由编译器生成，并且可能会有所不同编译的。</span><span class="sxs-lookup"><span data-stu-id="49e29-171">The name of the anonymous type is generated by the compiler, and may vary from compilation to compilation.</span></span> <span data-ttu-id="49e29-172">您的代码不应使用或依赖于一个匿名类型的名称。</span><span class="sxs-lookup"><span data-stu-id="49e29-172">Your code should not use or rely on the name of an anonymous type.</span></span>  
  
 <span data-ttu-id="49e29-173">类型的名称不可用，因为不能使用`As`子句声明`cust13`。</span><span class="sxs-lookup"><span data-stu-id="49e29-173">Because the name of the type is not available, you cannot use an `As` clause to declare `cust13`.</span></span> <span data-ttu-id="49e29-174">必须推断其类型。</span><span class="sxs-lookup"><span data-stu-id="49e29-174">Its type must be inferred.</span></span> <span data-ttu-id="49e29-175">如果不使用后期绑定，这限制了匿名类型的局部变量的使用。</span><span class="sxs-lookup"><span data-stu-id="49e29-175">Without using late binding, this limits the use of anonymous types to local variables.</span></span>  
  
 <span data-ttu-id="49e29-176">匿名类型提供了对关键支持[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="49e29-176">Anonymous types provide critical support for [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries.</span></span> <span data-ttu-id="49e29-177">有关使用查询中的匿名类型的详细信息，请参阅[匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)和[在 Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="49e29-177">For more information about the use of anonymous types in queries, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) and [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).</span></span>  
  
### <a name="remarks-about-anonymous-types"></a><span data-ttu-id="49e29-178">关于匿名类型的备注</span><span class="sxs-lookup"><span data-stu-id="49e29-178">Remarks About Anonymous Types</span></span>  
  
-   <span data-ttu-id="49e29-179">通常情况下，所有或大多数匿名类型声明中的属性将键属性，输入该关键字表示`Key`属性名称的前面。</span><span class="sxs-lookup"><span data-stu-id="49e29-179">Typically, all or most of the properties in an anonymous type declaration will be key properties, which are indicated by typing the keyword `Key` in front of the property name.</span></span>  
  
     <span data-ttu-id="49e29-180">[!code-vb[VbVbalrObjectInit #&14;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-180">[!code-vb[VbVbalrObjectInit#14](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_14.vb)]</span></span>  
  
     <span data-ttu-id="49e29-181">键属性的详细信息，请参阅[密钥](../../../../visual-basic/language-reference/modifiers/key.md)。</span><span class="sxs-lookup"><span data-stu-id="49e29-181">For more information about key properties, see [Key](../../../../visual-basic/language-reference/modifiers/key.md).</span></span>  
  
-   <span data-ttu-id="49e29-182">对于匿名类型定义必须声明至少一个属性，如命名类型，初始值设定项列表。</span><span class="sxs-lookup"><span data-stu-id="49e29-182">Like named types, initializer lists for anonymous type definitions must declare at least one property.</span></span>  
  
     <span data-ttu-id="49e29-183">[!code-vb[VbVbalrObjectInit #&2;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-183">[!code-vb[VbVbalrObjectInit#2](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_2.vb)]</span></span>  
  
-   <span data-ttu-id="49e29-184">当声明的匿名类型的实例时，编译器将生成匹配的匿名类型定义。</span><span class="sxs-lookup"><span data-stu-id="49e29-184">When an instance of an anonymous type is declared, the compiler generates a matching anonymous type definition.</span></span> <span data-ttu-id="49e29-185">名称和属性的数据类型，将从实例声明中，并由编译器定义中包含。</span><span class="sxs-lookup"><span data-stu-id="49e29-185">The names and data types of the properties are taken from the instance declaration, and are included by the compiler in the definition.</span></span> <span data-ttu-id="49e29-186">这些属性不是名为和，事先定义而会为命名类型。</span><span class="sxs-lookup"><span data-stu-id="49e29-186">The properties are not named and defined in advance, as they would be for a named type.</span></span> <span data-ttu-id="49e29-187">其类型会被推断。</span><span class="sxs-lookup"><span data-stu-id="49e29-187">Their types are inferred.</span></span> <span data-ttu-id="49e29-188">不能通过使用指定的属性的数据类型`As`子句。</span><span class="sxs-lookup"><span data-stu-id="49e29-188">You cannot specify the data types of the properties by using an `As` clause.</span></span>  
  
-   <span data-ttu-id="49e29-189">匿名类型也可以建立名称和它们的属性的值在其他几种方式。</span><span class="sxs-lookup"><span data-stu-id="49e29-189">Anonymous types can also establish the names and values of their properties in several other ways.</span></span> <span data-ttu-id="49e29-190">例如，匿名类型属性可能需要的名称和的变量，或者名称的值和另一个对象的属性的值。</span><span class="sxs-lookup"><span data-stu-id="49e29-190">For example, an anonymous type property can take both the name and the value of a variable, or the name and value of a property of another object.</span></span>  
  
     <span data-ttu-id="49e29-191">[!code-vb[VbVbalrObjectInit #&15;](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]</span><span class="sxs-lookup"><span data-stu-id="49e29-191">[!code-vb[VbVbalrObjectInit#15](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/object-initializers-named-and-anonymous-types_15.vb)]</span></span>  
  
     <span data-ttu-id="49e29-192">有关在匿名类型中定义属性的选项的详细信息，请参阅[如何︰ 推断属性名和匿名类型声明中的类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)。</span><span class="sxs-lookup"><span data-stu-id="49e29-192">For more information about the options for defining properties in anonymous types, see [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49e29-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49e29-193">See Also</span></span>  
 <span data-ttu-id="49e29-194">[局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="49e29-194">[Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="49e29-195"> [匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="49e29-195"> [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span></span>  
<span data-ttu-id="49e29-196"> [在 Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="49e29-196"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="49e29-197"> [如何︰ 推断匿名类型声明中属性名和类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md) </span><span class="sxs-lookup"><span data-stu-id="49e29-197"> [How to: Infer Property Names and Types in Anonymous Type Declarations](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md) </span></span>  
<span data-ttu-id="49e29-198"> [密钥](../../../../visual-basic/language-reference/modifiers/key.md) </span><span class="sxs-lookup"><span data-stu-id="49e29-198"> [Key](../../../../visual-basic/language-reference/modifiers/key.md) </span></span>  
<span data-ttu-id="49e29-199"> [如何：使用对象初始值设定项声明对象](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)</span><span class="sxs-lookup"><span data-stu-id="49e29-199"> [How to: Declare an Object by Using an Object Initializer](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)</span></span>

---
title: "Delegate 语句 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Delegate
dev_langs:
- VB
helpviewer_keywords:
- delegate keyword
- Delegate statement
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
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
ms.openlocfilehash: 052ef837dfe4f9d34081839eea47e35bc4824afd
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="delegate-statement"></a><span data-ttu-id="75f64-102">Delegate 语句</span><span class="sxs-lookup"><span data-stu-id="75f64-102">Delegate Statement</span></span>
<span data-ttu-id="75f64-103">用于声明委托。</span><span class="sxs-lookup"><span data-stu-id="75f64-103">Used to declare a delegate.</span></span> <span data-ttu-id="75f64-104">委托是一个引用类型，是指`Shared`方法的类型或对象的实例方法。</span><span class="sxs-lookup"><span data-stu-id="75f64-104">A delegate is a reference type that refers to a `Shared` method of a type or to an instance method of an object.</span></span> <span data-ttu-id="75f64-105">任何具有匹配的参数和返回类型的过程可以用于创建此委托类的实例。</span><span class="sxs-lookup"><span data-stu-id="75f64-105">Any procedure with matching parameter and return types can be used to create an instance of this delegate class.</span></span> <span data-ttu-id="75f64-106">然后可以通过委托实例就调用该过程。</span><span class="sxs-lookup"><span data-stu-id="75f64-106">The procedure can then later be invoked by means of the delegate instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75f64-107">语法</span><span class="sxs-lookup"><span data-stu-id="75f64-107">Syntax</span></span>  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a><span data-ttu-id="75f64-108">部件</span><span class="sxs-lookup"><span data-stu-id="75f64-108">Parts</span></span>  
  
|<span data-ttu-id="75f64-109">术语</span><span class="sxs-lookup"><span data-stu-id="75f64-109">Term</span></span>|<span data-ttu-id="75f64-110">定义</span><span class="sxs-lookup"><span data-stu-id="75f64-110">Definition</span></span>|  
|---|---|  
|`attrlist`|<span data-ttu-id="75f64-111">可选。</span><span class="sxs-lookup"><span data-stu-id="75f64-111">Optional.</span></span> <span data-ttu-id="75f64-112">适用于此委托属性的列表。</span><span class="sxs-lookup"><span data-stu-id="75f64-112">List of attributes that apply to this delegate.</span></span> <span data-ttu-id="75f64-113">用逗号分隔多个属性。</span><span class="sxs-lookup"><span data-stu-id="75f64-113">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="75f64-114">必须将括[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)在尖括号 ("`<`"和"`>`")。</span><span class="sxs-lookup"><span data-stu-id="75f64-114">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>|  
|`accessmodifier`|<span data-ttu-id="75f64-115">可选。</span><span class="sxs-lookup"><span data-stu-id="75f64-115">Optional.</span></span> <span data-ttu-id="75f64-116">指定哪些代码可以访问该委托。</span><span class="sxs-lookup"><span data-stu-id="75f64-116">Specifies what code can access the delegate.</span></span> <span data-ttu-id="75f64-117">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="75f64-117">Can be one of the following:</span></span><br /><br /><span data-ttu-id="75f64-118"> -   [公共](../../../visual-basic/language-reference/modifiers/public.md)。</span><span class="sxs-lookup"><span data-stu-id="75f64-118"> -   [Public](../../../visual-basic/language-reference/modifiers/public.md).</span></span> <span data-ttu-id="75f64-119">可以访问的元素声明委托的任何代码都可以访问它。</span><span class="sxs-lookup"><span data-stu-id="75f64-119">Any code that can access the element that declares the delegate can access it.</span></span><br /><span data-ttu-id="75f64-120">-   [受保护的](../../../visual-basic/language-reference/modifiers/protected.md)。</span><span class="sxs-lookup"><span data-stu-id="75f64-120">-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md).</span></span> <span data-ttu-id="75f64-121">只有在委托的类或派生的类中的代码可以访问它。</span><span class="sxs-lookup"><span data-stu-id="75f64-121">Only code within the delegate's class or a derived class can access it.</span></span><br /><span data-ttu-id="75f64-122">-   [友元](../../../visual-basic/language-reference/modifiers/friend.md)。</span><span class="sxs-lookup"><span data-stu-id="75f64-122">-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md).</span></span> <span data-ttu-id="75f64-123">只有同一程序集中的代码可以访问该委托。</span><span class="sxs-lookup"><span data-stu-id="75f64-123">Only code within the same assembly can access the delegate.</span></span><br /><span data-ttu-id="75f64-124">-   [专用](../../../visual-basic/language-reference/modifiers/private.md)。</span><span class="sxs-lookup"><span data-stu-id="75f64-124">-   [Private](../../../visual-basic/language-reference/modifiers/private.md).</span></span> <span data-ttu-id="75f64-125">仅在声明委托的元素内的代码可以访问它。</span><span class="sxs-lookup"><span data-stu-id="75f64-125">Only code within the element that declares the delegate can access it.</span></span><br /><br /> <span data-ttu-id="75f64-126">您可以指定`Protected Friend`以便实现从委托的类，派生的类中或同一程序集中的代码中访问。</span><span class="sxs-lookup"><span data-stu-id="75f64-126">You can specify `Protected Friend` to enable access from code within the delegate's class, a derived class, or the same assembly.</span></span>|  
|`Shadows`|<span data-ttu-id="75f64-127">可选。</span><span class="sxs-lookup"><span data-stu-id="75f64-127">Optional.</span></span> <span data-ttu-id="75f64-128">指示此委托重新声明隐藏同名的编程元素或在基类中重载元素集。</span><span class="sxs-lookup"><span data-stu-id="75f64-128">Indicates that this delegate redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="75f64-129">可以与任何其他类型一起隐藏任何类型的已声明元素。</span><span class="sxs-lookup"><span data-stu-id="75f64-129">You can shadow any kind of declared element with any other kind.</span></span><br /><br /> <span data-ttu-id="75f64-130">隐藏的元素不可在隐藏它的派生类中使用（除了从隐藏元素不可访问的位置）。</span><span class="sxs-lookup"><span data-stu-id="75f64-130">A shadowed element is unavailable from within the derived class that shadows it, except from where the shadowing element is inaccessible.</span></span> <span data-ttu-id="75f64-131">例如，如果`Private`元素将隐藏基类元素，不具有访问权限的代码`Private`元素访问的基类元素相反。</span><span class="sxs-lookup"><span data-stu-id="75f64-131">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>|  
|`Sub`|<span data-ttu-id="75f64-132">可选，但任何一个`Sub`或`Function`必须出现。</span><span class="sxs-lookup"><span data-stu-id="75f64-132">Optional, but either `Sub` or `Function` must appear.</span></span> <span data-ttu-id="75f64-133">将委托作为此过程声明`Sub`不返回值的过程。</span><span class="sxs-lookup"><span data-stu-id="75f64-133">Declares this procedure as a delegate `Sub` procedure that does not return a value.</span></span>|  
|`Function`|<span data-ttu-id="75f64-134">可选，但任何一个`Sub`或`Function`必须出现。</span><span class="sxs-lookup"><span data-stu-id="75f64-134">Optional, but either `Sub` or `Function` must appear.</span></span> <span data-ttu-id="75f64-135">将委托作为此过程声明`Function`返回一个值的过程。</span><span class="sxs-lookup"><span data-stu-id="75f64-135">Declares this procedure as a delegate `Function` procedure that returns a value.</span></span>|  
|`name`|<span data-ttu-id="75f64-136">必需。</span><span class="sxs-lookup"><span data-stu-id="75f64-136">Required.</span></span> <span data-ttu-id="75f64-137">委托类型; 的名称遵循标准的变量命名规则。</span><span class="sxs-lookup"><span data-stu-id="75f64-137">Name of the delegate type; follows standard variable naming conventions.</span></span>|  
|`typeparamlist`|<span data-ttu-id="75f64-138">可选。</span><span class="sxs-lookup"><span data-stu-id="75f64-138">Optional.</span></span> <span data-ttu-id="75f64-139">此委托的类型参数列表。</span><span class="sxs-lookup"><span data-stu-id="75f64-139">List of type parameters for this delegate.</span></span> <span data-ttu-id="75f64-140">由逗号分隔多个类型参数。</span><span class="sxs-lookup"><span data-stu-id="75f64-140">Multiple type parameters are separated by commas.</span></span> <span data-ttu-id="75f64-141">（可选） 每个类型参数可以声明变量使用`In`和`Out`泛型修饰符。</span><span class="sxs-lookup"><span data-stu-id="75f64-141">Optionally, each type parameter can be declared variant by using `In` and `Out` generic modifiers.</span></span> <span data-ttu-id="75f64-142">必须将括[类型列表](../../../visual-basic/language-reference/statements/type-list.md)在括号中，并引入其与`Of`关键字。</span><span class="sxs-lookup"><span data-stu-id="75f64-142">You must enclose the [Type List](../../../visual-basic/language-reference/statements/type-list.md) in parentheses and introduce it with the `Of` keyword.</span></span>|  
|`parameterlist`|<span data-ttu-id="75f64-143">可选。</span><span class="sxs-lookup"><span data-stu-id="75f64-143">Optional.</span></span> <span data-ttu-id="75f64-144">被调用时传递给过程的参数的列表。</span><span class="sxs-lookup"><span data-stu-id="75f64-144">List of parameters that are passed to the procedure when it is called.</span></span> <span data-ttu-id="75f64-145">必须将括[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)在括号中。</span><span class="sxs-lookup"><span data-stu-id="75f64-145">You must enclose the [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md) in parentheses.</span></span>|  
|`type`|<span data-ttu-id="75f64-146">如果指定，则必需`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="75f64-146">Required if you specify a `Function` procedure.</span></span> <span data-ttu-id="75f64-147">返回值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="75f64-147">Data type of the return value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75f64-148">备注</span><span class="sxs-lookup"><span data-stu-id="75f64-148">Remarks</span></span>  
 <span data-ttu-id="75f64-149">`Delegate`语句定义委托类的参数和返回类型。</span><span class="sxs-lookup"><span data-stu-id="75f64-149">The `Delegate` statement defines the parameter and return types of a delegate class.</span></span> <span data-ttu-id="75f64-150">任何具有匹配的参数和返回类型的过程可以用于创建此委托类的实例。</span><span class="sxs-lookup"><span data-stu-id="75f64-150">Any procedure with matching parameters and return types can be used to create an instance of this delegate class.</span></span> <span data-ttu-id="75f64-151">然后就可以被调用过程通过委托实例，通过调用该委托的`Invoke`方法。</span><span class="sxs-lookup"><span data-stu-id="75f64-151">The procedure can then later be invoked by means of the delegate instance, by calling the delegate's `Invoke` method.</span></span>  
  
 <span data-ttu-id="75f64-152">可以声明委托，在命名空间、 模块、 类或结构级别，但不是能在过程。</span><span class="sxs-lookup"><span data-stu-id="75f64-152">Delegates can be declared at the namespace, module, class, or structure level, but not within a procedure.</span></span>  
  
 <span data-ttu-id="75f64-153">每个委托类均可定义将对象方法指定传递到的构造函数。</span><span class="sxs-lookup"><span data-stu-id="75f64-153">Each delegate class defines a constructor that is passed the specification of an object method.</span></span> <span data-ttu-id="75f64-154">委托构造函数的参数必须是对方法或 lambda 表达式的引用。</span><span class="sxs-lookup"><span data-stu-id="75f64-154">An argument to a delegate constructor must be a reference to a method, or a lambda expression.</span></span>  
  
 <span data-ttu-id="75f64-155">若要指定对方法的引用，请使用以下语法︰</span><span class="sxs-lookup"><span data-stu-id="75f64-155">To specify a reference to a method, use the following syntax:</span></span>  
  
 <span data-ttu-id="75f64-156">`AddressOf` [`expression`.]`methodname`</span><span class="sxs-lookup"><span data-stu-id="75f64-156">`AddressOf` [`expression`.]`methodname`</span></span>  
  
 <span data-ttu-id="75f64-157">编译时类型`expression`必须是一个类或接口包含其签名与委托类的签名匹配的指定名称的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="75f64-157">The compile-time type of the `expression` must be the name of a class or an interface that contains a method of the specified name whose signature matches the signature of the delegate class.</span></span> <span data-ttu-id="75f64-158">`methodname`可以是共享的方法或实例方法。</span><span class="sxs-lookup"><span data-stu-id="75f64-158">The `methodname` can be either a shared method or an instance method.</span></span> <span data-ttu-id="75f64-159">`methodname`不是可选的即使您创建的类的默认方法的委托。</span><span class="sxs-lookup"><span data-stu-id="75f64-159">The `methodname` is not optional, even if you create a delegate for the default method of the class.</span></span>  
  
 <span data-ttu-id="75f64-160">若要指定 lambda 表达式，请使用以下语法︰</span><span class="sxs-lookup"><span data-stu-id="75f64-160">To specify a lambda expression, use the following syntax:</span></span>  
  
 <span data-ttu-id="75f64-161">`Function`([`parm` As `type`, `parm2` As `type2`, ...])`expression`</span><span class="sxs-lookup"><span data-stu-id="75f64-161">`Function` ([`parm` As `type`, `parm2` As `type2`, ...]) `expression`</span></span>  
  
 <span data-ttu-id="75f64-162">函数的签名必须与匹配的委托类型。</span><span class="sxs-lookup"><span data-stu-id="75f64-162">The signature of the function must match that of the delegate type.</span></span> <span data-ttu-id="75f64-163">有关 lambda 表达式的详细信息，请参阅 [Lambda 表达式](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="75f64-163">For more information about lambda expressions, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="75f64-164">有关委托的详细信息，请参阅[委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)。</span><span class="sxs-lookup"><span data-stu-id="75f64-164">For more information about delegates, see [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="75f64-165">示例</span><span class="sxs-lookup"><span data-stu-id="75f64-165">Example</span></span>  
 <span data-ttu-id="75f64-166">下面的示例使用`Delegate`语句来声明一个委托，对两个数字进行运算并返回一个数字。</span><span class="sxs-lookup"><span data-stu-id="75f64-166">The following example uses the `Delegate` statement to declare a delegate for operating on two numbers and returning a number.</span></span> <span data-ttu-id="75f64-167">`DelegateTest`方法采用这种类型的委托的一个实例，并使用它来对数字进行操作。</span><span class="sxs-lookup"><span data-stu-id="75f64-167">The `DelegateTest` method takes an instance of a delegate of this type and uses it to operate on pairs of numbers.</span></span>  
  
 <span data-ttu-id="75f64-168">[!code-vb[VbVbalrDelegates #&14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegate-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="75f64-168">[!code-vb[VbVbalrDelegates#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegate-statement_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f64-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75f64-169">See Also</span></span>  
 <span data-ttu-id="75f64-170">[AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="75f64-170">[AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="75f64-171"> [Of](../../../visual-basic/language-reference/statements/of-clause.md) </span><span class="sxs-lookup"><span data-stu-id="75f64-171"> [Of](../../../visual-basic/language-reference/statements/of-clause.md) </span></span>  
<span data-ttu-id="75f64-172"> [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="75f64-172"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="75f64-173"> [如何︰ 使用泛型类](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span><span class="sxs-lookup"><span data-stu-id="75f64-173"> [How to: Use a Generic Class](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span></span>  
<span data-ttu-id="75f64-174"> [Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="75f64-174"> [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="75f64-175"> [协变和逆变](http://msdn.microsoft.com/library/a58cc086-276f-4f91-a366-85b7f95f38b8) </span><span class="sxs-lookup"><span data-stu-id="75f64-175"> [Covariance and Contravariance](http://msdn.microsoft.com/library/a58cc086-276f-4f91-a366-85b7f95f38b8) </span></span>  
<span data-ttu-id="75f64-176"> [在](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="75f64-176"> [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) </span></span>  
<span data-ttu-id="75f64-177"> [扩展](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)</span><span class="sxs-lookup"><span data-stu-id="75f64-177"> [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)</span></span>

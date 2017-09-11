---
title: "Property 过程 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Set statement, Property procedures
- Visual Basic code, procedures
- return values, Property procedures
- syntax, Property procedures
- procedures, property
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], custom
- property procedures
- Get statement, property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: 22
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
ms.openlocfilehash: 6ba662a8cf9748b719bfbd7205ce65989e79d05a
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="37e4b-102">Property 过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37e4b-102">Property Procedures (Visual Basic)</span></span>
<span data-ttu-id="37e4b-103">Property 过程是一系列[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]操作上模块、 类或结构的自定义属性的语句。</span><span class="sxs-lookup"><span data-stu-id="37e4b-103">A property procedure is a series of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="37e4b-104">属性过程也被称为*属性访问器*。</span><span class="sxs-lookup"><span data-stu-id="37e4b-104">Property procedures are also known as *property accessors*.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="37e4b-105">提供了以下属性过程︰</span><span class="sxs-lookup"><span data-stu-id="37e4b-105"> provides for the following property procedures:</span></span>  
  
-   <span data-ttu-id="37e4b-106">一个`Get`过程将返回属性的值。</span><span class="sxs-lookup"><span data-stu-id="37e4b-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="37e4b-107">访问在表达式中的属性时调用它。</span><span class="sxs-lookup"><span data-stu-id="37e4b-107">It is called when you access the property in an expression.</span></span>  
  
-   <span data-ttu-id="37e4b-108">一个`Set`过程将属性设置为某个值，包括的对象引用。</span><span class="sxs-lookup"><span data-stu-id="37e4b-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="37e4b-109">将值分配给属性时调用它。</span><span class="sxs-lookup"><span data-stu-id="37e4b-109">It is called when you assign a value to the property.</span></span>  
  
 <span data-ttu-id="37e4b-110">通常要定义属性过程中使用的对`Get`和`Set`语句中，但您可以定义单独无论哪一过程，如果该属性是只读的 ([Get 语句](../../../../visual-basic/language-reference/statements/get-statement.md)) 或只写 ([Set 语句](../../../../visual-basic/language-reference/statements/set-statement.md))。</span><span class="sxs-lookup"><span data-stu-id="37e4b-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>  
  
 <span data-ttu-id="37e4b-111">可以省略`Get`和`Set`过程时使用自动实现的属性。</span><span class="sxs-lookup"><span data-stu-id="37e4b-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="37e4b-112">有关详细信息，请参阅[类属性](./auto-implemented-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="37e4b-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="37e4b-113">可以在类、 结构和模块中定义属性。</span><span class="sxs-lookup"><span data-stu-id="37e4b-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="37e4b-114">属性是`Public`默认情况下，这意味着可以从任何位置进行调用的应用程序可以访问该属性的容器中。</span><span class="sxs-lookup"><span data-stu-id="37e4b-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>  
  
 <span data-ttu-id="37e4b-115">属性和变量的比较，请参阅[属性之间的差异和 Visual Basic 中的变量](./differences-between-properties-and-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="37e4b-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md).</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="37e4b-116">声明语法</span><span class="sxs-lookup"><span data-stu-id="37e4b-116">Declaration Syntax</span></span>  
 <span data-ttu-id="37e4b-117">由内包含的代码块中定义的属性本身[属性语句](../../../../visual-basic/language-reference/statements/property-statement.md)和`End Property`语句。</span><span class="sxs-lookup"><span data-stu-id="37e4b-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="37e4b-118">在此块中，内部形式出现作为内部块括在声明语句内的每个 property 过程 (`Get`或`Set`) 和匹配`End`声明。</span><span class="sxs-lookup"><span data-stu-id="37e4b-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>  
  
 <span data-ttu-id="37e4b-119">声明的属性和它的过程的语法如下所示︰</span><span class="sxs-lookup"><span data-stu-id="37e4b-119">The syntax for declaring a property and its procedures is as follows:</span></span>  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 <span data-ttu-id="37e4b-120">`Modifiers`可以指定访问级别以及与重载、 重写、 共享、 隐藏的比较，相关的信息以及该属性是只读的还是只写。</span><span class="sxs-lookup"><span data-stu-id="37e4b-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="37e4b-121">`AccessLevel`上`Get`或`Set`过程可以是任何级别的限制性强于属性自身为指定的访问级别。</span><span class="sxs-lookup"><span data-stu-id="37e4b-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="37e4b-122">有关详细信息，请参阅[属性语句](../../../../visual-basic/language-reference/statements/property-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="37e4b-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="37e4b-123">数据类型</span><span class="sxs-lookup"><span data-stu-id="37e4b-123">Data Type</span></span>  
 <span data-ttu-id="37e4b-124">在中定义属性的数据类型和主体的访问级别`Property`语句不在的属性过程。</span><span class="sxs-lookup"><span data-stu-id="37e4b-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="37e4b-125">属性可以具有一种数据类型。</span><span class="sxs-lookup"><span data-stu-id="37e4b-125">A property can have only one data type.</span></span> <span data-ttu-id="37e4b-126">例如，不能定义属性存储`Decimal`值而检索`Double`值。</span><span class="sxs-lookup"><span data-stu-id="37e4b-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>  
  
### <a name="access-level"></a><span data-ttu-id="37e4b-127">访问级别</span><span class="sxs-lookup"><span data-stu-id="37e4b-127">Access Level</span></span>  
 <span data-ttu-id="37e4b-128">但是，您可以定义主要访问级别的属性和一个它的属性过程中的访问级别来进一步限制。</span><span class="sxs-lookup"><span data-stu-id="37e4b-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="37e4b-129">例如，您可以定义`Public`属性，然后定义`Private Set`过程。</span><span class="sxs-lookup"><span data-stu-id="37e4b-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="37e4b-130">`Get`过程保持`Public`。</span><span class="sxs-lookup"><span data-stu-id="37e4b-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="37e4b-131">可以更改属性的过程之一中的访问级别，您可以只是使其限制性强于主体的访问级别。</span><span class="sxs-lookup"><span data-stu-id="37e4b-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="37e4b-132">有关详细信息，请参阅[如何︰ 声明具有混合访问级别的属性](./how-to-declare-a-property-with-mixed-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="37e4b-132">For more information, see [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="37e4b-133">参数声明</span><span class="sxs-lookup"><span data-stu-id="37e4b-133">Parameter Declaration</span></span>  
 <span data-ttu-id="37e4b-134">声明每个参数相同的方式相似， [Sub 过程](./sub-procedures.md)，只不过必须传递机制`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="37e4b-134">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>  
  
 <span data-ttu-id="37e4b-135">参数列表中每个参数的语法是，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="37e4b-135">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 <span data-ttu-id="37e4b-136">如果该参数是可选的您还必须提供默认值作为其声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="37e4b-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="37e4b-137">用于指定默认值的语法如下所示︰</span><span class="sxs-lookup"><span data-stu-id="37e4b-137">The syntax for specifying a default value is as follows:</span></span>  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a><span data-ttu-id="37e4b-138">属性值</span><span class="sxs-lookup"><span data-stu-id="37e4b-138">Property Value</span></span>  
 <span data-ttu-id="37e4b-139">在`Get`的过程中，则返回值提供给调用表达式的值的属性。</span><span class="sxs-lookup"><span data-stu-id="37e4b-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>  
  
 <span data-ttu-id="37e4b-140">在`Set`的过程中，新的属性值传递给参数`Set`语句。</span><span class="sxs-lookup"><span data-stu-id="37e4b-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="37e4b-141">如果显式声明一个参数，您必须使用相同的数据类型作为属性声明它。</span><span class="sxs-lookup"><span data-stu-id="37e4b-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="37e4b-142">如果不声明一个参数，编译器将使用隐式参数`Value`来表示要分配给属性的新值。</span><span class="sxs-lookup"><span data-stu-id="37e4b-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="37e4b-143">调用语法</span><span class="sxs-lookup"><span data-stu-id="37e4b-143">Calling Syntax</span></span>  
 <span data-ttu-id="37e4b-144">通过使对该属性引用的隐式调用 property 过程。</span><span class="sxs-lookup"><span data-stu-id="37e4b-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="37e4b-145">您的属性名称相同的方式使用您将使用变量的名称，只不过你必须为不是可选的所有参数提供值，则必须将参数列表括在括号中。</span><span class="sxs-lookup"><span data-stu-id="37e4b-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="37e4b-146">如果未不提供任何参数，可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="37e4b-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="37e4b-147">隐式调用的语法`Set`过程是，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="37e4b-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>  
  
 `propertyname[(argumentlist)] = expression`  
  
 <span data-ttu-id="37e4b-148">隐式调用的语法`Get`过程是，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="37e4b-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="37e4b-149">声明和调用的插图</span><span class="sxs-lookup"><span data-stu-id="37e4b-149">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="37e4b-150">以下属性将存储为两个构成的名称、 名字和姓氏的完整名称。</span><span class="sxs-lookup"><span data-stu-id="37e4b-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="37e4b-151">当调用的代码中读取`fullName`、`Get`过程将组合构成的两个名称，并返回的完整名称。</span><span class="sxs-lookup"><span data-stu-id="37e4b-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="37e4b-152">当调用代码将分配一个新的完整名称，`Set`过程尝试将其分解为两个构成的名称。</span><span class="sxs-lookup"><span data-stu-id="37e4b-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="37e4b-153">如果找不到一个空间，它可以将其存储所有作为第一个名称。</span><span class="sxs-lookup"><span data-stu-id="37e4b-153">If it does not find a space, it stores it all as the first name.</span></span>  
  
 <span data-ttu-id="37e4b-154">[!code-vb[VbVbcnProcedures #&8;](./codesnippet/VisualBasic/property-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="37e4b-154">[!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/property-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="37e4b-155">下面的示例显示的属性过程的典型调用`fullName`。</span><span class="sxs-lookup"><span data-stu-id="37e4b-155">The following example shows typical calls to the property procedures of `fullName`.</span></span>  
  
 <span data-ttu-id="37e4b-156">[!code-vb[VbVbcnProcedures #&9;](./codesnippet/VisualBasic/property-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="37e4b-156">[!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/property-procedures_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37e4b-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37e4b-157">See Also</span></span>  
 <span data-ttu-id="37e4b-158">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="37e4b-158">[Procedures](./index.md) </span></span>  
<span data-ttu-id="37e4b-159"> [Function 过程](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="37e4b-159"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="37e4b-160"> [运算符过程](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="37e4b-160"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="37e4b-161"> [过程参数和变量](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="37e4b-161"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="37e4b-162"> [在 Visual Basic 中属性和变量之间的差异](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="37e4b-162"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="37e4b-163"> [如何︰ 创建属性](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="37e4b-163"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="37e4b-164"> [如何︰ 调用 Property 过程](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="37e4b-164"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="37e4b-165"> [如何︰ 声明和调用默认属性在 Visual Basic 中](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="37e4b-165"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="37e4b-166"> [如何︰ 在属性中放置值](./how-to-put-a-value-in-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="37e4b-166"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md) </span></span>  
<span data-ttu-id="37e4b-167"> [如何：从属性获取值](./how-to-get-a-value-from-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="37e4b-167"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md)</span></span>

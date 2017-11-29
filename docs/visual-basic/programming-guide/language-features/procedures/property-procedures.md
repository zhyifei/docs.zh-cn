---
title: "Property 过程 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cbdf49d5c3eb5ef71b25a060d62f55f19098f445
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="4c831-102">Property 过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c831-102">Property Procedures (Visual Basic)</span></span>
<span data-ttu-id="4c831-103">属性过程是一系列[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]操作模块、 类或结构上的自定义属性的语句。</span><span class="sxs-lookup"><span data-stu-id="4c831-103">A property procedure is a series of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="4c831-104">属性过程也称为是*属性访问器*。</span><span class="sxs-lookup"><span data-stu-id="4c831-104">Property procedures are also known as *property accessors*.</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="4c831-105">提供有关以下属性过程：</span><span class="sxs-lookup"><span data-stu-id="4c831-105"> provides for the following property procedures:</span></span>  
  
-   <span data-ttu-id="4c831-106">A`Get`过程返回属性的值。</span><span class="sxs-lookup"><span data-stu-id="4c831-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="4c831-107">就是当访问表达式中的属性。</span><span class="sxs-lookup"><span data-stu-id="4c831-107">It is called when you access the property in an expression.</span></span>  
  
-   <span data-ttu-id="4c831-108">A`Set`过程将属性设置为某个值，包括一个对象引用。</span><span class="sxs-lookup"><span data-stu-id="4c831-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="4c831-109">就是将值分配给属性。</span><span class="sxs-lookup"><span data-stu-id="4c831-109">It is called when you assign a value to the property.</span></span>  
  
 <span data-ttu-id="4c831-110">你通常定义属性过程中使用的对`Get`和`Set`语句，但如果属性是只读的可以定义单独任一过程 ([Get 语句](../../../../visual-basic/language-reference/statements/get-statement.md)) 或只写 ([设置语句](../../../../visual-basic/language-reference/statements/set-statement.md))。</span><span class="sxs-lookup"><span data-stu-id="4c831-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>  
  
 <span data-ttu-id="4c831-111">可以省略`Get`和`Set`过程时使用一个自动实现的属性。</span><span class="sxs-lookup"><span data-stu-id="4c831-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="4c831-112">有关详细信息，请参阅[自动实现的属性](./auto-implemented-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="4c831-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="4c831-113">你可以在类、 结构和模块定义属性。</span><span class="sxs-lookup"><span data-stu-id="4c831-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="4c831-114">属性是`Public`默认情况下，这意味着可以从任意位置进行调用的应用程序可以访问该属性的容器中。</span><span class="sxs-lookup"><span data-stu-id="4c831-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>  
  
 <span data-ttu-id="4c831-115">有关属性和变量的比较，请参阅[属性之间的差异和 Visual Basic 中的变量](./differences-between-properties-and-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="4c831-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md).</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="4c831-116">声明语法</span><span class="sxs-lookup"><span data-stu-id="4c831-116">Declaration Syntax</span></span>  
 <span data-ttu-id="4c831-117">属性本身被定义内包含的代码块[属性语句](../../../../visual-basic/language-reference/statements/property-statement.md)和`End Property`语句。</span><span class="sxs-lookup"><span data-stu-id="4c831-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="4c831-118">在此块中，每个属性过程将显示为包含在声明语句的内部块 (`Get`或`Set`) 和匹配`End`声明。</span><span class="sxs-lookup"><span data-stu-id="4c831-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>  
  
 <span data-ttu-id="4c831-119">声明属性和其过程的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c831-119">The syntax for declaring a property and its procedures is as follows:</span></span>  
  
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
  
 <span data-ttu-id="4c831-120">`Modifiers`可以指定访问级别和与重载，重写、 共享和隐藏，相关的信息以及属性是否为只读或只写。</span><span class="sxs-lookup"><span data-stu-id="4c831-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="4c831-121">`AccessLevel`上`Get`或`Set`过程可以是任何级别，比属性本身为指定的访问级别限制性更强。</span><span class="sxs-lookup"><span data-stu-id="4c831-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="4c831-122">有关详细信息，请参阅[属性语句](../../../../visual-basic/language-reference/statements/property-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="4c831-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="4c831-123">数据类型</span><span class="sxs-lookup"><span data-stu-id="4c831-123">Data Type</span></span>  
 <span data-ttu-id="4c831-124">在中定义属性的数据类型和主体的访问级别`Property`语句，不在属性过程。</span><span class="sxs-lookup"><span data-stu-id="4c831-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="4c831-125">属性可以具有只有一个数据类型。</span><span class="sxs-lookup"><span data-stu-id="4c831-125">A property can have only one data type.</span></span> <span data-ttu-id="4c831-126">例如，不能定义属性来存储`Decimal`值而检索`Double`值。</span><span class="sxs-lookup"><span data-stu-id="4c831-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>  
  
### <a name="access-level"></a><span data-ttu-id="4c831-127">访问级别</span><span class="sxs-lookup"><span data-stu-id="4c831-127">Access Level</span></span>  
 <span data-ttu-id="4c831-128">但是，你可以定义一个属性的主体的访问级别，并进一步限制中其一个属性过程的访问级别。</span><span class="sxs-lookup"><span data-stu-id="4c831-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="4c831-129">例如，你可以定义`Public`属性，然后定义`Private Set`过程。</span><span class="sxs-lookup"><span data-stu-id="4c831-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="4c831-130">`Get`过程保持`Public`。</span><span class="sxs-lookup"><span data-stu-id="4c831-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="4c831-131">可以更改属性的过程之一的访问级别，你可以只是使其比主体的访问级别限制性更强。</span><span class="sxs-lookup"><span data-stu-id="4c831-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="4c831-132">有关详细信息，请参阅[如何： 声明具有混合访问级别的属性](./how-to-declare-a-property-with-mixed-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="4c831-132">For more information, see [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="4c831-133">参数声明</span><span class="sxs-lookup"><span data-stu-id="4c831-133">Parameter Declaration</span></span>  
 <span data-ttu-id="4c831-134">声明每个参数使用的相同方式为[Sub 过程](./sub-procedures.md)，只不过的传递机制必须`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="4c831-134">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>  
  
 <span data-ttu-id="4c831-135">在参数列表中每个参数的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c831-135">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 <span data-ttu-id="4c831-136">如果参数是可选的你还必须提供默认值作为其声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="4c831-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="4c831-137">用于指定默认值的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c831-137">The syntax for specifying a default value is as follows:</span></span>  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a><span data-ttu-id="4c831-138">属性值</span><span class="sxs-lookup"><span data-stu-id="4c831-138">Property Value</span></span>  
 <span data-ttu-id="4c831-139">在`Get`过程，返回值提供给调用表达式作为值的属性。</span><span class="sxs-lookup"><span data-stu-id="4c831-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>  
  
 <span data-ttu-id="4c831-140">在`Set`过程中，新的属性值传递的参数给`Set`语句。</span><span class="sxs-lookup"><span data-stu-id="4c831-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="4c831-141">如果你将参数显式声明，必须将其声明与为属性相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="4c831-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="4c831-142">如果你未声明的参数，编译器将使用隐式参数`Value`来表示要分配给属性的新值。</span><span class="sxs-lookup"><span data-stu-id="4c831-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="4c831-143">调用语法</span><span class="sxs-lookup"><span data-stu-id="4c831-143">Calling Syntax</span></span>  
 <span data-ttu-id="4c831-144">通过使对该属性引用的隐式调用属性过程。</span><span class="sxs-lookup"><span data-stu-id="4c831-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="4c831-145">你使用的属性名称为相同的方式将使用的变量的名称，只不过你必须为不是可选的所有自变量提供值，必须将自变量列表括在括号中。</span><span class="sxs-lookup"><span data-stu-id="4c831-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="4c831-146">如果未不提供任何参数，你可以选择省略括号。</span><span class="sxs-lookup"><span data-stu-id="4c831-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="4c831-147">隐式调用的语法`Set`过程是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c831-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>  
  
 `propertyname[(argumentlist)] = expression`  
  
 <span data-ttu-id="4c831-148">隐式调用的语法`Get`过程是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c831-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="4c831-149">声明和调用图</span><span class="sxs-lookup"><span data-stu-id="4c831-149">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="4c831-150">以下属性将存储为两个构成的名称、 名字和姓氏的完整名称。</span><span class="sxs-lookup"><span data-stu-id="4c831-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="4c831-151">当调用的代码读取`fullName`、`Get`过程合并两个构成的名称，并返回的完整名称。</span><span class="sxs-lookup"><span data-stu-id="4c831-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="4c831-152">当调用的代码将分配新的完整名称，`Set`过程尝试将其分解为两个构成的名称。</span><span class="sxs-lookup"><span data-stu-id="4c831-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="4c831-153">如果找不到空间，它可以将其存储所有项作为第一个名称。</span><span class="sxs-lookup"><span data-stu-id="4c831-153">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 <span data-ttu-id="4c831-154">下面的示例演示对属性过程的典型调用`fullName`。</span><span class="sxs-lookup"><span data-stu-id="4c831-154">The following example shows typical calls to the property procedures of `fullName`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4c831-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c831-155">See Also</span></span>  
 [<span data-ttu-id="4c831-156">过程</span><span class="sxs-lookup"><span data-stu-id="4c831-156">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="4c831-157">Function 过程</span><span class="sxs-lookup"><span data-stu-id="4c831-157">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="4c831-158">运算符过程</span><span class="sxs-lookup"><span data-stu-id="4c831-158">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="4c831-159">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="4c831-159">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="4c831-160">在 Visual Basic 中属性和变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="4c831-160">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="4c831-161">如何：创建属性</span><span class="sxs-lookup"><span data-stu-id="4c831-161">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="4c831-162">如何：调用 Property 过程</span><span class="sxs-lookup"><span data-stu-id="4c831-162">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="4c831-163">如何： 声明和 Visual Basic 中调用默认属性</span><span class="sxs-lookup"><span data-stu-id="4c831-163">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="4c831-164">如何：在属性中放置值</span><span class="sxs-lookup"><span data-stu-id="4c831-164">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="4c831-165">如何：从属性获取值</span><span class="sxs-lookup"><span data-stu-id="4c831-165">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)

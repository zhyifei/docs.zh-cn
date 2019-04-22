---
title: Property 过程 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 47e93ee17f160ce5cd701fd0a12ec16b3997ce9b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828338"
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="90dd9-102">Property 过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90dd9-102">Property Procedures (Visual Basic)</span></span>
<span data-ttu-id="90dd9-103">属性过程是一系列操作模块、 类或结构上的自定义属性的 Visual Basic 语句。</span><span class="sxs-lookup"><span data-stu-id="90dd9-103">A property procedure is a series of Visual Basic statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="90dd9-104">属性过程也被称为*属性访问器*。</span><span class="sxs-lookup"><span data-stu-id="90dd9-104">Property procedures are also known as *property accessors*.</span></span>  
  
 <span data-ttu-id="90dd9-105">Visual Basic 提供的以下属性过程：</span><span class="sxs-lookup"><span data-stu-id="90dd9-105">Visual Basic provides for the following property procedures:</span></span>  
  
-   <span data-ttu-id="90dd9-106">一个`Get`过程将返回属性的值。</span><span class="sxs-lookup"><span data-stu-id="90dd9-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="90dd9-107">访问表达式中的属性时调用它。</span><span class="sxs-lookup"><span data-stu-id="90dd9-107">It is called when you access the property in an expression.</span></span>  
  
-   <span data-ttu-id="90dd9-108">一个`Set`过程将属性设置为某个值，包括的对象引用。</span><span class="sxs-lookup"><span data-stu-id="90dd9-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="90dd9-109">调用时将值分配给属性。</span><span class="sxs-lookup"><span data-stu-id="90dd9-109">It is called when you assign a value to the property.</span></span>  
  
 <span data-ttu-id="90dd9-110">通常使用的对中定义属性过程`Get`并`Set`语句，但你可以定义单独任一过程，如果该属性是只读的 ([Get 语句](../../../../visual-basic/language-reference/statements/get-statement.md)) 或只写 ([设置语句](../../../../visual-basic/language-reference/statements/set-statement.md))。</span><span class="sxs-lookup"><span data-stu-id="90dd9-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>  
  
 <span data-ttu-id="90dd9-111">可以省略`Get`和`Set`过程时使用自动实现的属性。</span><span class="sxs-lookup"><span data-stu-id="90dd9-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="90dd9-112">有关详细信息，请参阅[自动实现的属性](./auto-implemented-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="90dd9-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="90dd9-113">您可以在类、 结构和模块中定义属性。</span><span class="sxs-lookup"><span data-stu-id="90dd9-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="90dd9-114">属性是`Public`默认情况下，这意味着可以从任何位置调用它们的应用程序可以访问该属性的容器中。</span><span class="sxs-lookup"><span data-stu-id="90dd9-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>  
  
 <span data-ttu-id="90dd9-115">属性和变量的比较，请参阅[属性之间的差异和 Visual Basic 中的变量](./differences-between-properties-and-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="90dd9-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md).</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="90dd9-116">声明语法</span><span class="sxs-lookup"><span data-stu-id="90dd9-116">Declaration Syntax</span></span>  
 <span data-ttu-id="90dd9-117">属性本身定义内包含的代码块[Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)和`End Property`语句。</span><span class="sxs-lookup"><span data-stu-id="90dd9-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="90dd9-118">在此块中，每个属性过程显示为包含在声明语句内的内部块 (`Get`或`Set`) 和匹配`End`声明。</span><span class="sxs-lookup"><span data-stu-id="90dd9-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>  
  
 <span data-ttu-id="90dd9-119">声明的属性，并且其过程的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="90dd9-119">The syntax for declaring a property and its procedures is as follows:</span></span>  
  
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
  
 <span data-ttu-id="90dd9-120">`Modifiers`可以指定访问级别和重载、 重写、 共享和隐藏，有关的信息以及该属性是只读或只写。</span><span class="sxs-lookup"><span data-stu-id="90dd9-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="90dd9-121">`AccessLevel`上`Get`或`Set`过程可以为任何级别比属性本身为指定的访问级别限制性更强。</span><span class="sxs-lookup"><span data-stu-id="90dd9-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="90dd9-122">有关详细信息，请参阅[Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="90dd9-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="90dd9-123">数据类型</span><span class="sxs-lookup"><span data-stu-id="90dd9-123">Data Type</span></span>  
 <span data-ttu-id="90dd9-124">在定义属性的数据类型和主体的访问级别`Property`语句不在属性过程。</span><span class="sxs-lookup"><span data-stu-id="90dd9-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="90dd9-125">属性可以具有一种数据类型。</span><span class="sxs-lookup"><span data-stu-id="90dd9-125">A property can have only one data type.</span></span> <span data-ttu-id="90dd9-126">例如，不能定义属性来存储`Decimal`值，但检索`Double`值。</span><span class="sxs-lookup"><span data-stu-id="90dd9-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>  
  
### <a name="access-level"></a><span data-ttu-id="90dd9-127">访问级别</span><span class="sxs-lookup"><span data-stu-id="90dd9-127">Access Level</span></span>  
 <span data-ttu-id="90dd9-128">但是，可以定义一个属性的主体访问权限级别，并进一步限制所列属性的过程之一中的访问级别。</span><span class="sxs-lookup"><span data-stu-id="90dd9-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="90dd9-129">例如，可以定义`Public`属性，然后定义`Private Set`过程。</span><span class="sxs-lookup"><span data-stu-id="90dd9-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="90dd9-130">`Get`过程保持`Public`。</span><span class="sxs-lookup"><span data-stu-id="90dd9-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="90dd9-131">可以更改属性的过程之一中的访问级别，您可以只是使其比主体的访问级别限制性更强。</span><span class="sxs-lookup"><span data-stu-id="90dd9-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="90dd9-132">有关详细信息，请参阅[如何：声明具有混合的访问级别的属性](./how-to-declare-a-property-with-mixed-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="90dd9-132">For more information, see [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="90dd9-133">参数声明</span><span class="sxs-lookup"><span data-stu-id="90dd9-133">Parameter Declaration</span></span>  
 <span data-ttu-id="90dd9-134">将每个参数声明为执行操作的相同方式[Sub 过程](./sub-procedures.md)，但必须是传递机制`ByVal`。</span><span class="sxs-lookup"><span data-stu-id="90dd9-134">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>  
  
 <span data-ttu-id="90dd9-135">在参数列表中每个参数的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="90dd9-135">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 <span data-ttu-id="90dd9-136">如果参数是可选的您还必须提供一个默认值作为其声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="90dd9-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="90dd9-137">用于指定默认值的语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="90dd9-137">The syntax for specifying a default value is as follows:</span></span>  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a><span data-ttu-id="90dd9-138">属性值</span><span class="sxs-lookup"><span data-stu-id="90dd9-138">Property Value</span></span>  
 <span data-ttu-id="90dd9-139">在`Get`过程中，返回值提供给该属性的值调用的表达式。</span><span class="sxs-lookup"><span data-stu-id="90dd9-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>  
  
 <span data-ttu-id="90dd9-140">在中`Set`过程中，新的属性值传递到参数`Set`语句。</span><span class="sxs-lookup"><span data-stu-id="90dd9-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="90dd9-141">如果显式声明的参数，必须将其声明具有相同的数据类型的属性。</span><span class="sxs-lookup"><span data-stu-id="90dd9-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="90dd9-142">如果未声明的参数，编译器将使用隐式参数`Value`来表示要分配给属性的新值。</span><span class="sxs-lookup"><span data-stu-id="90dd9-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="90dd9-143">调用语法</span><span class="sxs-lookup"><span data-stu-id="90dd9-143">Calling Syntax</span></span>  
 <span data-ttu-id="90dd9-144">通过使对该属性引用的隐式调用属性过程。</span><span class="sxs-lookup"><span data-stu-id="90dd9-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="90dd9-145">您使用的属性名称为将使用变量的名称的方法相同，只不过必须为不是可选的所有参数提供值，必须将参数列表括在括号中。</span><span class="sxs-lookup"><span data-stu-id="90dd9-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="90dd9-146">如果未不提供任何参数，可以选择性地省略括号。</span><span class="sxs-lookup"><span data-stu-id="90dd9-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="90dd9-147">隐式调用的语法`Set`过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="90dd9-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>  
  
 `propertyname[(argumentlist)] = expression`  
  
 <span data-ttu-id="90dd9-148">隐式调用的语法`Get`过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="90dd9-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="90dd9-149">声明和调用的插图</span><span class="sxs-lookup"><span data-stu-id="90dd9-149">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="90dd9-150">以下属性将存储为两个构成的名称、 名字和姓氏的完整名称。</span><span class="sxs-lookup"><span data-stu-id="90dd9-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="90dd9-151">当调用代码中读取`fullName`，则`Get`过程组合姓名的两个组成部分，并返回的完整名称。</span><span class="sxs-lookup"><span data-stu-id="90dd9-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="90dd9-152">当调用代码将分配新的完整名称，`Set`过程尝试将其分为两个构成的名称。</span><span class="sxs-lookup"><span data-stu-id="90dd9-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="90dd9-153">如果找不到空间，它将其存储所有为第一个名称。</span><span class="sxs-lookup"><span data-stu-id="90dd9-153">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 <span data-ttu-id="90dd9-154">下面的示例演示的属性过程的典型调用`fullName`。</span><span class="sxs-lookup"><span data-stu-id="90dd9-154">The following example shows typical calls to the property procedures of `fullName`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="90dd9-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="90dd9-155">See also</span></span>

- [<span data-ttu-id="90dd9-156">过程</span><span class="sxs-lookup"><span data-stu-id="90dd9-156">Procedures</span></span>](./index.md)
- [<span data-ttu-id="90dd9-157">Function 过程</span><span class="sxs-lookup"><span data-stu-id="90dd9-157">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="90dd9-158">运算符过程</span><span class="sxs-lookup"><span data-stu-id="90dd9-158">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="90dd9-159">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="90dd9-159">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="90dd9-160">在 Visual Basic 中属性和变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="90dd9-160">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="90dd9-161">如何：创建属性</span><span class="sxs-lookup"><span data-stu-id="90dd9-161">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="90dd9-162">如何：调用 Property 过程</span><span class="sxs-lookup"><span data-stu-id="90dd9-162">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="90dd9-163">如何：声明并在 Visual Basic 中调用默认属性</span><span class="sxs-lookup"><span data-stu-id="90dd9-163">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="90dd9-164">如何：在属性中放置值</span><span class="sxs-lookup"><span data-stu-id="90dd9-164">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="90dd9-165">如何：从属性获取一个值</span><span class="sxs-lookup"><span data-stu-id="90dd9-165">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)

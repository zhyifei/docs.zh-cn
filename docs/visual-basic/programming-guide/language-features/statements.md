---
title: 语句 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- colons (:) [Visual Basic]
- constants [Visual Basic], defining
- underlines
- constants [Visual Basic], statements
- blue underline [Visual Basic]
- procedures [Visual Basic], statements
- variables [Visual Basic], assigning
- line breaks [Visual Basic], in code
- executable statements [Visual Basic]
- variables [Visual Basic], defining
- statements [Visual Basic], about statements
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
ms.openlocfilehash: e66acae5e98d561883f4ad59853dfd862c8ebfee
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43462391"
---
# <a name="statements-in-visual-basic"></a><span data-ttu-id="3cc5d-102">语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cc5d-102">Statements in Visual Basic</span></span>

<span data-ttu-id="3cc5d-103">在 Visual Basic 中的语句是完整的指令。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-103">A statement in Visual Basic is a complete instruction.</span></span> <span data-ttu-id="3cc5d-104">它可以包含关键字、 运算符、 变量、 常量和表达式。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-104">It can contain keywords, operators, variables, constants, and expressions.</span></span> <span data-ttu-id="3cc5d-105">每个语句都属于以下类别之一：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-105">Each statement belongs to one of the following categories:</span></span>

- <span data-ttu-id="3cc5d-106">**声明语句**，其中命名变量、 常量或过程中，并还可以指定数据类型。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-106">**Declaration Statements**, which name a variable, constant, or procedure, and can also specify a data type.</span></span>

- <span data-ttu-id="3cc5d-107">**可执行语句**，它启动操作。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-107">**Executable Statements**, which initiate actions.</span></span> <span data-ttu-id="3cc5d-108">这些语句可以调用的方法或函数，并且它们可以循环或分支的代码块。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-108">These statements can call a method or function, and they can loop or branch through blocks of code.</span></span> <span data-ttu-id="3cc5d-109">可执行语句包括**赋值语句**，其中将一个值或表达式分配给变量或常量。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-109">Executable statements include **Assignment Statements**, which assign a value or expression to a variable or constant.</span></span>

<span data-ttu-id="3cc5d-110">本主题介绍每个类别。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-110">This topic describes each category.</span></span> <span data-ttu-id="3cc5d-111">此外，本主题介绍如何组合在单个行上的多个语句以及如何通过多个线路 continue 语句。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-111">Also, this topic describes how to combine multiple statements on a single line and how to continue a statement over multiple lines.</span></span>

## <a name="declaration-statements"></a><span data-ttu-id="3cc5d-112">声明语句</span><span class="sxs-lookup"><span data-stu-id="3cc5d-112">Declaration statements</span></span>

<span data-ttu-id="3cc5d-113">使用声明语句进行命名和定义过程、 变量、 属性、 数组和常量。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-113">You use declaration statements to name and define procedures, variables, properties, arrays, and constants.</span></span> <span data-ttu-id="3cc5d-114">声明编程元素时，您还可以定义其数据类型、 访问级别和作用域。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-114">When you declare a programming element, you can also define its data type, access level, and scope.</span></span> <span data-ttu-id="3cc5d-115">有关详细信息，请参阅[声明元素的特性](./declared-elements/declared-element-characteristics.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-115">For more information, see [Declared Element Characteristics](./declared-elements/declared-element-characteristics.md).</span></span>

<span data-ttu-id="3cc5d-116">下面的示例包含三个声明。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-116">The following example contains three declarations.</span></span>

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

<span data-ttu-id="3cc5d-117">第一个声明是`Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-117">The first declaration is the `Sub` statement.</span></span> <span data-ttu-id="3cc5d-118">以及其匹配`End Sub`语句，它声明一个名为过程`applyFormat`。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-118">Together with its matching `End Sub` statement, it declares a procedure named `applyFormat`.</span></span> <span data-ttu-id="3cc5d-119">它还指定`applyFormat`是`Public`，这意味着可以引用它的任何代码可以调用它。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-119">It also specifies that `applyFormat` is `Public`, which means that any code that can refer to it can call it.</span></span>

<span data-ttu-id="3cc5d-120">第二个声明`Const`语句，用于声明常量`limit`，并指定`Integer`数据类型和 33 的值。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-120">The second declaration is the `Const` statement, which declares the constant `limit`, specifying the `Integer` data type and a value of 33.</span></span>

<span data-ttu-id="3cc5d-121">第三个声明是`Dim`语句，用于声明变量`thisWidget`。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-121">The third declaration is the `Dim` statement, which declares the variable `thisWidget`.</span></span> <span data-ttu-id="3cc5d-122">数据类型是特定对象，即从创建对象`Widget`类。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-122">The data type is a specific object, namely an object created from the `Widget` class.</span></span> <span data-ttu-id="3cc5d-123">您可以声明为具有任何基本数据类型，或在您使用的应用程序中公开的任何对象类型的变量。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-123">You can declare a variable to be of any elementary data type or of any object type that is exposed in the application you are using.</span></span>

### <a name="initial-values"></a><span data-ttu-id="3cc5d-124">初始值</span><span class="sxs-lookup"><span data-stu-id="3cc5d-124">Initial Values</span></span>

<span data-ttu-id="3cc5d-125">包含声明语句的代码运行时，Visual Basic 会保留已声明元素所需的内存。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-125">When the code containing a declaration statement runs, Visual Basic reserves the memory required for the declared element.</span></span> <span data-ttu-id="3cc5d-126">如果该元素具有一个值，则 Visual Basic 会将它初始化为其数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-126">If the element holds a value, Visual Basic initializes it to the default value for its data type.</span></span> <span data-ttu-id="3cc5d-127">详细信息，请参阅"行为"中[Dim 语句](../../language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-127">For more information, see "Behavior" in [Dim Statement](../../language-reference/statements/dim-statement.md).</span></span>

<span data-ttu-id="3cc5d-128">如以下示例所示，您可以将初始值分配给一个变量，作为其声明的一部分。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-128">You can assign an initial value to a variable as part of its declaration, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

<span data-ttu-id="3cc5d-129">如果变量是对象变量，可以显式创建它的类的实例时通过使用声明[New 运算符](../../../visual-basic/language-reference/operators/new-operator.md)关键字，如下面的示例说明了。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-129">If a variable is an object variable, you can explicitly create an instance of its class when you declare it by using the [New Operator](../../../visual-basic/language-reference/operators/new-operator.md) keyword, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

<span data-ttu-id="3cc5d-130">请注意直到执行到达的声明语句，在声明语句中指定的初始值未分配给一个变量。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-130">Note that the initial value you specify in a declaration statement is not assigned to a variable until execution reaches its declaration statement.</span></span> <span data-ttu-id="3cc5d-131">在此之前，该变量包含其数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-131">Until that time, the variable contains the default value for its data type.</span></span>

## <a name="executable-statements"></a><span data-ttu-id="3cc5d-132">可执行语句</span><span class="sxs-lookup"><span data-stu-id="3cc5d-132">Executable statements</span></span>

<span data-ttu-id="3cc5d-133">一个可执行语句执行的操作。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-133">An executable statement performs an action.</span></span> <span data-ttu-id="3cc5d-134">它可以调用的过程，在代码中，只需遍历多个语句的另一个位置的分支或计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-134">It can call a procedure, branch to another place in the code, loop through several statements, or evaluate an expression.</span></span> <span data-ttu-id="3cc5d-135">赋值语句是一种特殊情况的一个可执行语句。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-135">An assignment statement is a special case of an executable statement.</span></span>

<span data-ttu-id="3cc5d-136">下面的示例使用`If...Then...Else`控制结构来运行不同的变量的值所基于的代码块。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-136">The following example uses an `If...Then...Else` control structure to run different blocks of code based on the value of a variable.</span></span> <span data-ttu-id="3cc5d-137">在每个代码块中，`For...Next`循环运行指定的次数。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-137">Within each block of code, a `For...Next` loop runs a specified number of times.</span></span>

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

<span data-ttu-id="3cc5d-138">`If`前面的示例中的语句将检查参数的值`clockwise`。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-138">The `If` statement in the preceding example checks the value of the parameter `clockwise`.</span></span> <span data-ttu-id="3cc5d-139">如果值为`True`，它将调用`spinClockwise`方法的`aWidget`。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-139">If the value is `True`, it calls the `spinClockwise` method of `aWidget`.</span></span> <span data-ttu-id="3cc5d-140">如果值为`False`，它将调用`spinCounterClockwise`方法的`aWidget`。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-140">If the value is `False`, it calls the `spinCounterClockwise` method of `aWidget`.</span></span> <span data-ttu-id="3cc5d-141">`If...Then...Else`控制结构结尾`End If`。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-141">The `If...Then...Else` control structure ends with `End If`.</span></span>

<span data-ttu-id="3cc5d-142">`For...Next`循环中每个块调用适当的方法数乘以的值相等`revolutions`参数。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-142">The `For...Next` loop within each block calls the appropriate method a number of times equal to the value of the `revolutions` parameter.</span></span>

## <a name="assignment-statements"></a><span data-ttu-id="3cc5d-143">赋值语句</span><span class="sxs-lookup"><span data-stu-id="3cc5d-143">Assignment statements</span></span>

<span data-ttu-id="3cc5d-144">赋值语句执行分配操作，包括获取赋值运算符右侧的值 (`=`) 并将其存储在左侧，如以下示例所示的元素中。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-144">Assignment statements carry out assignment operations, which consist of taking the value on the right side of the assignment operator (`=`) and storing it in the element on the left, as in the following example.</span></span>

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

<span data-ttu-id="3cc5d-145">在前面的示例中，在赋值语句将存储在变量中的文本值 42 `v`。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-145">In the preceding example, the assignment statement stores the literal value 42 in the variable `v`.</span></span>

### <a name="eligible-programming-elements"></a><span data-ttu-id="3cc5d-146">符合条件的编程元素</span><span class="sxs-lookup"><span data-stu-id="3cc5d-146">Eligible programming elements</span></span>

<span data-ttu-id="3cc5d-147">赋值运算符左侧的编程元素必须能够接受并存储的值。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-147">The programming element on the left side of the assignment operator must be able to accept and store a value.</span></span> <span data-ttu-id="3cc5d-148">这意味着它必须是变量或属性不是[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)，必须为数组元素。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-148">This means it must be a variable or property that is not [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), or it must be an array element.</span></span> <span data-ttu-id="3cc5d-149">在赋值语句的上下文中，有时称为这样的元素*左值*，"左值。"</span><span class="sxs-lookup"><span data-stu-id="3cc5d-149">In the context of an assignment statement, such an element is sometimes called an *lvalue*, for "left value."</span></span>

<span data-ttu-id="3cc5d-150">赋值运算符右侧的值生成一个表达式，其可以包含文本、 常量、 变量、 属性、 数组元素、 其他表达式或函数调用的任意组合。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-150">The value on the right side of the assignment operator is generated by an expression, which can consist of any combination of literals, constants, variables, properties, array elements, other expressions, or function calls.</span></span> <span data-ttu-id="3cc5d-151">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-151">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

<span data-ttu-id="3cc5d-152">前面的示例将添加在变量中保存的值`y`变量中保存的值为`z`，然后添加对函数的调用返回的值`findResult`。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-152">The preceding example adds the value held in variable `y` to the value held in variable `z`, and then adds the value returned by the call to function `findResult`.</span></span> <span data-ttu-id="3cc5d-153">此表达式的总值然后存储在变量`x`。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-153">The total value of this expression is then stored in variable `x`.</span></span>

### <a name="data-types-in-assignment-statements"></a><span data-ttu-id="3cc5d-154">赋值语句中的数据类型</span><span class="sxs-lookup"><span data-stu-id="3cc5d-154">Data types in assignment statements</span></span>

<span data-ttu-id="3cc5d-155">除数值外，还可以将赋值运算符`String`值，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-155">In addition to numeric values, the assignment operator can also assign `String` values, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

<span data-ttu-id="3cc5d-156">你还可以分配`Boolean`值，使用`Boolean`文字或`Boolean`表达式，如下面的示例将说明。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-156">You can also assign `Boolean` values, using either a `Boolean` literal or a `Boolean` expression, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

<span data-ttu-id="3cc5d-157">同样，将适当的值分配到的编程元素`Char`， `Date`，或`Object`数据类型。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-157">Similarly, you can assign appropriate values to programming elements of the `Char`, `Date`, or `Object` data type.</span></span> <span data-ttu-id="3cc5d-158">此外可以声明为从其创建该实例的类的元素分配对象实例。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-158">You can also assign an object instance to an element declared to be of the class from which that instance is created.</span></span>

### <a name="compound-assignment-statements"></a><span data-ttu-id="3cc5d-159">复合赋值语句</span><span class="sxs-lookup"><span data-stu-id="3cc5d-159">Compound assignment statements</span></span>

<span data-ttu-id="3cc5d-160">*复合赋值语句*首先执行的操作之前将其分配到编程元素中的表达式。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-160">*Compound assignment statements* first perform an operation on an expression before assigning it to a programming element.</span></span> <span data-ttu-id="3cc5d-161">下面的示例说明了这些运算符之一`+=`，右侧表达式的值的运算符左侧的变量值时都会增加。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-161">The following example illustrates one of these operators, `+=`, which increments the value of the variable on the left side of the operator by the value of the expression on the right.</span></span>

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

<span data-ttu-id="3cc5d-162">前面的示例将 1 添加到的值`n`，然后将存储在该新值`n`。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-162">The preceding example adds 1 to the value of `n`, and then stores that new value in `n`.</span></span> <span data-ttu-id="3cc5d-163">它是一种速记属性等效于以下语句：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-163">It is a shorthand equivalent of the following statement:</span></span>

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

<span data-ttu-id="3cc5d-164">可以使用此类型的运算符执行多种不同的复合赋值操作。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-164">A variety of compound assignment operations can be performed using operators of this type.</span></span> <span data-ttu-id="3cc5d-165">有关这些运算符和相关的详细信息的列表，请参阅[赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-165">For a list of these operators and more information about them, see [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md).</span></span>

<span data-ttu-id="3cc5d-166">串联赋值运算符 (`&=`) 可用于将字符串添加到现有的末尾字符串，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-166">The concatenation assignment operator (`&=`) is useful for adding a string to the end of already existing strings, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a><span data-ttu-id="3cc5d-167">赋值语句中的类型转换</span><span class="sxs-lookup"><span data-stu-id="3cc5d-167">Type Conversions in Assignment Statements</span></span>

<span data-ttu-id="3cc5d-168">适用于该目标元素的数据类型必须是将分配给变量、 属性或数组元素的值。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-168">The value you assign to a variable, property, or array element must be of a data type appropriate to that destination element.</span></span> <span data-ttu-id="3cc5d-169">一般情况下，应尝试生成相同的数据类型与目标元素的值。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-169">In general, you should try to generate a value of the same data type as that of the destination element.</span></span> <span data-ttu-id="3cc5d-170">但是，某些类型可以在分配期间转换为其他类型中。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-170">However, some types can be converted to other types during assignment.</span></span>

<span data-ttu-id="3cc5d-171">有关数据类型之间进行转换的信息，请参阅[在 Visual Basic 中的类型转换](./data-types/type-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-171">For information on converting between data types, see [Type Conversions in Visual Basic](./data-types/type-conversions.md).</span></span> <span data-ttu-id="3cc5d-172">简单地说，Visual Basic 会自动将给定类型的值转换为其扩大的任何其他类型。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-172">In brief, Visual Basic automatically converts a value of a given type to any other type to which it widens.</span></span> <span data-ttu-id="3cc5d-173">一个*扩大转换*是中的一个始终在运行时成功，不会丢失任何数据。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-173">A *widening conversion* is one in that always succeeds at run time and does not lose any data.</span></span> <span data-ttu-id="3cc5d-174">例如，Visual Basic 将转换`Integer`值设为`Double`在适当的时候，因为`Integer`加宽到`Double`。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-174">For example, Visual Basic converts an `Integer` value to `Double` when appropriate, because `Integer` widens to `Double`.</span></span> <span data-ttu-id="3cc5d-175">有关详细信息，请参阅 [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-175">For more information, see [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="3cc5d-176">*收缩转换*（那些不扩大转换） 执行的运行时，在发生故障或数据丢失的风险。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-176">*Narrowing conversions* (those that are not widening) carry a risk of failure at run time, or of data loss.</span></span> <span data-ttu-id="3cc5d-177">您可以通过使用类型转换函数，显式执行收缩转换或可以指示编译器通过设置隐式执行所有转换`Option Strict Off`。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-177">You can perform a narrowing conversion explicitly by using a type conversion function, or you can direct the compiler to perform all conversions implicitly by setting `Option Strict Off`.</span></span> <span data-ttu-id="3cc5d-178">有关详细信息，请参阅[隐式转换和显式转换](./data-types/implicit-and-explicit-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-178">For more information, see [Implicit and Explicit Conversions](./data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="putting-multiple-statements-on-one-line"></a><span data-ttu-id="3cc5d-179">将多个语句放在同一行</span><span class="sxs-lookup"><span data-stu-id="3cc5d-179">Putting multiple statements on one line</span></span>

<span data-ttu-id="3cc5d-180">在由冒号分隔的单一行中可以有多个语句 (`:`) 字符。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-180">You can have multiple statements on a single line separated by the colon (`:`) character.</span></span> <span data-ttu-id="3cc5d-181">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-181">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

<span data-ttu-id="3cc5d-182">虽然偶尔带来方便，则这种形式的语法使代码难以阅读和维护。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-182">Though occasionally convenient, this form of syntax makes your code hard to read and maintain.</span></span> <span data-ttu-id="3cc5d-183">因此，建议您保留到行的一条语句。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-183">Thus, it is recommended that you keep one statement to a line.</span></span>

## <a name="continuing-a-statement-over-multiple-lines"></a><span data-ttu-id="3cc5d-184">跨多行继续一条语句</span><span class="sxs-lookup"><span data-stu-id="3cc5d-184">Continuing a statement over multiple lines</span></span>

<span data-ttu-id="3cc5d-185">语句通常可以在一行，但太长时，您可以继续其在使用行继续符序列，其中包括空格和下划线字符的下一行 (`_`) 后跟回车符。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-185">A statement usually fits on one line, but when it is too long, you can continue it onto the next line using a line-continuation sequence, which consists of a space followed by an underscore character (`_`) followed by a carriage return.</span></span> <span data-ttu-id="3cc5d-186">在以下示例中，`MsgBox`可执行语句连续超过两行。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-186">In the following example, the `MsgBox` executable statement is continued over two lines.</span></span>

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a><span data-ttu-id="3cc5d-187">隐式行继续符</span><span class="sxs-lookup"><span data-stu-id="3cc5d-187">Implicit line continuation</span></span>

<span data-ttu-id="3cc5d-188">在许多情况下，你可以继续语句在下一步的后续行而无需使用下划线字符 (`_`)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-188">In many cases, you can continue a statement on the next consecutive line without using the underscore character (`_`).</span></span> <span data-ttu-id="3cc5d-189">在下一行代码中的以下语法元素隐式继续该语句。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-189">The following syntax elements implicitly continue the statement on the next line of code.</span></span>

- <span data-ttu-id="3cc5d-190">逗号 (`,`)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-190">After a comma (`,`).</span></span> <span data-ttu-id="3cc5d-191">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-191">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- <span data-ttu-id="3cc5d-192">左括号之后 (`(`) 或右括号之前 (`)`)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-192">After an open parenthesis (`(`) or before a closing parenthesis (`)`).</span></span> <span data-ttu-id="3cc5d-193">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-193">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- <span data-ttu-id="3cc5d-194">在左大括号 (`{`) 或右大括号前 (`}`)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-194">After an open curly brace (`{`) or before a closing curly brace (`}`).</span></span> <span data-ttu-id="3cc5d-195">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-195">For example:</span></span>

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    <span data-ttu-id="3cc5d-196">有关详细信息，请参阅[对象初始值设定项： 命名类型和匿名类型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)或[集合初始值设定项](./collection-initializers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-196">For more information, see [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md) or [Collection Initializers](./collection-initializers/index.md).</span></span>

- <span data-ttu-id="3cc5d-197">后一种开放嵌入式表达式 (`<%=`) 或嵌入式表达式结束之前 (`%>`) 在 XML 文本中。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-197">After an open embedded expression (`<%=`) or before the close of an embedded expression (`%>`) within an XML literal.</span></span> <span data-ttu-id="3cc5d-198">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-198">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   <span data-ttu-id="3cc5d-199">有关详细信息，请参阅[XML 中的嵌入式表达式](./xml/embedded-expressions-in-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-199">For more information, see [Embedded Expressions in XML](./xml/embedded-expressions-in-xml.md).</span></span>

- <span data-ttu-id="3cc5d-200">串联运算符后 (`&`)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-200">After the concatenation operator (`&`).</span></span> <span data-ttu-id="3cc5d-201">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-201">For example:</span></span>

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   <span data-ttu-id="3cc5d-202">有关详细信息，请参阅[运算符按功能列出](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-202">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="3cc5d-203">在赋值运算符 (`=`， `&=`， `:=`， `+=`， `-=`， `*=`， `/=`， `\=`， `^=`， `<<=`， `>>=`)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-203">After assignment operators (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).</span></span> <span data-ttu-id="3cc5d-204">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-204">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="3cc5d-205">有关详细信息，请参阅[运算符按功能列出](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-205">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="3cc5d-206">在二元运算符 (`+`， `-`， `/`， `*`， `Mod`， `<>`， `<`， `>`， `<=`， `>=`， `^`， `>>`，`<<`， `And`， `AndAlso`， `Or`， `OrElse`， `Like`， `Xor`) 表达式中。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-206">After binary operators (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) within an expression.</span></span> <span data-ttu-id="3cc5d-207">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-207">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   <span data-ttu-id="3cc5d-208">有关详细信息，请参阅[运算符按功能列出](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-208">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="3cc5d-209">之后`Is`和`IsNot`运算符。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-209">After the `Is` and `IsNot` operators.</span></span> <span data-ttu-id="3cc5d-210">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-210">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   <span data-ttu-id="3cc5d-211">有关详细信息，请参阅[运算符按功能列出](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-211">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="3cc5d-212">成员的限定符字符后 (`.`) 和成员名称前。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-212">After a member qualifier character (`.`) and before the member name.</span></span> <span data-ttu-id="3cc5d-213">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-213">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="3cc5d-214">但是，您必须包含行继续符 (`_`) 时使用以下成员的限定符字符`With`语句或提供一种类型的初始化列表中的值。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-214">However, you must include a line-continuation character (`_`) following a member qualifier character when you are using the `With` statement or supplying values in the initialization list for a type.</span></span> <span data-ttu-id="3cc5d-215">请考虑之后赋值运算符换行 (例如， `=`) 使用时`With`语句或对象初始化列表。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-215">Consider breaking the line after the assignment operator (for example, `=`) when you are using `With` statements or object initialization lists.</span></span> <span data-ttu-id="3cc5d-216">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-216">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   <span data-ttu-id="3cc5d-217">有关详细信息，请参阅[使用...使用语句结束](../../../visual-basic/language-reference/statements/with-end-with-statement.md)或[对象初始值设定项： 命名类型和匿名类型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-217">For more information, see [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md) or [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

- <span data-ttu-id="3cc5d-218">XML 轴属性限定符后 (`.`或`.@`或`...`)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-218">After an XML axis property qualifier (`.` or `.@` or `...`).</span></span> <span data-ttu-id="3cc5d-219">但是，您必须包含行继续符 (`_`) 在使用时，指定成员限定符的时`With`关键字。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-219">However, you must include a line-continuation character (`_`) when you specify a member qualifier when you are using the `With` keyword.</span></span> <span data-ttu-id="3cc5d-220">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-220">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   <span data-ttu-id="3cc5d-221">有关详细信息，请参阅[XML 轴属性](../../../visual-basic/language-reference/xml-axis/index.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-221">For more information, see [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>

- <span data-ttu-id="3cc5d-222">在小于-号 (<) 或更高版本之前的登录比 (`>`) 指定属性时。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-222">After a less-than sign (<) or before a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="3cc5d-223">此外后更高版本的登录比 (`>`) 指定属性时。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-223">Also after a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="3cc5d-224">但是，您必须包含行继续符 (`_`) 指定程序集级别或模块级属性时。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-224">However, you must include a line-continuation character (`_`) when you specify assembly-level or module-level attributes.</span></span> <span data-ttu-id="3cc5d-225">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-225">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   <span data-ttu-id="3cc5d-226">有关详细信息，请参阅[的特性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-226">For more information, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span>

- <span data-ttu-id="3cc5d-227">之前和之后查询运算符 (`Aggregate`， `Distinct`， `From`， `Group By`， `Group Join`， `Join`， `Let`， `Order By`， `Select`， `Skip`， `Skip While`， `Take`， `Take While`， `Where`， `In`， `Into`， `On`， `Ascending`，和`Descending`)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-227">Before and after query operators (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, and `Descending`).</span></span> <span data-ttu-id="3cc5d-228">不能中断的组成的多个关键字的查询运算符关键字之间的行 (`Order By`， `Group Join`， `Take While`，和`Skip While`)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-228">You cannot break a line between the keywords of query operators that are made up of multiple keywords (`Order By`, `Group Join`, `Take While`, and `Skip While`).</span></span> <span data-ttu-id="3cc5d-229">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-229">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   <span data-ttu-id="3cc5d-230">有关详细信息，请参阅[查询](../../../visual-basic/language-reference/queries/index.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-230">For more information, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span>

- <span data-ttu-id="3cc5d-231">之后`In`中的关键字`For Each`语句。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-231">After the `In` keyword in a `For Each` statement.</span></span> <span data-ttu-id="3cc5d-232">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-232">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   <span data-ttu-id="3cc5d-233">有关详细信息，请参阅[为每个...下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-233">For more information, see [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>

- <span data-ttu-id="3cc5d-234">之后`From`集合初始值设定项中的关键字。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-234">After the `From` keyword in a collection initializer.</span></span> <span data-ttu-id="3cc5d-235">例如：</span><span class="sxs-lookup"><span data-stu-id="3cc5d-235">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   <span data-ttu-id="3cc5d-236">有关详细信息，请参阅[集合初始值设定项](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-236">For more information, see [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span></span>

## <a name="adding-comments"></a><span data-ttu-id="3cc5d-237">添加注释</span><span class="sxs-lookup"><span data-stu-id="3cc5d-237">Adding comments</span></span>

<span data-ttu-id="3cc5d-238">源代码并不总是很容易理解，甚至对程序员而言。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-238">Source code is not always self-explanatory, even to the programmer who wrote it.</span></span> <span data-ttu-id="3cc5d-239">为了帮助说明其代码，因此，大多数编程人员可以自由利用嵌入的注释。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-239">To help document their code, therefore, most programmers make liberal use of embedded comments.</span></span> <span data-ttu-id="3cc5d-240">在代码中的注释可以解释的过程或任何人读取或更高版本使用它的特定指令。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-240">Comments in code can explain a procedure or a particular instruction to anyone reading or working with it later.</span></span> <span data-ttu-id="3cc5d-241">Visual Basic 在编译期间，将忽略注释，它们不会影响已编译的代码。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-241">Visual Basic ignores comments during compilation, and they do not affect the compiled code.</span></span>

<span data-ttu-id="3cc5d-242">注释行开头撇号 (`'`) 或`REM`跟一个空格。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-242">Comment lines begin with an apostrophe (`'`) or `REM` followed by a space.</span></span> <span data-ttu-id="3cc5d-243">可以将它们添加任意位置在代码中，除字符串中。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-243">They can be added anywhere in code, except within a string.</span></span> <span data-ttu-id="3cc5d-244">要追加到一条语句注释，插入一个撇号或`REM`后面添加注释的语句之后。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-244">To append a comment to a statement, insert an apostrophe or `REM` after the statement, followed by the comment.</span></span> <span data-ttu-id="3cc5d-245">注释还可以在其自己单独的行上。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-245">Comments can also go on their own separate line.</span></span> <span data-ttu-id="3cc5d-246">下面的示例演示了各种选项。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-246">The following example demonstrates these possibilities.</span></span>

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a><span data-ttu-id="3cc5d-247">检查编译错误</span><span class="sxs-lookup"><span data-stu-id="3cc5d-247">Checking compilation errors</span></span>

<span data-ttu-id="3cc5d-248">如果键入一行代码后，该行显示的蓝色波浪下划线 （也可能会显示一条错误消息），则语句中有语法错误。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-248">If, after you type a line of code, the line is displayed with a wavy blue underline (an error message may appear as well), there is a syntax error in the statement.</span></span> <span data-ttu-id="3cc5d-249">必须了解什么是错误的语句 （通过在任务列表中，查找或悬停鼠标指针错误和读取的错误消息） 并更正它。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-249">You must find out what is wrong with the statement (by looking in the task list, or hovering over the error with the mouse pointer and reading the error message) and correct it.</span></span> <span data-ttu-id="3cc5d-250">在代码中修复所有语法错误，直到你的程序将无法正确编译。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-250">Until you have fixed all syntax errors in your code, your program will fail to compile correctly.</span></span>

## <a name="related-sections"></a><span data-ttu-id="3cc5d-251">相关章节</span><span class="sxs-lookup"><span data-stu-id="3cc5d-251">Related sections</span></span>

|<span data-ttu-id="3cc5d-252">术语</span><span class="sxs-lookup"><span data-stu-id="3cc5d-252">Term</span></span>|<span data-ttu-id="3cc5d-253">定义</span><span class="sxs-lookup"><span data-stu-id="3cc5d-253">Definition</span></span>|
|---|---|
|[<span data-ttu-id="3cc5d-254">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="3cc5d-254">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)|<span data-ttu-id="3cc5d-255">提供一些链接，如涉及赋值运算符的语言参考页`=`， `*=`，和`&=`。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-255">Provides links to language reference pages covering assignment operators such as `=`, `*=`, and `&=`.</span></span>|
|[<span data-ttu-id="3cc5d-256">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="3cc5d-256">Operators and Expressions</span></span>](./operators-and-expressions/index.md)|<span data-ttu-id="3cc5d-257">演示如何组合元素和运算符以生成新值。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-257">Shows how to combine elements with operators to yield new values.</span></span>|
|[<span data-ttu-id="3cc5d-258">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="3cc5d-258">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|<span data-ttu-id="3cc5d-259">演示如何拆分为多行的一条语句以及如何将多个语句置于同一行上。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-259">Shows how to break a single statement into multiple lines and how to place multiple statements on the same line.</span></span>|
|[<span data-ttu-id="3cc5d-260">如何：标记语句</span><span class="sxs-lookup"><span data-stu-id="3cc5d-260">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|<span data-ttu-id="3cc5d-261">演示如何标记代码行。</span><span class="sxs-lookup"><span data-stu-id="3cc5d-261">Shows how to label a line of code.</span></span>|

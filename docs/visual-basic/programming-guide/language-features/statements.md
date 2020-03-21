---
title: 语句
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
ms.openlocfilehash: f63f0f0212913f95baab2a8a43c4b7f25a859cd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401465"
---
# <a name="statements-in-visual-basic"></a><span data-ttu-id="cf7d3-102">语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf7d3-102">Statements in Visual Basic</span></span>

<span data-ttu-id="cf7d3-103">Visual Basic 中的语句是一个完整的指令。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-103">A statement in Visual Basic is a complete instruction.</span></span> <span data-ttu-id="cf7d3-104">它可以包含关键字、运算符、变量、常量和表达式。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-104">It can contain keywords, operators, variables, constants, and expressions.</span></span> <span data-ttu-id="cf7d3-105">每个语句都属于以下类别之一：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-105">Each statement belongs to one of the following categories:</span></span>

- <span data-ttu-id="cf7d3-106">**声明语句**，用于命名变量、常量或过程，也可以指定数据类型。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-106">**Declaration Statements**, which name a variable, constant, or procedure, and can also specify a data type.</span></span>

- <span data-ttu-id="cf7d3-107">**可执行语句**，启动操作。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-107">**Executable Statements**, which initiate actions.</span></span> <span data-ttu-id="cf7d3-108">这些语句可以调用方法或函数，并且它们可以循环或分支代码块。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-108">These statements can call a method or function, and they can loop or branch through blocks of code.</span></span> <span data-ttu-id="cf7d3-109">可执行语句包括**赋值语句**，用于将值或表达式分配给变量或常量。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-109">Executable statements include **Assignment Statements**, which assign a value or expression to a variable or constant.</span></span>

<span data-ttu-id="cf7d3-110">本主题介绍每个类别。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-110">This topic describes each category.</span></span> <span data-ttu-id="cf7d3-111">此外，本主题还介绍如何在一行上组合多个语句，以及如何在多行上继续语句。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-111">Also, this topic describes how to combine multiple statements on a single line and how to continue a statement over multiple lines.</span></span>

## <a name="declaration-statements"></a><span data-ttu-id="cf7d3-112">声明语句</span><span class="sxs-lookup"><span data-stu-id="cf7d3-112">Declaration statements</span></span>

<span data-ttu-id="cf7d3-113">使用声明语句命名和定义过程、变量、属性、数组和常量。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-113">You use declaration statements to name and define procedures, variables, properties, arrays, and constants.</span></span> <span data-ttu-id="cf7d3-114">声明编程元素时，还可以定义其数据类型、访问级别和范围。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-114">When you declare a programming element, you can also define its data type, access level, and scope.</span></span> <span data-ttu-id="cf7d3-115">有关详细信息，请参阅[声明的元素特征](./declared-elements/declared-element-characteristics.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-115">For more information, see [Declared Element Characteristics](./declared-elements/declared-element-characteristics.md).</span></span>

<span data-ttu-id="cf7d3-116">下面的示例包含三个声明。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-116">The following example contains three declarations.</span></span>

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

<span data-ttu-id="cf7d3-117">第一个声明是`Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-117">The first declaration is the `Sub` statement.</span></span> <span data-ttu-id="cf7d3-118">与其匹配`End Sub`语句一起，它声明名为 的过程`applyFormat`。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-118">Together with its matching `End Sub` statement, it declares a procedure named `applyFormat`.</span></span> <span data-ttu-id="cf7d3-119">它还指定 是`applyFormat``Public`，这意味着任何可以引用它的代码都可以调用它。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-119">It also specifies that `applyFormat` is `Public`, which means that any code that can refer to it can call it.</span></span>

<span data-ttu-id="cf7d3-120">第二个声明是`Const`语句，它声明常量`limit`，指定`Integer`数据类型和值 33。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-120">The second declaration is the `Const` statement, which declares the constant `limit`, specifying the `Integer` data type and a value of 33.</span></span>

<span data-ttu-id="cf7d3-121">第三个声明是`Dim`语句，它声明变量`thisWidget`。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-121">The third declaration is the `Dim` statement, which declares the variable `thisWidget`.</span></span> <span data-ttu-id="cf7d3-122">数据类型是特定对象，即从`Widget`类创建的对象。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-122">The data type is a specific object, namely an object created from the `Widget` class.</span></span> <span data-ttu-id="cf7d3-123">可以将变量声明为任何基本数据类型或正在使用的应用程序中公开的任何对象类型。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-123">You can declare a variable to be of any elementary data type or of any object type that is exposed in the application you are using.</span></span>

### <a name="initial-values"></a><span data-ttu-id="cf7d3-124">初始值</span><span class="sxs-lookup"><span data-stu-id="cf7d3-124">Initial Values</span></span>

<span data-ttu-id="cf7d3-125">当包含声明语句的代码运行时，Visual Basic 保留声明元素所需的内存。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-125">When the code containing a declaration statement runs, Visual Basic reserves the memory required for the declared element.</span></span> <span data-ttu-id="cf7d3-126">如果元素包含一个值，Visual Basic 会将其初始化为其数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-126">If the element holds a value, Visual Basic initializes it to the default value for its data type.</span></span> <span data-ttu-id="cf7d3-127">有关详细信息，请参阅[Dim 语句](../../language-reference/statements/dim-statement.md)中的"行为"。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-127">For more information, see "Behavior" in [Dim Statement](../../language-reference/statements/dim-statement.md).</span></span>

<span data-ttu-id="cf7d3-128">您可以为其声明的一部分为变量分配初始值，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-128">You can assign an initial value to a variable as part of its declaration, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

<span data-ttu-id="cf7d3-129">如果变量是对象变量，则可以在使用[New 运算符](../../../visual-basic/language-reference/operators/new-operator.md)关键字声明其类时显式创建其类的实例，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-129">If a variable is an object variable, you can explicitly create an instance of its class when you declare it by using the [New Operator](../../../visual-basic/language-reference/operators/new-operator.md) keyword, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

<span data-ttu-id="cf7d3-130">请注意，在执行到达其声明语句之前，声明语句中指定的初始值不会分配给变量。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-130">Note that the initial value you specify in a declaration statement is not assigned to a variable until execution reaches its declaration statement.</span></span> <span data-ttu-id="cf7d3-131">在此之前，变量包含其数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-131">Until that time, the variable contains the default value for its data type.</span></span>

## <a name="executable-statements"></a><span data-ttu-id="cf7d3-132">可执行语句</span><span class="sxs-lookup"><span data-stu-id="cf7d3-132">Executable statements</span></span>

<span data-ttu-id="cf7d3-133">可执行语句执行操作。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-133">An executable statement performs an action.</span></span> <span data-ttu-id="cf7d3-134">它可以调用过程、分支到代码中的另一个位置、循环访问多个语句或计算表达式。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-134">It can call a procedure, branch to another place in the code, loop through several statements, or evaluate an expression.</span></span> <span data-ttu-id="cf7d3-135">赋值语句是可执行语句的特殊情况。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-135">An assignment statement is a special case of an executable statement.</span></span>

<span data-ttu-id="cf7d3-136">下面的示例使用`If...Then...Else`控件结构根据变量的值运行不同的代码块。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-136">The following example uses an `If...Then...Else` control structure to run different blocks of code based on the value of a variable.</span></span> <span data-ttu-id="cf7d3-137">在每个代码块中，循环`For...Next`运行指定的次数。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-137">Within each block of code, a `For...Next` loop runs a specified number of times.</span></span>

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

<span data-ttu-id="cf7d3-138">上`If`例中的语句检查 参数`clockwise`的值 。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-138">The `If` statement in the preceding example checks the value of the parameter `clockwise`.</span></span> <span data-ttu-id="cf7d3-139">如果值为`True`，则调用`spinClockwise`方法`aWidget`。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-139">If the value is `True`, it calls the `spinClockwise` method of `aWidget`.</span></span> <span data-ttu-id="cf7d3-140">如果值为`False`，则调用`spinCounterClockwise`方法`aWidget`。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-140">If the value is `False`, it calls the `spinCounterClockwise` method of `aWidget`.</span></span> <span data-ttu-id="cf7d3-141">控制`If...Then...Else`结构以`End If`结尾。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-141">The `If...Then...Else` control structure ends with `End If`.</span></span>

<span data-ttu-id="cf7d3-142">每个`For...Next`块中的循环调用适当的方法的次数等于`revolutions`参数的值。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-142">The `For...Next` loop within each block calls the appropriate method a number of times equal to the value of the `revolutions` parameter.</span></span>

## <a name="assignment-statements"></a><span data-ttu-id="cf7d3-143">分配语句</span><span class="sxs-lookup"><span data-stu-id="cf7d3-143">Assignment statements</span></span>

<span data-ttu-id="cf7d3-144">分配语句执行赋值操作，其中包括获取赋值运算符 （`=`） 右侧的值并将其存储在左侧的元素中，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-144">Assignment statements carry out assignment operations, which consist of taking the value on the right side of the assignment operator (`=`) and storing it in the element on the left, as in the following example.</span></span>

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

<span data-ttu-id="cf7d3-145">在前面的示例中，赋值语句在变量`v`中存储文本值 42。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-145">In the preceding example, the assignment statement stores the literal value 42 in the variable `v`.</span></span>

### <a name="eligible-programming-elements"></a><span data-ttu-id="cf7d3-146">合格的编程元素</span><span class="sxs-lookup"><span data-stu-id="cf7d3-146">Eligible programming elements</span></span>

<span data-ttu-id="cf7d3-147">赋值运算符左侧的编程元素必须能够接受并存储值。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-147">The programming element on the left side of the assignment operator must be able to accept and store a value.</span></span> <span data-ttu-id="cf7d3-148">这意味着它必须是一个变量或属性，它不是[ReadOnly，](../../../visual-basic/language-reference/modifiers/readonly.md)或者它必须是数组元素。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-148">This means it must be a variable or property that is not [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), or it must be an array element.</span></span> <span data-ttu-id="cf7d3-149">在赋值语句的上下文中，此类元素有时称为*lvalue，* 表示为"左值"。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-149">In the context of an assignment statement, such an element is sometimes called an *lvalue*, for "left value."</span></span>

<span data-ttu-id="cf7d3-150">赋值运算符右侧的值由表达式生成，表达式可以由文本、常量、变量、属性、数组元素、其他表达式或函数调用的任意组合组成。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-150">The value on the right side of the assignment operator is generated by an expression, which can consist of any combination of literals, constants, variables, properties, array elements, other expressions, or function calls.</span></span> <span data-ttu-id="cf7d3-151">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-151">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

<span data-ttu-id="cf7d3-152">前面的示例将变量`y`中持有的值添加到变量`z`中的值，然后添加调用 函数 返回的值。 `findResult`</span><span class="sxs-lookup"><span data-stu-id="cf7d3-152">The preceding example adds the value held in variable `y` to the value held in variable `z`, and then adds the value returned by the call to function `findResult`.</span></span> <span data-ttu-id="cf7d3-153">然后，此表达式的总值存储在变量`x`中。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-153">The total value of this expression is then stored in variable `x`.</span></span>

### <a name="data-types-in-assignment-statements"></a><span data-ttu-id="cf7d3-154">赋值语句中的数据类型</span><span class="sxs-lookup"><span data-stu-id="cf7d3-154">Data types in assignment statements</span></span>

<span data-ttu-id="cf7d3-155">除了数值之外，赋值运算符还可以分配`String`值，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-155">In addition to numeric values, the assignment operator can also assign `String` values, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

<span data-ttu-id="cf7d3-156">您还可以使用`Boolean`文本或`Boolean`表达式`Boolean`分配值，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-156">You can also assign `Boolean` values, using either a `Boolean` literal or a `Boolean` expression, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

<span data-ttu-id="cf7d3-157">同样，您可以为`Char`的编程元素分配适当的值，`Date`或`Object`数据类型的编程元素。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-157">Similarly, you can assign appropriate values to programming elements of the `Char`, `Date`, or `Object` data type.</span></span> <span data-ttu-id="cf7d3-158">还可以将对象实例分配给声明为创建该实例的类的元素。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-158">You can also assign an object instance to an element declared to be of the class from which that instance is created.</span></span>

### <a name="compound-assignment-statements"></a><span data-ttu-id="cf7d3-159">复合赋值语句</span><span class="sxs-lookup"><span data-stu-id="cf7d3-159">Compound assignment statements</span></span>

<span data-ttu-id="cf7d3-160">*复合赋值语句*首先对表达式执行操作，然后再将其分配给编程元素。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-160">*Compound assignment statements* first perform an operation on an expression before assigning it to a programming element.</span></span> <span data-ttu-id="cf7d3-161">下面的示例说明了这些运算符之一 ，`+=`该运算符将运算符左侧变量的值由右侧表达式的值递增。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-161">The following example illustrates one of these operators, `+=`, which increments the value of the variable on the left side of the operator by the value of the expression on the right.</span></span>

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

<span data-ttu-id="cf7d3-162">前面的示例将 1 添加到`n`的值，然后将新值存储在 中。 `n`</span><span class="sxs-lookup"><span data-stu-id="cf7d3-162">The preceding example adds 1 to the value of `n`, and then stores that new value in `n`.</span></span> <span data-ttu-id="cf7d3-163">它是以下语句的速记等效项：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-163">It is a shorthand equivalent of the following statement:</span></span>

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

<span data-ttu-id="cf7d3-164">可以使用此类运算符执行各种复合赋值操作。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-164">A variety of compound assignment operations can be performed using operators of this type.</span></span> <span data-ttu-id="cf7d3-165">有关这些运算符的列表及其的详细信息，请参阅[分配运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-165">For a list of these operators and more information about them, see [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md).</span></span>

<span data-ttu-id="cf7d3-166">串联赋值运算符 （`&=`） 可用于将字符串添加到现有字符串的末尾，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-166">The concatenation assignment operator (`&=`) is useful for adding a string to the end of already existing strings, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a><span data-ttu-id="cf7d3-167">在分配语句中键入转换</span><span class="sxs-lookup"><span data-stu-id="cf7d3-167">Type Conversions in Assignment Statements</span></span>

<span data-ttu-id="cf7d3-168">分配给变量、属性或数组元素的值必须为适合该目标元素的数据类型。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-168">The value you assign to a variable, property, or array element must be of a data type appropriate to that destination element.</span></span> <span data-ttu-id="cf7d3-169">通常，应尝试生成与目标元素相同的数据类型的值。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-169">In general, you should try to generate a value of the same data type as that of the destination element.</span></span> <span data-ttu-id="cf7d3-170">但是，某些类型可以在分配期间转换为其他类型的类型。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-170">However, some types can be converted to other types during assignment.</span></span>

<span data-ttu-id="cf7d3-171">有关数据类型之间转换的信息，请参阅[可视化基本 中的"类型转换](./data-types/type-conversions.md)"。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-171">For information on converting between data types, see [Type Conversions in Visual Basic](./data-types/type-conversions.md).</span></span> <span data-ttu-id="cf7d3-172">简而言之，Visual Basic 会自动将给定类型的值转换为它扩展到的任何其他类型。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-172">In brief, Visual Basic automatically converts a value of a given type to any other type to which it widens.</span></span> <span data-ttu-id="cf7d3-173">*加宽转换*是始终在运行时成功且不会丢失任何数据的转换。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-173">A *widening conversion* is one in that always succeeds at run time and does not lose any data.</span></span> <span data-ttu-id="cf7d3-174">例如，Visual `Integer` Basic 将值转换为适当`Double`值，因为`Integer`范围将扩大为`Double`。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-174">For example, Visual Basic converts an `Integer` value to `Double` when appropriate, because `Integer` widens to `Double`.</span></span> <span data-ttu-id="cf7d3-175">有关详细信息，请参阅 [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-175">For more information, see [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="cf7d3-176">*缩小转换*（未扩大的转换）有在运行时失败或数据丢失的风险。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-176">*Narrowing conversions* (those that are not widening) carry a risk of failure at run time, or of data loss.</span></span> <span data-ttu-id="cf7d3-177">您可以使用类型转换函数显式执行缩小转换，也可以通过设置`Option Strict Off`来指示编译器隐式执行所有转换。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-177">You can perform a narrowing conversion explicitly by using a type conversion function, or you can direct the compiler to perform all conversions implicitly by setting `Option Strict Off`.</span></span> <span data-ttu-id="cf7d3-178">有关详细信息，请参阅[隐式和显式转换](./data-types/implicit-and-explicit-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-178">For more information, see [Implicit and Explicit Conversions](./data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="putting-multiple-statements-on-one-line"></a><span data-ttu-id="cf7d3-179">将多个语句放在一行上</span><span class="sxs-lookup"><span data-stu-id="cf7d3-179">Putting multiple statements on one line</span></span>

<span data-ttu-id="cf7d3-180">单行上的多个语句由冒号 （`:`） 字符分隔。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-180">You can have multiple statements on a single line separated by the colon (`:`) character.</span></span> <span data-ttu-id="cf7d3-181">下面的示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-181">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

<span data-ttu-id="cf7d3-182">虽然偶尔方便，但这种语法形式使代码难以阅读和维护。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-182">Though occasionally convenient, this form of syntax makes your code hard to read and maintain.</span></span> <span data-ttu-id="cf7d3-183">因此，建议您将一个语句保留为一行。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-183">Thus, it is recommended that you keep one statement to a line.</span></span>

## <a name="continuing-a-statement-over-multiple-lines"></a><span data-ttu-id="cf7d3-184">在多行上继续语句</span><span class="sxs-lookup"><span data-stu-id="cf7d3-184">Continuing a statement over multiple lines</span></span>

<span data-ttu-id="cf7d3-185">语句通常适合一行，但当太长时，可以使用行延续序列将其延续到下一行上，该序列由空格后跟下划线字符 （`_`） 后跟回车符组成。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-185">A statement usually fits on one line, but when it is too long, you can continue it onto the next line using a line-continuation sequence, which consists of a space followed by an underscore character (`_`) followed by a carriage return.</span></span> <span data-ttu-id="cf7d3-186">在下面的示例中，`MsgBox`可执行语句在两行上继续。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-186">In the following example, the `MsgBox` executable statement is continued over two lines.</span></span>

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a><span data-ttu-id="cf7d3-187">隐式行延续</span><span class="sxs-lookup"><span data-stu-id="cf7d3-187">Implicit line continuation</span></span>

<span data-ttu-id="cf7d3-188">在许多情况下，您可以在下一条连续行上继续语句，而无需使用下划线字符 （`_`。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-188">In many cases, you can continue a statement on the next consecutive line without using the underscore character (`_`).</span></span> <span data-ttu-id="cf7d3-189">以下语法元素隐式地继续下一行代码上的语句。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-189">The following syntax elements implicitly continue the statement on the next line of code.</span></span>

- <span data-ttu-id="cf7d3-190">逗号后 （`,`。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-190">After a comma (`,`).</span></span> <span data-ttu-id="cf7d3-191">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-191">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- <span data-ttu-id="cf7d3-192">开放括号后 （`(`） 或关闭括号之前 （`)`）</span><span class="sxs-lookup"><span data-stu-id="cf7d3-192">After an open parenthesis (`(`) or before a closing parenthesis (`)`).</span></span> <span data-ttu-id="cf7d3-193">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-193">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- <span data-ttu-id="cf7d3-194">打开大括号 （`{`） 后或关闭大括号 （`}`） 之前。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-194">After an open curly brace (`{`) or before a closing curly brace (`}`).</span></span> <span data-ttu-id="cf7d3-195">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-195">For example:</span></span>

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    <span data-ttu-id="cf7d3-196">有关详细信息，请参阅[对象初始化器：命名和匿名类型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)或[集合初始化器](./collection-initializers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-196">For more information, see [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md) or [Collection Initializers](./collection-initializers/index.md).</span></span>

- <span data-ttu-id="cf7d3-197">在 XML 文本中`<%=`打开的嵌入表达式 （ ） 之后`%>`或嵌入表达式 （ ） 关闭之前。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-197">After an open embedded expression (`<%=`) or before the close of an embedded expression (`%>`) within an XML literal.</span></span> <span data-ttu-id="cf7d3-198">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-198">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   <span data-ttu-id="cf7d3-199">有关详细信息，请参阅[XML 中的嵌入式表达式](./xml/embedded-expressions-in-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-199">For more information, see [Embedded Expressions in XML](./xml/embedded-expressions-in-xml.md).</span></span>

- <span data-ttu-id="cf7d3-200">串联运算符后 （`&`。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-200">After the concatenation operator (`&`).</span></span> <span data-ttu-id="cf7d3-201">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-201">For example:</span></span>

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   <span data-ttu-id="cf7d3-202">有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-202">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="cf7d3-203">分配运算符后`=`（、 `:=` `&=` `+=`、 `-=` `*=`、 `/=` `\=`、 `^=` `<<=`、 `>>=`、 、 、 、 、 、 、 、</span><span class="sxs-lookup"><span data-stu-id="cf7d3-203">After assignment operators (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).</span></span> <span data-ttu-id="cf7d3-204">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-204">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="cf7d3-205">有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-205">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="cf7d3-206">After binary operators (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) within an expression.</span><span class="sxs-lookup"><span data-stu-id="cf7d3-206">After binary operators (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) within an expression.</span></span> <span data-ttu-id="cf7d3-207">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-207">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   <span data-ttu-id="cf7d3-208">有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-208">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="cf7d3-209">和`Is``IsNot`运算符之后。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-209">After the `Is` and `IsNot` operators.</span></span> <span data-ttu-id="cf7d3-210">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-210">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   <span data-ttu-id="cf7d3-211">有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-211">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="cf7d3-212">在成员限定符之后`.`（ ） 和成员名称之前。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-212">After a member qualifier character (`.`) and before the member name.</span></span> <span data-ttu-id="cf7d3-213">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-213">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="cf7d3-214">但是，当您在类型的初始化列表中使用语句或`_`提供值时，`With`必须在成员限定符字符之后包含行延续字符 （ ）。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-214">However, you must include a line-continuation character (`_`) following a member qualifier character when you are using the `With` statement or supplying values in the initialization list for a type.</span></span> <span data-ttu-id="cf7d3-215">使用`=``With`语句或对象初始化列表时，请考虑在赋值运算符（例如）之后中断行。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-215">Consider breaking the line after the assignment operator (for example, `=`) when you are using `With` statements or object initialization lists.</span></span> <span data-ttu-id="cf7d3-216">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-216">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   <span data-ttu-id="cf7d3-217">有关详细信息，请参阅[...结尾与语句](../../../visual-basic/language-reference/statements/with-end-with-statement.md)或[对象初始化器：命名和匿名类型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-217">For more information, see [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md) or [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

- <span data-ttu-id="cf7d3-218">在 XML 轴属性限定`.`符`.@` `...`（ 或 ） 之后。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-218">After an XML axis property qualifier (`.` or `.@` or `...`).</span></span> <span data-ttu-id="cf7d3-219">但是，在使用 关键字时指定成员限定符`_`时，`With`必须包含行延续字符 （ ）。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-219">However, you must include a line-continuation character (`_`) when you specify a member qualifier when you are using the `With` keyword.</span></span> <span data-ttu-id="cf7d3-220">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-220">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   <span data-ttu-id="cf7d3-221">有关详细信息，请参阅[XML 轴属性](../../../visual-basic/language-reference/xml-axis/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-221">For more information, see [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>

- <span data-ttu-id="cf7d3-222">指定属性时，小于符号 （<） 后或大于符号 （`>`） 之前。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-222">After a less-than sign (<) or before a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="cf7d3-223">指定属性时，在大于符号`>`（ ） 之后。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-223">Also after a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="cf7d3-224">但是，在指定装配体级或模块级属性`_`时，必须包含一个线延续字符 （ 。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-224">However, you must include a line-continuation character (`_`) when you specify assembly-level or module-level attributes.</span></span> <span data-ttu-id="cf7d3-225">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-225">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   <span data-ttu-id="cf7d3-226">有关详细信息，请参阅[属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-226">For more information, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span>

- <span data-ttu-id="cf7d3-227">查询运算符（、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、、`Aggregate` `Distinct` `From` `Group By` `Group Join` `Join` `Let` `Order By` `Select` `Skip` `Skip While` `Take` `Take While` `Where` `In` `Into` `On` `Ascending` `Descending`</span><span class="sxs-lookup"><span data-stu-id="cf7d3-227">Before and after query operators (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, and `Descending`).</span></span> <span data-ttu-id="cf7d3-228">不能在`Order By`由多个关键字 （、、`Group Join``Take While`和`Skip While`） 组成的查询运算符的关键字之间换行。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-228">You cannot break a line between the keywords of query operators that are made up of multiple keywords (`Order By`, `Group Join`, `Take While`, and `Skip While`).</span></span> <span data-ttu-id="cf7d3-229">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-229">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   <span data-ttu-id="cf7d3-230">有关详细信息，请参阅[查询](../../../visual-basic/language-reference/queries/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-230">For more information, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span>

- <span data-ttu-id="cf7d3-231">语句中的`In``For Each`关键字之后。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-231">After the `In` keyword in a `For Each` statement.</span></span> <span data-ttu-id="cf7d3-232">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-232">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   <span data-ttu-id="cf7d3-233">有关详细信息，请参阅[每个...下一个语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cf7d3-233">For more information, see [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>

- <span data-ttu-id="cf7d3-234">在`From`集合初始化器中的关键字之后。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-234">After the `From` keyword in a collection initializer.</span></span> <span data-ttu-id="cf7d3-235">例如：</span><span class="sxs-lookup"><span data-stu-id="cf7d3-235">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   <span data-ttu-id="cf7d3-236">有关详细信息，请参阅[集合初始值设定项](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-236">For more information, see [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span></span>

## <a name="adding-comments"></a><span data-ttu-id="cf7d3-237">添加注释</span><span class="sxs-lookup"><span data-stu-id="cf7d3-237">Adding comments</span></span>

<span data-ttu-id="cf7d3-238">源代码并不总是不言自明的，即使是编写源代码的程序员也是如此。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-238">Source code is not always self-explanatory, even to the programmer who wrote it.</span></span> <span data-ttu-id="cf7d3-239">因此，为了帮助记录他们的代码，大多数程序员都自由使用嵌入式注释。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-239">To help document their code, therefore, most programmers make liberal use of embedded comments.</span></span> <span data-ttu-id="cf7d3-240">代码中的注释可以向以后阅读或使用它的人解释过程或特定指令。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-240">Comments in code can explain a procedure or a particular instruction to anyone reading or working with it later.</span></span> <span data-ttu-id="cf7d3-241">Visual Basic 在编译过程中忽略注释，它们不会影响编译的代码。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-241">Visual Basic ignores comments during compilation, and they do not affect the compiled code.</span></span>

<span data-ttu-id="cf7d3-242">注释行以撇号开头或`'``REM`后跟空格。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-242">Comment lines begin with an apostrophe (`'`) or `REM` followed by a space.</span></span> <span data-ttu-id="cf7d3-243">它们可以添加到代码中的任意位置，但字符串中除外。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-243">They can be added anywhere in code, except within a string.</span></span> <span data-ttu-id="cf7d3-244">若要在语句上附加注释，请插入撇号或`REM`语句后，然后插入注释。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-244">To append a comment to a statement, insert an apostrophe or `REM` after the statement, followed by the comment.</span></span> <span data-ttu-id="cf7d3-245">注释也可以单独行。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-245">Comments can also go on their own separate line.</span></span> <span data-ttu-id="cf7d3-246">下面的示例演示了这些可能性。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-246">The following example demonstrates these possibilities.</span></span>

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a><span data-ttu-id="cf7d3-247">检查编译错误</span><span class="sxs-lookup"><span data-stu-id="cf7d3-247">Checking compilation errors</span></span>

<span data-ttu-id="cf7d3-248">如果在键入一行代码后，行以波浪蓝色下划线显示（也可能显示错误消息），则语句中存在语法错误。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-248">If, after you type a line of code, the line is displayed with a wavy blue underline (an error message may appear as well), there is a syntax error in the statement.</span></span> <span data-ttu-id="cf7d3-249">您必须找出该语句的问题所在（通过查看任务列表，或用鼠标指针悬停在错误上并读取错误消息），并更正它。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-249">You must find out what is wrong with the statement (by looking in the task list, or hovering over the error with the mouse pointer and reading the error message) and correct it.</span></span> <span data-ttu-id="cf7d3-250">在修复代码中的所有语法错误之前，程序将无法正确编译。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-250">Until you have fixed all syntax errors in your code, your program will fail to compile correctly.</span></span>

## <a name="related-sections"></a><span data-ttu-id="cf7d3-251">相关章节</span><span class="sxs-lookup"><span data-stu-id="cf7d3-251">Related sections</span></span>

|<span data-ttu-id="cf7d3-252">术语</span><span class="sxs-lookup"><span data-stu-id="cf7d3-252">Term</span></span>|<span data-ttu-id="cf7d3-253">定义</span><span class="sxs-lookup"><span data-stu-id="cf7d3-253">Definition</span></span>|
|---|---|
|[<span data-ttu-id="cf7d3-254">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="cf7d3-254">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)|<span data-ttu-id="cf7d3-255">提供指向语言参考页的链接，这些页涵盖赋`=`值`*=`运算符（`&=`如 ）和 。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-255">Provides links to language reference pages covering assignment operators such as `=`, `*=`, and `&=`.</span></span>|
|[<span data-ttu-id="cf7d3-256">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="cf7d3-256">Operators and Expressions</span></span>](./operators-and-expressions/index.md)|<span data-ttu-id="cf7d3-257">演示如何将元素与运算符组合以生成新值。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-257">Shows how to combine elements with operators to yield new values.</span></span>|
|[<span data-ttu-id="cf7d3-258">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="cf7d3-258">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|<span data-ttu-id="cf7d3-259">演示如何将单个语句分成多行，以及如何在同一行上放置多个语句。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-259">Shows how to break a single statement into multiple lines and how to place multiple statements on the same line.</span></span>|
|[<span data-ttu-id="cf7d3-260">如何：标记语句</span><span class="sxs-lookup"><span data-stu-id="cf7d3-260">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|<span data-ttu-id="cf7d3-261">演示如何标记代码行。</span><span class="sxs-lookup"><span data-stu-id="cf7d3-261">Shows how to label a line of code.</span></span>|

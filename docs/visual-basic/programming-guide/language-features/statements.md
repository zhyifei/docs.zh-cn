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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352507"
---
# <a name="statements-in-visual-basic"></a><span data-ttu-id="b4e01-102">语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4e01-102">Statements in Visual Basic</span></span>

<span data-ttu-id="b4e01-103">Visual Basic 中的语句是一个完整的说明。</span><span class="sxs-lookup"><span data-stu-id="b4e01-103">A statement in Visual Basic is a complete instruction.</span></span> <span data-ttu-id="b4e01-104">它可以包含关键字、运算符、变量、常量和表达式。</span><span class="sxs-lookup"><span data-stu-id="b4e01-104">It can contain keywords, operators, variables, constants, and expressions.</span></span> <span data-ttu-id="b4e01-105">每个语句属于以下类别之一：</span><span class="sxs-lookup"><span data-stu-id="b4e01-105">Each statement belongs to one of the following categories:</span></span>

- <span data-ttu-id="b4e01-106">**声明语句**，用于命名变量、常量或过程，还可以指定数据类型。</span><span class="sxs-lookup"><span data-stu-id="b4e01-106">**Declaration Statements**, which name a variable, constant, or procedure, and can also specify a data type.</span></span>

- <span data-ttu-id="b4e01-107">启动操作的**可执行语句**。</span><span class="sxs-lookup"><span data-stu-id="b4e01-107">**Executable Statements**, which initiate actions.</span></span> <span data-ttu-id="b4e01-108">这些语句可以调用方法或函数，并且它们可以循环或分支到代码块。</span><span class="sxs-lookup"><span data-stu-id="b4e01-108">These statements can call a method or function, and they can loop or branch through blocks of code.</span></span> <span data-ttu-id="b4e01-109">可执行语句包括**赋值语句，赋值语句**将值或表达式分配给变量或常数。</span><span class="sxs-lookup"><span data-stu-id="b4e01-109">Executable statements include **Assignment Statements**, which assign a value or expression to a variable or constant.</span></span>

<span data-ttu-id="b4e01-110">本主题介绍每个类别。</span><span class="sxs-lookup"><span data-stu-id="b4e01-110">This topic describes each category.</span></span> <span data-ttu-id="b4e01-111">此外，本主题还介绍如何在单个行上组合多个语句以及如何在多行上继续执行语句。</span><span class="sxs-lookup"><span data-stu-id="b4e01-111">Also, this topic describes how to combine multiple statements on a single line and how to continue a statement over multiple lines.</span></span>

## <a name="declaration-statements"></a><span data-ttu-id="b4e01-112">声明语句</span><span class="sxs-lookup"><span data-stu-id="b4e01-112">Declaration statements</span></span>

<span data-ttu-id="b4e01-113">使用声明语句来命名和定义过程、变量、属性、数组和常量。</span><span class="sxs-lookup"><span data-stu-id="b4e01-113">You use declaration statements to name and define procedures, variables, properties, arrays, and constants.</span></span> <span data-ttu-id="b4e01-114">在声明编程元素时，还可以定义其数据类型、访问级别和作用域。</span><span class="sxs-lookup"><span data-stu-id="b4e01-114">When you declare a programming element, you can also define its data type, access level, and scope.</span></span> <span data-ttu-id="b4e01-115">有关详细信息，请参阅[声明的元素特征](./declared-elements/declared-element-characteristics.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-115">For more information, see [Declared Element Characteristics](./declared-elements/declared-element-characteristics.md).</span></span>

<span data-ttu-id="b4e01-116">下面的示例包含三个声明。</span><span class="sxs-lookup"><span data-stu-id="b4e01-116">The following example contains three declarations.</span></span>

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

<span data-ttu-id="b4e01-117">第一个声明是 `Sub` 语句。</span><span class="sxs-lookup"><span data-stu-id="b4e01-117">The first declaration is the `Sub` statement.</span></span> <span data-ttu-id="b4e01-118">它与它的匹配 `End Sub` 语句一起声明名为 `applyFormat`的过程。</span><span class="sxs-lookup"><span data-stu-id="b4e01-118">Together with its matching `End Sub` statement, it declares a procedure named `applyFormat`.</span></span> <span data-ttu-id="b4e01-119">它还指定 `applyFormat` `Public`，这意味着可引用它的任何代码都可以调用它。</span><span class="sxs-lookup"><span data-stu-id="b4e01-119">It also specifies that `applyFormat` is `Public`, which means that any code that can refer to it can call it.</span></span>

<span data-ttu-id="b4e01-120">第二个声明是 `Const` 语句，该语句 `limit`指定 `Integer` 数据类型和值33。</span><span class="sxs-lookup"><span data-stu-id="b4e01-120">The second declaration is the `Const` statement, which declares the constant `limit`, specifying the `Integer` data type and a value of 33.</span></span>

<span data-ttu-id="b4e01-121">第三个声明是 `Dim` 语句，该语句 `thisWidget`声明变量。</span><span class="sxs-lookup"><span data-stu-id="b4e01-121">The third declaration is the `Dim` statement, which declares the variable `thisWidget`.</span></span> <span data-ttu-id="b4e01-122">数据类型是一个特定对象，即从 `Widget` 类创建的对象。</span><span class="sxs-lookup"><span data-stu-id="b4e01-122">The data type is a specific object, namely an object created from the `Widget` class.</span></span> <span data-ttu-id="b4e01-123">可以将变量声明为任意基本数据类型，或者声明为在所使用的应用程序中公开的任何对象类型。</span><span class="sxs-lookup"><span data-stu-id="b4e01-123">You can declare a variable to be of any elementary data type or of any object type that is exposed in the application you are using.</span></span>

### <a name="initial-values"></a><span data-ttu-id="b4e01-124">初始值</span><span class="sxs-lookup"><span data-stu-id="b4e01-124">Initial Values</span></span>

<span data-ttu-id="b4e01-125">当包含声明语句的代码运行时，Visual Basic 保留已声明的元素所需的内存。</span><span class="sxs-lookup"><span data-stu-id="b4e01-125">When the code containing a declaration statement runs, Visual Basic reserves the memory required for the declared element.</span></span> <span data-ttu-id="b4e01-126">如果元素包含值，Visual Basic 会将其初始化为其数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="b4e01-126">If the element holds a value, Visual Basic initializes it to the default value for its data type.</span></span> <span data-ttu-id="b4e01-127">有关详细信息，请参阅[Dim 语句](../../language-reference/statements/dim-statement.md)中的 "行为"。</span><span class="sxs-lookup"><span data-stu-id="b4e01-127">For more information, see "Behavior" in [Dim Statement](../../language-reference/statements/dim-statement.md).</span></span>

<span data-ttu-id="b4e01-128">可以将初始值分配给变量作为其声明的一部分，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="b4e01-128">You can assign an initial value to a variable as part of its declaration, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

<span data-ttu-id="b4e01-129">如果变量是一个对象变量，则可以在使用[New 运算符](../../../visual-basic/language-reference/operators/new-operator.md)关键字声明它时显式创建该类的实例，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="b4e01-129">If a variable is an object variable, you can explicitly create an instance of its class when you declare it by using the [New Operator](../../../visual-basic/language-reference/operators/new-operator.md) keyword, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

<span data-ttu-id="b4e01-130">请注意，在声明语句中指定的初始值不会分配给变量，直到执行到达其声明语句。</span><span class="sxs-lookup"><span data-stu-id="b4e01-130">Note that the initial value you specify in a declaration statement is not assigned to a variable until execution reaches its declaration statement.</span></span> <span data-ttu-id="b4e01-131">在此之前，变量包含其数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="b4e01-131">Until that time, the variable contains the default value for its data type.</span></span>

## <a name="executable-statements"></a><span data-ttu-id="b4e01-132">可执行语句</span><span class="sxs-lookup"><span data-stu-id="b4e01-132">Executable statements</span></span>

<span data-ttu-id="b4e01-133">可执行语句执行操作。</span><span class="sxs-lookup"><span data-stu-id="b4e01-133">An executable statement performs an action.</span></span> <span data-ttu-id="b4e01-134">它可以调用过程、分支到代码中的其他位置、循环几个语句或计算表达式。</span><span class="sxs-lookup"><span data-stu-id="b4e01-134">It can call a procedure, branch to another place in the code, loop through several statements, or evaluate an expression.</span></span> <span data-ttu-id="b4e01-135">赋值语句是可执行语句的特殊情况。</span><span class="sxs-lookup"><span data-stu-id="b4e01-135">An assignment statement is a special case of an executable statement.</span></span>

<span data-ttu-id="b4e01-136">下面的示例使用 `If...Then...Else` 控件结构基于变量的值运行不同的代码块。</span><span class="sxs-lookup"><span data-stu-id="b4e01-136">The following example uses an `If...Then...Else` control structure to run different blocks of code based on the value of a variable.</span></span> <span data-ttu-id="b4e01-137">在每个代码块中，`For...Next` 循环会运行指定的次数。</span><span class="sxs-lookup"><span data-stu-id="b4e01-137">Within each block of code, a `For...Next` loop runs a specified number of times.</span></span>

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

<span data-ttu-id="b4e01-138">前面的示例中的 `If` 语句检查参数 `clockwise`的值。</span><span class="sxs-lookup"><span data-stu-id="b4e01-138">The `If` statement in the preceding example checks the value of the parameter `clockwise`.</span></span> <span data-ttu-id="b4e01-139">如果 `True`值，则它将调用 `aWidget`的 `spinClockwise` 方法。</span><span class="sxs-lookup"><span data-stu-id="b4e01-139">If the value is `True`, it calls the `spinClockwise` method of `aWidget`.</span></span> <span data-ttu-id="b4e01-140">如果 `False`值，则它将调用 `aWidget`的 `spinCounterClockwise` 方法。</span><span class="sxs-lookup"><span data-stu-id="b4e01-140">If the value is `False`, it calls the `spinCounterClockwise` method of `aWidget`.</span></span> <span data-ttu-id="b4e01-141">`If...Then...Else` 控制结构以 `End If`结束。</span><span class="sxs-lookup"><span data-stu-id="b4e01-141">The `If...Then...Else` control structure ends with `End If`.</span></span>

<span data-ttu-id="b4e01-142">每个块中的 `For...Next` 循环将调用相应的方法，这几次等于 `revolutions` 参数的值。</span><span class="sxs-lookup"><span data-stu-id="b4e01-142">The `For...Next` loop within each block calls the appropriate method a number of times equal to the value of the `revolutions` parameter.</span></span>

## <a name="assignment-statements"></a><span data-ttu-id="b4e01-143">赋值语句</span><span class="sxs-lookup"><span data-stu-id="b4e01-143">Assignment statements</span></span>

<span data-ttu-id="b4e01-144">赋值语句执行赋值运算，其中包含赋值运算符（`=`）右侧的值并将其存储在左侧的元素中，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="b4e01-144">Assignment statements carry out assignment operations, which consist of taking the value on the right side of the assignment operator (`=`) and storing it in the element on the left, as in the following example.</span></span>

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

<span data-ttu-id="b4e01-145">在前面的示例中，赋值语句将文本值42存储在变量 `v`中。</span><span class="sxs-lookup"><span data-stu-id="b4e01-145">In the preceding example, the assignment statement stores the literal value 42 in the variable `v`.</span></span>

### <a name="eligible-programming-elements"></a><span data-ttu-id="b4e01-146">符合条件的编程元素</span><span class="sxs-lookup"><span data-stu-id="b4e01-146">Eligible programming elements</span></span>

<span data-ttu-id="b4e01-147">赋值运算符左侧的编程元素必须能够接受和存储值。</span><span class="sxs-lookup"><span data-stu-id="b4e01-147">The programming element on the left side of the assignment operator must be able to accept and store a value.</span></span> <span data-ttu-id="b4e01-148">这意味着它必须是不是[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)的变量或属性，或者必须是数组元素。</span><span class="sxs-lookup"><span data-stu-id="b4e01-148">This means it must be a variable or property that is not [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), or it must be an array element.</span></span> <span data-ttu-id="b4e01-149">在赋值语句的上下文中，此类元素有时*称为左值，表示*"左值"。</span><span class="sxs-lookup"><span data-stu-id="b4e01-149">In the context of an assignment statement, such an element is sometimes called an *lvalue*, for "left value."</span></span>

<span data-ttu-id="b4e01-150">赋值运算符右侧的值是由表达式生成的，表达式可以包含文本、常量、变量、属性、数组元素、其他表达式或函数调用的任意组合。</span><span class="sxs-lookup"><span data-stu-id="b4e01-150">The value on the right side of the assignment operator is generated by an expression, which can consist of any combination of literals, constants, variables, properties, array elements, other expressions, or function calls.</span></span> <span data-ttu-id="b4e01-151">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="b4e01-151">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

<span data-ttu-id="b4e01-152">前面的示例将变量 `y` 中保存的值添加到变量 `z`中保存的值，然后将对函数的调用返回的值添加 `findResult`。</span><span class="sxs-lookup"><span data-stu-id="b4e01-152">The preceding example adds the value held in variable `y` to the value held in variable `z`, and then adds the value returned by the call to function `findResult`.</span></span> <span data-ttu-id="b4e01-153">然后，此表达式的总值存储在变量 `x`中。</span><span class="sxs-lookup"><span data-stu-id="b4e01-153">The total value of this expression is then stored in variable `x`.</span></span>

### <a name="data-types-in-assignment-statements"></a><span data-ttu-id="b4e01-154">赋值语句中的数据类型</span><span class="sxs-lookup"><span data-stu-id="b4e01-154">Data types in assignment statements</span></span>

<span data-ttu-id="b4e01-155">除了数值之外，赋值运算符还可以分配 `String` 值，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="b4e01-155">In addition to numeric values, the assignment operator can also assign `String` values, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

<span data-ttu-id="b4e01-156">你还可以使用 `Boolean` 文本或 `Boolean` 表达式来分配 `Boolean` 值，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="b4e01-156">You can also assign `Boolean` values, using either a `Boolean` literal or a `Boolean` expression, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

<span data-ttu-id="b4e01-157">同样，你可以为 `Char`、`Date`或 `Object` 数据类型的编程元素分配适当的值。</span><span class="sxs-lookup"><span data-stu-id="b4e01-157">Similarly, you can assign appropriate values to programming elements of the `Char`, `Date`, or `Object` data type.</span></span> <span data-ttu-id="b4e01-158">还可以将对象实例分配给声明为从中创建该实例的类的元素。</span><span class="sxs-lookup"><span data-stu-id="b4e01-158">You can also assign an object instance to an element declared to be of the class from which that instance is created.</span></span>

### <a name="compound-assignment-statements"></a><span data-ttu-id="b4e01-159">复合赋值语句</span><span class="sxs-lookup"><span data-stu-id="b4e01-159">Compound assignment statements</span></span>

<span data-ttu-id="b4e01-160">*复合赋值语句*首先对表达式执行操作，然后将其分配给编程元素。</span><span class="sxs-lookup"><span data-stu-id="b4e01-160">*Compound assignment statements* first perform an operation on an expression before assigning it to a programming element.</span></span> <span data-ttu-id="b4e01-161">下面的示例说明其中一个运算符 `+=`，这会将运算符左侧的变量的值增加到右侧表达式的值。</span><span class="sxs-lookup"><span data-stu-id="b4e01-161">The following example illustrates one of these operators, `+=`, which increments the value of the variable on the left side of the operator by the value of the expression on the right.</span></span>

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

<span data-ttu-id="b4e01-162">前面的示例将 `n`的值加1，然后将该新值存储在 `n`中。</span><span class="sxs-lookup"><span data-stu-id="b4e01-162">The preceding example adds 1 to the value of `n`, and then stores that new value in `n`.</span></span> <span data-ttu-id="b4e01-163">它是以下语句的速记等效项：</span><span class="sxs-lookup"><span data-stu-id="b4e01-163">It is a shorthand equivalent of the following statement:</span></span>

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

<span data-ttu-id="b4e01-164">可以使用此类型的运算符执行各种复合赋值运算。</span><span class="sxs-lookup"><span data-stu-id="b4e01-164">A variety of compound assignment operations can be performed using operators of this type.</span></span> <span data-ttu-id="b4e01-165">有关这些运算符的列表以及它们的详细信息，请参阅[赋值运算符](../../../visual-basic/language-reference/operators/assignment-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-165">For a list of these operators and more information about them, see [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md).</span></span>

<span data-ttu-id="b4e01-166">串联赋值运算符（`&=`）可用于向现有字符串的末尾添加字符串，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="b4e01-166">The concatenation assignment operator (`&=`) is useful for adding a string to the end of already existing strings, as the following example illustrates.</span></span>

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a><span data-ttu-id="b4e01-167">赋值语句中的类型转换</span><span class="sxs-lookup"><span data-stu-id="b4e01-167">Type Conversions in Assignment Statements</span></span>

<span data-ttu-id="b4e01-168">分配给变量、属性或数组元素的值必须是适合于该目标元素的数据类型。</span><span class="sxs-lookup"><span data-stu-id="b4e01-168">The value you assign to a variable, property, or array element must be of a data type appropriate to that destination element.</span></span> <span data-ttu-id="b4e01-169">通常，应尝试生成与目标元素的数据类型相同的值。</span><span class="sxs-lookup"><span data-stu-id="b4e01-169">In general, you should try to generate a value of the same data type as that of the destination element.</span></span> <span data-ttu-id="b4e01-170">但是，在赋值期间，某些类型可以转换为其他类型。</span><span class="sxs-lookup"><span data-stu-id="b4e01-170">However, some types can be converted to other types during assignment.</span></span>

<span data-ttu-id="b4e01-171">有关数据类型之间的转换的信息，请参阅[Visual Basic 中的类型转换](./data-types/type-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-171">For information on converting between data types, see [Type Conversions in Visual Basic](./data-types/type-conversions.md).</span></span> <span data-ttu-id="b4e01-172">简言之，Visual Basic 会自动将给定类型的值转换为它扩展到的任何其他类型。</span><span class="sxs-lookup"><span data-stu-id="b4e01-172">In brief, Visual Basic automatically converts a value of a given type to any other type to which it widens.</span></span> <span data-ttu-id="b4e01-173">*扩大转换*是指在运行时始终成功，不会丢失任何数据。</span><span class="sxs-lookup"><span data-stu-id="b4e01-173">A *widening conversion* is one in that always succeeds at run time and does not lose any data.</span></span> <span data-ttu-id="b4e01-174">例如，Visual Basic 在适当的情况下将 `Integer` 值转换为 `Double`，因为 `Integer` 扩大到 `Double`。</span><span class="sxs-lookup"><span data-stu-id="b4e01-174">For example, Visual Basic converts an `Integer` value to `Double` when appropriate, because `Integer` widens to `Double`.</span></span> <span data-ttu-id="b4e01-175">有关详细信息，请参阅 [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-175">For more information, see [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md).</span></span>

<span data-ttu-id="b4e01-176">*收缩转换*（不扩大的转换）在运行时或数据丢失时具有失败的风险。</span><span class="sxs-lookup"><span data-stu-id="b4e01-176">*Narrowing conversions* (those that are not widening) carry a risk of failure at run time, or of data loss.</span></span> <span data-ttu-id="b4e01-177">您可以通过使用类型转换函数显式执行收缩转换，也可以通过设置 `Option Strict Off`来指示编译器隐式执行所有转换。</span><span class="sxs-lookup"><span data-stu-id="b4e01-177">You can perform a narrowing conversion explicitly by using a type conversion function, or you can direct the compiler to perform all conversions implicitly by setting `Option Strict Off`.</span></span> <span data-ttu-id="b4e01-178">有关详细信息，请参阅[隐式和显式转换](./data-types/implicit-and-explicit-conversions.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-178">For more information, see [Implicit and Explicit Conversions](./data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="putting-multiple-statements-on-one-line"></a><span data-ttu-id="b4e01-179">在一行上放置多个语句</span><span class="sxs-lookup"><span data-stu-id="b4e01-179">Putting multiple statements on one line</span></span>

<span data-ttu-id="b4e01-180">可以在单个行上包含多个语句，并用冒号（`:`）字符分隔。</span><span class="sxs-lookup"><span data-stu-id="b4e01-180">You can have multiple statements on a single line separated by the colon (`:`) character.</span></span> <span data-ttu-id="b4e01-181">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="b4e01-181">The following example illustrates this.</span></span>

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

<span data-ttu-id="b4e01-182">尽管偶尔很方便，但这种形式的语法使您的代码更难以阅读和维护。</span><span class="sxs-lookup"><span data-stu-id="b4e01-182">Though occasionally convenient, this form of syntax makes your code hard to read and maintain.</span></span> <span data-ttu-id="b4e01-183">因此，建议您将一条语句保存到一行。</span><span class="sxs-lookup"><span data-stu-id="b4e01-183">Thus, it is recommended that you keep one statement to a line.</span></span>

## <a name="continuing-a-statement-over-multiple-lines"></a><span data-ttu-id="b4e01-184">在多行上继续执行语句</span><span class="sxs-lookup"><span data-stu-id="b4e01-184">Continuing a statement over multiple lines</span></span>

<span data-ttu-id="b4e01-185">语句通常适用于一行，但当它太长时，可以使用行继续符（包含一个空格，后跟一个下划线字符（`_`），后跟一个回车符）来继续执行下一行。</span><span class="sxs-lookup"><span data-stu-id="b4e01-185">A statement usually fits on one line, but when it is too long, you can continue it onto the next line using a line-continuation sequence, which consists of a space followed by an underscore character (`_`) followed by a carriage return.</span></span> <span data-ttu-id="b4e01-186">在下面的示例中，`MsgBox` 可执行语句将继续经过两行。</span><span class="sxs-lookup"><span data-stu-id="b4e01-186">In the following example, the `MsgBox` executable statement is continued over two lines.</span></span>

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a><span data-ttu-id="b4e01-187">隐式行继续</span><span class="sxs-lookup"><span data-stu-id="b4e01-187">Implicit line continuation</span></span>

<span data-ttu-id="b4e01-188">在许多情况下，可以在下一连续行继续执行语句，而无需使用下划线字符（`_`）。</span><span class="sxs-lookup"><span data-stu-id="b4e01-188">In many cases, you can continue a statement on the next consecutive line without using the underscore character (`_`).</span></span> <span data-ttu-id="b4e01-189">以下语法元素隐式地在下一行代码中继续执行语句。</span><span class="sxs-lookup"><span data-stu-id="b4e01-189">The following syntax elements implicitly continue the statement on the next line of code.</span></span>

- <span data-ttu-id="b4e01-190">在逗号（`,`）之后。</span><span class="sxs-lookup"><span data-stu-id="b4e01-190">After a comma (`,`).</span></span> <span data-ttu-id="b4e01-191">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-191">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- <span data-ttu-id="b4e01-192">在左括号（`(`）或右括号（`)`）之前。</span><span class="sxs-lookup"><span data-stu-id="b4e01-192">After an open parenthesis (`(`) or before a closing parenthesis (`)`).</span></span> <span data-ttu-id="b4e01-193">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-193">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- <span data-ttu-id="b4e01-194">在左大括号（`{`）之后或右大括号（`}`）之前。</span><span class="sxs-lookup"><span data-stu-id="b4e01-194">After an open curly brace (`{`) or before a closing curly brace (`}`).</span></span> <span data-ttu-id="b4e01-195">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-195">For example:</span></span>

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    <span data-ttu-id="b4e01-196">有关详细信息，请参阅[对象初始值设定项：命名类型和匿名类型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)或[集合初始值设定项](./collection-initializers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-196">For more information, see [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md) or [Collection Initializers](./collection-initializers/index.md).</span></span>

- <span data-ttu-id="b4e01-197">在 XML 文本中打开的嵌入式表达式（`<%=`）之后或在嵌入的表达式（`%>`）结束之前。</span><span class="sxs-lookup"><span data-stu-id="b4e01-197">After an open embedded expression (`<%=`) or before the close of an embedded expression (`%>`) within an XML literal.</span></span> <span data-ttu-id="b4e01-198">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-198">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   <span data-ttu-id="b4e01-199">有关详细信息，请参阅[XML 中的嵌入式表达式](./xml/embedded-expressions-in-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-199">For more information, see [Embedded Expressions in XML](./xml/embedded-expressions-in-xml.md).</span></span>

- <span data-ttu-id="b4e01-200">串联运算符（`&`）之后。</span><span class="sxs-lookup"><span data-stu-id="b4e01-200">After the concatenation operator (`&`).</span></span> <span data-ttu-id="b4e01-201">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-201">For example:</span></span>

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   <span data-ttu-id="b4e01-202">有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-202">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="b4e01-203">赋值运算符（`=`、`&=`、`:=`、`+=`、`-=`、`*=`、`/=`、`\=`、`^=`、`<<=`、`>>=`）之后。</span><span class="sxs-lookup"><span data-stu-id="b4e01-203">After assignment operators (`=`, `&=`, `:=`, `+=`, `-=`, `*=`, `/=`, `\=`, `^=`, `<<=`, `>>=`).</span></span> <span data-ttu-id="b4e01-204">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-204">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="b4e01-205">有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-205">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="b4e01-206">在表达式中的二元运算符（`+`、`-`、`/`、`*`、`Mod`、`<>`、`<`、`>`、`<=`、`>=`、`^`、`>>`、`<<`、`And`、`AndAlso`、`Or`、`OrElse`、`Like`、`Xor`）之后。</span><span class="sxs-lookup"><span data-stu-id="b4e01-206">After binary operators (`+`, `-`, `/`, `*`, `Mod`, `<>`, `<`, `>`, `<=`, `>=`, `^`, `>>`, `<<`, `And`, `AndAlso`, `Or`, `OrElse`, `Like`, `Xor`) within an expression.</span></span> <span data-ttu-id="b4e01-207">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-207">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   <span data-ttu-id="b4e01-208">有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-208">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="b4e01-209">在 `Is` 和 `IsNot` 运算符之后。</span><span class="sxs-lookup"><span data-stu-id="b4e01-209">After the `Is` and `IsNot` operators.</span></span> <span data-ttu-id="b4e01-210">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-210">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   <span data-ttu-id="b4e01-211">有关详细信息，请参阅[按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-211">For more information, see [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md).</span></span>

- <span data-ttu-id="b4e01-212">在成员限定符字符（`.`）之后、成员名称之前。</span><span class="sxs-lookup"><span data-stu-id="b4e01-212">After a member qualifier character (`.`) and before the member name.</span></span> <span data-ttu-id="b4e01-213">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-213">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   <span data-ttu-id="b4e01-214">但是，当你使用 `With` 语句或在类型的初始化列表中提供值时，必须在成员限定符后面包含行继续符（`_`）。</span><span class="sxs-lookup"><span data-stu-id="b4e01-214">However, you must include a line-continuation character (`_`) following a member qualifier character when you are using the `With` statement or supplying values in the initialization list for a type.</span></span> <span data-ttu-id="b4e01-215">使用 `With` 语句或对象初始化列表时，请考虑在赋值运算符（例如 `=`）之后中断行。</span><span class="sxs-lookup"><span data-stu-id="b4e01-215">Consider breaking the line after the assignment operator (for example, `=`) when you are using `With` statements or object initialization lists.</span></span> <span data-ttu-id="b4e01-216">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-216">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   <span data-ttu-id="b4e01-217">有关详细信息，请参阅[With .。。End With 语句](../../../visual-basic/language-reference/statements/with-end-with-statement.md)或[对象初始值设定项：命名类型和匿名类型](./objects-and-classes/object-initializers-named-and-anonymous-types.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-217">For more information, see [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md) or [Object Initializers: Named and Anonymous Types](./objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

- <span data-ttu-id="b4e01-218">在 XML 轴属性限定符之后（`.` 或 `.@` 或 `...`）。</span><span class="sxs-lookup"><span data-stu-id="b4e01-218">After an XML axis property qualifier (`.` or `.@` or `...`).</span></span> <span data-ttu-id="b4e01-219">但是，在使用 `With` 关键字时，如果指定成员限定符，则必须包含行继续符（`_`）。</span><span class="sxs-lookup"><span data-stu-id="b4e01-219">However, you must include a line-continuation character (`_`) when you specify a member qualifier when you are using the `With` keyword.</span></span> <span data-ttu-id="b4e01-220">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-220">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   <span data-ttu-id="b4e01-221">有关详细信息，请参阅[XML 轴属性](../../../visual-basic/language-reference/xml-axis/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-221">For more information, see [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>

- <span data-ttu-id="b4e01-222">在指定特性时，小于号（<）或大于号（`>`）之前。</span><span class="sxs-lookup"><span data-stu-id="b4e01-222">After a less-than sign (<) or before a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="b4e01-223">当指定特性时，还应在大于号（`>`）之后。</span><span class="sxs-lookup"><span data-stu-id="b4e01-223">Also after a greater-than sign (`>`) when you specify an attribute.</span></span> <span data-ttu-id="b4e01-224">但是，在指定程序集级别或模块级特性时，必须包含行继续符（`_`）。</span><span class="sxs-lookup"><span data-stu-id="b4e01-224">However, you must include a line-continuation character (`_`) when you specify assembly-level or module-level attributes.</span></span> <span data-ttu-id="b4e01-225">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-225">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   <span data-ttu-id="b4e01-226">有关详细信息，请参阅[属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-226">For more information, see [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md).</span></span>

- <span data-ttu-id="b4e01-227">查询运算符之前和之后（`Aggregate`、`Distinct`、`From`、`Group By`、`Group Join`、`Join`、`Let`、`Order By`、`Select`、`Skip`、`Skip While`、`Take`、`Take While`、`Where`、`In`、`Into`、`On`、`Ascending`和 `Descending`）。</span><span class="sxs-lookup"><span data-stu-id="b4e01-227">Before and after query operators (`Aggregate`, `Distinct`, `From`, `Group By`, `Group Join`, `Join`, `Let`, `Order By`, `Select`, `Skip`, `Skip While`, `Take`, `Take While`, `Where`, `In`, `Into`, `On`, `Ascending`, and `Descending`).</span></span> <span data-ttu-id="b4e01-228">不能在由多个关键字（`Order By`、`Group Join`、`Take While`和 `Skip While`）组成的查询运算符的关键字之间进行分隔。</span><span class="sxs-lookup"><span data-stu-id="b4e01-228">You cannot break a line between the keywords of query operators that are made up of multiple keywords (`Order By`, `Group Join`, `Take While`, and `Skip While`).</span></span> <span data-ttu-id="b4e01-229">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-229">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   <span data-ttu-id="b4e01-230">有关详细信息，请参阅[查询](../../../visual-basic/language-reference/queries/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-230">For more information, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span>

- <span data-ttu-id="b4e01-231">在 `For Each` 语句中 `In` 关键字之后。</span><span class="sxs-lookup"><span data-stu-id="b4e01-231">After the `In` keyword in a `For Each` statement.</span></span> <span data-ttu-id="b4e01-232">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-232">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   <span data-ttu-id="b4e01-233">有关详细信息，请参阅[For Each .。。下一语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-233">For more information, see [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>

- <span data-ttu-id="b4e01-234">集合初始值设定项中 `From` 关键字之后。</span><span class="sxs-lookup"><span data-stu-id="b4e01-234">After the `From` keyword in a collection initializer.</span></span> <span data-ttu-id="b4e01-235">例如：</span><span class="sxs-lookup"><span data-stu-id="b4e01-235">For example:</span></span>

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   <span data-ttu-id="b4e01-236">有关详细信息，请参阅[集合初始值设定项](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b4e01-236">For more information, see [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span></span>

## <a name="adding-comments"></a><span data-ttu-id="b4e01-237">添加注释</span><span class="sxs-lookup"><span data-stu-id="b4e01-237">Adding comments</span></span>

<span data-ttu-id="b4e01-238">源代码并非始终能一目了然，即使是编写它的程序员也是如此。</span><span class="sxs-lookup"><span data-stu-id="b4e01-238">Source code is not always self-explanatory, even to the programmer who wrote it.</span></span> <span data-ttu-id="b4e01-239">为帮助记录其代码，大多数程序员可以自由地利用嵌入的注释。</span><span class="sxs-lookup"><span data-stu-id="b4e01-239">To help document their code, therefore, most programmers make liberal use of embedded comments.</span></span> <span data-ttu-id="b4e01-240">代码中的注释可以解释过程或特定的指令，以便以后阅读或使用它。</span><span class="sxs-lookup"><span data-stu-id="b4e01-240">Comments in code can explain a procedure or a particular instruction to anyone reading or working with it later.</span></span> <span data-ttu-id="b4e01-241">Visual Basic 将在编译过程中忽略注释，并且它们不会影响编译的代码。</span><span class="sxs-lookup"><span data-stu-id="b4e01-241">Visual Basic ignores comments during compilation, and they do not affect the compiled code.</span></span>

<span data-ttu-id="b4e01-242">注释行以撇号（`'`）或 `REM` 后跟一个空格开头。</span><span class="sxs-lookup"><span data-stu-id="b4e01-242">Comment lines begin with an apostrophe (`'`) or `REM` followed by a space.</span></span> <span data-ttu-id="b4e01-243">它们可以添加到代码中的任何位置，但在字符串中除外。</span><span class="sxs-lookup"><span data-stu-id="b4e01-243">They can be added anywhere in code, except within a string.</span></span> <span data-ttu-id="b4e01-244">若要将注释追加到语句，请在语句后插入撇号或 `REM`，后跟注释。</span><span class="sxs-lookup"><span data-stu-id="b4e01-244">To append a comment to a statement, insert an apostrophe or `REM` after the statement, followed by the comment.</span></span> <span data-ttu-id="b4e01-245">注释还可以在单独的行上。</span><span class="sxs-lookup"><span data-stu-id="b4e01-245">Comments can also go on their own separate line.</span></span> <span data-ttu-id="b4e01-246">下面的示例演示了这些可能。</span><span class="sxs-lookup"><span data-stu-id="b4e01-246">The following example demonstrates these possibilities.</span></span>

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a><span data-ttu-id="b4e01-247">检查编译错误</span><span class="sxs-lookup"><span data-stu-id="b4e01-247">Checking compilation errors</span></span>

<span data-ttu-id="b4e01-248">如果键入代码行后，将显示带有蓝色波浪下划线的行（也可能会显示错误消息），语句中存在语法错误。</span><span class="sxs-lookup"><span data-stu-id="b4e01-248">If, after you type a line of code, the line is displayed with a wavy blue underline (an error message may appear as well), there is a syntax error in the statement.</span></span> <span data-ttu-id="b4e01-249">您必须找出语句出错的内容（通过查看任务列表，或将鼠标指针悬停在错误上并阅读错误消息），然后更正错误。</span><span class="sxs-lookup"><span data-stu-id="b4e01-249">You must find out what is wrong with the statement (by looking in the task list, or hovering over the error with the mouse pointer and reading the error message) and correct it.</span></span> <span data-ttu-id="b4e01-250">在代码中修复所有语法错误之前，程序将无法正确编译。</span><span class="sxs-lookup"><span data-stu-id="b4e01-250">Until you have fixed all syntax errors in your code, your program will fail to compile correctly.</span></span>

## <a name="related-sections"></a><span data-ttu-id="b4e01-251">相关章节</span><span class="sxs-lookup"><span data-stu-id="b4e01-251">Related sections</span></span>

|<span data-ttu-id="b4e01-252">术语</span><span class="sxs-lookup"><span data-stu-id="b4e01-252">Term</span></span>|<span data-ttu-id="b4e01-253">Definition</span><span class="sxs-lookup"><span data-stu-id="b4e01-253">Definition</span></span>|
|---|---|
|[<span data-ttu-id="b4e01-254">赋值运算符</span><span class="sxs-lookup"><span data-stu-id="b4e01-254">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)|<span data-ttu-id="b4e01-255">提供与 `=`、`*=`和 `&=`等赋值运算符相关的语言参考页面的链接。</span><span class="sxs-lookup"><span data-stu-id="b4e01-255">Provides links to language reference pages covering assignment operators such as `=`, `*=`, and `&=`.</span></span>|
|[<span data-ttu-id="b4e01-256">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="b4e01-256">Operators and Expressions</span></span>](./operators-and-expressions/index.md)|<span data-ttu-id="b4e01-257">演示如何将元素与运算符组合以生成新值。</span><span class="sxs-lookup"><span data-stu-id="b4e01-257">Shows how to combine elements with operators to yield new values.</span></span>|
|[<span data-ttu-id="b4e01-258">如何：在代码中拆分和合并语句</span><span class="sxs-lookup"><span data-stu-id="b4e01-258">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|<span data-ttu-id="b4e01-259">说明如何将单个语句分解为多行，以及如何在同一行上放置多个语句。</span><span class="sxs-lookup"><span data-stu-id="b4e01-259">Shows how to break a single statement into multiple lines and how to place multiple statements on the same line.</span></span>|
|[<span data-ttu-id="b4e01-260">如何：标记语句</span><span class="sxs-lookup"><span data-stu-id="b4e01-260">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|<span data-ttu-id="b4e01-261">说明如何为代码行添加标签。</span><span class="sxs-lookup"><span data-stu-id="b4e01-261">Shows how to label a line of code.</span></span>|

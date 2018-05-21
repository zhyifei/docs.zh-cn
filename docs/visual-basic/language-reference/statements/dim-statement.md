---
title: Dim 语句 (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: b3384b771748a1f2c9e841407042f81ce6ebe76d
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="ffec5-102">Dim 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffec5-102">Dim Statement (Visual Basic)</span></span>
<span data-ttu-id="ffec5-103">声明，并为一个或多个变量分配存储空间。</span><span class="sxs-lookup"><span data-stu-id="ffec5-103">Declares and allocates storage space for one or more variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffec5-104">语法</span><span class="sxs-lookup"><span data-stu-id="ffec5-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a><span data-ttu-id="ffec5-105">部件</span><span class="sxs-lookup"><span data-stu-id="ffec5-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="ffec5-106">可选。</span><span class="sxs-lookup"><span data-stu-id="ffec5-106">Optional.</span></span> <span data-ttu-id="ffec5-107">请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="ffec5-108">可选。</span><span class="sxs-lookup"><span data-stu-id="ffec5-108">Optional.</span></span> <span data-ttu-id="ffec5-109">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="ffec5-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="ffec5-110">Public</span><span class="sxs-lookup"><span data-stu-id="ffec5-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="ffec5-111">Protected</span><span class="sxs-lookup"><span data-stu-id="ffec5-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="ffec5-112">Friend</span><span class="sxs-lookup"><span data-stu-id="ffec5-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="ffec5-113">Private</span><span class="sxs-lookup"><span data-stu-id="ffec5-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   [<span data-ttu-id="ffec5-114">受保护的友元</span><span class="sxs-lookup"><span data-stu-id="ffec5-114">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)
    
    - [<span data-ttu-id="ffec5-115">私有受保护</span><span class="sxs-lookup"><span data-stu-id="ffec5-115">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

     <span data-ttu-id="ffec5-116">请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-116">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `Shared`  
  
     <span data-ttu-id="ffec5-117">可选。</span><span class="sxs-lookup"><span data-stu-id="ffec5-117">Optional.</span></span> <span data-ttu-id="ffec5-118">请参阅[共享](../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-118">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="ffec5-119">可选。</span><span class="sxs-lookup"><span data-stu-id="ffec5-119">Optional.</span></span> <span data-ttu-id="ffec5-120">请参阅[阴影](../../../visual-basic/language-reference/modifiers/shadows.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-120">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Static`  
  
     <span data-ttu-id="ffec5-121">可选。</span><span class="sxs-lookup"><span data-stu-id="ffec5-121">Optional.</span></span> <span data-ttu-id="ffec5-122">请参阅[静态](../../../visual-basic/language-reference/modifiers/static.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-122">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="ffec5-123">可选。</span><span class="sxs-lookup"><span data-stu-id="ffec5-123">Optional.</span></span> <span data-ttu-id="ffec5-124">请参阅[ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-124">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WithEvents`  
  
     <span data-ttu-id="ffec5-125">可选。</span><span class="sxs-lookup"><span data-stu-id="ffec5-125">Optional.</span></span> <span data-ttu-id="ffec5-126">指定的这些引用可以引发事件的类的实例的对象变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-126">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="ffec5-127">请参阅[WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-127">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>  
  
-   `variablelist`  
  
     <span data-ttu-id="ffec5-128">必须的。</span><span class="sxs-lookup"><span data-stu-id="ffec5-128">Required.</span></span> <span data-ttu-id="ffec5-129">正在此语句中声明的变量的列表。</span><span class="sxs-lookup"><span data-stu-id="ffec5-129">List of variables being declared in this statement.</span></span>  
  
     `variable [ , variable ... ]`  
  
     <span data-ttu-id="ffec5-130">每个 `variable` 都具有以下语法和部件：</span><span class="sxs-lookup"><span data-stu-id="ffec5-130">Each `variable` has the following syntax and parts:</span></span>  
  
     <span data-ttu-id="ffec5-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="ffec5-131">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="ffec5-132">部件</span><span class="sxs-lookup"><span data-stu-id="ffec5-132">Part</span></span>|<span data-ttu-id="ffec5-133">描述</span><span class="sxs-lookup"><span data-stu-id="ffec5-133">Description</span></span>|  
    |---|---|  
    |`variablename`|<span data-ttu-id="ffec5-134">必须的。</span><span class="sxs-lookup"><span data-stu-id="ffec5-134">Required.</span></span> <span data-ttu-id="ffec5-135">变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ffec5-135">Name of the variable.</span></span> <span data-ttu-id="ffec5-136">请参阅[声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-136">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
    |`boundslist`|<span data-ttu-id="ffec5-137">可选。</span><span class="sxs-lookup"><span data-stu-id="ffec5-137">Optional.</span></span> <span data-ttu-id="ffec5-138">一个数组变量的每个维度的边界的列表。</span><span class="sxs-lookup"><span data-stu-id="ffec5-138">List of bounds of each dimension of an array variable.</span></span>|  
    |`New`|<span data-ttu-id="ffec5-139">可选。</span><span class="sxs-lookup"><span data-stu-id="ffec5-139">Optional.</span></span> <span data-ttu-id="ffec5-140">创建类的新实例时`Dim`语句在运行时。</span><span class="sxs-lookup"><span data-stu-id="ffec5-140">Creates a new instance of the class when the `Dim` statement runs.</span></span>|  
    |`datatype`|<span data-ttu-id="ffec5-141">可选。</span><span class="sxs-lookup"><span data-stu-id="ffec5-141">Optional.</span></span> <span data-ttu-id="ffec5-142">变量的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ffec5-142">Data type of the variable.</span></span>|  
    |`With`|<span data-ttu-id="ffec5-143">可选。</span><span class="sxs-lookup"><span data-stu-id="ffec5-143">Optional.</span></span> <span data-ttu-id="ffec5-144">引入了对象初始值设定项列表。</span><span class="sxs-lookup"><span data-stu-id="ffec5-144">Introduces the object initializer list.</span></span>|  
    |`propertyname`|<span data-ttu-id="ffec5-145">可选。</span><span class="sxs-lookup"><span data-stu-id="ffec5-145">Optional.</span></span> <span data-ttu-id="ffec5-146">类中的属性的名称进行的实例。</span><span class="sxs-lookup"><span data-stu-id="ffec5-146">The name of a property in the class you are making an instance of.</span></span>|  
    |`propinitializer`|<span data-ttu-id="ffec5-147">需要在之后`propertyname`=。</span><span class="sxs-lookup"><span data-stu-id="ffec5-147">Required after `propertyname` =.</span></span> <span data-ttu-id="ffec5-148">指出计算并将其分配给属性名的表达式。</span><span class="sxs-lookup"><span data-stu-id="ffec5-148">The expression that is evaluated and assigned to the property name.</span></span>|  
    |`initializer`|<span data-ttu-id="ffec5-149">可选如果`New`未指定。</span><span class="sxs-lookup"><span data-stu-id="ffec5-149">Optional if `New` is not specified.</span></span> <span data-ttu-id="ffec5-150">计算并将其创建时分配给变量的表达式。</span><span class="sxs-lookup"><span data-stu-id="ffec5-150">Expression that is evaluated and assigned to the variable when it is created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffec5-151">备注</span><span class="sxs-lookup"><span data-stu-id="ffec5-151">Remarks</span></span>  
 <span data-ttu-id="ffec5-152">Visual Basic 编译器使用`Dim`语句来确定变量的数据类型和其他信息，例如哪些代码可以访问该变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-152">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="ffec5-153">下面的示例声明一个变量以保存`Integer`值。</span><span class="sxs-lookup"><span data-stu-id="ffec5-153">The following example declares a variable to hold an `Integer` value.</span></span>  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 <span data-ttu-id="ffec5-154">你可以指定任何数据类型或枚举、 结构、 类或接口的名称。</span><span class="sxs-lookup"><span data-stu-id="ffec5-154">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="ffec5-155">对于引用类型，你使用`New`关键字来创建类的新实例或结构指定的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ffec5-155">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="ffec5-156">如果你使用`New`，您不使用初始值设定项表达式。</span><span class="sxs-lookup"><span data-stu-id="ffec5-156">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="ffec5-157">相反，你提供自变量，如有必要，将从其创建变量的类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="ffec5-157">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 <span data-ttu-id="ffec5-158">你可以声明过程、 块、 类、 结构或模块中的变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-158">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="ffec5-159">不能声明源文件、 命名空间或接口中的变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-159">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="ffec5-160">有关详细信息，请参阅[声明上下文和默认访问级别](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-160">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="ffec5-161">在模块级别，在任何过程中，外部声明的变量是*成员变量*或*字段*。</span><span class="sxs-lookup"><span data-stu-id="ffec5-161">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="ffec5-162">成员变量是在其类、 结构或模块整个范围内。</span><span class="sxs-lookup"><span data-stu-id="ffec5-162">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="ffec5-163">在过程级别声明的变量是*局部变量*。</span><span class="sxs-lookup"><span data-stu-id="ffec5-163">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="ffec5-164">本地变量为仅在它们的过程或块内的作用域中。</span><span class="sxs-lookup"><span data-stu-id="ffec5-164">Local variables are in scope only within their procedure or block.</span></span>  
  
 <span data-ttu-id="ffec5-165">以下访问修饰符用于声明变量的过程之外： `Public`， `Protected`， `Friend`， `Protected Friend`，和`Private`。</span><span class="sxs-lookup"><span data-stu-id="ffec5-165">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="ffec5-166">有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-166">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="ffec5-167">`Dim`关键字是可选的并且通常忽略如果你指定任何以下修饰符： `Public`， `Protected`， `Friend`， `Protected Friend`， `Private`， `Shared`， `Shadows`， `Static`，`ReadOnly`，或`WithEvents`。</span><span class="sxs-lookup"><span data-stu-id="ffec5-167">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 <span data-ttu-id="ffec5-168">如果`Option Explicit`是 （默认值），编译器要求声明为你使用每个变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-168">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="ffec5-169">有关详细信息，请参阅[Option Explicit 语句](../../../visual-basic/language-reference/statements/option-explicit-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-169">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>  
  
## <a name="specifying-an-initial-value"></a><span data-ttu-id="ffec5-170">指定的初始值</span><span class="sxs-lookup"><span data-stu-id="ffec5-170">Specifying an Initial Value</span></span>  
 <span data-ttu-id="ffec5-171">创建时，你可以将值赋给变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-171">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="ffec5-172">对于值类型，你使用*初始值设定项*来提供要分配给变量的表达式。</span><span class="sxs-lookup"><span data-stu-id="ffec5-172">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="ffec5-173">表达式计算结果必须为一个常数，可以在编译时计算。</span><span class="sxs-lookup"><span data-stu-id="ffec5-173">The expression must evaluate to a constant that can be calculated at compile time.</span></span>  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 <span data-ttu-id="ffec5-174">如果指定一个初始值设定项，并且数据类型中未指定`As`子句，*类型推理*用于推断初始值设定项中的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ffec5-174">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="ffec5-175">在下面的示例中，同时`num1`和`num2`强类型为整数。</span><span class="sxs-lookup"><span data-stu-id="ffec5-175">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="ffec5-176">在第二个声明中，类型推理推断出类型 3 的值。</span><span class="sxs-lookup"><span data-stu-id="ffec5-176">In the second declaration, type inference infers the type from the value 3.</span></span>  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 <span data-ttu-id="ffec5-177">类型推理在过程级别适用。</span><span class="sxs-lookup"><span data-stu-id="ffec5-177">Type inference applies at the procedure level.</span></span> <span data-ttu-id="ffec5-178">它不适用于类、 结构、 模块或接口中的过程之外。</span><span class="sxs-lookup"><span data-stu-id="ffec5-178">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="ffec5-179">有关类型推理的详细信息，请参阅[Option Infer 语句](../../../visual-basic/language-reference/statements/option-infer-statement.md)和[本地类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-179">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="ffec5-180">有关数据类型或初始值设定项未指定时，会发生什么情况的信息，请参阅[默认数据类型和值](../../../visual-basic/language-reference/statements/dim-statement.md#default)本主题中更高版本。</span><span class="sxs-lookup"><span data-stu-id="ffec5-180">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>  
  
 <span data-ttu-id="ffec5-181">你可以使用*对象初始值设定项*声明命名类型和匿名类型的实例。</span><span class="sxs-lookup"><span data-stu-id="ffec5-181">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="ffec5-182">下面的代码创建的实例`Student`类，并使用对象初始值设定项来初始化属性。</span><span class="sxs-lookup"><span data-stu-id="ffec5-182">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 <span data-ttu-id="ffec5-183">有关对象初始值设定项的详细信息，请参阅[如何： 使用对象初始值设定项声明对象](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)，[对象初始值设定项： 命名类型和匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)，和[匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="ffec5-183">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="declaring-multiple-variables"></a><span data-ttu-id="ffec5-184">声明多个变量</span><span class="sxs-lookup"><span data-stu-id="ffec5-184">Declaring Multiple Variables</span></span>  
 <span data-ttu-id="ffec5-185">您可以声明一个声明语句中的多个变量用括号指定为每个，并按照每个数组名称的变量名称。</span><span class="sxs-lookup"><span data-stu-id="ffec5-185">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="ffec5-186">以逗号分隔多个变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-186">Multiple variables are separated by commas.</span></span>  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 <span data-ttu-id="ffec5-187">如果声明多个变量具有一个`As`子句，也不能提供该组的变量的初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="ffec5-187">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>  
  
 <span data-ttu-id="ffec5-188">你可以通过使用单独指定为不同的变量的不同的数据类型`As`子句为每个声明的变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-188">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="ffec5-189">每个变量采用中第一个指定的数据类型`As`子句遇到后其`variablename`一部分。</span><span class="sxs-lookup"><span data-stu-id="ffec5-189">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a><span data-ttu-id="ffec5-190">数组</span><span class="sxs-lookup"><span data-stu-id="ffec5-190">Arrays</span></span>  
 <span data-ttu-id="ffec5-191">你可以声明一个变量以保存*数组*，后者可以容纳多个值。</span><span class="sxs-lookup"><span data-stu-id="ffec5-191">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="ffec5-192">若要指定变量包含一个数组，请按照其`variablename`后面紧跟一对括号。</span><span class="sxs-lookup"><span data-stu-id="ffec5-192">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="ffec5-193">有关数组的详细信息，请参阅[数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-193">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="ffec5-194">你可以指定的下限和上限的数组的每个维度。</span><span class="sxs-lookup"><span data-stu-id="ffec5-194">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="ffec5-195">若要执行此操作，包括`boundslist`在括号内。</span><span class="sxs-lookup"><span data-stu-id="ffec5-195">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="ffec5-196">为每个维度，`boundslist`指定上限和下限 （可选）。</span><span class="sxs-lookup"><span data-stu-id="ffec5-196">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="ffec5-197">下限始终为零，或不指定它是否。</span><span class="sxs-lookup"><span data-stu-id="ffec5-197">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="ffec5-198">每个索引可能会不同于通过其上界值零。</span><span class="sxs-lookup"><span data-stu-id="ffec5-198">Each index can vary from zero through its upper bound value.</span></span>  
  
 <span data-ttu-id="ffec5-199">下面的两个语句是等效的。</span><span class="sxs-lookup"><span data-stu-id="ffec5-199">The following two statements are equivalent.</span></span> <span data-ttu-id="ffec5-200">每个语句声明数组 21`Integer`元素。</span><span class="sxs-lookup"><span data-stu-id="ffec5-200">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="ffec5-201">访问数组时，索引可能会不同于 0 到 20。</span><span class="sxs-lookup"><span data-stu-id="ffec5-201">When you access the array, the index can vary from 0 through 20.</span></span>  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 <span data-ttu-id="ffec5-202">下面的语句声明类型的一个二维数组`Double`。</span><span class="sxs-lookup"><span data-stu-id="ffec5-202">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="ffec5-203">数组有 6 列 (5 + 1) 每个 4 行 (3 + 1)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-203">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="ffec5-204">请注意，上限表示的索引，不维的长度的最大可能值。</span><span class="sxs-lookup"><span data-stu-id="ffec5-204">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="ffec5-205">维度的长度为上边界加 1。</span><span class="sxs-lookup"><span data-stu-id="ffec5-205">The length of the dimension is the upper bound plus one.</span></span>  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 <span data-ttu-id="ffec5-206">数组可以有 1 到 32 的维度。</span><span class="sxs-lookup"><span data-stu-id="ffec5-206">An array can have from 1 to 32 dimensions.</span></span>  
  
 <span data-ttu-id="ffec5-207">你可以将所有边界在一个数组声明以留空。</span><span class="sxs-lookup"><span data-stu-id="ffec5-207">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="ffec5-208">如果这样做，数组将具有你指定的维度数，但不会被初始化。</span><span class="sxs-lookup"><span data-stu-id="ffec5-208">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="ffec5-209">它具有的值`Nothing`之前至少初始化的某些元素。</span><span class="sxs-lookup"><span data-stu-id="ffec5-209">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="ffec5-210">`Dim`语句必须指定用于所有维度或任何维度的边界。</span><span class="sxs-lookup"><span data-stu-id="ffec5-210">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 <span data-ttu-id="ffec5-211">如果数组具有多个维度，必须包含以逗号分隔括号以指示维度数。</span><span class="sxs-lookup"><span data-stu-id="ffec5-211">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 <span data-ttu-id="ffec5-212">你可以声明*零长度数组*通过声明一个要为-1 的数组的维度。</span><span class="sxs-lookup"><span data-stu-id="ffec5-212">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="ffec5-213">包含一个零长度数组的变量不具有值`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="ffec5-213">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="ffec5-214">零长度数组所需的某些公共语言运行时函数。</span><span class="sxs-lookup"><span data-stu-id="ffec5-214">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="ffec5-215">如果你尝试访问这样的数组，则会发生运行时异常。</span><span class="sxs-lookup"><span data-stu-id="ffec5-215">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="ffec5-216">有关详细信息，请参阅[数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-216">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="ffec5-217">可以通过使用数组文本初始化的数组的值。</span><span class="sxs-lookup"><span data-stu-id="ffec5-217">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="ffec5-218">若要执行此操作，括住的初始化值用括号 (`{}`)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-218">To do this, surround the initialization values with braces (`{}`).</span></span>  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 <span data-ttu-id="ffec5-219">对于多维数组，每个单独的维度的初始化括在外部的维度中的大括号中。</span><span class="sxs-lookup"><span data-stu-id="ffec5-219">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="ffec5-220">按行优先顺序来指定元素。</span><span class="sxs-lookup"><span data-stu-id="ffec5-220">The elements are specified in row-major order.</span></span>  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 <span data-ttu-id="ffec5-221">有关数组文本的详细信息，请参阅[数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-221">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
##  <a name="default"></a> <span data-ttu-id="ffec5-222">默认数据类型和值</span><span class="sxs-lookup"><span data-stu-id="ffec5-222">Default Data Types and Values</span></span>  
 <span data-ttu-id="ffec5-223">下表描述了指定 `Dim` 语句中数据类型和初始值设定项的各种组合的结果。</span><span class="sxs-lookup"><span data-stu-id="ffec5-223">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="ffec5-224">是否指定数据类型？</span><span class="sxs-lookup"><span data-stu-id="ffec5-224">Data type specified?</span></span>|<span data-ttu-id="ffec5-225">是否指定初始值设定项？</span><span class="sxs-lookup"><span data-stu-id="ffec5-225">Initializer specified?</span></span>|<span data-ttu-id="ffec5-226">示例</span><span class="sxs-lookup"><span data-stu-id="ffec5-226">Example</span></span>|<span data-ttu-id="ffec5-227">结果</span><span class="sxs-lookup"><span data-stu-id="ffec5-227">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="ffec5-228">否</span><span class="sxs-lookup"><span data-stu-id="ffec5-228">No</span></span>|<span data-ttu-id="ffec5-229">否</span><span class="sxs-lookup"><span data-stu-id="ffec5-229">No</span></span>|`Dim qty`|<span data-ttu-id="ffec5-230">如果[Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md)为 off （默认），则变量设置为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="ffec5-230">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="ffec5-231">如果 `Option Strict` 处于打开状态，则发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="ffec5-231">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="ffec5-232">否</span><span class="sxs-lookup"><span data-stu-id="ffec5-232">No</span></span>|<span data-ttu-id="ffec5-233">是</span><span class="sxs-lookup"><span data-stu-id="ffec5-233">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="ffec5-234">如果[Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)位于 （默认值），则变量采用数据类型的初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="ffec5-234">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="ffec5-235">请参阅[局部类型推理](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-235">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="ffec5-236">如果 `Option Infer` 和 `Option Strict` 均处于关闭状态，则变量采用 `Object` 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ffec5-236">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="ffec5-237">如果 `Option Infer` 处于关闭状态但 `Option Strict` 处于打开状态，则发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="ffec5-237">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="ffec5-238">是</span><span class="sxs-lookup"><span data-stu-id="ffec5-238">Yes</span></span>|<span data-ttu-id="ffec5-239">否</span><span class="sxs-lookup"><span data-stu-id="ffec5-239">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="ffec5-240">将变量初始化为数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="ffec5-240">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="ffec5-241">请参阅本节后面的表。</span><span class="sxs-lookup"><span data-stu-id="ffec5-241">See the table later in this section.</span></span>|  
|<span data-ttu-id="ffec5-242">是</span><span class="sxs-lookup"><span data-stu-id="ffec5-242">Yes</span></span>|<span data-ttu-id="ffec5-243">是</span><span class="sxs-lookup"><span data-stu-id="ffec5-243">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="ffec5-244">如果初始值设定项的数据类型不可转换为指定数据类型，则会发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="ffec5-244">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
 <span data-ttu-id="ffec5-245">如果你指定的数据类型，但不是指定初始值设定项，Visual Basic 将变量初始化为其数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="ffec5-245">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="ffec5-246">下表显示的默认初始化值。</span><span class="sxs-lookup"><span data-stu-id="ffec5-246">The following table shows the default initialization values.</span></span>  
  
|<span data-ttu-id="ffec5-247">数据类型</span><span class="sxs-lookup"><span data-stu-id="ffec5-247">Data type</span></span>|<span data-ttu-id="ffec5-248">默认值</span><span class="sxs-lookup"><span data-stu-id="ffec5-248">Default value</span></span>|  
|---|---|  
|<span data-ttu-id="ffec5-249">所有数值类型 (包括`Byte`和`SByte`)</span><span class="sxs-lookup"><span data-stu-id="ffec5-249">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="ffec5-250">0</span><span class="sxs-lookup"><span data-stu-id="ffec5-250">0</span></span>|  
|`Char`|<span data-ttu-id="ffec5-251">二进制 0</span><span class="sxs-lookup"><span data-stu-id="ffec5-251">Binary 0</span></span>|  
|<span data-ttu-id="ffec5-252">所有引用类型 (包括`Object`， `String`，和所有数组)</span><span class="sxs-lookup"><span data-stu-id="ffec5-252">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|<span data-ttu-id="ffec5-253">1 年 1 月 1 日 12:00 AM (01/01/0001 12:00:00 AM)</span><span class="sxs-lookup"><span data-stu-id="ffec5-253">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|  
  
 <span data-ttu-id="ffec5-254">一个结构的每个元素初始化就像它是单独的变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-254">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="ffec5-255">如果你声明一个数组的长度，但不是初始化它的元素，每个元素将初始化就像它是单独的变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-255">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>  
  
## <a name="static-local-variable-lifetime"></a><span data-ttu-id="ffec5-256">静态本地变量的生存期</span><span class="sxs-lookup"><span data-stu-id="ffec5-256">Static Local Variable Lifetime</span></span>  
 <span data-ttu-id="ffec5-257">A`Static`本地变量具有比在其中声明该过程的更长的生存期。</span><span class="sxs-lookup"><span data-stu-id="ffec5-257">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="ffec5-258">变量的生存期的边界依赖于过程的声明位置，以及是否有`Shared`。</span><span class="sxs-lookup"><span data-stu-id="ffec5-258">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>  
  
|<span data-ttu-id="ffec5-259">过程声明</span><span class="sxs-lookup"><span data-stu-id="ffec5-259">Procedure declaration</span></span>|<span data-ttu-id="ffec5-260">初始化变量</span><span class="sxs-lookup"><span data-stu-id="ffec5-260">Variable initialized</span></span>|<span data-ttu-id="ffec5-261">变量停止现有</span><span class="sxs-lookup"><span data-stu-id="ffec5-261">Variable stops existing</span></span>|  
|---|---|---|  
|<span data-ttu-id="ffec5-262">模块中</span><span class="sxs-lookup"><span data-stu-id="ffec5-262">In a module</span></span>|<span data-ttu-id="ffec5-263">在首次调用该过程</span><span class="sxs-lookup"><span data-stu-id="ffec5-263">The first time the procedure is called</span></span>|<span data-ttu-id="ffec5-264">当程序停止执行</span><span class="sxs-lookup"><span data-stu-id="ffec5-264">When your program stops execution</span></span>|  
|<span data-ttu-id="ffec5-265">在类或结构，过程是 `Shared`</span><span class="sxs-lookup"><span data-stu-id="ffec5-265">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="ffec5-266">第一次该过程称为某个特定实例上或对类或结构本身</span><span class="sxs-lookup"><span data-stu-id="ffec5-266">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="ffec5-267">当程序停止执行</span><span class="sxs-lookup"><span data-stu-id="ffec5-267">When your program stops execution</span></span>|  
|<span data-ttu-id="ffec5-268">在类或结构，过程并不 `Shared`</span><span class="sxs-lookup"><span data-stu-id="ffec5-268">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="ffec5-269">第一次特定实例上调用过程</span><span class="sxs-lookup"><span data-stu-id="ffec5-269">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="ffec5-270">当垃圾回收 (GC) 释放该实例</span><span class="sxs-lookup"><span data-stu-id="ffec5-270">When the instance is released for garbage collection (GC)</span></span>|  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="ffec5-271">特性和修饰符</span><span class="sxs-lookup"><span data-stu-id="ffec5-271">Attributes and Modifiers</span></span>  
 <span data-ttu-id="ffec5-272">仅对成员变量上，而不是本地变量，你可以应用特性。</span><span class="sxs-lookup"><span data-stu-id="ffec5-272">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="ffec5-273">属性提供信息对程序集的元数据，这并没有意义的临时存储，例如本地变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-273">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>  
  
 <span data-ttu-id="ffec5-274">在模块级别，不能使用`Static`修饰符来声明变量的成员。</span><span class="sxs-lookup"><span data-stu-id="ffec5-274">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="ffec5-275">在过程级别，不能使用`Shared`， `Shadows`， `ReadOnly`， `WithEvents`，或任何访问修饰符来声明本地变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-275">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>  
  
 <span data-ttu-id="ffec5-276">你可以指定哪些代码可以通过提供访问变量`accessmodifier`。</span><span class="sxs-lookup"><span data-stu-id="ffec5-276">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="ffec5-277">类和模块成员 （任何过程） 之外的变量默认为私有访问，并使用结构成员变量默认的公共访问权限。</span><span class="sxs-lookup"><span data-stu-id="ffec5-277">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="ffec5-278">你可以调整其访问级别有访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="ffec5-278">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="ffec5-279">不能在 （过程） 中的本地变量上使用访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="ffec5-279">You cannot use access modifiers on local variables (inside a procedure).</span></span>  
  
 <span data-ttu-id="ffec5-280">你可以指定`WithEvents`仅在成员变量上，而不是上一个过程中本地变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-280">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="ffec5-281">如果指定`WithEvents`，该变量的数据类型必须是特定类类型，不`Object`。</span><span class="sxs-lookup"><span data-stu-id="ffec5-281">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="ffec5-282">你不能声明具有数组`WithEvents`。</span><span class="sxs-lookup"><span data-stu-id="ffec5-282">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="ffec5-283">有关事件的详细信息，请参阅[事件](../../../visual-basic/programming-guide/language-features/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-283">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ffec5-284">代码类之外，结构或模块必须限定该类、 结构或模块的名称的成员变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ffec5-284">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="ffec5-285">之外的过程或块不能引用该过程或块中任何本地变量的代码。</span><span class="sxs-lookup"><span data-stu-id="ffec5-285">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>  
  
## <a name="releasing-managed-resources"></a><span data-ttu-id="ffec5-286">释放托管的资源</span><span class="sxs-lookup"><span data-stu-id="ffec5-286">Releasing Managed Resources</span></span>  
 <span data-ttu-id="ffec5-287">.NET Framework 垃圾回收器释放托管资源而无需您采取任何额外编码。</span><span class="sxs-lookup"><span data-stu-id="ffec5-287">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="ffec5-288">但是，你可以强制资源的托管资源而不是等待垃圾回收器释放。</span><span class="sxs-lookup"><span data-stu-id="ffec5-288">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="ffec5-289">如果一个类持有特别有价值且稀缺资源 （如数据库连接或文件句柄），你可能不想等待下一步的垃圾回收，以清理不再使用的类实例。</span><span class="sxs-lookup"><span data-stu-id="ffec5-289">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="ffec5-290">类可以实现<xref:System.IDisposable>接口提供一种方法来释放垃圾回收之前的资源。</span><span class="sxs-lookup"><span data-stu-id="ffec5-290">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="ffec5-291">实现该接口的类公开`Dispose`可以调用以进行强制宝贵的资源以立即释放的方法。</span><span class="sxs-lookup"><span data-stu-id="ffec5-291">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>  
  
 <span data-ttu-id="ffec5-292">`Using`语句获取资源、 执行一组语句，然后释放资源的过程进行自动化。</span><span class="sxs-lookup"><span data-stu-id="ffec5-292">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="ffec5-293">但是，必须实现资源<xref:System.IDisposable>接口。</span><span class="sxs-lookup"><span data-stu-id="ffec5-293">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="ffec5-294">有关详细信息，请参阅 [Using 语句](../../../visual-basic/language-reference/statements/using-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="ffec5-294">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffec5-295">示例</span><span class="sxs-lookup"><span data-stu-id="ffec5-295">Example</span></span>  
 <span data-ttu-id="ffec5-296">下面的示例通过使用声明变量`Dim`语句使用各种选项。</span><span class="sxs-lookup"><span data-stu-id="ffec5-296">The following example declares variables by using the `Dim` statement with various options.</span></span>  
  
 [!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="ffec5-297">示例</span><span class="sxs-lookup"><span data-stu-id="ffec5-297">Example</span></span>  
 <span data-ttu-id="ffec5-298">下面的示例列出介于 1 和 30 之间的质数。</span><span class="sxs-lookup"><span data-stu-id="ffec5-298">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="ffec5-299">代码注释中描述了本地变量的作用域。</span><span class="sxs-lookup"><span data-stu-id="ffec5-299">The scope of local variables is described in code comments.</span></span>  
  
 [!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="ffec5-300">示例</span><span class="sxs-lookup"><span data-stu-id="ffec5-300">Example</span></span>  
 <span data-ttu-id="ffec5-301">在下面的示例中，`speedValue`在类级别声明变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-301">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="ffec5-302">`Private`关键字用于声明变量。</span><span class="sxs-lookup"><span data-stu-id="ffec5-302">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="ffec5-303">中的任何过程可以访问此变量`Car`类。</span><span class="sxs-lookup"><span data-stu-id="ffec5-303">The variable can be accessed by any procedure in the `Car` class.</span></span>  
  
 [!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ffec5-304">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffec5-304">See Also</span></span>  
 [<span data-ttu-id="ffec5-305">Const 语句</span><span class="sxs-lookup"><span data-stu-id="ffec5-305">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="ffec5-306">ReDim 语句</span><span class="sxs-lookup"><span data-stu-id="ffec5-306">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="ffec5-307">Option Explicit 语句</span><span class="sxs-lookup"><span data-stu-id="ffec5-307">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="ffec5-308">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="ffec5-308">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="ffec5-309">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="ffec5-309">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="ffec5-310">“项目设计器”->“编译”页 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffec5-310">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [<span data-ttu-id="ffec5-311">变量声明</span><span class="sxs-lookup"><span data-stu-id="ffec5-311">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="ffec5-312">数组</span><span class="sxs-lookup"><span data-stu-id="ffec5-312">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="ffec5-313">对象初始值设定项：命名类型和匿名类型</span><span class="sxs-lookup"><span data-stu-id="ffec5-313">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="ffec5-314">匿名类型</span><span class="sxs-lookup"><span data-stu-id="ffec5-314">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="ffec5-315">对象初始值设定项：命名类型和匿名类型</span><span class="sxs-lookup"><span data-stu-id="ffec5-315">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="ffec5-316">如何：使用对象初始值设定项声明对象</span><span class="sxs-lookup"><span data-stu-id="ffec5-316">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)  
 [<span data-ttu-id="ffec5-317">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="ffec5-317">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)

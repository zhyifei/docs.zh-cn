---
title: 如何：声明并在 Visual Basic 中调用默认属性
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: 9ca9a0ccdac3ac13429928233a0c09d58427ce74
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295635"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="0ceb7-102">如何：声明并在 Visual Basic 中调用默认属性</span><span class="sxs-lookup"><span data-stu-id="0ceb7-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="0ceb7-103">一个*默认属性*是一个类或结构的属性，而无需指定它可以访问你的代码。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="0ceb7-104">当调用代码名称的类或结构，但未一个属性和上下文允许访问某一属性时，Visual Basic 对该类或结构的默认属性解析的访问权限，如果存在。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-104">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="0ceb7-105">类或结构最多可以有一个默认属性。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="0ceb7-106">但是，可以重载默认属性，并且具有多个版本。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="0ceb7-107">有关详细信息，请参阅[默认](../../../../visual-basic/language-reference/modifiers/default.md)。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="0ceb7-108">若要声明默认属性</span><span class="sxs-lookup"><span data-stu-id="0ceb7-108">To declare a default property</span></span>  
  
1. <span data-ttu-id="0ceb7-109">以正常方式声明的属性。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-109">Declare the property in the normal way.</span></span> <span data-ttu-id="0ceb7-110">未指定`Shared`或`Private`关键字。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2. <span data-ttu-id="0ceb7-111">包括`Default`属性声明中的关键字。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3. <span data-ttu-id="0ceb7-112">指定至少一个参数的属性。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="0ceb7-113">不能定义不采用任何参数的默认属性。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="0ceb7-114">若要调用默认属性</span><span class="sxs-lookup"><span data-stu-id="0ceb7-114">To call a default property</span></span>  
  
1. <span data-ttu-id="0ceb7-115">声明包含的类或结构类型的变量。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. <span data-ttu-id="0ceb7-116">使用的表达式中单独的变量名称通常要包括的属性名称。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. <span data-ttu-id="0ceb7-117">变量名后面加上括号中的参数列表。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="0ceb7-118">默认属性需要至少一个参数。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. <span data-ttu-id="0ceb7-119">若要检索默认属性值，请使用变量名称，其自变量列表，或等号后面的表达式中 (`=`) 在赋值语句登录。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. <span data-ttu-id="0ceb7-120">若要设置默认属性值，使用其自变量列表，在赋值语句左侧的变量的名称。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. <span data-ttu-id="0ceb7-121">就像访问任何其他属性一样，始终可以指定默认属性名以及变量名。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="0ceb7-122">示例</span><span class="sxs-lookup"><span data-stu-id="0ceb7-122">Example</span></span>  
 <span data-ttu-id="0ceb7-123">下面的示例声明了默认属性的类上。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="0ceb7-124">示例</span><span class="sxs-lookup"><span data-stu-id="0ceb7-124">Example</span></span>  
 <span data-ttu-id="0ceb7-125">下面的示例演示如何调用默认属性`myProperty`类上`class1`。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="0ceb7-126">三个赋值语句存储中的值`myProperty`，和<xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>调用读取这些值。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 <span data-ttu-id="0ceb7-127">默认属性的最常见用途是<xref:Microsoft.VisualBasic.Collection.Item%2A>对各种集合类型的属性。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0ceb7-128">可靠编程</span><span class="sxs-lookup"><span data-stu-id="0ceb7-128">Robust Programming</span></span>  
 <span data-ttu-id="0ceb7-129">默认属性可能会导致小减少源代码的字符，但它们会使代码更难以阅读。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="0ceb7-130">如果发出对类或结构名称的引用时，调用代码不熟悉你的类或结构，它无法确定该引用访问的类或结构本身或默认属性。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="0ceb7-131">这可能会导致编译器错误或细微的运行时逻辑错误。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="0ceb7-132">您可以始终使用某种程度上减少默认属性错误的可能性[Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)设置编译器类型检查到`On`。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="0ceb7-133">如果想要使用预定义的类或结构在代码中，您必须确定是否具有默认属性，以及如果成功，其名称是什么。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="0ceb7-134">由于这些缺点，应考虑未定义默认属性。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="0ceb7-135">代码的可读性，应该还考虑始终显式引用的所有属性，包括默认属性。</span><span class="sxs-lookup"><span data-stu-id="0ceb7-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ceb7-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ceb7-136">See also</span></span>

- [<span data-ttu-id="0ceb7-137">Property 过程</span><span class="sxs-lookup"><span data-stu-id="0ceb7-137">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="0ceb7-138">过程形参和实参</span><span class="sxs-lookup"><span data-stu-id="0ceb7-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="0ceb7-139">Property Statement</span><span class="sxs-lookup"><span data-stu-id="0ceb7-139">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="0ceb7-140">默认</span><span class="sxs-lookup"><span data-stu-id="0ceb7-140">Default</span></span>](../../../../visual-basic/language-reference/modifiers/default.md)
- [<span data-ttu-id="0ceb7-141">Visual Basic 中属性和变量的差异</span><span class="sxs-lookup"><span data-stu-id="0ceb7-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="0ceb7-142">如何：创建属性</span><span class="sxs-lookup"><span data-stu-id="0ceb7-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="0ceb7-143">如何：声明具有混合访问级别的属性</span><span class="sxs-lookup"><span data-stu-id="0ceb7-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="0ceb7-144">如何：调用 Property 过程</span><span class="sxs-lookup"><span data-stu-id="0ceb7-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="0ceb7-145">如何：在属性中放置值</span><span class="sxs-lookup"><span data-stu-id="0ceb7-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="0ceb7-146">如何：从属性获取值</span><span class="sxs-lookup"><span data-stu-id="0ceb7-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)

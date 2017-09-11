---
title: "如何︰ 为过程 (Visual Basic 中) 中定义参数 |Microsoft 文档"
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
- procedure parameters, defining data types for
- procedures, parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters, defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: 15
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
ms.openlocfilehash: 5a29bab1c18920d293c51d83d4d8cffdcefe936c
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="37723-102">如何：为过程定义参数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37723-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>
<span data-ttu-id="37723-103">一个*参数*允许调用的代码将值传递给该过程，在它调用时。</span><span class="sxs-lookup"><span data-stu-id="37723-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="37723-104">声明一个过程的每个参数相同的方式声明变量，指定其名称和数据类型。</span><span class="sxs-lookup"><span data-stu-id="37723-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="37723-105">您还指定传递机制，以及该参数是否可选。</span><span class="sxs-lookup"><span data-stu-id="37723-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="37723-106">有关详细信息，请参阅[过程参数和变量](./procedure-parameters-and-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="37723-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="37723-107">若要定义过程参数</span><span class="sxs-lookup"><span data-stu-id="37723-107">To define a procedure parameter</span></span>  
  
1.  <span data-ttu-id="37723-108">在过程声明中，将添加到过程的参数列表，用逗号将它与其他参数的参数名称。</span><span class="sxs-lookup"><span data-stu-id="37723-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2.  <span data-ttu-id="37723-109">确定参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="37723-109">Decide the data type of the parameter.</span></span>  
  
3.  <span data-ttu-id="37723-110">请按照参数名称后的加`As`子句来指定数据类型。</span><span class="sxs-lookup"><span data-stu-id="37723-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4.  <span data-ttu-id="37723-111">确定所需的参数的传递机制。</span><span class="sxs-lookup"><span data-stu-id="37723-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="37723-112">通常情况下参数按值传递，除非您想要能够更改它的值调用的代码中的过程。</span><span class="sxs-lookup"><span data-stu-id="37723-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5.  <span data-ttu-id="37723-113">参数名称前面加上[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)或[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)指定传递机制。</span><span class="sxs-lookup"><span data-stu-id="37723-113">Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="37723-114">有关详细信息，请参阅[差异之间传递的参数值和通过引用来](./differences-between-passing-an-argument-by-value-and-by-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="37723-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6.  <span data-ttu-id="37723-115">如果该参数是可选的在前面的传递机制与[可选](../../../../visual-basic/language-reference/modifiers/optional.md)，然后按照参数的数据类型以等号 (`=`) 和默认值。</span><span class="sxs-lookup"><span data-stu-id="37723-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="37723-116">下面的示例定义的轮廓`Sub`带有三个参数的过程。</span><span class="sxs-lookup"><span data-stu-id="37723-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="37723-117">前两个要求，并且第三个是可选的。</span><span class="sxs-lookup"><span data-stu-id="37723-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="37723-118">参数声明由逗号分隔的参数列表中。</span><span class="sxs-lookup"><span data-stu-id="37723-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     <span data-ttu-id="37723-119">[!code-vb[VbVbcnProcedures 第&33;](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="37723-119">[!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="37723-120">第一个参数接受`customer`对象，并`updateCustomer`可以直接更新该变量传递给`c`因为则参数进行传递[ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)。</span><span class="sxs-lookup"><span data-stu-id="37723-120">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="37723-121">该过程不能更改最后两个参数的值，因为它们传递[ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)。</span><span class="sxs-lookup"><span data-stu-id="37723-121">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="37723-122">如果调用代码不会提供的值`level`参数，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]将其设置为默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="37723-122">If the calling code does not supply a value for the `level` parameter, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="37723-123">如果类型检查开关 ([Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) 是`Off`、`As`子句是可选的当您定义参数。</span><span class="sxs-lookup"><span data-stu-id="37723-123">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="37723-124">但是，如果任何一个参数使用`As`子句中，所有人必须使用它。</span><span class="sxs-lookup"><span data-stu-id="37723-124">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="37723-125">如果类型检查开关是`On`、`As`子句是必需的每个参数定义。</span><span class="sxs-lookup"><span data-stu-id="37723-125">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="37723-126">指定所有编程元素的数据类型被称为*强类型化*。</span><span class="sxs-lookup"><span data-stu-id="37723-126">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="37723-127">当您将设置`Option Strict On`，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]强制使用强类型化。</span><span class="sxs-lookup"><span data-stu-id="37723-127">When you set `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enforces strong typing.</span></span> <span data-ttu-id="37723-128">这是强烈建议，原因如下︰</span><span class="sxs-lookup"><span data-stu-id="37723-128">This is strongly recommended, for the following reasons:</span></span>  
  
    -   <span data-ttu-id="37723-129">它使您的变量和参数的 IntelliSense 支持。</span><span class="sxs-lookup"><span data-stu-id="37723-129">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="37723-130">这样，您可以在您的代码中键入时看到它们的属性和其他成员。</span><span class="sxs-lookup"><span data-stu-id="37723-130">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    -   <span data-ttu-id="37723-131">它允许编译器执行类型检查。</span><span class="sxs-lookup"><span data-stu-id="37723-131">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="37723-132">这可帮助捕获在运行时由于如溢出错误而失败的语句。</span><span class="sxs-lookup"><span data-stu-id="37723-132">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="37723-133">不支持它们的对象，它还捕获对方法的调用。</span><span class="sxs-lookup"><span data-stu-id="37723-133">It also catches calls to methods on objects that do not support them.</span></span>  
  
    -   <span data-ttu-id="37723-134">这会导致更快地执行代码。</span><span class="sxs-lookup"><span data-stu-id="37723-134">It results in faster execution of your code.</span></span> <span data-ttu-id="37723-135">一种的原因是，如果您未指定的编程元素的数据类型[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器将其分配`Object`类型。</span><span class="sxs-lookup"><span data-stu-id="37723-135">One reason for this is that if you do not specify a data type for a programming element, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler assigns it the `Object` type.</span></span> <span data-ttu-id="37723-136">已编译的代码可能需要将之间来回转换`Object`和其他数据类型，这会降低性能。</span><span class="sxs-lookup"><span data-stu-id="37723-136">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37723-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37723-137">See Also</span></span>  
 <span data-ttu-id="37723-138">[过程](./index.md) </span><span class="sxs-lookup"><span data-stu-id="37723-138">[Procedures](./index.md) </span></span>  
<span data-ttu-id="37723-139"> [Sub 过程](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="37723-139"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="37723-140"> [Function 过程](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="37723-140"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="37723-141"> [如何︰ 将参数传递给过程](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="37723-141"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="37723-142"> [通过值和通过引用传递参数](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="37723-142"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="37723-143"> [递归过程](./recursive-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="37723-143"> [Recursive Procedures](./recursive-procedures.md) </span></span>  
<span data-ttu-id="37723-144"> [过程重载](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="37723-144"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="37723-145"> [对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="37723-145"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="37723-146"> [面向对象的编程](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span><span class="sxs-lookup"><span data-stu-id="37723-146"> [Object-Oriented Programming](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span></span>

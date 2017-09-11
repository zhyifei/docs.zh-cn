---
title: "在 Visual Basic 中的变量声明 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables, declarations
- Dim statement, variable declaration
- declaring variables
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime, variables
- variables [Visual Basic], lifetime
- access levels, variables
- scope, declaration statements
- variables [Visual Basic], access level
- local variables, declarations
- scope, variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
caps.latest.revision: 31
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
ms.openlocfilehash: dac536b99eb4515c75381dc4e28720a92e1001f0
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="variable-declaration-in-visual-basic"></a><span data-ttu-id="15796-102">Visual Basic 中的变量声明</span><span class="sxs-lookup"><span data-stu-id="15796-102">Variable Declaration in Visual Basic</span></span>
<span data-ttu-id="15796-103">声明一个变量来指定其名称和特性。</span><span class="sxs-lookup"><span data-stu-id="15796-103">You declare a variable to specify its name and characteristics.</span></span> <span data-ttu-id="15796-104">变量的声明语句是[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="15796-104">The declaration statement for variables is the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="15796-105">其位置和内容确定变量的特征。</span><span class="sxs-lookup"><span data-stu-id="15796-105">Its location and contents determine the variable's characteristics.</span></span>  
  
 <span data-ttu-id="15796-106">有关变量的命名规则和注意事项，请参阅[声明元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。</span><span class="sxs-lookup"><span data-stu-id="15796-106">For variable naming rules and considerations, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="declaration-levels"></a><span data-ttu-id="15796-107">声明级别</span><span class="sxs-lookup"><span data-stu-id="15796-107">Declaration Levels</span></span>  
  
### <a name="local-and-member-variables"></a><span data-ttu-id="15796-108">本地和成员变量</span><span class="sxs-lookup"><span data-stu-id="15796-108">Local and Member Variables</span></span>  
 <span data-ttu-id="15796-109">一个*局部变量*是指在过程内声明。</span><span class="sxs-lookup"><span data-stu-id="15796-109">A *local variable* is one that is declared within a procedure.</span></span> <span data-ttu-id="15796-110">一个*成员变量*属于[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]类型; 它在模块级别，在类、 结构或模块，但不是能在内部的类、 结构或模块的任何过程声明。</span><span class="sxs-lookup"><span data-stu-id="15796-110">A *member variable* is a member of a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] type; it is declared at module level, inside a class, structure, or module, but not within any procedure internal to that class, structure, or module.</span></span>  
  
### <a name="shared-and-instance-variables"></a><span data-ttu-id="15796-111">共享变量和实例变量</span><span class="sxs-lookup"><span data-stu-id="15796-111">Shared and Instance Variables</span></span>  
 <span data-ttu-id="15796-112">在类或结构中，成员变量的类别取决于共享它。</span><span class="sxs-lookup"><span data-stu-id="15796-112">In a class or structure, the category of a member variable depends on whether or not it is shared.</span></span> <span data-ttu-id="15796-113">如果使用声明[共享](../../../../visual-basic/language-reference/modifiers/shared.md)关键字，它是*共享的变量*，并且它存在于类或结构的所有实例都共享的单个副本中。</span><span class="sxs-lookup"><span data-stu-id="15796-113">If it is declared with the [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) keyword, it is a *shared variable*, and it exists in a single copy shared among all instances of the class or structure.</span></span>  
  
 <span data-ttu-id="15796-114">否则，很*实例变量*，并为类或结构的每个实例创建的单独副本。</span><span class="sxs-lookup"><span data-stu-id="15796-114">Otherwise it is an *instance variable*, and a separate copy of it is created for each instance of the class or structure.</span></span> <span data-ttu-id="15796-115">给定的实例变量副本是仅对类或结构在其中创建的实例可用。</span><span class="sxs-lookup"><span data-stu-id="15796-115">A given copy of an instance variable is available only to the instance of the class or structure in which it was created.</span></span> <span data-ttu-id="15796-116">它不依赖于类或结构的任何其他实例中实例变量的副本。</span><span class="sxs-lookup"><span data-stu-id="15796-116">It is independent of a copy of the instance variable in any other instance of the class or structure.</span></span>  
  
## <a name="declaring-data-type"></a><span data-ttu-id="15796-117">将数据类型声明</span><span class="sxs-lookup"><span data-stu-id="15796-117">Declaring Data Type</span></span>  
 <span data-ttu-id="15796-118">[作为](../../../../visual-basic/language-reference/statements/as-clause.md)声明语句中的子句可用于定义数据类型或所声明的变量的对象类型。</span><span class="sxs-lookup"><span data-stu-id="15796-118">The [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause in the declaration statement allows you to define the data type or object type of the variable you are declaring.</span></span> <span data-ttu-id="15796-119">你可以指定任何以下类型的变量︰</span><span class="sxs-lookup"><span data-stu-id="15796-119">You can specify any of the following types for a variable:</span></span>  
  
-   <span data-ttu-id="15796-120">基本数据类型，如`Boolean`， `Long`，或`Decimal`</span><span class="sxs-lookup"><span data-stu-id="15796-120">An elementary data type, such as `Boolean`, `Long`, or `Decimal`</span></span>  
  
-   <span data-ttu-id="15796-121">复合数据类型，如数组或结构</span><span class="sxs-lookup"><span data-stu-id="15796-121">A composite data type, such as an array or structure</span></span>  
  
-   <span data-ttu-id="15796-122">对象类型或在您的应用程序或其他应用程序中定义的类</span><span class="sxs-lookup"><span data-stu-id="15796-122">An object type, or class, defined either in your application or in another application</span></span>  
  
-   <span data-ttu-id="15796-123">一个[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]类，如<xref:System.Windows.Forms.Label>或<xref:System.Windows.Forms.TextBox></xref:System.Windows.Forms.TextBox></xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="15796-123">A [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] class, such as <xref:System.Windows.Forms.Label> or <xref:System.Windows.Forms.TextBox></span></span>  
  
-   <span data-ttu-id="15796-124">接口类型，如<xref:System.IComparable>或<xref:System.IDisposable></xref:System.IDisposable></xref:System.IComparable></span><span class="sxs-lookup"><span data-stu-id="15796-124">An interface type, such as <xref:System.IComparable> or <xref:System.IDisposable></span></span>  
  
 <span data-ttu-id="15796-125">您可以声明在一个语句中的几个变量，而无需重复的数据类型。</span><span class="sxs-lookup"><span data-stu-id="15796-125">You can declare several variables in one statement without having to repeat the data type.</span></span> <span data-ttu-id="15796-126">在下面的语句中，变量`i`， `j`，和`k`都声明为类型`Integer`，`l`和`m`作为`Long`，和`x`和`y`作为`Single`:</span><span class="sxs-lookup"><span data-stu-id="15796-126">In the following statements, the variables `i`, `j`, and `k` are declared as type `Integer`, `l` and `m` as `Long`, and `x` and `y` as `Single`:</span></span>  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 <span data-ttu-id="15796-127">数据类型的详细信息，请参阅[数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)。</span><span class="sxs-lookup"><span data-stu-id="15796-127">For more information on data types, see [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md).</span></span> <span data-ttu-id="15796-128">对象的详细信息，请参阅[对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)和[使用组件编程](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)。</span><span class="sxs-lookup"><span data-stu-id="15796-128">For more information on objects, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) and [Programming with Components](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span></span>  
  
## <a name="local-type-inference"></a><span data-ttu-id="15796-129">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="15796-129">Local Type Inference</span></span>  
 <span data-ttu-id="15796-130">*类型推理*用来确定未声明的局部变量的数据类型`As`子句。</span><span class="sxs-lookup"><span data-stu-id="15796-130">*Type inference* is used to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="15796-131">编译器推断出类型的变量的初始化表达式的类型。</span><span class="sxs-lookup"><span data-stu-id="15796-131">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="15796-132">这使您无需显式声明一个类型声明变量。</span><span class="sxs-lookup"><span data-stu-id="15796-132">This enables you to declare variables without explicitly stating a type.</span></span> <span data-ttu-id="15796-133">在下面的示例中，同时`num1`和`num2`强类型化为整数。</span><span class="sxs-lookup"><span data-stu-id="15796-133">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 <span data-ttu-id="15796-134">[!code-vb[VbVbalrTypeInference #&1;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="15796-134">[!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]</span></span>  
  
 <span data-ttu-id="15796-135">如果你想要使用局部类型推理`Option Infer`必须设置为`On`。</span><span class="sxs-lookup"><span data-stu-id="15796-135">If you want to use local type inference, `Option Infer` must be set to `On`.</span></span> <span data-ttu-id="15796-136">有关详细信息，请参阅[本地类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)和[Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="15796-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="characteristics-of-declared-variables"></a><span data-ttu-id="15796-137">已声明的变量的特征</span><span class="sxs-lookup"><span data-stu-id="15796-137">Characteristics of Declared Variables</span></span>  
 <span data-ttu-id="15796-138">*生存期*的变量是一段时间期间它是可供使用。</span><span class="sxs-lookup"><span data-stu-id="15796-138">The *lifetime* of a variable is the period of time during which it is available for use.</span></span> <span data-ttu-id="15796-139">一般情况下，变量存在，只要继续存在 （如过程或类） 中声明的元素。</span><span class="sxs-lookup"><span data-stu-id="15796-139">In general, a variable exists as long as the element that declares it (such as a procedure or class) continues to exist.</span></span> <span data-ttu-id="15796-140">如果该变量并不需要它的包含元素的生存期过后继续存在，您不需要执行任何特殊的声明中。</span><span class="sxs-lookup"><span data-stu-id="15796-140">If the variable does not need to continue existing beyond the lifetime of its containing element, you do not need to do anything special in the declaration.</span></span> <span data-ttu-id="15796-141">如果变量需要继续存在时间超过其包含元素，则可以包括`Static`或`Shared`关键字在其`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="15796-141">If the variable needs to continue to exist longer than its containing element, you can include the `Static` or `Shared` keyword in its `Dim` statement.</span></span> <span data-ttu-id="15796-142">有关详细信息，请参阅[Visual Basic 中的生存期](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)。</span><span class="sxs-lookup"><span data-stu-id="15796-142">For more information, see [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).</span></span>  
  
 <span data-ttu-id="15796-143">*范围*的变量是一组的所有代码都可以引用它，而不用限定其名称。</span><span class="sxs-lookup"><span data-stu-id="15796-143">The *scope* of a variable is the set of all code that can refer to it without qualifying its name.</span></span> <span data-ttu-id="15796-144">声明位置取决于该变量的作用域。</span><span class="sxs-lookup"><span data-stu-id="15796-144">A variable's scope is determined by where it is declared.</span></span> <span data-ttu-id="15796-145">位于某个给定区域中的代码可以使用而不必限定它们的名称在该区域中定义的变量。</span><span class="sxs-lookup"><span data-stu-id="15796-145">Code located in a given region can use the variables defined in that region without having to qualify their names.</span></span> <span data-ttu-id="15796-146">有关详细信息，请参阅[在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)。</span><span class="sxs-lookup"><span data-stu-id="15796-146">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
 <span data-ttu-id="15796-147">变量的*访问级别*是有权访问它的代码的范围。</span><span class="sxs-lookup"><span data-stu-id="15796-147">A variable's *access level* is the extent of code that has permission to access it.</span></span> <span data-ttu-id="15796-148">这由访问修饰符 (如[公共](../../../../visual-basic/language-reference/modifiers/public.md)或[专用](../../../../visual-basic/language-reference/modifiers/private.md)) 中使用`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="15796-148">This is determined by the access modifier (such as [Public](../../../../visual-basic/language-reference/modifiers/public.md) or [Private](../../../../visual-basic/language-reference/modifiers/private.md)) that you use in the `Dim` statement.</span></span> <span data-ttu-id="15796-149">有关详细信息，请参阅[Visual Basic 中的访问级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="15796-149">For more information, see [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15796-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15796-150">See Also</span></span>  
 <span data-ttu-id="15796-151">[如何︰ 创建新变量](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md) </span><span class="sxs-lookup"><span data-stu-id="15796-151">[How to: Create a New Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md) </span></span>  
<span data-ttu-id="15796-152"> [如何︰ 将数据移入和移出变量](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="15796-152"> [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span></span>  
<span data-ttu-id="15796-153"> [数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="15796-153"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="15796-154"> [受保护](../../../../visual-basic/language-reference/modifiers/protected.md) </span><span class="sxs-lookup"><span data-stu-id="15796-154"> [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) </span></span>  
<span data-ttu-id="15796-155"> [友元](../../../../visual-basic/language-reference/modifiers/friend.md) </span><span class="sxs-lookup"><span data-stu-id="15796-155"> [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) </span></span>  
<span data-ttu-id="15796-156"> [静态](../../../../visual-basic/language-reference/modifiers/static.md) </span><span class="sxs-lookup"><span data-stu-id="15796-156"> [Static](../../../../visual-basic/language-reference/modifiers/static.md) </span></span>  
<span data-ttu-id="15796-157"> [已声明的元素的特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="15796-157"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="15796-158"> [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="15796-158"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="15796-159"> [Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span><span class="sxs-lookup"><span data-stu-id="15796-159"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span></span>

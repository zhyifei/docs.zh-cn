---
title: 常量概述 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6526f7270602b3e1a4e8d953732c393ff252b2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="constants-overview-visual-basic"></a><span data-ttu-id="fb34e-102">常量概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fb34e-102">Constants Overview (Visual Basic)</span></span>
<span data-ttu-id="fb34e-103">常量是有意义的名称发生的数字或字符串不会更改。</span><span class="sxs-lookup"><span data-stu-id="fb34e-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="fb34e-104">常量存储的名称可以看出，保持不变的应用程序的执行中值。</span><span class="sxs-lookup"><span data-stu-id="fb34e-104">Constants store values that, as the name implies, remain the same throughout the execution of an application.</span></span> <span data-ttu-id="fb34e-105">你可以大幅提高代码的可读性和更加轻松地使用常量的维护。</span><span class="sxs-lookup"><span data-stu-id="fb34e-105">You can greatly improve the readability of your code and make it easier to maintain by using constants.</span></span> <span data-ttu-id="fb34e-106">在包含重新出现的值的代码中使用它们，或这取决于一些很难记住或没有明显意义的数字。</span><span class="sxs-lookup"><span data-stu-id="fb34e-106">Use them in code that contains values that reappear or that depends on certain numbers that are difficult to remember or have no obvious meaning.</span></span>  
  
## <a name="how-to-create-and-use-constants"></a><span data-ttu-id="fb34e-107">如何创建和使用常量</span><span class="sxs-lookup"><span data-stu-id="fb34e-107">How to Create and Use Constants</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="fb34e-108">包含大量的预定义的常量，主要用于打印和显示。</span><span class="sxs-lookup"><span data-stu-id="fb34e-108"> contains a number of predefined constants, mainly using for printing and displaying.</span></span> <span data-ttu-id="fb34e-109">你还可以创建你自己常量具有与`Const`语句，用于创建变量的名称使用相同的规则。</span><span class="sxs-lookup"><span data-stu-id="fb34e-109">You can also create your own constants with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="fb34e-110">如果`Option Strict`是`On`，您必须显式声明的常量的类型。</span><span class="sxs-lookup"><span data-stu-id="fb34e-110">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
 <span data-ttu-id="fb34e-111">常量的作用域，它是所有代码都可以引用它而无须限定其名称的集，等同于在同一位置中声明的变量。</span><span class="sxs-lookup"><span data-stu-id="fb34e-111">A constant's scope, which is the set of all code that can refer to it without qualifying its name, is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="fb34e-112">若要创建一个常数，位于某个特定过程的作用域内，将其声明该过程内。</span><span class="sxs-lookup"><span data-stu-id="fb34e-112">To create a constant that exists within the scope of a particular procedure, declare it inside that procedure.</span></span> <span data-ttu-id="fb34e-113">若要创建一个常数，用于在整个应用程序都可用，将使用其声明`Public`类的声明部分中的关键字。</span><span class="sxs-lookup"><span data-stu-id="fb34e-113">To create a constant that is available throughout an application, declare it using the `Public` keyword in the declarations section of the class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb34e-114">尽管常量某种程度上类似于变量，但无法对其进行修改，或将新值分配给它们，因为你可以对变量。</span><span class="sxs-lookup"><span data-stu-id="fb34e-114">Although constants somewhat resemble variables, you cannot modify them or assign new values to them as you can to variables.</span></span>  
  
 <span data-ttu-id="fb34e-115">在代码中使用的常量可以定义由控件或你使用的组件对象模型或它们可以是用户定义 （即，那些你自己创建的）。</span><span class="sxs-lookup"><span data-stu-id="fb34e-115">The constants you use in your code can be defined by the object model for controls or components you work with, or they can be user-defined (that is, those you create yourself).</span></span>  
  
## <a name="compile-time-and-run-time-constants"></a><span data-ttu-id="fb34e-116">编译时和运行时常量</span><span class="sxs-lookup"><span data-stu-id="fb34e-116">Compile-time and Run-time Constants</span></span>  
 <span data-ttu-id="fb34e-117">在编译代码，可以仅计算运行时常量，应用程序运行时的时间计算编译时常量。</span><span class="sxs-lookup"><span data-stu-id="fb34e-117">A compile-time constant is computed at the time the code is compiled, while a run-time constant can only be computed while the application is running.</span></span> <span data-ttu-id="fb34e-118">编译时常量将在每次运行应用程序，而运行时常量可能会更改每个时间时具有相同的值。</span><span class="sxs-lookup"><span data-stu-id="fb34e-118">A compile-time constant will have the same value each time an application runs, while a run-time constant may change each time.</span></span> <span data-ttu-id="fb34e-119">编译时常量所需的情况下，如数组边界、 case 表达式或枚举器初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="fb34e-119">Compile-time constants are required for cases such as array bounds, case expressions, or enumerator initializers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fb34e-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="fb34e-120">In This Section</span></span>  
  
|<span data-ttu-id="fb34e-121">定义</span><span class="sxs-lookup"><span data-stu-id="fb34e-121">Definition</span></span>|<span data-ttu-id="fb34e-122">术语</span><span class="sxs-lookup"><span data-stu-id="fb34e-122">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="fb34e-123">如何：声明常量</span><span class="sxs-lookup"><span data-stu-id="fb34e-123">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|<span data-ttu-id="fb34e-124">说明如何使用`Const`语句以声明常量，并将其值; 设置为值通过声明一个常数，分配有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="fb34e-124">Explains how to use the `Const` statement to declare a constant and set its value; by declaring a constant, you assign a meaningful name to the value.</span></span>|  
|[<span data-ttu-id="fb34e-125">用户定义的常量</span><span class="sxs-lookup"><span data-stu-id="fb34e-125">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|<span data-ttu-id="fb34e-126">描述如何创建你自己的常量，包括有关范围的信息以及如何避免循环引用。</span><span class="sxs-lookup"><span data-stu-id="fb34e-126">Describes how to create your own constants, including information on scoping and how to avoid circular references.</span></span>|  
|[<span data-ttu-id="fb34e-127">常量和文本数据类型</span><span class="sxs-lookup"><span data-stu-id="fb34e-127">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|<span data-ttu-id="fb34e-128">提供有关如何信息[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器初始化常量时`Option Explicit`处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="fb34e-128">Provides information on how the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler initializes constants when `Option Explicit` is turned off.</span></span>|  
|[<span data-ttu-id="fb34e-129">如何：将相关的常量值组合在一起</span><span class="sxs-lookup"><span data-stu-id="fb34e-129">How to: Group Related Constant Values Together</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|<span data-ttu-id="fb34e-130">演示如何组相关的常量值。</span><span class="sxs-lookup"><span data-stu-id="fb34e-130">Demonstrates how to group constant values that are related.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="fb34e-131">参考</span><span class="sxs-lookup"><span data-stu-id="fb34e-131">Reference</span></span>  
  
|<span data-ttu-id="fb34e-132">定义</span><span class="sxs-lookup"><span data-stu-id="fb34e-132">Definition</span></span>|<span data-ttu-id="fb34e-133">术语</span><span class="sxs-lookup"><span data-stu-id="fb34e-133">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="fb34e-134">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="fb34e-134">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)|<span data-ttu-id="fb34e-135">列出由预定义的常量[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fb34e-135">Lists the constants predefined by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>|  
|[<span data-ttu-id="fb34e-136">Const 语句</span><span class="sxs-lookup"><span data-stu-id="fb34e-136">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)|<span data-ttu-id="fb34e-137">描述`Const`语句和其使用。</span><span class="sxs-lookup"><span data-stu-id="fb34e-137">Describes the `Const` statement and its use.</span></span>|  
|[<span data-ttu-id="fb34e-138">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="fb34e-138">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|<span data-ttu-id="fb34e-139">描述`Option Strict`语句和其使用。</span><span class="sxs-lookup"><span data-stu-id="fb34e-139">Describes the `Option Strict` statement and its use.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb34e-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb34e-140">See Also</span></span>  
 [<span data-ttu-id="fb34e-141">枚举概述</span><span class="sxs-lookup"><span data-stu-id="fb34e-141">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="fb34e-142">如何：在 Visual Basic 中初始化数组变量</span><span class="sxs-lookup"><span data-stu-id="fb34e-142">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)

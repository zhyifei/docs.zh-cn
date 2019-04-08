---
title: 常量概述 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
ms.openlocfilehash: 2939110de77718baf32e2a0d8f1aa52dba997cf3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841266"
---
# <a name="constants-overview-visual-basic"></a><span data-ttu-id="44ca2-102">常量概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44ca2-102">Constants Overview (Visual Basic)</span></span>
<span data-ttu-id="44ca2-103">常量是有意义的名称采用的数字或字符串不会更改的位置。</span><span class="sxs-lookup"><span data-stu-id="44ca2-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="44ca2-104">常量存储值，如名称所示，将保持不变的应用程序执行中。</span><span class="sxs-lookup"><span data-stu-id="44ca2-104">Constants store values that, as the name implies, remain the same throughout the execution of an application.</span></span> <span data-ttu-id="44ca2-105">可以极大地提高代码的可读性并使其更易于维护使用常量。</span><span class="sxs-lookup"><span data-stu-id="44ca2-105">You can greatly improve the readability of your code and make it easier to maintain by using constants.</span></span> <span data-ttu-id="44ca2-106">包含的值会重新出现的代码中使用它们，或这取决于一些很难记住或没有任何明显的意义的数字。</span><span class="sxs-lookup"><span data-stu-id="44ca2-106">Use them in code that contains values that reappear or that depends on certain numbers that are difficult to remember or have no obvious meaning.</span></span>  
  
## <a name="how-to-create-and-use-constants"></a><span data-ttu-id="44ca2-107">如何创建和使用常量</span><span class="sxs-lookup"><span data-stu-id="44ca2-107">How to Create and Use Constants</span></span>  
 <span data-ttu-id="44ca2-108">Visual Basic 包含大量预定义的常量，主要用于打印和显示。</span><span class="sxs-lookup"><span data-stu-id="44ca2-108">Visual Basic contains a number of predefined constants, mainly using for printing and displaying.</span></span> <span data-ttu-id="44ca2-109">您还可以创建您自己常量与`Const`语句，用于创建变量的名称使用相同的规则。</span><span class="sxs-lookup"><span data-stu-id="44ca2-109">You can also create your own constants with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="44ca2-110">如果`Option Strict`是`On`，必须显式声明常量的类型。</span><span class="sxs-lookup"><span data-stu-id="44ca2-110">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
 <span data-ttu-id="44ca2-111">常量的作用域，这是变量的组的所有代码都可以引用它而无需限定其名称，是变量的在同一位置中声明相同。</span><span class="sxs-lookup"><span data-stu-id="44ca2-111">A constant's scope, which is the set of all code that can refer to it without qualifying its name, is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="44ca2-112">若要创建一个常量，它位于特定过程的作用域内，将其声明在该过程。</span><span class="sxs-lookup"><span data-stu-id="44ca2-112">To create a constant that exists within the scope of a particular procedure, declare it inside that procedure.</span></span> <span data-ttu-id="44ca2-113">若要创建一个常量，它是整个应用程序可用，将使用其声明`Public`类的声明部分中的关键字。</span><span class="sxs-lookup"><span data-stu-id="44ca2-113">To create a constant that is available throughout an application, declare it using the `Public` keyword in the declarations section of the class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44ca2-114">虽然常数某种程度上类似于变量，不能对其进行修改，或如变量可以为它们分配新值。</span><span class="sxs-lookup"><span data-stu-id="44ca2-114">Although constants somewhat resemble variables, you cannot modify them or assign new values to them as you can to variables.</span></span>  
  
 <span data-ttu-id="44ca2-115">在代码中使用的常量可以定义由对象模型的控件或组件，或它们可以是用户定义 （即，那些您自己创建）。</span><span class="sxs-lookup"><span data-stu-id="44ca2-115">The constants you use in your code can be defined by the object model for controls or components you work with, or they can be user-defined (that is, those you create yourself).</span></span>  
  
## <a name="compile-time-and-run-time-constants"></a><span data-ttu-id="44ca2-116">编译时和运行时常量</span><span class="sxs-lookup"><span data-stu-id="44ca2-116">Compile-time and Run-time Constants</span></span>  
 <span data-ttu-id="44ca2-117">编译时常量是在编译代码，而可以仅计算运行时常量，该应用程序运行时的时间计算的。</span><span class="sxs-lookup"><span data-stu-id="44ca2-117">A compile-time constant is computed at the time the code is compiled, while a run-time constant can only be computed while the application is running.</span></span> <span data-ttu-id="44ca2-118">编译时常量将在每次运行应用程序，而运行时常量可能每次更改的时具有相同的值。</span><span class="sxs-lookup"><span data-stu-id="44ca2-118">A compile-time constant will have the same value each time an application runs, while a run-time constant may change each time.</span></span> <span data-ttu-id="44ca2-119">需要如数组界限、 case 表达式或枚举器初始值设定项的情况下编译时常量。</span><span class="sxs-lookup"><span data-stu-id="44ca2-119">Compile-time constants are required for cases such as array bounds, case expressions, or enumerator initializers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44ca2-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="44ca2-120">In This Section</span></span>  
  
|<span data-ttu-id="44ca2-121">定义</span><span class="sxs-lookup"><span data-stu-id="44ca2-121">Definition</span></span>|<span data-ttu-id="44ca2-122">术语</span><span class="sxs-lookup"><span data-stu-id="44ca2-122">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="44ca2-123">如何：声明常量</span><span class="sxs-lookup"><span data-stu-id="44ca2-123">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|<span data-ttu-id="44ca2-124">说明如何使用`Const`语句声明一个常量，并将其值; 设置为值通过声明一个常量，分配有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="44ca2-124">Explains how to use the `Const` statement to declare a constant and set its value; by declaring a constant, you assign a meaningful name to the value.</span></span>|  
|[<span data-ttu-id="44ca2-125">用户定义的常量</span><span class="sxs-lookup"><span data-stu-id="44ca2-125">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|<span data-ttu-id="44ca2-126">介绍如何创建你自己的常量，包括有关范围的信息以及如何避免循环引用。</span><span class="sxs-lookup"><span data-stu-id="44ca2-126">Describes how to create your own constants, including information on scoping and how to avoid circular references.</span></span>|  
|[<span data-ttu-id="44ca2-127">常量和文本数据类型</span><span class="sxs-lookup"><span data-stu-id="44ca2-127">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|<span data-ttu-id="44ca2-128">提供有关 Visual Basic 编译器如何初始化常量的信息时`Option Explicit`处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="44ca2-128">Provides information on how the Visual Basic compiler initializes constants when `Option Explicit` is turned off.</span></span>|  
|[<span data-ttu-id="44ca2-129">如何：相关的常量值组合在一起</span><span class="sxs-lookup"><span data-stu-id="44ca2-129">How to: Group Related Constant Values Together</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|<span data-ttu-id="44ca2-130">演示如何对分组相关的常量值。</span><span class="sxs-lookup"><span data-stu-id="44ca2-130">Demonstrates how to group constant values that are related.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="44ca2-131">参考</span><span class="sxs-lookup"><span data-stu-id="44ca2-131">Reference</span></span>  
  
|<span data-ttu-id="44ca2-132">定义</span><span class="sxs-lookup"><span data-stu-id="44ca2-132">Definition</span></span>|<span data-ttu-id="44ca2-133">术语</span><span class="sxs-lookup"><span data-stu-id="44ca2-133">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="44ca2-134">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="44ca2-134">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)|<span data-ttu-id="44ca2-135">列出预定义的 Visual Basic 的常量。</span><span class="sxs-lookup"><span data-stu-id="44ca2-135">Lists the constants predefined by Visual Basic.</span></span>|  
|[<span data-ttu-id="44ca2-136">Const 语句</span><span class="sxs-lookup"><span data-stu-id="44ca2-136">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)|<span data-ttu-id="44ca2-137">介绍`Const`语句和它的使用。</span><span class="sxs-lookup"><span data-stu-id="44ca2-137">Describes the `Const` statement and its use.</span></span>|  
|[<span data-ttu-id="44ca2-138">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="44ca2-138">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|<span data-ttu-id="44ca2-139">介绍`Option Strict`语句和它的使用。</span><span class="sxs-lookup"><span data-stu-id="44ca2-139">Describes the `Option Strict` statement and its use.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44ca2-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="44ca2-140">See also</span></span>

- [<span data-ttu-id="44ca2-141">枚举概述</span><span class="sxs-lookup"><span data-stu-id="44ca2-141">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="44ca2-142">如何：初始化数组变量在 Visual Basic 中</span><span class="sxs-lookup"><span data-stu-id="44ca2-142">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)

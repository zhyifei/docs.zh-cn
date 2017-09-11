---
title: "常量概述 (Visual Basic 中) |Microsoft 文档"
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
- constants
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
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
ms.openlocfilehash: 2df21b9e3e814c654b355472aa645481060c6f68
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="constants-overview-visual-basic"></a><span data-ttu-id="b49b9-102">常量概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b49b9-102">Constants Overview (Visual Basic)</span></span>
<span data-ttu-id="b49b9-103">常量是有意义的名称，取代了数字或字符串，它不会更改。</span><span class="sxs-lookup"><span data-stu-id="b49b9-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="b49b9-104">常数存储值，如名称所示，保持不变的在整个应用程序的执行过程。</span><span class="sxs-lookup"><span data-stu-id="b49b9-104">Constants store values that, as the name implies, remain the same throughout the execution of an application.</span></span> <span data-ttu-id="b49b9-105">可以极大地提高代码的可读性并更加轻松地使用常量的维护。</span><span class="sxs-lookup"><span data-stu-id="b49b9-105">You can greatly improve the readability of your code and make it easier to maintain by using constants.</span></span> <span data-ttu-id="b49b9-106">在包含重新出现的值的代码中使用它们，或这取决于一些难以记住或没有明显意义的数字。</span><span class="sxs-lookup"><span data-stu-id="b49b9-106">Use them in code that contains values that reappear or that depends on certain numbers that are difficult to remember or have no obvious meaning.</span></span>  
  
## <a name="how-to-create-and-use-constants"></a><span data-ttu-id="b49b9-107">如何创建和使用常量</span><span class="sxs-lookup"><span data-stu-id="b49b9-107">How to Create and Use Constants</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="b49b9-108">包含大量的预定义的常量，主要用于打印和显示。</span><span class="sxs-lookup"><span data-stu-id="b49b9-108"> contains a number of predefined constants, mainly using for printing and displaying.</span></span> <span data-ttu-id="b49b9-109">您还可以创建您自己常量与`Const`语句，但创建的变量名中使用相同的规则。</span><span class="sxs-lookup"><span data-stu-id="b49b9-109">You can also create your own constants with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="b49b9-110">如果`Option Strict`是`On`，所以必须显式声明常量的类型。</span><span class="sxs-lookup"><span data-stu-id="b49b9-110">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
 <span data-ttu-id="b49b9-111">常量的作用域，它是所有代码都可以引用它，而不用限定其名称的集，等同于在同一位置中声明的变量。</span><span class="sxs-lookup"><span data-stu-id="b49b9-111">A constant's scope, which is the set of all code that can refer to it without qualifying its name, is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="b49b9-112">若要创建一个常量，它位于某个特定过程的作用域内，请在该过程内声明。</span><span class="sxs-lookup"><span data-stu-id="b49b9-112">To create a constant that exists within the scope of a particular procedure, declare it inside that procedure.</span></span> <span data-ttu-id="b49b9-113">若要创建一个常量，它在整个应用程序都可用，将使用其声明`Public`类的声明部分中的关键字。</span><span class="sxs-lookup"><span data-stu-id="b49b9-113">To create a constant that is available throughout an application, declare it using the `Public` keyword in the declarations section of the class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b49b9-114">虽然常量某种程度上类似于变量，不能对其进行修改，或根据对变量可以将新值分配给它们。</span><span class="sxs-lookup"><span data-stu-id="b49b9-114">Although constants somewhat resemble variables, you cannot modify them or assign new values to them as you can to variables.</span></span>  
  
 <span data-ttu-id="b49b9-115">可通过控件或您使用的组件的对象模型定义在代码中使用的常量或它们可以是用户定义 （即，您自己创建）。</span><span class="sxs-lookup"><span data-stu-id="b49b9-115">The constants you use in your code can be defined by the object model for controls or components you work with, or they can be user-defined (that is, those you create yourself).</span></span>  
  
## <a name="compile-time-and-run-time-constants"></a><span data-ttu-id="b49b9-116">编译时和运行时常量</span><span class="sxs-lookup"><span data-stu-id="b49b9-116">Compile-time and Run-time Constants</span></span>  
 <span data-ttu-id="b49b9-117">编译时常量是在编译代码，而可以只计算运行时常量，该应用程序运行时的时间计算的。</span><span class="sxs-lookup"><span data-stu-id="b49b9-117">A compile-time constant is computed at the time the code is compiled, while a run-time constant can only be computed while the application is running.</span></span> <span data-ttu-id="b49b9-118">编译时常量将在每次应用程序运行，而每次时可能会更改运行时常量具有相同的值。</span><span class="sxs-lookup"><span data-stu-id="b49b9-118">A compile-time constant will have the same value each time an application runs, while a run-time constant may change each time.</span></span> <span data-ttu-id="b49b9-119">编译时常量是必需的情况下，如数组界限、 case 表达式或枚举器初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="b49b9-119">Compile-time constants are required for cases such as array bounds, case expressions, or enumerator initializers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b49b9-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="b49b9-120">In This Section</span></span>  
  
|<span data-ttu-id="b49b9-121">定义</span><span class="sxs-lookup"><span data-stu-id="b49b9-121">Definition</span></span>|<span data-ttu-id="b49b9-122">术语</span><span class="sxs-lookup"><span data-stu-id="b49b9-122">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="b49b9-123">如何：声明常量</span><span class="sxs-lookup"><span data-stu-id="b49b9-123">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|<span data-ttu-id="b49b9-124">说明如何使用`Const`语句声明一个常量，并将其值; 设置为值通过声明一个常数，分配有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="b49b9-124">Explains how to use the `Const` statement to declare a constant and set its value; by declaring a constant, you assign a meaningful name to the value.</span></span>|  
|[<span data-ttu-id="b49b9-125">用户定义的常量</span><span class="sxs-lookup"><span data-stu-id="b49b9-125">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|<span data-ttu-id="b49b9-126">描述如何创建您自己的常数，包括有关范围的信息以及如何避免循环引用。</span><span class="sxs-lookup"><span data-stu-id="b49b9-126">Describes how to create your own constants, including information on scoping and how to avoid circular references.</span></span>|  
|[<span data-ttu-id="b49b9-127">常量和文本数据类型</span><span class="sxs-lookup"><span data-stu-id="b49b9-127">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|<span data-ttu-id="b49b9-128">提供了有关的信息[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器初始化常量时`Option Explicit`处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="b49b9-128">Provides information on how the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler initializes constants when `Option Explicit` is turned off.</span></span>|  
|[<span data-ttu-id="b49b9-129">如何：将相关的常量值组合在一起</span><span class="sxs-lookup"><span data-stu-id="b49b9-129">How to: Group Related Constant Values Together</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|<span data-ttu-id="b49b9-130">演示如何相关的常量值进行分组。</span><span class="sxs-lookup"><span data-stu-id="b49b9-130">Demonstrates how to group constant values that are related.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="b49b9-131">参考</span><span class="sxs-lookup"><span data-stu-id="b49b9-131">Reference</span></span>  
  
|<span data-ttu-id="b49b9-132">定义</span><span class="sxs-lookup"><span data-stu-id="b49b9-132">Definition</span></span>|<span data-ttu-id="b49b9-133">术语</span><span class="sxs-lookup"><span data-stu-id="b49b9-133">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="b49b9-134">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="b49b9-134">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)|<span data-ttu-id="b49b9-135">列出预定义的常量[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b49b9-135">Lists the constants predefined by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>|  
|[<span data-ttu-id="b49b9-136">Const 语句</span><span class="sxs-lookup"><span data-stu-id="b49b9-136">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)|<span data-ttu-id="b49b9-137">描述`Const`语句和它的使用。</span><span class="sxs-lookup"><span data-stu-id="b49b9-137">Describes the `Const` statement and its use.</span></span>|  
|[<span data-ttu-id="b49b9-138">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="b49b9-138">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|<span data-ttu-id="b49b9-139">描述`Option Strict`语句和它的使用。</span><span class="sxs-lookup"><span data-stu-id="b49b9-139">Describes the `Option Strict` statement and its use.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b49b9-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b49b9-140">See Also</span></span>  
 <span data-ttu-id="b49b9-141">[枚举概述](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b49b9-141">[Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="b49b9-142"> [如何︰ 初始化数组变量在 Visual Basic 中](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span><span class="sxs-lookup"><span data-stu-id="b49b9-142"> [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span></span>

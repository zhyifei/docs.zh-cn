---
title: "用户定义的常量 (Visual Basic) |Microsoft 文档"
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
- constants, circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants
- scope, constants
- constants, user-defined
- circular references between constants
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
caps.latest.revision: 19
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
ms.openlocfilehash: b1ab1501309823b1565d5198fff25edf2927a2ce
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="22733-102">用户定义的常量 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22733-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="22733-103">常量是有意义的名称，取代了数字或字符串，它不会更改。</span><span class="sxs-lookup"><span data-stu-id="22733-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="22733-104">常数存储，如名称所示，保持不变的应用程序的执行中的值。</span><span class="sxs-lookup"><span data-stu-id="22733-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="22733-105">您可以使用由该控件或您使用的组件定义的常量或可以创建您自己。</span><span class="sxs-lookup"><span data-stu-id="22733-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="22733-106">创建您自己的常数称作*用户定义*。</span><span class="sxs-lookup"><span data-stu-id="22733-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="22733-107">声明常量`Const`语句，但创建的变量名中使用相同的规则。</span><span class="sxs-lookup"><span data-stu-id="22733-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="22733-108">如果`Option Strict`是`On`，所以必须显式声明常量的类型。</span><span class="sxs-lookup"><span data-stu-id="22733-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="22733-109">Const 语句使用情况</span><span class="sxs-lookup"><span data-stu-id="22733-109">Const Statement Usage</span></span>  
 <span data-ttu-id="22733-110">一个`Const`语句可以表示数学或日期/时间数量︰</span><span class="sxs-lookup"><span data-stu-id="22733-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 <span data-ttu-id="22733-111">[!code-vb[VbEnumsTask #&10;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="22733-111">[!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]</span></span>  
  
 <span data-ttu-id="22733-112">它还可以定义`String`常量︰</span><span class="sxs-lookup"><span data-stu-id="22733-112">It also can define `String` constants:</span></span>  
  
 <span data-ttu-id="22733-113">[!code-vb[VbEnumsTask #&13;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="22733-113">[!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]</span></span>  
  
 <span data-ttu-id="22733-114">等号右侧的表达式 ( `=` ) 通常是一个数字或文本字符串，但也可以是 （尽管该表达式不能包含对函数的调用），结果为数字或字符串的表达式。</span><span class="sxs-lookup"><span data-stu-id="22733-114">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="22733-115">您甚至可以定义根据以前定义的常量的常量︰</span><span class="sxs-lookup"><span data-stu-id="22733-115">You can even define constants in terms of previously defined constants:</span></span>  
  
 <span data-ttu-id="22733-116">[!code-vb[VbEnumsTask #&15;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="22733-116">[!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]</span></span>  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="22733-117">作用域的用户定义的常量</span><span class="sxs-lookup"><span data-stu-id="22733-117">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="22733-118">一个`Const`语句的作用域是在同一位置声明的变量相同。</span><span class="sxs-lookup"><span data-stu-id="22733-118">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="22733-119">可以在任何通过以下方式指定作用域︰</span><span class="sxs-lookup"><span data-stu-id="22733-119">You can specify scope in any of the following ways:</span></span>  
  
-   <span data-ttu-id="22733-120">若要创建过程中只存在一个常量，请在该过程中声明。</span><span class="sxs-lookup"><span data-stu-id="22733-120">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
-   <span data-ttu-id="22733-121">若要创建一个类中的所有过程但不是属于该模块以外的任何代码都可用的常数，请将其声明的类的声明部分。</span><span class="sxs-lookup"><span data-stu-id="22733-121">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="22733-122">若要创建一个常量，它可对所有成员的程序集，但不是向外部客户端的程序集，将使用其声明`Friend`类的声明部分中的关键字。</span><span class="sxs-lookup"><span data-stu-id="22733-122">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="22733-123">若要创建整个应用程序中可用的常数，声明它使用`Public`关键字在下面的声明部分类。</span><span class="sxs-lookup"><span data-stu-id="22733-123">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="22733-124">有关详细信息，请参阅[如何︰ 声明常量](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)。</span><span class="sxs-lookup"><span data-stu-id="22733-124">For more information, see [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="22733-125">避免循环引用</span><span class="sxs-lookup"><span data-stu-id="22733-125">Avoiding Circular References</span></span>  
 <span data-ttu-id="22733-126">由于可以依据其他常数定义常量，所以有可能无意中产生*循环*，或两个或多个常量之间的循环引用。</span><span class="sxs-lookup"><span data-stu-id="22733-126">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="22733-127">有两个或多个公共常量，其中每个用另一个，如以下示例所示来定义，则会出现一个周期︰</span><span class="sxs-lookup"><span data-stu-id="22733-127">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 <span data-ttu-id="22733-128">[!code-vb[VbEnumsTask #&16;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="22733-128">[!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]</span></span>  
<span data-ttu-id="22733-129">[!code-vb[VbEnumsTask #&17;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="22733-129">[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]</span></span>  
  
 <span data-ttu-id="22733-130">如果发生一次，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]生成一个编译器错误。</span><span class="sxs-lookup"><span data-stu-id="22733-130">If a cycle occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22733-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22733-131">See Also</span></span>  
 <span data-ttu-id="22733-132">[Const 语句](../../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="22733-132">[Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="22733-133"> [常量和 Literal 数据类型](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="22733-133"> [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="22733-134"> [常量和枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md) </span><span class="sxs-lookup"><span data-stu-id="22733-134"> [Constants and Enumerations](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md) </span></span>  
<span data-ttu-id="22733-135"> [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="22733-135"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md) </span></span>  
<span data-ttu-id="22733-136"> [枚举概述](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="22733-136"> [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="22733-137"> [常量概述](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="22733-137"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="22733-138"> [如何︰ 声明枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="22733-138"> [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="22733-139"> [枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="22733-139"> [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="22733-140"> [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="22733-140"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>

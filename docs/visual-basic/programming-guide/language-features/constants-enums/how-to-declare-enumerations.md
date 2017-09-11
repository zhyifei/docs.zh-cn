---
title: "如何︰ 声明枚举 (Visual Basic 中) |Microsoft 文档"
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
- declarations, enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: 24
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
ms.openlocfilehash: 7adaca7e7252ce7165a5fd27b5bc9c049388206c
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="b99ba-102">如何：声明枚举 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b99ba-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="b99ba-103">创建一个包含枚举`Enum`的类或模块中的声明部分语句。</span><span class="sxs-lookup"><span data-stu-id="b99ba-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="b99ba-104">不能声明在方法内的枚举。</span><span class="sxs-lookup"><span data-stu-id="b99ba-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="b99ba-105">若要指定适当的访问级别，使用`Private`， `Protected`， `Friend`，或`Public`。</span><span class="sxs-lookup"><span data-stu-id="b99ba-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="b99ba-106">`Enum`类型都有一个名称、 一个基础类型和一组字段，各表示一个常数。</span><span class="sxs-lookup"><span data-stu-id="b99ba-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="b99ba-107">该名称必须是一个有效[!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]限定符。</span><span class="sxs-lookup"><span data-stu-id="b99ba-107">The name must be a valid [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] qualifier.</span></span> <span data-ttu-id="b99ba-108">基础类型必须是整数类型之一-`Byte`， `Short`，`Long`或`Integer`。</span><span class="sxs-lookup"><span data-stu-id="b99ba-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="b99ba-109">默认为 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="b99ba-109">`Integer` is the default.</span></span> <span data-ttu-id="b99ba-110">枚举始终强类型和不可互换与整数类型。</span><span class="sxs-lookup"><span data-stu-id="b99ba-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="b99ba-111">枚举不能具有浮点值。</span><span class="sxs-lookup"><span data-stu-id="b99ba-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="b99ba-112">如果枚举器分配一个浮点值与`Option Strict On`，将导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="b99ba-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="b99ba-113">如果`Option Strict`是`Off`的值自动转换为`Enum`类型。</span><span class="sxs-lookup"><span data-stu-id="b99ba-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="b99ba-114">有关如何使用和信息的名称，`Imports`语句来进行名称限定不必要的请参阅[枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)。</span><span class="sxs-lookup"><span data-stu-id="b99ba-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="b99ba-115">声明枚举</span><span class="sxs-lookup"><span data-stu-id="b99ba-115">To declare an enumeration</span></span>  
  
1.  <span data-ttu-id="b99ba-116">编写一个包括代码访问级别的声明`Enum`关键字和有效的名称，如下面的示例，其中每个声明一个不同`Enum`。</span><span class="sxs-lookup"><span data-stu-id="b99ba-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     <span data-ttu-id="b99ba-117">[!code-vb[VbEnumsTask #&3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b99ba-117">[!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]</span></span>  
  
2.  <span data-ttu-id="b99ba-118">枚举中定义的常量。</span><span class="sxs-lookup"><span data-stu-id="b99ba-118">Define the constants in the enumeration.</span></span> <span data-ttu-id="b99ba-119">默认情况下，将为枚举中的第一个常数初始化为`0`，而后面的常数将初始化为其中一个比前面的常数的值。</span><span class="sxs-lookup"><span data-stu-id="b99ba-119">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="b99ba-120">例如，下面的枚举， `Days`，包含一个名为常量`Sunday`值`0`，一个名为常量`Monday`值`1`，一个名为常量`Tuesday`值为`2`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="b99ba-120">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     <span data-ttu-id="b99ba-121">[!code-vb[VbEnumsTask #&4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b99ba-121">[!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]</span></span>  
  
3.  <span data-ttu-id="b99ba-122">可以使用赋值语句，显式枚举中常数中分配的值。</span><span class="sxs-lookup"><span data-stu-id="b99ba-122">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="b99ba-123">您可以分配任何整数值，包括负数。</span><span class="sxs-lookup"><span data-stu-id="b99ba-123">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="b99ba-124">例如，您可能想常量与值小于零，表示错误情况。</span><span class="sxs-lookup"><span data-stu-id="b99ba-124">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="b99ba-125">在下面的枚举常量`Invalid`显式分配的值`–1`，和常量`Sunday`的值赋给`0`。</span><span class="sxs-lookup"><span data-stu-id="b99ba-125">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="b99ba-126">因为它是在枚举中，第一个常量`Saturday`还初始化为值`0`。</span><span class="sxs-lookup"><span data-stu-id="b99ba-126">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="b99ba-127">值`Monday`是`1`(一的值大于`Sunday`); 的值`Tuesday`是`2`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="b99ba-127">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     <span data-ttu-id="b99ba-128">[!code-vb[VbEnumsTask #&5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b99ba-128">[!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]</span></span>  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="b99ba-129">若要声明为显式类型枚举</span><span class="sxs-lookup"><span data-stu-id="b99ba-129">To declare an enumeration as an explicit type</span></span>  
  
-   <span data-ttu-id="b99ba-130">使用指定的枚举类型`As`子句，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="b99ba-130">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     <span data-ttu-id="b99ba-131">[!code-vb[VbEnumsTask #&6;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="b99ba-131">[!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b99ba-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b99ba-132">See Also</span></span>  
 <span data-ttu-id="b99ba-133">[枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="b99ba-133">[Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="b99ba-134"> [如何︰ 为枚举成员，请参阅](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span><span class="sxs-lookup"><span data-stu-id="b99ba-134"> [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span></span>  
<span data-ttu-id="b99ba-135"> [如何︰ 循环访问在 Visual Basic 中枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span><span class="sxs-lookup"><span data-stu-id="b99ba-135"> [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span></span>  
<span data-ttu-id="b99ba-136"> [如何︰ 确定与枚举值关联的字符串](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span><span class="sxs-lookup"><span data-stu-id="b99ba-136"> [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span></span>  
<span data-ttu-id="b99ba-137"> [何时使用枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md) </span><span class="sxs-lookup"><span data-stu-id="b99ba-137"> [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md) </span></span>  
<span data-ttu-id="b99ba-138"> [常量概述](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="b99ba-138"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="b99ba-139"> [常量和 Literal 数据类型](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="b99ba-139"> [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="b99ba-140"> [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="b99ba-140"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>

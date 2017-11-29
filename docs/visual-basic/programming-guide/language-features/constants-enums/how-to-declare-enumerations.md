---
title: "如何：声明枚举 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 938550ebbfcf099729db3de96b809549cb234d81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="60e37-102">如何：声明枚举 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60e37-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="60e37-103">创建一个包含枚举`Enum`声明部分中的类或模块的语句。</span><span class="sxs-lookup"><span data-stu-id="60e37-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="60e37-104">不能声明枚举的方法内。</span><span class="sxs-lookup"><span data-stu-id="60e37-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="60e37-105">若要指定适当的访问级别，使用`Private`， `Protected`， `Friend`，或`Public`。</span><span class="sxs-lookup"><span data-stu-id="60e37-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="60e37-106">`Enum`类型都有名称、 一个基础类型和一组字段，各表示常量。</span><span class="sxs-lookup"><span data-stu-id="60e37-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="60e37-107">该名称必须是有效的 Visual Basic.NET 限定符。</span><span class="sxs-lookup"><span data-stu-id="60e37-107">The name must be a valid Visual Basic .NET qualifier.</span></span> <span data-ttu-id="60e37-108">基础类型必须是整数类型之一-`Byte`， `Short`，`Long`或`Integer`。</span><span class="sxs-lookup"><span data-stu-id="60e37-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="60e37-109">默认为 `Integer`。</span><span class="sxs-lookup"><span data-stu-id="60e37-109">`Integer` is the default.</span></span> <span data-ttu-id="60e37-110">枚举始终强类型和不可互换与整数类型。</span><span class="sxs-lookup"><span data-stu-id="60e37-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="60e37-111">枚举不能具有浮点值。</span><span class="sxs-lookup"><span data-stu-id="60e37-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="60e37-112">如果枚举分配具有的浮点值`Option Strict On`，将导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="60e37-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="60e37-113">如果`Option Strict`是`Off`，值自动转换为`Enum`类型。</span><span class="sxs-lookup"><span data-stu-id="60e37-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="60e37-114">有关如何使用和名称，信息`Imports`语句使名称限定不必要的请参阅[枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)。</span><span class="sxs-lookup"><span data-stu-id="60e37-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="60e37-115">若要声明枚举</span><span class="sxs-lookup"><span data-stu-id="60e37-115">To declare an enumeration</span></span>  
  
1.  <span data-ttu-id="60e37-116">编写包含代码访问级别，声明`Enum`关键字和有效的名称，如下面的示例，其中每个声明不同`Enum`。</span><span class="sxs-lookup"><span data-stu-id="60e37-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  <span data-ttu-id="60e37-117">枚举中定义常量。</span><span class="sxs-lookup"><span data-stu-id="60e37-117">Define the constants in the enumeration.</span></span> <span data-ttu-id="60e37-118">默认情况下，枚举中的第一个常数初始化为`0`，而后续常量将初始化为一个多个前面的常数的值。</span><span class="sxs-lookup"><span data-stu-id="60e37-118">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="60e37-119">例如，下面的枚举， `Days`，包含名为常量`Sunday`值`0`，名为常量`Monday`值`1`，名为常量`Tuesday`的值与`2`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="60e37-119">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  <span data-ttu-id="60e37-120">显式可以通过使用赋值语句将值分配给枚举中的常量。</span><span class="sxs-lookup"><span data-stu-id="60e37-120">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="60e37-121">你可以分配任何整数值，包括负数。</span><span class="sxs-lookup"><span data-stu-id="60e37-121">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="60e37-122">例如，你可能想常量值小于零表示错误条件。</span><span class="sxs-lookup"><span data-stu-id="60e37-122">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="60e37-123">在下面的枚举常量`Invalid`显式分配的值`–1`，和常量`Sunday`分配的值`0`。</span><span class="sxs-lookup"><span data-stu-id="60e37-123">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="60e37-124">因为它是在枚举中，第一个常量`Saturday`还初始化为值`0`。</span><span class="sxs-lookup"><span data-stu-id="60e37-124">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="60e37-125">值`Monday`是`1`(一的值大于`Sunday`); 的值`Tuesday`是`2`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="60e37-125">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="60e37-126">若要声明为显式类型枚举</span><span class="sxs-lookup"><span data-stu-id="60e37-126">To declare an enumeration as an explicit type</span></span>  
  
-   <span data-ttu-id="60e37-127">通过使用指定的枚举类型`As`子句，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="60e37-127">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="60e37-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60e37-128">See Also</span></span>  
 [<span data-ttu-id="60e37-129">枚举和名称限定</span><span class="sxs-lookup"><span data-stu-id="60e37-129">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="60e37-130">如何：引用枚举成员</span><span class="sxs-lookup"><span data-stu-id="60e37-130">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="60e37-131">如何： 循环访问 Visual Basic 中的一个枚举</span><span class="sxs-lookup"><span data-stu-id="60e37-131">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="60e37-132">如何：确定与枚举值关联的字符串</span><span class="sxs-lookup"><span data-stu-id="60e37-132">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="60e37-133">何时使用枚举</span><span class="sxs-lookup"><span data-stu-id="60e37-133">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="60e37-134">常量概述</span><span class="sxs-lookup"><span data-stu-id="60e37-134">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="60e37-135">常量和文本数据类型</span><span class="sxs-lookup"><span data-stu-id="60e37-135">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="60e37-136">常量和枚举</span><span class="sxs-lookup"><span data-stu-id="60e37-136">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)

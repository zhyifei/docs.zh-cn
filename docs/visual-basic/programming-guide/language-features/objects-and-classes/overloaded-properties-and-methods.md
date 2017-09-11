---
title: "重载属性和方法 (Visual Basic 中) |Microsoft 文档"
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
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names, multiple procedures with same
- procedures, mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword, overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: 12
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
ms.openlocfilehash: 0b0040f78fd8e091027e32efae3a0f26c2a08622
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="457c7-102">重载属性和方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="457c7-102">Overloaded Properties and Methods (Visual Basic)</span></span>
<span data-ttu-id="457c7-103">重载是创建多个过程、 实例构造函数或在具有相同名称但不同的参数类型的类中的属性。</span><span class="sxs-lookup"><span data-stu-id="457c7-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>  
  
## <a name="overloading-usage"></a><span data-ttu-id="457c7-104">重载用法</span><span class="sxs-lookup"><span data-stu-id="457c7-104">Overloading Usage</span></span>  
 <span data-ttu-id="457c7-105">当您的对象模型指示您使用有关对不同的数据类型进行操作的过程相同的名称，则重载是特别有用。</span><span class="sxs-lookup"><span data-stu-id="457c7-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="457c7-106">例如，可以显示几种不同的数据类型的类可以具有`Display`过程如下所示︰</span><span class="sxs-lookup"><span data-stu-id="457c7-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>  
  
 <span data-ttu-id="457c7-107">[!code-vb[VbVbalrOOP #&64;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="457c7-107">[!code-vb[VbVbalrOOP#64](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]</span></span>  
  
 <span data-ttu-id="457c7-108">如果没有重载，您需要创建不同的名称，为每个过程，即使它们做同样的内容，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="457c7-108">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>  
  
 <span data-ttu-id="457c7-109">[!code-vb[VbVbalrOOP #&65;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="457c7-109">[!code-vb[VbVbalrOOP#65](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]</span></span>  
  
 <span data-ttu-id="457c7-110">重载使得更轻松地使用属性或方法，因为它提供了一种可用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="457c7-110">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="457c7-111">例如，重载`Display`以前可以与任何下面的代码行调用讨论的方法︰</span><span class="sxs-lookup"><span data-stu-id="457c7-111">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>  
  
 <span data-ttu-id="457c7-112">[!code-vb[VbVbalrOOP #&66;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="457c7-112">[!code-vb[VbVbalrOOP#66](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]</span></span>  
  
 <span data-ttu-id="457c7-113">在运行时，[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]调用参数的数据类型的正确的过程基于您指定。</span><span class="sxs-lookup"><span data-stu-id="457c7-113">At run time, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] calls the correct procedure based on the data types of the parameters you specify.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="457c7-114">重载规则</span><span class="sxs-lookup"><span data-stu-id="457c7-114">Overloading Rules</span></span>  
 <span data-ttu-id="457c7-115">通过添加两个或多个属性或方法具有相同名称创建一个类的重载的成员。</span><span class="sxs-lookup"><span data-stu-id="457c7-115">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="457c7-116">除了重载派生的成员，每个重载的成员必须具有不同的参数列表和以下各项不能用作区别特征，重载属性或过程时︰</span><span class="sxs-lookup"><span data-stu-id="457c7-116">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>  
  
-   <span data-ttu-id="457c7-117">修饰符，如`ByVal`或`ByRef`，适用于一个成员或成员的参数。</span><span class="sxs-lookup"><span data-stu-id="457c7-117">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>  
  
-   <span data-ttu-id="457c7-118">参数的名称</span><span class="sxs-lookup"><span data-stu-id="457c7-118">Names of parameters</span></span>  
  
-   <span data-ttu-id="457c7-119">过程的返回类型</span><span class="sxs-lookup"><span data-stu-id="457c7-119">Return types of procedures</span></span>  
  
 <span data-ttu-id="457c7-120">`Overloads`关键字时是可选的重载，但如果任一重载成员使用`Overloads`关键字，则具有相同名称的所有其他重载的成员还必须指定此关键字。</span><span class="sxs-lookup"><span data-stu-id="457c7-120">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>  
  
 <span data-ttu-id="457c7-121">派生的类可以重载具有相同的参数和参数类型，该过程称为的成员的继承的成员*按名称和签名隐藏*。</span><span class="sxs-lookup"><span data-stu-id="457c7-121">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="457c7-122">如果`Overloads`关键字按名称和签名隐藏，派生的类的成员将使用实现而不是在基的类中，实现和为该成员的所有其他重载将可供派生类的实例时使用。</span><span class="sxs-lookup"><span data-stu-id="457c7-122">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>  
  
 <span data-ttu-id="457c7-123">如果`Overloads`重载具有相同的参数和参数类型的成员继承的成员时省略关键字，则该重载称为*按名称隐藏*。</span><span class="sxs-lookup"><span data-stu-id="457c7-123">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="457c7-124">按名称隐藏替换的继承成员的实现，并使所有其他重载实例派生的类和其对于都不可用。</span><span class="sxs-lookup"><span data-stu-id="457c7-124">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>  
  
 <span data-ttu-id="457c7-125">`Overloads`和`Shadows`修饰符不能同时使用具有相同属性或方法。</span><span class="sxs-lookup"><span data-stu-id="457c7-125">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="457c7-126">示例</span><span class="sxs-lookup"><span data-stu-id="457c7-126">Example</span></span>  
 <span data-ttu-id="457c7-127">下面的示例创建接受的重载的方法`String`或`Decimal`美元金额限度和返回一个包含增值税的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="457c7-127">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>  
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="457c7-128">若要使用此示例创建一个重载的方法</span><span class="sxs-lookup"><span data-stu-id="457c7-128">To use this example to create an overloaded method</span></span>  
  
1.  <span data-ttu-id="457c7-129">打开新项目并添加一个名为类`TaxClass`。</span><span class="sxs-lookup"><span data-stu-id="457c7-129">Open a new project and add a class named `TaxClass`.</span></span>  
  
2.  <span data-ttu-id="457c7-130">向 `TaxClass` 类添加下面的代码。</span><span class="sxs-lookup"><span data-stu-id="457c7-130">Add the following code to the `TaxClass` class.</span></span>  
  
     <span data-ttu-id="457c7-131">[!code-vb[VbVbalrOOP #&67;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="457c7-131">[!code-vb[VbVbalrOOP#67](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]</span></span>  
  
3.  <span data-ttu-id="457c7-132">向窗体中添加下面的过程。</span><span class="sxs-lookup"><span data-stu-id="457c7-132">Add the following procedure to your form.</span></span>  
  
     <span data-ttu-id="457c7-133">[!code-vb[VbVbalrOOP #&68;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="457c7-133">[!code-vb[VbVbalrOOP#68](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]</span></span>  
  
4.  <span data-ttu-id="457c7-134">将按钮添加到表单中，然后调用`ShowTax`过程从`Button1_Click`该按钮的事件。</span><span class="sxs-lookup"><span data-stu-id="457c7-134">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>  
  
5.  <span data-ttu-id="457c7-135">运行该项目并单击要测试的重载的窗体上的按钮`ShowTax`过程。</span><span class="sxs-lookup"><span data-stu-id="457c7-135">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>  
  
 <span data-ttu-id="457c7-136">在运行时，编译器将选择与正在使用的参数匹配的适当重载的函数。</span><span class="sxs-lookup"><span data-stu-id="457c7-136">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="457c7-137">重载的方法时单击按钮时，与第一次调用`Price`参数是一个字符串，该邮件，"价格是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="457c7-137">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="457c7-138">税是 $5.12"显示。</span><span class="sxs-lookup"><span data-stu-id="457c7-138">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="457c7-139">`TaxAmount`使用调用`Decimal`值的第二个时间和消息，"价格是十进制数。</span><span class="sxs-lookup"><span data-stu-id="457c7-139">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="457c7-140">税是 $5.12"显示。</span><span class="sxs-lookup"><span data-stu-id="457c7-140">Tax is $5.12" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457c7-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="457c7-141">See Also</span></span>  
 <span data-ttu-id="457c7-142">[对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="457c7-142">[Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="457c7-143"> [Visual Basic 中的隐藏](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md) </span><span class="sxs-lookup"><span data-stu-id="457c7-143"> [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md) </span></span>  
<span data-ttu-id="457c7-144"> [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="457c7-144"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="457c7-145"> [继承的基础知识](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) </span><span class="sxs-lookup"><span data-stu-id="457c7-145"> [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md) </span></span>  
<span data-ttu-id="457c7-146"> [阴影](../../../../visual-basic/language-reference/modifiers/shadows.md) </span><span class="sxs-lookup"><span data-stu-id="457c7-146"> [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) </span></span>  
<span data-ttu-id="457c7-147"> [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) </span><span class="sxs-lookup"><span data-stu-id="457c7-147"> [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) </span></span>  
<span data-ttu-id="457c7-148"> [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) </span><span class="sxs-lookup"><span data-stu-id="457c7-148"> [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) </span></span>  
<span data-ttu-id="457c7-149"> [重载](../../../../visual-basic/language-reference/modifiers/overloads.md) </span><span class="sxs-lookup"><span data-stu-id="457c7-149"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) </span></span>  
<span data-ttu-id="457c7-150"> [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)</span><span class="sxs-lookup"><span data-stu-id="457c7-150"> [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)</span></span>

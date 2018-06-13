---
title: 重载的属性和方法 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: c0aa7c4a13e049045743044a98020a1aab2cf1a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652189"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a><span data-ttu-id="96685-102">重载的属性和方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96685-102">Overloaded properties and methods (Visual Basic)</span></span>

<span data-ttu-id="96685-103">重载是创建多个过程、 实例构造函数或在具有相同名称但不同的自变量类型的类的属性。</span><span class="sxs-lookup"><span data-stu-id="96685-103">Overloading is the creation of more than one procedure, instance constructor, or property in a class with the same name but different argument types.</span></span>  
  
## <a name="overloading-usage"></a><span data-ttu-id="96685-104">重载使用情况</span><span class="sxs-lookup"><span data-stu-id="96685-104">Overloading usage</span></span>

 <span data-ttu-id="96685-105">当您的对象模型指示你使用的操作对不同数据类型的过程相同的名称，则重载是特别有用。</span><span class="sxs-lookup"><span data-stu-id="96685-105">Overloading is especially useful when your object model dictates that you employ identical names for procedures that operate on different data types.</span></span> <span data-ttu-id="96685-106">例如，可以显示多种不同的数据类型的类可能具有`Display`过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="96685-106">For example, a class that can display several different data types could have `Display` procedures that look like this:</span></span>  
  
 [!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]
  
 <span data-ttu-id="96685-107">如果没有重载，你将需要创建不同的名称，为每个过程，即使它们执行相同的操作中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="96685-107">Without overloading, you would need to create distinct names for each procedure, even though they do the same thing, as shown next:</span></span>  
  
 [!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]
  
 <span data-ttu-id="96685-108">重载，使得更轻松地使用属性或方法，因为它提供了一种可以使用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="96685-108">Overloading makes it easier to use properties or methods because it provides a choice of data types that can be used.</span></span> <span data-ttu-id="96685-109">例如，重载`Display`以前可以使用以下代码行的任何调用讨论的方法：</span><span class="sxs-lookup"><span data-stu-id="96685-109">For example, the overloaded `Display` method discussed previously can be called with any of the following lines of code:</span></span>  
  
 [!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]
  
 <span data-ttu-id="96685-110">在运行时，Visual Basic 调用正确的过程基于你指定的参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="96685-110">At run time, Visual Basic calls the correct procedure based on the data types of the parameters you specify.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="96685-111">重载规则</span><span class="sxs-lookup"><span data-stu-id="96685-111">Overloading rules</span></span>

 <span data-ttu-id="96685-112">通过添加两个或多个属性或方法具有相同名称创建的类重载的成员。</span><span class="sxs-lookup"><span data-stu-id="96685-112">You create an overloaded member for a class by adding two or more properties or methods with the same name.</span></span> <span data-ttu-id="96685-113">除非是重载派生成员，每个重载的成员必须具有不同的参数列表和重载属性或过程时，不作为区别性功能使用以下各项：</span><span class="sxs-lookup"><span data-stu-id="96685-113">Except for overloaded derived members, each overloaded member must have different parameter lists, and the following items cannot be used as a differentiating feature when overloading a property or procedure:</span></span>  
  
-   <span data-ttu-id="96685-114">修饰符，如`ByVal`或`ByRef`，适用于成员或参数的成员。</span><span class="sxs-lookup"><span data-stu-id="96685-114">Modifiers, such as `ByVal` or `ByRef`, that apply to a member, or parameters of the member.</span></span>  
  
-   <span data-ttu-id="96685-115">参数的名称</span><span class="sxs-lookup"><span data-stu-id="96685-115">Names of parameters</span></span>  
  
-   <span data-ttu-id="96685-116">返回类型的过程</span><span class="sxs-lookup"><span data-stu-id="96685-116">Return types of procedures</span></span>  
  
 <span data-ttu-id="96685-117">`Overloads`关键字时是可选的重载，但如果任一重载成员均使用`Overloads`关键字，则所有其他重载的成员具有相同名称还必须指定此关键字。</span><span class="sxs-lookup"><span data-stu-id="96685-117">The `Overloads` keyword is optional when overloading, but if any overloaded member uses the `Overloads` keyword, then all other overloaded members with the same name must also specify this keyword.</span></span>  
  
 <span data-ttu-id="96685-118">派生的类可以重载具有相同的参数和参数类型，该过程称为的成员的继承的成员*按名称和签名隐藏*。</span><span class="sxs-lookup"><span data-stu-id="96685-118">Derived classes can overload inherited members with members that have identical parameters and parameter types, a process known as *shadowing by name and signature*.</span></span> <span data-ttu-id="96685-119">如果`Overloads`按名称和签名隐藏，派生的类的成员的实现将使用而不是在基的类中，实现和所有其他重载对于该成员将可供使用的实例时所使用关键字派生的类。</span><span class="sxs-lookup"><span data-stu-id="96685-119">If the `Overloads` keyword is used when shadowing by name and signature, the derived class's implementation of the member will be used instead of the implementation in the base class, and all other overloads for that member will be available to instances of the derived class.</span></span>  
  
 <span data-ttu-id="96685-120">如果`Overloads`重载具有成员的具有相同的参数和参数类型，继承的成员时省略关键字，则该重载称为*通过名称来隐藏*。</span><span class="sxs-lookup"><span data-stu-id="96685-120">If the `Overloads` keyword is omitted when overloading an inherited member with a member that has identical parameters and parameter types, then the overloading is called *shadowing by name*.</span></span> <span data-ttu-id="96685-121">通过名称来隐藏替换继承的成员，实现，并使所有其他重载到的实例派生的类和其对于不可用。</span><span class="sxs-lookup"><span data-stu-id="96685-121">Shadowing by name replaces the inherited implementation of a member, and it makes all other overloads unavailable to instances of the derived class and its decedents.</span></span>  
  
 <span data-ttu-id="96685-122">`Overloads`和`Shadows`修饰符不能同时使用具有相同的属性或方法。</span><span class="sxs-lookup"><span data-stu-id="96685-122">The `Overloads` and `Shadows` modifiers cannot both be used with the same property or method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="96685-123">示例</span><span class="sxs-lookup"><span data-stu-id="96685-123">Example</span></span>

 <span data-ttu-id="96685-124">下面的示例创建接受的重载的方法`String`或`Decimal`美元总金额和返回包含增值税的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="96685-124">The following example creates overloaded methods that accept either a `String` or `Decimal` representation of a dollar amount and return a string containing the sales tax.</span></span>  
  
#### <a name="to-use-this-example-to-create-an-overloaded-method"></a><span data-ttu-id="96685-125">若要使用此示例创建了重载的方法</span><span class="sxs-lookup"><span data-stu-id="96685-125">To use this example to create an overloaded method</span></span>
  
1.  <span data-ttu-id="96685-126">打开一个新项目并添加一个名为类`TaxClass`。</span><span class="sxs-lookup"><span data-stu-id="96685-126">Open a new project and add a class named `TaxClass`.</span></span>  
  
2.  <span data-ttu-id="96685-127">向 `TaxClass` 类添加下面的代码。</span><span class="sxs-lookup"><span data-stu-id="96685-127">Add the following code to the `TaxClass` class.</span></span>  
  
     [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]
  
3.  <span data-ttu-id="96685-128">向窗体中添加下面的过程。</span><span class="sxs-lookup"><span data-stu-id="96685-128">Add the following procedure to your form.</span></span>  
  
     [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]
  
4.  <span data-ttu-id="96685-129">将按钮添加到表单中，然后调用`ShowTax`过程从`Button1_Click`该按钮的事件。</span><span class="sxs-lookup"><span data-stu-id="96685-129">Add a button to your form and call the `ShowTax` procedure from the `Button1_Click` event of the button.</span></span>  
  
5.  <span data-ttu-id="96685-130">运行该项目并单击要测试的重载的窗体上的按钮`ShowTax`过程。</span><span class="sxs-lookup"><span data-stu-id="96685-130">Run the project and click the button on the form to test the overloaded `ShowTax` procedure.</span></span>  
  
 <span data-ttu-id="96685-131">在运行时，编译器将选择相应的重载的函数正在使用的参数匹配。</span><span class="sxs-lookup"><span data-stu-id="96685-131">At run time, the compiler chooses the appropriate overloaded function that matches the parameters being used.</span></span> <span data-ttu-id="96685-132">重载的方法时单击按钮时，都会首先调用与`Price`参数是一个字符串和消息，"价格是一个字符串。</span><span class="sxs-lookup"><span data-stu-id="96685-132">When you click the button, the overloaded method is called first with a `Price` parameter that is a string and the message, "Price is a String.</span></span> <span data-ttu-id="96685-133">税金是 $5.12"显示。</span><span class="sxs-lookup"><span data-stu-id="96685-133">Tax is $5.12" is displayed.</span></span> <span data-ttu-id="96685-134">`TaxAmount` 使用调用`Decimal`值的第二个时间和消息时，请"价格是十进制。</span><span class="sxs-lookup"><span data-stu-id="96685-134">`TaxAmount` is called with a `Decimal` value the second time and the message, "Price is a Decimal.</span></span> <span data-ttu-id="96685-135">税金是 $5.12"显示。</span><span class="sxs-lookup"><span data-stu-id="96685-135">Tax is $5.12" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96685-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="96685-136">See also</span></span>

 [<span data-ttu-id="96685-137">对象和类</span><span class="sxs-lookup"><span data-stu-id="96685-137">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="96685-138">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="96685-138">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="96685-139">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="96685-139">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="96685-140">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="96685-140">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="96685-141">Shadows</span><span class="sxs-lookup"><span data-stu-id="96685-141">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="96685-142">ByVal</span><span class="sxs-lookup"><span data-stu-id="96685-142">ByVal</span></span>](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [<span data-ttu-id="96685-143">ByRef</span><span class="sxs-lookup"><span data-stu-id="96685-143">ByRef</span></span>](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [<span data-ttu-id="96685-144">重载</span><span class="sxs-lookup"><span data-stu-id="96685-144">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="96685-145">Shadows</span><span class="sxs-lookup"><span data-stu-id="96685-145">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)

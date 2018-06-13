---
title: MustInherit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 5d622c1cff77a45c8de7772af7efbb73586f4400
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602835"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="74039-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74039-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="74039-103">指定一个类可以仅用作基类，您不能直接从它创建一个对象。</span><span class="sxs-lookup"><span data-stu-id="74039-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74039-104">备注</span><span class="sxs-lookup"><span data-stu-id="74039-104">Remarks</span></span>  
 <span data-ttu-id="74039-105">用途*基类*(也称为*抽象类*) 是定义普遍适用于所有从它派生的类的功能。</span><span class="sxs-lookup"><span data-stu-id="74039-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="74039-106">这可以节省派生的类无需重新定义的常用元素。</span><span class="sxs-lookup"><span data-stu-id="74039-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="74039-107">在某些情况下，此常用的功能不足够完成，以使可用对象，并且每个派生的类定义所缺少的功能。</span><span class="sxs-lookup"><span data-stu-id="74039-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="74039-108">在这种情况下，你希望使用的代码只能从派生类中创建对象。</span><span class="sxs-lookup"><span data-stu-id="74039-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="74039-109">你使用`MustInherit`来强制执行此基本类。</span><span class="sxs-lookup"><span data-stu-id="74039-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="74039-110">另一个用途`MustInherit`类是限制对一组相关的类的变量。</span><span class="sxs-lookup"><span data-stu-id="74039-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="74039-111">你可以定义一个基类，并从其派生所有这些相关的类。</span><span class="sxs-lookup"><span data-stu-id="74039-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="74039-112">基类不需要提供任何功能普遍适用于所有派生的类，但其可用作筛选器将值赋给变量。</span><span class="sxs-lookup"><span data-stu-id="74039-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="74039-113">如果你使用的代码声明一个变量，作为类的基类，则 Visual Basic，可从派生类之一仅对象分配给该变量。</span><span class="sxs-lookup"><span data-stu-id="74039-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="74039-114">.NET Framework 定义了几个`MustInherit`类，它们之间<xref:System.Array>， <xref:System.Enum>，和<xref:System.ValueType>。</span><span class="sxs-lookup"><span data-stu-id="74039-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="74039-115"><xref:System.ValueType> 是一个基类，用于限制变量的示例。</span><span class="sxs-lookup"><span data-stu-id="74039-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="74039-116">所有值类型都派生自<xref:System.ValueType>。</span><span class="sxs-lookup"><span data-stu-id="74039-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="74039-117">如果你声明一个变量，作为<xref:System.ValueType>，可以将只有值类型分配给该变量。</span><span class="sxs-lookup"><span data-stu-id="74039-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="74039-118">规则</span><span class="sxs-lookup"><span data-stu-id="74039-118">Rules</span></span>  
  
-   <span data-ttu-id="74039-119">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="74039-119">**Declaration Context.**</span></span> <span data-ttu-id="74039-120">你可以使用`MustInherit`仅在`Class`语句。</span><span class="sxs-lookup"><span data-stu-id="74039-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
-   <span data-ttu-id="74039-121">**组合的修饰符。**</span><span class="sxs-lookup"><span data-stu-id="74039-121">**Combined Modifiers.**</span></span> <span data-ttu-id="74039-122">不能指定`MustInherit`连同`NotInheritable`同一声明中。</span><span class="sxs-lookup"><span data-stu-id="74039-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74039-123">示例</span><span class="sxs-lookup"><span data-stu-id="74039-123">Example</span></span>  
 <span data-ttu-id="74039-124">下面的示例演示强制的继承和强制重写。</span><span class="sxs-lookup"><span data-stu-id="74039-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="74039-125">基类`shape`定义变量`acrossLine`。</span><span class="sxs-lookup"><span data-stu-id="74039-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="74039-126">类`circle`和`square`派生自`shape`。</span><span class="sxs-lookup"><span data-stu-id="74039-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="74039-127">他们会继承的定义`acrossLine`，但它们必须定义函数`area`因为该计算每种类型的形状不同。</span><span class="sxs-lookup"><span data-stu-id="74039-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](../../../visual-basic/language-reference/codesnippet/VisualBasic/mustinherit_1.vb)]  
  
 <span data-ttu-id="74039-128">你可以声明`shape1`和`shape2`类型`shape`。</span><span class="sxs-lookup"><span data-stu-id="74039-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="74039-129">但是，你无法从其创建对象`shape`因为它缺少的功能函数`area`和标记`MustInherit`。</span><span class="sxs-lookup"><span data-stu-id="74039-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="74039-130">因为它们被声明为`shape`，变量`shape1`和`shape2`限于对象派生的类从`circle`和`square`。</span><span class="sxs-lookup"><span data-stu-id="74039-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="74039-131">Visual Basic 不允许您将任何其他对象分配给这些变量，这为你提供类型安全的高级别。</span><span class="sxs-lookup"><span data-stu-id="74039-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="74039-132">用法</span><span class="sxs-lookup"><span data-stu-id="74039-132">Usage</span></span>  
 <span data-ttu-id="74039-133">`MustInherit`修饰符可用于在此上下文中：</span><span class="sxs-lookup"><span data-stu-id="74039-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="74039-134">Class 语句</span><span class="sxs-lookup"><span data-stu-id="74039-134">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="74039-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="74039-135">See Also</span></span>  
 [<span data-ttu-id="74039-136">Inherits 语句</span><span class="sxs-lookup"><span data-stu-id="74039-136">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="74039-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="74039-137">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [<span data-ttu-id="74039-138">关键字</span><span class="sxs-lookup"><span data-stu-id="74039-138">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="74039-139">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="74039-139">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)

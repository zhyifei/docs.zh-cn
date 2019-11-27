---
title: MustInherit
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
ms.openlocfilehash: 30befaaf194d78d26a57f29c59bf0a603e9f07a3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351499"
---
# <a name="mustinherit-visual-basic"></a><span data-ttu-id="2ce55-102">MustInherit (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ce55-102">MustInherit (Visual Basic)</span></span>
<span data-ttu-id="2ce55-103">指定类只能用作基类，并且不能直接从其创建对象。</span><span class="sxs-lookup"><span data-stu-id="2ce55-103">Specifies that a class can be used only as a base class and that you cannot create an object directly from it.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ce55-104">备注</span><span class="sxs-lookup"><span data-stu-id="2ce55-104">Remarks</span></span>  
 <span data-ttu-id="2ce55-105">*基类*（也称为*抽象类*）的目的是定义从其派生的所有类所共有的功能。</span><span class="sxs-lookup"><span data-stu-id="2ce55-105">The purpose of a *base class* (also known as an *abstract class*) is to define functionality that is common to all the classes derived from it.</span></span> <span data-ttu-id="2ce55-106">这会保存派生类，使其不必重新定义公共元素。</span><span class="sxs-lookup"><span data-stu-id="2ce55-106">This saves the derived classes from having to redefine the common elements.</span></span> <span data-ttu-id="2ce55-107">在某些情况下，这种通用功能不够完整，无法生成可用的对象，并且每个派生类都定义了缺少的功能。</span><span class="sxs-lookup"><span data-stu-id="2ce55-107">In some cases, this common functionality is not complete enough to make a usable object, and each derived class defines the missing functionality.</span></span> <span data-ttu-id="2ce55-108">在这种情况下，你希望使用代码仅在派生类中创建对象。</span><span class="sxs-lookup"><span data-stu-id="2ce55-108">In such a case, you want the consuming code to create objects only from the derived classes.</span></span> <span data-ttu-id="2ce55-109">使用基类上的 `MustInherit` 来强制执行此类。</span><span class="sxs-lookup"><span data-stu-id="2ce55-109">You use `MustInherit` on the base class to enforce this.</span></span>  
  
 <span data-ttu-id="2ce55-110">`MustInherit` 类的另一种用法是将变量限制为一组相关的类。</span><span class="sxs-lookup"><span data-stu-id="2ce55-110">Another use of a `MustInherit` class is to restrict a variable to a set of related classes.</span></span> <span data-ttu-id="2ce55-111">你可以定义一个基类，并从其派生所有这些相关的类。</span><span class="sxs-lookup"><span data-stu-id="2ce55-111">You can define a base class and derive all these related classes from it.</span></span> <span data-ttu-id="2ce55-112">基类不需要提供所有派生类共有的任何功能，但它可以充当用于向变量赋值的筛选器。</span><span class="sxs-lookup"><span data-stu-id="2ce55-112">The base class does not need to provide any functionality common to all the derived classes, but it can serve as a filter for assigning values to variables.</span></span> <span data-ttu-id="2ce55-113">如果你使用的代码将变量声明为基类，则 Visual Basic 允许你仅将一个派生类中的对象分配给该变量。</span><span class="sxs-lookup"><span data-stu-id="2ce55-113">If your consuming code declares a variable as the base class, Visual Basic allows you to assign only an object from one of the derived classes to that variable.</span></span>  
  
 <span data-ttu-id="2ce55-114">.NET Framework 定义了多个 `MustInherit` 类，它们 <xref:System.Array>、<xref:System.Enum>和 <xref:System.ValueType>中。</span><span class="sxs-lookup"><span data-stu-id="2ce55-114">The .NET Framework defines several `MustInherit` classes, among them <xref:System.Array>, <xref:System.Enum>, and <xref:System.ValueType>.</span></span> <span data-ttu-id="2ce55-115"><xref:System.ValueType> 是限制变量的基类的一个示例。</span><span class="sxs-lookup"><span data-stu-id="2ce55-115"><xref:System.ValueType> is an example of a base class that restricts a variable.</span></span> <span data-ttu-id="2ce55-116">所有值类型都派生自 <xref:System.ValueType>。</span><span class="sxs-lookup"><span data-stu-id="2ce55-116">All value types derive from <xref:System.ValueType>.</span></span> <span data-ttu-id="2ce55-117">如果将变量声明为 <xref:System.ValueType>，则只能将值类型分配给该变量。</span><span class="sxs-lookup"><span data-stu-id="2ce55-117">If you declare a variable as <xref:System.ValueType>, you can assign only value types to that variable.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="2ce55-118">规则</span><span class="sxs-lookup"><span data-stu-id="2ce55-118">Rules</span></span>  
  
- <span data-ttu-id="2ce55-119">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="2ce55-119">**Declaration Context.**</span></span> <span data-ttu-id="2ce55-120">只能在 `Class` 语句中使用 `MustInherit`。</span><span class="sxs-lookup"><span data-stu-id="2ce55-120">You can use `MustInherit` only in a `Class` statement.</span></span>  
  
- <span data-ttu-id="2ce55-121">**组合修饰符。**</span><span class="sxs-lookup"><span data-stu-id="2ce55-121">**Combined Modifiers.**</span></span> <span data-ttu-id="2ce55-122">不能在同一声明中同时指定 `MustInherit` 和 `NotInheritable`。</span><span class="sxs-lookup"><span data-stu-id="2ce55-122">You cannot specify `MustInherit` together with `NotInheritable` in the same declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ce55-123">示例</span><span class="sxs-lookup"><span data-stu-id="2ce55-123">Example</span></span>  
 <span data-ttu-id="2ce55-124">下面的示例演示强制的继承和强制重写。</span><span class="sxs-lookup"><span data-stu-id="2ce55-124">The following example illustrates both forced inheritance and forced overriding.</span></span> <span data-ttu-id="2ce55-125">基类 `shape` 定义 `acrossLine`变量。</span><span class="sxs-lookup"><span data-stu-id="2ce55-125">The base class `shape` defines a variable `acrossLine`.</span></span> <span data-ttu-id="2ce55-126">类 `circle` 和 `square` 派生自 `shape`。</span><span class="sxs-lookup"><span data-stu-id="2ce55-126">The classes `circle` and `square` derive from `shape`.</span></span> <span data-ttu-id="2ce55-127">它们继承 `acrossLine`的定义，但必须定义函数 `area`，因为每种形状的计算都是不同的。</span><span class="sxs-lookup"><span data-stu-id="2ce55-127">They inherit the definition of `acrossLine`, but they must define the function `area` because that calculation is different for each kind of shape.</span></span>  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 <span data-ttu-id="2ce55-128">可以将 `shape1` 和 `shape2` 声明为 `shape`类型。</span><span class="sxs-lookup"><span data-stu-id="2ce55-128">You can declare `shape1` and `shape2` to be of type `shape`.</span></span> <span data-ttu-id="2ce55-129">但是，不能从 `shape` 创建对象，因为它缺少函数 `area` 的功能，并将其标记为 `MustInherit`。</span><span class="sxs-lookup"><span data-stu-id="2ce55-129">However, you cannot create an object from `shape` because it lacks the functionality of the function `area` and is marked `MustInherit`.</span></span>  
  
 <span data-ttu-id="2ce55-130">由于它们被声明为 `shape`，因此 `shape1` 和 `shape2` 的变量仅限于派生类 `circle` 和 `square`中的对象。</span><span class="sxs-lookup"><span data-stu-id="2ce55-130">Because they are declared as `shape`, the variables `shape1` and `shape2` are restricted to objects from the derived classes `circle` and `square`.</span></span> <span data-ttu-id="2ce55-131">Visual Basic 不允许将任何其他对象分配给这些变量，这为你提供了高级别的类型安全性。</span><span class="sxs-lookup"><span data-stu-id="2ce55-131">Visual Basic does not allow you to assign any other object to these variables, which gives you a high level of type safety.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="2ce55-132">用法</span><span class="sxs-lookup"><span data-stu-id="2ce55-132">Usage</span></span>  
 <span data-ttu-id="2ce55-133">`MustInherit` 修饰符可用于以下上下文：</span><span class="sxs-lookup"><span data-stu-id="2ce55-133">The `MustInherit` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="2ce55-134">Class 语句</span><span class="sxs-lookup"><span data-stu-id="2ce55-134">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="2ce55-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ce55-135">See also</span></span>

- [<span data-ttu-id="2ce55-136">Inherits 语句</span><span class="sxs-lookup"><span data-stu-id="2ce55-136">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="2ce55-137">NotInheritable</span><span class="sxs-lookup"><span data-stu-id="2ce55-137">NotInheritable</span></span>](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [<span data-ttu-id="2ce55-138">关键字</span><span class="sxs-lookup"><span data-stu-id="2ce55-138">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="2ce55-139">继承的基础知识</span><span class="sxs-lookup"><span data-stu-id="2ce55-139">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)

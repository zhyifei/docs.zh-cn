---
title: 隐藏和重写之间的差异 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: b935184f0e4d0378bfea69811aa4e6c068a9776f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827921"
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a><span data-ttu-id="92820-102">隐藏和重写之间的差异 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92820-102">Differences Between Shadowing and Overriding (Visual Basic)</span></span>
<span data-ttu-id="92820-103">定义从基类继承的类时，你有时想要重新定义一个或多个派生类中的基类元素。</span><span class="sxs-lookup"><span data-stu-id="92820-103">When you define a class that inherits from a base class, you sometimes want to redefine one or more of the base class elements in the derived class.</span></span> <span data-ttu-id="92820-104">隐藏和重写均可用于此目的。</span><span class="sxs-lookup"><span data-stu-id="92820-104">Shadowing and overriding are both available for this purpose.</span></span>  
  
## <a name="comparison"></a><span data-ttu-id="92820-105">比较</span><span class="sxs-lookup"><span data-stu-id="92820-105">Comparison</span></span>  
 <span data-ttu-id="92820-106">隐藏和重写同时使用时派生的类继承自基类，并同时重新定义与另一个声明的元素。</span><span class="sxs-lookup"><span data-stu-id="92820-106">Shadowing and overriding are both used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="92820-107">但是，两者之间的重大差异。</span><span class="sxs-lookup"><span data-stu-id="92820-107">But there are significant differences between the two.</span></span>  
  
 <span data-ttu-id="92820-108">下表比较了隐藏和重写。</span><span class="sxs-lookup"><span data-stu-id="92820-108">The following table compares shadowing with overriding.</span></span>  
  
||||  
|---|---|---|  
|<span data-ttu-id="92820-109">比较点</span><span class="sxs-lookup"><span data-stu-id="92820-109">Point of comparison</span></span>|<span data-ttu-id="92820-110">阴影操作</span><span class="sxs-lookup"><span data-stu-id="92820-110">Shadowing</span></span>|<span data-ttu-id="92820-111">重写</span><span class="sxs-lookup"><span data-stu-id="92820-111">Overriding</span></span>|  
|<span data-ttu-id="92820-112">用途</span><span class="sxs-lookup"><span data-stu-id="92820-112">Purpose</span></span>|<span data-ttu-id="92820-113">防止后续的 base 类修改引入您已经在派生类中定义的成员</span><span class="sxs-lookup"><span data-stu-id="92820-113">Protects against a subsequent base-class modification that introduces a member you have already defined in your derived class</span></span>|<span data-ttu-id="92820-114">通过定义的过程或具有相同的调用顺序属性不同的实现，从而实现多形性<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="92820-114">Achieves polymorphism by defining a different implementation of a procedure or property with the same calling sequence<sup>1</sup></span></span>|  
|<span data-ttu-id="92820-115">重新定义的元素</span><span class="sxs-lookup"><span data-stu-id="92820-115">Redefined element</span></span>|<span data-ttu-id="92820-116">任何声明的元素类型</span><span class="sxs-lookup"><span data-stu-id="92820-116">Any declared element type</span></span>|<span data-ttu-id="92820-117">只有过程 (`Function`， `Sub`，或`Operator`) 或属性</span><span class="sxs-lookup"><span data-stu-id="92820-117">Only a procedure (`Function`, `Sub`, or `Operator`) or property</span></span>|  
|<span data-ttu-id="92820-118">重新定义元素</span><span class="sxs-lookup"><span data-stu-id="92820-118">Redefining element</span></span>|<span data-ttu-id="92820-119">任何声明的元素类型</span><span class="sxs-lookup"><span data-stu-id="92820-119">Any declared element type</span></span>|<span data-ttu-id="92820-120">过程或属性与相同的调用序列<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="92820-120">Only a procedure or property with the identical calling sequence<sup>1</sup></span></span>|  
|<span data-ttu-id="92820-121">重定义元素的访问级别</span><span class="sxs-lookup"><span data-stu-id="92820-121">Access level of redefining element</span></span>|<span data-ttu-id="92820-122">任何访问级别</span><span class="sxs-lookup"><span data-stu-id="92820-122">Any access level</span></span>|<span data-ttu-id="92820-123">不能更改重写元素的访问级别</span><span class="sxs-lookup"><span data-stu-id="92820-123">Cannot change access level of overridden element</span></span>|  
|<span data-ttu-id="92820-124">可读性和可写性的重新定义元素</span><span class="sxs-lookup"><span data-stu-id="92820-124">Readability and writability of redefining element</span></span>|<span data-ttu-id="92820-125">任意组合</span><span class="sxs-lookup"><span data-stu-id="92820-125">Any combination</span></span>|<span data-ttu-id="92820-126">不能更改可读性或可写性的重写的属性</span><span class="sxs-lookup"><span data-stu-id="92820-126">Cannot change readability or writability of overridden property</span></span>|  
|<span data-ttu-id="92820-127">控制重定义</span><span class="sxs-lookup"><span data-stu-id="92820-127">Control over redefining</span></span>|<span data-ttu-id="92820-128">不能强制或禁止隐藏基类元素</span><span class="sxs-lookup"><span data-stu-id="92820-128">Base class element cannot enforce or prohibit shadowing</span></span>|<span data-ttu-id="92820-129">可以指定基类元素`MustOverride`， `NotOverridable`，或 `Overridable`</span><span class="sxs-lookup"><span data-stu-id="92820-129">Base class element can specify `MustOverride`, `NotOverridable`, or `Overridable`</span></span>|  
|<span data-ttu-id="92820-130">关键字的用法</span><span class="sxs-lookup"><span data-stu-id="92820-130">Keyword usage</span></span>|<span data-ttu-id="92820-131">`Shadows` 在派生类; 建议`Shadows`如果既不假定`Shadows`也不`Overrides`指定<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="92820-131">`Shadows` recommended in derived class; `Shadows` assumed if neither `Shadows` nor `Overrides` specified<sup>2</sup></span></span>|<span data-ttu-id="92820-132">`Overridable` 或`MustOverride`所需基类; 中`Overrides`派生类中所需</span><span class="sxs-lookup"><span data-stu-id="92820-132">`Overridable` or `MustOverride` required in base class; `Overrides` required in derived class</span></span>|  
|<span data-ttu-id="92820-133">由派生类中派生的类重新定义元素的继承</span><span class="sxs-lookup"><span data-stu-id="92820-133">Inheritance of redefining element by classes deriving from your derived class</span></span>|<span data-ttu-id="92820-134">通过继承隐藏元素进一步派生的类;隐藏的元素仍隐藏<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="92820-134">Shadowing element inherited by further derived classes; shadowed element still hidden<sup>3</sup></span></span>|<span data-ttu-id="92820-135">通过重写元素继承其他派生类;被替代的元素仍被重写</span><span class="sxs-lookup"><span data-stu-id="92820-135">Overriding element inherited by further derived classes; overridden element still overridden</span></span>|  
  
 <span data-ttu-id="92820-136"><sup>1</sup> *调用序列*包含的元素类型 (`Function`， `Sub`， `Operator`，或`Property`)、 名称、 参数列表和返回类型。</span><span class="sxs-lookup"><span data-stu-id="92820-136"><sup>1</sup> The *calling sequence* consists of the element type (`Function`, `Sub`, `Operator`, or `Property`), name, parameter list, and return type.</span></span> <span data-ttu-id="92820-137">无法重写属性，或在相反方向的过程。</span><span class="sxs-lookup"><span data-stu-id="92820-137">You cannot override a procedure with a property, or the other way around.</span></span> <span data-ttu-id="92820-138">不能重写一种类型的过程 (`Function`， `Sub`，或`Operator`) 与另一个类型。</span><span class="sxs-lookup"><span data-stu-id="92820-138">You cannot override one kind of procedure (`Function`, `Sub`, or `Operator`) with another kind.</span></span>  
  
 <span data-ttu-id="92820-139"><sup>2</sup>如果不指定`Shadows`或`Overrides`，编译器会发出警告消息，以帮助你确保想要使用哪种类型的重定义。</span><span class="sxs-lookup"><span data-stu-id="92820-139"><sup>2</sup> If you do not specify either `Shadows` or `Overrides`, the compiler issues a warning message to help you be sure which kind of redefinition you want to use.</span></span> <span data-ttu-id="92820-140">如果忽略该警告，则使用隐藏的机制。</span><span class="sxs-lookup"><span data-stu-id="92820-140">If you ignore the warning, the shadowing mechanism is used.</span></span>  
  
 <span data-ttu-id="92820-141"><sup>3</sup>隐藏元素不可进一步派生类中，如果没有继承隐藏。</span><span class="sxs-lookup"><span data-stu-id="92820-141"><sup>3</sup> If the shadowing element is inaccessible in a further derived class, shadowing is not inherited.</span></span> <span data-ttu-id="92820-142">例如，如果声明隐藏元素为`Private`，派生类中派生一个类继承而不是隐藏的元素的原始元素。</span><span class="sxs-lookup"><span data-stu-id="92820-142">For example, if you declare the shadowing element as `Private`, a class deriving from your derived class inherits the original element instead of the shadowing element.</span></span>  
  
## <a name="guidelines"></a><span data-ttu-id="92820-143">准则</span><span class="sxs-lookup"><span data-stu-id="92820-143">Guidelines</span></span>  
 <span data-ttu-id="92820-144">通常用在以下情况下重写：</span><span class="sxs-lookup"><span data-stu-id="92820-144">You normally use overriding in the following cases:</span></span>  
  
-   <span data-ttu-id="92820-145">可以定义多态派生的类。</span><span class="sxs-lookup"><span data-stu-id="92820-145">You are defining polymorphic derived classes.</span></span>  
  
-   <span data-ttu-id="92820-146">需要安全地让编译器强制执行完全相同的元素类型和调用的序列。</span><span class="sxs-lookup"><span data-stu-id="92820-146">You want the safety of having the compiler enforce the identical element type and calling sequence.</span></span>  
  
 <span data-ttu-id="92820-147">通常用在以下情况下隐藏：</span><span class="sxs-lookup"><span data-stu-id="92820-147">You normally use shadowing in the following cases:</span></span>  
  
-   <span data-ttu-id="92820-148">您希望您的基类可能会被修改，并定义使用您所遇到的相同名称的元素。</span><span class="sxs-lookup"><span data-stu-id="92820-148">You anticipate that your base class might be modified and define an element using the same name as yours.</span></span>  
  
-   <span data-ttu-id="92820-149">你希望可以随意更改的元素类型或调用序列。</span><span class="sxs-lookup"><span data-stu-id="92820-149">You want the freedom of changing the element type or calling sequence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92820-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="92820-150">See also</span></span>

- [<span data-ttu-id="92820-151">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="92820-151">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="92820-152">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="92820-152">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="92820-153">如何：隐藏与您的变量同名的变量</span><span class="sxs-lookup"><span data-stu-id="92820-153">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="92820-154">如何：隐藏继承的变量</span><span class="sxs-lookup"><span data-stu-id="92820-154">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="92820-155">如何：访问被派生类隐藏的变量</span><span class="sxs-lookup"><span data-stu-id="92820-155">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="92820-156">Shadows</span><span class="sxs-lookup"><span data-stu-id="92820-156">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="92820-157">Overrides</span><span class="sxs-lookup"><span data-stu-id="92820-157">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)

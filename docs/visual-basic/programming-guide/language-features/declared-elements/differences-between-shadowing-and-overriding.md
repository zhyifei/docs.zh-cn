---
title: "隐藏和重写之间的差异 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d67486d9c6af96d314abad7142ba86779d74f5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a><span data-ttu-id="f48a9-102">隐藏和重写之间的差异 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f48a9-102">Differences Between Shadowing and Overriding (Visual Basic)</span></span>
<span data-ttu-id="f48a9-103">在定义继承自基类的类时，你有时想要重新定义一个或多个派生类中的基类元素。</span><span class="sxs-lookup"><span data-stu-id="f48a9-103">When you define a class that inherits from a base class, you sometimes want to redefine one or more of the base class elements in the derived class.</span></span> <span data-ttu-id="f48a9-104">隐藏和重写均可用于此目的。</span><span class="sxs-lookup"><span data-stu-id="f48a9-104">Shadowing and overriding are both available for this purpose.</span></span>  
  
## <a name="comparison"></a><span data-ttu-id="f48a9-105">比较</span><span class="sxs-lookup"><span data-stu-id="f48a9-105">Comparison</span></span>  
 <span data-ttu-id="f48a9-106">隐藏和重写同时时将使用派生的类继承自基类，并同时重新定义与另一个声明的元素。</span><span class="sxs-lookup"><span data-stu-id="f48a9-106">Shadowing and overriding are both used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="f48a9-107">但是，这两者之间的重大差异。</span><span class="sxs-lookup"><span data-stu-id="f48a9-107">But there are significant differences between the two.</span></span>  
  
 <span data-ttu-id="f48a9-108">下表比较隐藏和重写。</span><span class="sxs-lookup"><span data-stu-id="f48a9-108">The following table compares shadowing with overriding.</span></span>  
  
||||  
|---|---|---|  
|<span data-ttu-id="f48a9-109">比较点</span><span class="sxs-lookup"><span data-stu-id="f48a9-109">Point of comparison</span></span>|<span data-ttu-id="f48a9-110">隐藏</span><span class="sxs-lookup"><span data-stu-id="f48a9-110">Shadowing</span></span>|<span data-ttu-id="f48a9-111">重写</span><span class="sxs-lookup"><span data-stu-id="f48a9-111">Overriding</span></span>|  
|<span data-ttu-id="f48a9-112">用途</span><span class="sxs-lookup"><span data-stu-id="f48a9-112">Purpose</span></span>|<span data-ttu-id="f48a9-113">防止后续的基类修改引入你具有已定义在派生类中的成员</span><span class="sxs-lookup"><span data-stu-id="f48a9-113">Protects against a subsequent base-class modification that introduces a member you have already defined in your derived class</span></span>|<span data-ttu-id="f48a9-114">通过定义的过程或属性具有相同调用的序列的不同实现来实现多态性<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f48a9-114">Achieves polymorphism by defining a different implementation of a procedure or property with the same calling sequence<sup>1</sup></span></span>|  
|<span data-ttu-id="f48a9-115">重新定义的元素</span><span class="sxs-lookup"><span data-stu-id="f48a9-115">Redefined element</span></span>|<span data-ttu-id="f48a9-116">任何声明的元素类型</span><span class="sxs-lookup"><span data-stu-id="f48a9-116">Any declared element type</span></span>|<span data-ttu-id="f48a9-117">只有过程 (`Function`， `Sub`，或`Operator`) 或属性</span><span class="sxs-lookup"><span data-stu-id="f48a9-117">Only a procedure (`Function`, `Sub`, or `Operator`) or property</span></span>|  
|<span data-ttu-id="f48a9-118">重新定义元素</span><span class="sxs-lookup"><span data-stu-id="f48a9-118">Redefining element</span></span>|<span data-ttu-id="f48a9-119">任何声明的元素类型</span><span class="sxs-lookup"><span data-stu-id="f48a9-119">Any declared element type</span></span>|<span data-ttu-id="f48a9-120">过程或属性与相同的调用序列<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f48a9-120">Only a procedure or property with the identical calling sequence<sup>1</sup></span></span>|  
|<span data-ttu-id="f48a9-121">重定义元素的访问级别</span><span class="sxs-lookup"><span data-stu-id="f48a9-121">Access level of redefining element</span></span>|<span data-ttu-id="f48a9-122">任何访问级别</span><span class="sxs-lookup"><span data-stu-id="f48a9-122">Any access level</span></span>|<span data-ttu-id="f48a9-123">不能更改重写元素的访问的级别</span><span class="sxs-lookup"><span data-stu-id="f48a9-123">Cannot change access level of overridden element</span></span>|  
|<span data-ttu-id="f48a9-124">提高可读性并对可写性重新定义元素</span><span class="sxs-lookup"><span data-stu-id="f48a9-124">Readability and writability of redefining element</span></span>|<span data-ttu-id="f48a9-125">任意组合</span><span class="sxs-lookup"><span data-stu-id="f48a9-125">Any combination</span></span>|<span data-ttu-id="f48a9-126">不能更改可读性或可写性的重写的属性</span><span class="sxs-lookup"><span data-stu-id="f48a9-126">Cannot change readability or writability of overridden property</span></span>|  
|<span data-ttu-id="f48a9-127">控制重定义</span><span class="sxs-lookup"><span data-stu-id="f48a9-127">Control over redefining</span></span>|<span data-ttu-id="f48a9-128">不能强制或禁止隐藏基类元素</span><span class="sxs-lookup"><span data-stu-id="f48a9-128">Base class element cannot enforce or prohibit shadowing</span></span>|<span data-ttu-id="f48a9-129">基类元素可指定`MustOverride`， `NotOverridable`，或`Overridable`</span><span class="sxs-lookup"><span data-stu-id="f48a9-129">Base class element can specify `MustOverride`, `NotOverridable`, or `Overridable`</span></span>|  
|<span data-ttu-id="f48a9-130">关键字的用法</span><span class="sxs-lookup"><span data-stu-id="f48a9-130">Keyword usage</span></span>|<span data-ttu-id="f48a9-131">`Shadows`在派生类; 建议`Shadows`假定如果既不`Shadows`也不`Overrides`指定<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f48a9-131">`Shadows` recommended in derived class; `Shadows` assumed if neither `Shadows` nor `Overrides` specified<sup>2</sup></span></span>|<span data-ttu-id="f48a9-132">`Overridable`或`MustOverride`所需基类; 中`Overrides`在派生类中所需</span><span class="sxs-lookup"><span data-stu-id="f48a9-132">`Overridable` or `MustOverride` required in base class; `Overrides` required in derived class</span></span>|  
|<span data-ttu-id="f48a9-133">重新元素定义由派生类中派生的类的继承</span><span class="sxs-lookup"><span data-stu-id="f48a9-133">Inheritance of redefining element by classes deriving from your derived class</span></span>|<span data-ttu-id="f48a9-134">通过继承隐藏元素进一步派生类;隐藏的元素仍隐藏<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f48a9-134">Shadowing element inherited by further derived classes; shadowed element still hidden<sup>3</sup></span></span>|<span data-ttu-id="f48a9-135">通过重写元素继承进一步派生类;重写的元素仍中重写</span><span class="sxs-lookup"><span data-stu-id="f48a9-135">Overriding element inherited by further derived classes; overridden element still overridden</span></span>|  
  
 <span data-ttu-id="f48a9-136"><sup>1</sup> *调用序列*包含元素类型 (`Function`， `Sub`， `Operator`，或`Property`)，名称、 参数列表和返回类型。</span><span class="sxs-lookup"><span data-stu-id="f48a9-136"><sup>1</sup> The *calling sequence* consists of the element type (`Function`, `Sub`, `Operator`, or `Property`), name, parameter list, and return type.</span></span> <span data-ttu-id="f48a9-137">不能重写属性，或另一种方法解决过程。</span><span class="sxs-lookup"><span data-stu-id="f48a9-137">You cannot override a procedure with a property, or the other way around.</span></span> <span data-ttu-id="f48a9-138">不能重写一种类型的过程 (`Function`， `Sub`，或`Operator`) 与另一个类型。</span><span class="sxs-lookup"><span data-stu-id="f48a9-138">You cannot override one kind of procedure (`Function`, `Sub`, or `Operator`) with another kind.</span></span>  
  
 <span data-ttu-id="f48a9-139"><sup>2</sup>如果不指定`Shadows`或`Overrides`，编译器会发出警告消息，以帮助您确定要使用哪种类型的重定义。</span><span class="sxs-lookup"><span data-stu-id="f48a9-139"><sup>2</sup> If you do not specify either `Shadows` or `Overrides`, the compiler issues a warning message to help you be sure which kind of redefinition you want to use.</span></span> <span data-ttu-id="f48a9-140">如果忽略该警告，则使用隐藏的机制。</span><span class="sxs-lookup"><span data-stu-id="f48a9-140">If you ignore the warning, the shadowing mechanism is used.</span></span>  
  
 <span data-ttu-id="f48a9-141"><sup>3</sup>隐藏元素不可进一步的派生类中，如果没有继承隐藏。</span><span class="sxs-lookup"><span data-stu-id="f48a9-141"><sup>3</sup> If the shadowing element is inaccessible in a further derived class, shadowing is not inherited.</span></span> <span data-ttu-id="f48a9-142">例如，如果声明隐藏元素为`Private`，从派生类派生一个类继承的原始元素而不是隐藏的元素。</span><span class="sxs-lookup"><span data-stu-id="f48a9-142">For example, if you declare the shadowing element as `Private`, a class deriving from your derived class inherits the original element instead of the shadowing element.</span></span>  
  
## <a name="guidelines"></a><span data-ttu-id="f48a9-143">准则</span><span class="sxs-lookup"><span data-stu-id="f48a9-143">Guidelines</span></span>  
 <span data-ttu-id="f48a9-144">你通常使用重写在以下情况：</span><span class="sxs-lookup"><span data-stu-id="f48a9-144">You normally use overriding in the following cases:</span></span>  
  
-   <span data-ttu-id="f48a9-145">你定义的多态的派生的类。</span><span class="sxs-lookup"><span data-stu-id="f48a9-145">You are defining polymorphic derived classes.</span></span>  
  
-   <span data-ttu-id="f48a9-146">你想让编译器强制执行相同的元素类型和调用的序列的安全性。</span><span class="sxs-lookup"><span data-stu-id="f48a9-146">You want the safety of having the compiler enforce the identical element type and calling sequence.</span></span>  
  
 <span data-ttu-id="f48a9-147">你通常使用隐藏在以下情况：</span><span class="sxs-lookup"><span data-stu-id="f48a9-147">You normally use shadowing in the following cases:</span></span>  
  
-   <span data-ttu-id="f48a9-148">您希望您的基类可能会被修改，并定义与您使用的相同名称的元素。</span><span class="sxs-lookup"><span data-stu-id="f48a9-148">You anticipate that your base class might be modified and define an element using the same name as yours.</span></span>  
  
-   <span data-ttu-id="f48a9-149">你希望可以随意更改的元素类型或调用序列。</span><span class="sxs-lookup"><span data-stu-id="f48a9-149">You want the freedom of changing the element type or calling sequence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f48a9-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f48a9-150">See Also</span></span>  
 [<span data-ttu-id="f48a9-151">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="f48a9-151">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="f48a9-152">在 Visual Basic 中隐藏</span><span class="sxs-lookup"><span data-stu-id="f48a9-152">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="f48a9-153">如何：隐藏与你的变量同名的变量</span><span class="sxs-lookup"><span data-stu-id="f48a9-153">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [<span data-ttu-id="f48a9-154">如何：隐藏继承的变量</span><span class="sxs-lookup"><span data-stu-id="f48a9-154">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [<span data-ttu-id="f48a9-155">如何：访问被派生类隐藏的变量</span><span class="sxs-lookup"><span data-stu-id="f48a9-155">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [<span data-ttu-id="f48a9-156">Shadows</span><span class="sxs-lookup"><span data-stu-id="f48a9-156">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="f48a9-157">Overrides</span><span class="sxs-lookup"><span data-stu-id="f48a9-157">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)

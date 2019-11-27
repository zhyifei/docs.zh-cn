---
title: 隐藏和重写之间的差异
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: 8d1ebdcd0a23dff69a7acca22268c03e30ec06d9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345419"
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a><span data-ttu-id="319ae-102">隐藏和重写之间的差异 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="319ae-102">Differences Between Shadowing and Overriding (Visual Basic)</span></span>
<span data-ttu-id="319ae-103">在定义继承自基类的类时，有时需要重新定义派生类中的一个或多个基类元素。</span><span class="sxs-lookup"><span data-stu-id="319ae-103">When you define a class that inherits from a base class, you sometimes want to redefine one or more of the base class elements in the derived class.</span></span> <span data-ttu-id="319ae-104">隐藏和重写都可用于此目的。</span><span class="sxs-lookup"><span data-stu-id="319ae-104">Shadowing and overriding are both available for this purpose.</span></span>  
  
## <a name="comparison"></a><span data-ttu-id="319ae-105">比较</span><span class="sxs-lookup"><span data-stu-id="319ae-105">Comparison</span></span>  
 <span data-ttu-id="319ae-106">当派生类从基类继承时使用隐藏和重写，并且这两种方法都将一个已声明的元素重定义为另一个。</span><span class="sxs-lookup"><span data-stu-id="319ae-106">Shadowing and overriding are both used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="319ae-107">但两者之间存在重大差异。</span><span class="sxs-lookup"><span data-stu-id="319ae-107">But there are significant differences between the two.</span></span>  
  
 <span data-ttu-id="319ae-108">下表将隐藏与重写进行比较。</span><span class="sxs-lookup"><span data-stu-id="319ae-108">The following table compares shadowing with overriding.</span></span>  
  
||||  
|---|---|---|  
|<span data-ttu-id="319ae-109">比较点</span><span class="sxs-lookup"><span data-stu-id="319ae-109">Point of comparison</span></span>|<span data-ttu-id="319ae-110">阴影操作</span><span class="sxs-lookup"><span data-stu-id="319ae-110">Shadowing</span></span>|<span data-ttu-id="319ae-111">取代</span><span class="sxs-lookup"><span data-stu-id="319ae-111">Overriding</span></span>|  
|<span data-ttu-id="319ae-112">目的</span><span class="sxs-lookup"><span data-stu-id="319ae-112">Purpose</span></span>|<span data-ttu-id="319ae-113">针对引入已在派生类中定义的成员的后续基类修改进行保护</span><span class="sxs-lookup"><span data-stu-id="319ae-113">Protects against a subsequent base-class modification that introduces a member you have already defined in your derived class</span></span>|<span data-ttu-id="319ae-114">通过定义具有相同调用序列的过程或属性的不同实现来实现多态性<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="319ae-114">Achieves polymorphism by defining a different implementation of a procedure or property with the same calling sequence<sup>1</sup></span></span>|  
|<span data-ttu-id="319ae-115">重新定义的元素</span><span class="sxs-lookup"><span data-stu-id="319ae-115">Redefined element</span></span>|<span data-ttu-id="319ae-116">任何声明的元素类型</span><span class="sxs-lookup"><span data-stu-id="319ae-116">Any declared element type</span></span>|<span data-ttu-id="319ae-117">仅过程（`Function`、`Sub`或 `Operator`）或属性</span><span class="sxs-lookup"><span data-stu-id="319ae-117">Only a procedure (`Function`, `Sub`, or `Operator`) or property</span></span>|  
|<span data-ttu-id="319ae-118">重定义元素</span><span class="sxs-lookup"><span data-stu-id="319ae-118">Redefining element</span></span>|<span data-ttu-id="319ae-119">任何声明的元素类型</span><span class="sxs-lookup"><span data-stu-id="319ae-119">Any declared element type</span></span>|<span data-ttu-id="319ae-120">仅具有相同调用序列的过程或属性<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="319ae-120">Only a procedure or property with the identical calling sequence<sup>1</sup></span></span>|  
|<span data-ttu-id="319ae-121">重定义元素的访问级别</span><span class="sxs-lookup"><span data-stu-id="319ae-121">Access level of redefining element</span></span>|<span data-ttu-id="319ae-122">任何访问级别</span><span class="sxs-lookup"><span data-stu-id="319ae-122">Any access level</span></span>|<span data-ttu-id="319ae-123">无法更改重写元素的访问级别</span><span class="sxs-lookup"><span data-stu-id="319ae-123">Cannot change access level of overridden element</span></span>|  
|<span data-ttu-id="319ae-124">重定义元素的可读性和可写性</span><span class="sxs-lookup"><span data-stu-id="319ae-124">Readability and writability of redefining element</span></span>|<span data-ttu-id="319ae-125">任何组合</span><span class="sxs-lookup"><span data-stu-id="319ae-125">Any combination</span></span>|<span data-ttu-id="319ae-126">无法更改重写属性的可读性或可写性</span><span class="sxs-lookup"><span data-stu-id="319ae-126">Cannot change readability or writability of overridden property</span></span>|  
|<span data-ttu-id="319ae-127">控制重定义</span><span class="sxs-lookup"><span data-stu-id="319ae-127">Control over redefining</span></span>|<span data-ttu-id="319ae-128">基类元素无法强制或禁止隐藏</span><span class="sxs-lookup"><span data-stu-id="319ae-128">Base class element cannot enforce or prohibit shadowing</span></span>|<span data-ttu-id="319ae-129">基类元素可以指定 `MustOverride`、`NotOverridable`或 `Overridable`</span><span class="sxs-lookup"><span data-stu-id="319ae-129">Base class element can specify `MustOverride`, `NotOverridable`, or `Overridable`</span></span>|  
|<span data-ttu-id="319ae-130">关键字用法</span><span class="sxs-lookup"><span data-stu-id="319ae-130">Keyword usage</span></span>|<span data-ttu-id="319ae-131">在派生类中建议 `Shadows`;如果 `Shadows` 和 `Overrides` 均<sup>未指定，</sup>则假定 `Shadows`</span><span class="sxs-lookup"><span data-stu-id="319ae-131">`Shadows` recommended in derived class; `Shadows` assumed if neither `Shadows` nor `Overrides` specified<sup>2</sup></span></span>|<span data-ttu-id="319ae-132">基类中需要 `Overridable` 或 `MustOverride`;派生类中需要 `Overrides`</span><span class="sxs-lookup"><span data-stu-id="319ae-132">`Overridable` or `MustOverride` required in base class; `Overrides` required in derived class</span></span>|  
|<span data-ttu-id="319ae-133">从派生类派生的类的重定义元素的继承</span><span class="sxs-lookup"><span data-stu-id="319ae-133">Inheritance of redefining element by classes deriving from your derived class</span></span>|<span data-ttu-id="319ae-134">由进一步的派生类继承的隐藏元素;隐藏的元素仍隐藏<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="319ae-134">Shadowing element inherited by further derived classes; shadowed element still hidden<sup>3</sup></span></span>|<span data-ttu-id="319ae-135">重写由进一步派生的类继承的元素;重写的元素仍将被重写</span><span class="sxs-lookup"><span data-stu-id="319ae-135">Overriding element inherited by further derived classes; overridden element still overridden</span></span>|  
  
 <span data-ttu-id="319ae-136"><sup>1</sup> *调用序列*包含元素类型（`Function`、`Sub`、`Operator`或 `Property`）、名称、参数列表和返回类型。</span><span class="sxs-lookup"><span data-stu-id="319ae-136"><sup>1</sup> The *calling sequence* consists of the element type (`Function`, `Sub`, `Operator`, or `Property`), name, parameter list, and return type.</span></span> <span data-ttu-id="319ae-137">不能使用属性或其他方法来重写过程。</span><span class="sxs-lookup"><span data-stu-id="319ae-137">You cannot override a procedure with a property, or the other way around.</span></span> <span data-ttu-id="319ae-138">不能重写另一种类型的过程（`Function`、`Sub`或 `Operator`）。</span><span class="sxs-lookup"><span data-stu-id="319ae-138">You cannot override one kind of procedure (`Function`, `Sub`, or `Operator`) with another kind.</span></span>  
  
 <span data-ttu-id="319ae-139"><sup>2</sup>如果未指定 `Shadows` 或 `Overrides`，则编译器会发出警告消息，帮助您确定要使用的重新定义类型。</span><span class="sxs-lookup"><span data-stu-id="319ae-139"><sup>2</sup> If you do not specify either `Shadows` or `Overrides`, the compiler issues a warning message to help you be sure which kind of redefinition you want to use.</span></span> <span data-ttu-id="319ae-140">如果忽略该警告，则使用隐藏机制。</span><span class="sxs-lookup"><span data-stu-id="319ae-140">If you ignore the warning, the shadowing mechanism is used.</span></span>  
  
 <span data-ttu-id="319ae-141"><sup>3</sup>如果无法在进一步的派生类中访问隐藏元素，则不会继承隐藏。</span><span class="sxs-lookup"><span data-stu-id="319ae-141"><sup>3</sup> If the shadowing element is inaccessible in a further derived class, shadowing is not inherited.</span></span> <span data-ttu-id="319ae-142">例如，如果将隐藏元素声明为 `Private`，派生自派生类的类将继承原始元素，而不是隐藏元素。</span><span class="sxs-lookup"><span data-stu-id="319ae-142">For example, if you declare the shadowing element as `Private`, a class deriving from your derived class inherits the original element instead of the shadowing element.</span></span>  
  
## <a name="guidelines"></a><span data-ttu-id="319ae-143">指南</span><span class="sxs-lookup"><span data-stu-id="319ae-143">Guidelines</span></span>  
 <span data-ttu-id="319ae-144">在以下情况下，通常使用重写：</span><span class="sxs-lookup"><span data-stu-id="319ae-144">You normally use overriding in the following cases:</span></span>  
  
- <span data-ttu-id="319ae-145">你要定义多态派生类。</span><span class="sxs-lookup"><span data-stu-id="319ae-145">You are defining polymorphic derived classes.</span></span>  
  
- <span data-ttu-id="319ae-146">您希望安全地让编译器强制执行相同的元素类型和调用序列。</span><span class="sxs-lookup"><span data-stu-id="319ae-146">You want the safety of having the compiler enforce the identical element type and calling sequence.</span></span>  
  
 <span data-ttu-id="319ae-147">通常会在以下情况下使用隐藏：</span><span class="sxs-lookup"><span data-stu-id="319ae-147">You normally use shadowing in the following cases:</span></span>  
  
- <span data-ttu-id="319ae-148">你预计可能会修改基类，并使用与你的名称相同的名称来定义元素。</span><span class="sxs-lookup"><span data-stu-id="319ae-148">You anticipate that your base class might be modified and define an element using the same name as yours.</span></span>  
  
- <span data-ttu-id="319ae-149">您希望自由更改元素类型或调用序列。</span><span class="sxs-lookup"><span data-stu-id="319ae-149">You want the freedom of changing the element type or calling sequence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="319ae-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="319ae-150">See also</span></span>

- [<span data-ttu-id="319ae-151">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="319ae-151">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="319ae-152">Visual Basic 中的阴影</span><span class="sxs-lookup"><span data-stu-id="319ae-152">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="319ae-153">如何：隐藏与你的变量同名的变量</span><span class="sxs-lookup"><span data-stu-id="319ae-153">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="319ae-154">如何：隐藏继承的变量</span><span class="sxs-lookup"><span data-stu-id="319ae-154">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="319ae-155">如何：访问被派生类隐藏的变量</span><span class="sxs-lookup"><span data-stu-id="319ae-155">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="319ae-156">Shadows</span><span class="sxs-lookup"><span data-stu-id="319ae-156">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="319ae-157">Overrides</span><span class="sxs-lookup"><span data-stu-id="319ae-157">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)

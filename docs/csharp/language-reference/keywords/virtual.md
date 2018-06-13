---
title: virtual（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
ms.openlocfilehash: 5a188e9a7cbb7a1c497d577039c2b2578eaa7526
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172641"
---
# <a name="virtual-c-reference"></a><span data-ttu-id="44f07-102">virtual（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="44f07-102">virtual (C# Reference)</span></span>
<span data-ttu-id="44f07-103">`virtual` 关键字用于修改方法、属性、索引器或事件声明，并使它们可以在派生类中被重写。</span><span class="sxs-lookup"><span data-stu-id="44f07-103">The `virtual` keyword is used to modify a method, property, indexer, or event declaration and allow for it to be overridden in a derived class.</span></span> <span data-ttu-id="44f07-104">例如，此方法可被任何继承它的类替代：</span><span class="sxs-lookup"><span data-stu-id="44f07-104">For example, this method can be overridden by any class that inherits it:</span></span>  
  
```csharp  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 <span data-ttu-id="44f07-105">虚拟成员的实现可由派生类中的[替代成员](../../../csharp/language-reference/keywords/override.md)更改。</span><span class="sxs-lookup"><span data-stu-id="44f07-105">The implementation of a virtual member can be changed by an [overriding member](../../../csharp/language-reference/keywords/override.md) in a derived class.</span></span> <span data-ttu-id="44f07-106">有关如何使用 `virtual` 关键字的详细信息，请参阅[使用 Override 和 New 关键字进行版本控制](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)和[了解何时使用 Override 和 New 关键字](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)。</span><span class="sxs-lookup"><span data-stu-id="44f07-106">For more information about how to use the `virtual` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing When to Use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44f07-107">备注</span><span class="sxs-lookup"><span data-stu-id="44f07-107">Remarks</span></span>  
 <span data-ttu-id="44f07-108">调用虚拟方法时，将为替代的成员检查该对象的运行时类型。</span><span class="sxs-lookup"><span data-stu-id="44f07-108">When a virtual method is invoked, the run-time type of the object is checked for an overriding member.</span></span> <span data-ttu-id="44f07-109">将调用大部分派生类中的该替代成员，如果没有派生类替代该成员，则它可能是原始成员。</span><span class="sxs-lookup"><span data-stu-id="44f07-109">The overriding member in the most derived class is called, which might be the original member, if no derived class has overridden the member.</span></span>  
  
 <span data-ttu-id="44f07-110">默认情况下，方法是非虚拟的。</span><span class="sxs-lookup"><span data-stu-id="44f07-110">By default, methods are non-virtual.</span></span> <span data-ttu-id="44f07-111">不能替代非虚方法。</span><span class="sxs-lookup"><span data-stu-id="44f07-111">You cannot override a non-virtual method.</span></span>  
  
 <span data-ttu-id="44f07-112">`virtual` 修饰符不能与 `static`、`abstract``private` 或 `override` 修饰符一起使用。</span><span class="sxs-lookup"><span data-stu-id="44f07-112">You cannot use the `virtual` modifier with the `static`, `abstract`, `private`, or `override` modifiers.</span></span> <span data-ttu-id="44f07-113">以下示例显示了虚拟属性：</span><span class="sxs-lookup"><span data-stu-id="44f07-113">The following example shows a virtual property:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]  
  
 <span data-ttu-id="44f07-114">除声明和调用语法不同外，虚拟属性的行为与抽象方法相似。</span><span class="sxs-lookup"><span data-stu-id="44f07-114">Virtual properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
-   <span data-ttu-id="44f07-115">在静态属性上使用 `virtual` 修饰符是错误的。</span><span class="sxs-lookup"><span data-stu-id="44f07-115">It is an error to use the `virtual` modifier on a static property.</span></span>  
  
-   <span data-ttu-id="44f07-116">通过包括使用 `override` 修饰符的属性声明，可在派生类中替代虚拟继承属性。</span><span class="sxs-lookup"><span data-stu-id="44f07-116">A virtual inherited property can be overridden in a derived class by including a property declaration that uses the `override` modifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44f07-117">示例</span><span class="sxs-lookup"><span data-stu-id="44f07-117">Example</span></span>  
 <span data-ttu-id="44f07-118">在该示例中，`Shape` 类包含 `x`、`y` 两个坐标和 `Area()` 虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="44f07-118">In this example, the `Shape` class contains the two coordinates `x`, `y`, and the `Area()` virtual method.</span></span> <span data-ttu-id="44f07-119">不同的形状类（如 `Circle`、`Cylinder` 和 `Sphere`）继承 `Shape` 类，并为每个图形计算表面积。</span><span class="sxs-lookup"><span data-stu-id="44f07-119">Different shape classes such as `Circle`, `Cylinder`, and `Sphere` inherit the `Shape` class, and the surface area is calculated for each figure.</span></span> <span data-ttu-id="44f07-120">每个派生类都有各自的 `Area()` 替代实现。</span><span class="sxs-lookup"><span data-stu-id="44f07-120">Each derived class has it own override implementation of `Area()`.</span></span>  
  
 <span data-ttu-id="44f07-121">请注意，继承的类 `Circle``Sphere` 和 `Cylinder` 均使用初始化基类的构造函数，如下面的声明中所示。</span><span class="sxs-lookup"><span data-stu-id="44f07-121">Notice that the inherited classes `Circle`, `Sphere`, and `Cylinder` all use constructors that initialize the base class, as shown in the following declaration.</span></span>  
  
```csharp  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 <span data-ttu-id="44f07-122">根据与方法关联的对象，下面的程序通过调用 `Area()` 方法的相应实现来计算并显示每个对象的相应区域。</span><span class="sxs-lookup"><span data-stu-id="44f07-122">The following program calculates and displays the appropriate area for each figure by invoking the appropriate implementation of the `Area()` method, according to the object that is associated with the method.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="44f07-123">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="44f07-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="44f07-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="44f07-124">See Also</span></span>  
 [<span data-ttu-id="44f07-125">C# 参考</span><span class="sxs-lookup"><span data-stu-id="44f07-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="44f07-126">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="44f07-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="44f07-127">修饰符</span><span class="sxs-lookup"><span data-stu-id="44f07-127">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="44f07-128">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="44f07-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="44f07-129">多态性</span><span class="sxs-lookup"><span data-stu-id="44f07-129">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
 [<span data-ttu-id="44f07-130">abstract</span><span class="sxs-lookup"><span data-stu-id="44f07-130">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
 [<span data-ttu-id="44f07-131">override</span><span class="sxs-lookup"><span data-stu-id="44f07-131">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
 [<span data-ttu-id="44f07-132">new</span><span class="sxs-lookup"><span data-stu-id="44f07-132">new</span></span>](../../../csharp/language-reference/keywords/new.md)

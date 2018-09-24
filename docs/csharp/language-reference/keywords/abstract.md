---
title: abstract（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- abstract
- abstract_CSharpKeyword
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
ms.openlocfilehash: d0a51afe61e75b750ed8bf336ca4636cb58dfbba
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "45742240"
---
# <a name="abstract-c-reference"></a><span data-ttu-id="45adc-102">abstract（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="45adc-102">abstract (C# Reference)</span></span>
<span data-ttu-id="45adc-103">`abstract` 修饰符指示被修改内容的实现已丢失或不完整。</span><span class="sxs-lookup"><span data-stu-id="45adc-103">The `abstract` modifier indicates that the thing being modified has a missing or incomplete implementation.</span></span> <span data-ttu-id="45adc-104">abstract 修饰符可用于类、方法、属性、索引和事件。</span><span class="sxs-lookup"><span data-stu-id="45adc-104">The abstract modifier can be used with classes, methods, properties, indexers, and events.</span></span> <span data-ttu-id="45adc-105">在类声明中使用 `abstract` 修饰符以指示某个类仅旨在作为其他类的基类。</span><span class="sxs-lookup"><span data-stu-id="45adc-105">Use the `abstract` modifier in a class declaration to indicate that a class is intended only to be a base class of other classes.</span></span> <span data-ttu-id="45adc-106">标记为 abstract 的成员，或包含在抽象类中的成员，都必须由派生自抽象类的类来实现。</span><span class="sxs-lookup"><span data-stu-id="45adc-106">Members marked as abstract, or included in an abstract class, must be implemented by classes that derive from the abstract class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45adc-107">示例</span><span class="sxs-lookup"><span data-stu-id="45adc-107">Example</span></span>  
 <span data-ttu-id="45adc-108">在此示例中，类 `Square` 必须提供 `Area` 的实现，因为它派生自 `ShapesClass`：</span><span class="sxs-lookup"><span data-stu-id="45adc-108">In this example, the class `Square` must provide an implementation of `Area` because it derives from `ShapesClass`:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]
  
 <span data-ttu-id="45adc-109">抽象类具有以下功能：</span><span class="sxs-lookup"><span data-stu-id="45adc-109">Abstract classes have the following features:</span></span>  
  
-   <span data-ttu-id="45adc-110">抽象类不能实例化。</span><span class="sxs-lookup"><span data-stu-id="45adc-110">An abstract class cannot be instantiated.</span></span>  
  
-   <span data-ttu-id="45adc-111">抽象类可能包含抽象方法和访问器。</span><span class="sxs-lookup"><span data-stu-id="45adc-111">An abstract class may contain abstract methods and accessors.</span></span>  
  
-   <span data-ttu-id="45adc-112">无法使用 [sealed](../../../csharp/language-reference/keywords/sealed.md) 修饰符来修改抽象类，因为两个修饰符具有相反的含义。</span><span class="sxs-lookup"><span data-stu-id="45adc-112">It is not possible to modify an abstract class with the [sealed](../../../csharp/language-reference/keywords/sealed.md) modifier because the two modifers have opposite meanings.</span></span> <span data-ttu-id="45adc-113">`sealed` 修饰符阻止类被继承，而 `abstract` 修饰符要求类被继承。</span><span class="sxs-lookup"><span data-stu-id="45adc-113">The `sealed` modifier prevents a class from being inherited and the `abstract` modifier requires a class to be inherited.</span></span>  
  
-   <span data-ttu-id="45adc-114">派生自抽象类的非抽象类，必须包含全部已继承的抽象方法和访问器的实际实现。</span><span class="sxs-lookup"><span data-stu-id="45adc-114">A non-abstract class derived from an abstract class must include actual implementations of all inherited abstract methods and accessors.</span></span>  
  
 <span data-ttu-id="45adc-115">在方法或属性声明中使用 `abstract` 修饰符，以指示该方法或属性不包含实现。</span><span class="sxs-lookup"><span data-stu-id="45adc-115">Use the `abstract` modifier in a method or property declaration to indicate that the method or property does not contain implementation.</span></span>  
  
 <span data-ttu-id="45adc-116">抽象方法具有以下功能：</span><span class="sxs-lookup"><span data-stu-id="45adc-116">Abstract methods have the following features:</span></span>  
  
-   <span data-ttu-id="45adc-117">抽象方法是隐式的虚拟方法。</span><span class="sxs-lookup"><span data-stu-id="45adc-117">An abstract method is implicitly a virtual method.</span></span>  
  
-   <span data-ttu-id="45adc-118">只有抽象类中才允许抽象方法声明。</span><span class="sxs-lookup"><span data-stu-id="45adc-118">Abstract method declarations are only permitted in abstract classes.</span></span>  
  
-   <span data-ttu-id="45adc-119">由于抽象方法声明不提供实际的实现，因此没有方法主体；方法声明仅以分号结尾，且签名后没有大括号 ({ })。</span><span class="sxs-lookup"><span data-stu-id="45adc-119">Because an abstract method declaration provides no actual implementation, there is no method body; the method declaration simply ends with a semicolon and there are no curly braces ({ }) following the signature.</span></span> <span data-ttu-id="45adc-120">例如:</span><span class="sxs-lookup"><span data-stu-id="45adc-120">For example:</span></span>  
  
    ```csharp  
    public abstract void MyMethod();  
    ```  
  
     <span data-ttu-id="45adc-121">实现由方法 [override](../../../csharp/language-reference/keywords/override.md) 提供，它是非抽象类的成员。</span><span class="sxs-lookup"><span data-stu-id="45adc-121">The implementation is provided by a method [override](../../../csharp/language-reference/keywords/override.md), which is a member of a non-abstract class.</span></span>  
  
-   <span data-ttu-id="45adc-122">在抽象方法声明中使用 [static](../../../csharp/language-reference/keywords/static.md) 或 [virtual](../../../csharp/language-reference/keywords/virtual.md) 修饰符是错误的。</span><span class="sxs-lookup"><span data-stu-id="45adc-122">It is an error to use the [static](../../../csharp/language-reference/keywords/static.md) or [virtual](../../../csharp/language-reference/keywords/virtual.md) modifiers in an abstract method declaration.</span></span>  
  
 <span data-ttu-id="45adc-123">除了声明和调用语法方面不同外，抽象属性的行为与抽象方法相似。</span><span class="sxs-lookup"><span data-stu-id="45adc-123">Abstract properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
-   <span data-ttu-id="45adc-124">在静态属性上使用 `abstract` 修饰符是错误的。</span><span class="sxs-lookup"><span data-stu-id="45adc-124">It is an error to use the `abstract` modifier on a static property.</span></span>  
  
-   <span data-ttu-id="45adc-125">通过包含使用 [override](../../../csharp/language-reference/keywords/override.md) 修饰符的属性声明，可在派生类中重写抽象继承属性。</span><span class="sxs-lookup"><span data-stu-id="45adc-125">An abstract inherited property can be overridden in a derived class by including a property declaration that uses the [override](../../../csharp/language-reference/keywords/override.md) modifier.</span></span>  
  
 <span data-ttu-id="45adc-126">有关抽象类的详细信息，请参阅[抽象类、密封类及类成员](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)。</span><span class="sxs-lookup"><span data-stu-id="45adc-126">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="45adc-127">抽象类必须为所有接口成员提供实现。</span><span class="sxs-lookup"><span data-stu-id="45adc-127">An abstract class must provide implementation for all interface members.</span></span>  
  
 <span data-ttu-id="45adc-128">实现接口的抽象类有可能将接口方法映射到抽象方法上。</span><span class="sxs-lookup"><span data-stu-id="45adc-128">An abstract class that implements an interface might map the interface methods onto abstract methods.</span></span> <span data-ttu-id="45adc-129">例如:</span><span class="sxs-lookup"><span data-stu-id="45adc-129">For example:</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#2)]
  
## <a name="example"></a><span data-ttu-id="45adc-130">示例</span><span class="sxs-lookup"><span data-stu-id="45adc-130">Example</span></span>  
 <span data-ttu-id="45adc-131">在此示例中，类 `DerivedClass` 派生自抽象类 `BaseClass`。</span><span class="sxs-lookup"><span data-stu-id="45adc-131">In this example, the class `DerivedClass` is derived from an abstract class `BaseClass`.</span></span> <span data-ttu-id="45adc-132">抽象类包含抽象方法 `AbstractMethod`，以及两个抽象属性 `X` 和 `Y`。</span><span class="sxs-lookup"><span data-stu-id="45adc-132">The abstract class contains an abstract method, `AbstractMethod`, and two abstract properties, `X` and `Y`.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#3)]
  
 <span data-ttu-id="45adc-133">在前面的示例中，如果你尝试通过使用如下语句来实例化抽象类：</span><span class="sxs-lookup"><span data-stu-id="45adc-133">In the preceding example, if you attempt to instantiate the abstract class by using a statement like this:</span></span>  
  
```csharp
BaseClass bc = new BaseClass();   // Error  
```  
  
<span data-ttu-id="45adc-134">将遇到一个错误，告知编译器无法创建抽象类“BaseClass”的实例。</span><span class="sxs-lookup"><span data-stu-id="45adc-134">You will get an error saying that the compiler cannot create an instance of the abstract class 'BaseClass'.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="45adc-135">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="45adc-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="45adc-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="45adc-136">See Also</span></span>  

- [<span data-ttu-id="45adc-137">C# 参考</span><span class="sxs-lookup"><span data-stu-id="45adc-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="45adc-138">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="45adc-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="45adc-139">修饰符</span><span class="sxs-lookup"><span data-stu-id="45adc-139">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
- [<span data-ttu-id="45adc-140">virtual</span><span class="sxs-lookup"><span data-stu-id="45adc-140">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)  
- [<span data-ttu-id="45adc-141">override</span><span class="sxs-lookup"><span data-stu-id="45adc-141">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
- [<span data-ttu-id="45adc-142">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="45adc-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

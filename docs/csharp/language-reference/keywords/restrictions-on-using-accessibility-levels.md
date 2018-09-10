---
title: 可访问性级别的使用限制（C# 参考）
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: 2bcf2b12d1aa1488e6d3e46f5b37ac9535b138dd
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43389346"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a><span data-ttu-id="648cc-102">可访问性级别的使用限制（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="648cc-102">Restrictions on using accessibility levels (C# Reference)</span></span>

<span data-ttu-id="648cc-103">在声明中指定类型时，检查类型的可访问性级别是否依赖于成员或其他类型的可访问性级别。</span><span class="sxs-lookup"><span data-stu-id="648cc-103">When you specify a type in a declaration, check whether the accessibility level of the type is dependent on the accessibility level of a member or of another type.</span></span> <span data-ttu-id="648cc-104">例如，直接基类必须至少具有与派生类相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="648cc-104">For example, the direct base class must be at least as accessible as the derived class.</span></span> <span data-ttu-id="648cc-105">以下声明会导致编译器错误，因为基类 `BaseClass` 的可访问性低于 `MyClass`：</span><span class="sxs-lookup"><span data-stu-id="648cc-105">The following declarations cause a compiler error because the base class `BaseClass` is less accessible than `MyClass`:</span></span>

```csharp
class BaseClass {...}
public class MyClass: BaseClass {...} // Error
```

<span data-ttu-id="648cc-106">下表汇总了对已声明可访问性级别的限制。</span><span class="sxs-lookup"><span data-stu-id="648cc-106">The following table summarizes the restrictions on declared accessibility levels.</span></span>

|<span data-ttu-id="648cc-107">上下文</span><span class="sxs-lookup"><span data-stu-id="648cc-107">Context</span></span>|<span data-ttu-id="648cc-108">备注</span><span class="sxs-lookup"><span data-stu-id="648cc-108">Remarks</span></span>|
|-------------|-------------|
|[<span data-ttu-id="648cc-109">类</span><span class="sxs-lookup"><span data-stu-id="648cc-109">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)|<span data-ttu-id="648cc-110">类类型的直接基类必须至少具有与类类型本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="648cc-110">The direct base class of a class type must be at least as accessible as the class type itself.</span></span>|
|[<span data-ttu-id="648cc-111">接口</span><span class="sxs-lookup"><span data-stu-id="648cc-111">Interfaces</span></span>](../../programming-guide/interfaces/index.md)|<span data-ttu-id="648cc-112">接口类型的显式基接口必须至少具有与接口类型本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="648cc-112">The explicit base interfaces of an interface type must be at least as accessible as the interface type itself.</span></span>|
|[<span data-ttu-id="648cc-113">委托</span><span class="sxs-lookup"><span data-stu-id="648cc-113">Delegates</span></span>](../../programming-guide/delegates/index.md)|<span data-ttu-id="648cc-114">委托类型的返回类型和参数类型必须至少具有与委托类型本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="648cc-114">The return type and parameter types of a delegate type must be at least as accessible as the delegate type itself.</span></span>|
|[<span data-ttu-id="648cc-115">常量</span><span class="sxs-lookup"><span data-stu-id="648cc-115">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="648cc-116">常量的类型必须至少具有与常量本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="648cc-116">The type of a constant must be at least as accessible as the constant itself.</span></span>|
|[<span data-ttu-id="648cc-117">字段</span><span class="sxs-lookup"><span data-stu-id="648cc-117">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="648cc-118">字段的类型必须至少具有与字段本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="648cc-118">The type of a field must be at least as accessible as the field itself.</span></span>|
|[<span data-ttu-id="648cc-119">方法</span><span class="sxs-lookup"><span data-stu-id="648cc-119">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="648cc-120">方法的返回类型和参数类型必须至少具有与方法本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="648cc-120">The return type and parameter types of a method must be at least as accessible as the method itself.</span></span>|
|[<span data-ttu-id="648cc-121">属性</span><span class="sxs-lookup"><span data-stu-id="648cc-121">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="648cc-122">属性的类型必须至少具有与属性本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="648cc-122">The type of a property must be at least as accessible as the property itself.</span></span>|
|[<span data-ttu-id="648cc-123">事件</span><span class="sxs-lookup"><span data-stu-id="648cc-123">Events</span></span>](../../programming-guide/events/index.md)|<span data-ttu-id="648cc-124">事件的类型必须至少具有与事件本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="648cc-124">The type of an event must be at least as accessible as the event itself.</span></span>|
|[<span data-ttu-id="648cc-125">索引器</span><span class="sxs-lookup"><span data-stu-id="648cc-125">Indexers</span></span>](../../programming-guide/indexers/index.md)|<span data-ttu-id="648cc-126">索引器的类型和参数类型必须至少具有与索引器本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="648cc-126">The type and parameter types of an indexer must be at least as accessible as the indexer itself.</span></span>|
|[<span data-ttu-id="648cc-127">运算符</span><span class="sxs-lookup"><span data-stu-id="648cc-127">Operators</span></span>](../../programming-guide/statements-expressions-operators/operators.md)|<span data-ttu-id="648cc-128">运算符的类型和参数类型必须至少具有与运算符本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="648cc-128">The return type and parameter types of an operator must be at least as accessible as the operator itself.</span></span>|
|[<span data-ttu-id="648cc-129">构造函数</span><span class="sxs-lookup"><span data-stu-id="648cc-129">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="648cc-130">构造函数的参数类型必须至少具有与构造函数本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="648cc-130">The parameter types of a constructor must be at least as accessible as the constructor itself.</span></span>|

## <a name="example"></a><span data-ttu-id="648cc-131">示例</span><span class="sxs-lookup"><span data-stu-id="648cc-131">Example</span></span>

<span data-ttu-id="648cc-132">下面的示例包含不同类型的错误声明。</span><span class="sxs-lookup"><span data-stu-id="648cc-132">The following example contains erroneous declarations of different types.</span></span> <span data-ttu-id="648cc-133">每个声明后的注释指示预期编译器错误。</span><span class="sxs-lookup"><span data-stu-id="648cc-133">The comment following each declaration indicates the expected compiler error.</span></span>

```csharp
// Restrictions on Using Accessibility Levels
// CS0052 expected as well as CS0053, CS0056, and CS0057
// To make the program work, change access level of both class B
// and MyPrivateMethod() to public.

using System;

// A delegate:
delegate int MyDelegate();

class B
{
    // A private method:
    static int MyPrivateMethod()
    {
        return 0;
    }
}

public class A
{
    // Error: The type B is less accessible than the field A.myField.
    public B myField = new B();

    // Error: The type B is less accessible
    // than the constant A.myConst.
    public readonly B myConst = new B();

    public B MyMethod()
    {
        // Error: The type B is less accessible 
        // than the method A.MyMethod.
        return new B();
    }

    // Error: The type B is less accessible than the property A.MyProp
    public B MyProp
    {
        set
        {
        }
    }

    MyDelegate d = new MyDelegate(B.MyPrivateMethod);
    // Even when B is declared public, you still get the error: 
    // "The parameter B.MyPrivateMethod is not accessible due to 
    // protection level."

    public static B operator +(A m1, B m2)
    {
        // Error: The type B is less accessible
        // than the operator A.operator +(A,B)
        return new B();
    }

    static void Main()
    {
        Console.Write("Compiled successfully");
    }
}
```

## <a name="c-language-specification"></a><span data-ttu-id="648cc-134">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="648cc-134">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="648cc-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="648cc-135">See also</span></span>

- [<span data-ttu-id="648cc-136">C# 参考</span><span class="sxs-lookup"><span data-stu-id="648cc-136">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="648cc-137">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="648cc-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="648cc-138">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="648cc-138">C# Keywords</span></span>](../../language-reference/keywords/index.md)
- [<span data-ttu-id="648cc-139">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="648cc-139">Access Modifiers</span></span>](../../language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="648cc-140">可访问域</span><span class="sxs-lookup"><span data-stu-id="648cc-140">Accessibility Domain</span></span>](../../language-reference/keywords/accessibility-domain.md)
- [<span data-ttu-id="648cc-141">可访问性级别</span><span class="sxs-lookup"><span data-stu-id="648cc-141">Accessibility Levels</span></span>](../../language-reference/keywords/accessibility-levels.md)
- [<span data-ttu-id="648cc-142">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="648cc-142">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="648cc-143">public</span><span class="sxs-lookup"><span data-stu-id="648cc-143">public</span></span>](../../language-reference/keywords/public.md)
- [<span data-ttu-id="648cc-144">专用</span><span class="sxs-lookup"><span data-stu-id="648cc-144">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="648cc-145">protected</span><span class="sxs-lookup"><span data-stu-id="648cc-145">protected</span></span>](../../language-reference/keywords/protected.md)
- [<span data-ttu-id="648cc-146">internal</span><span class="sxs-lookup"><span data-stu-id="648cc-146">internal</span></span>](../../language-reference/keywords/internal.md)
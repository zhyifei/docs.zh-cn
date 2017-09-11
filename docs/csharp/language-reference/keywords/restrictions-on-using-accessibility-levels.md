---
title: "可访问性级别的使用限制（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8e49afd38fd776593b87f065a079da0d546df4a6
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a><span data-ttu-id="4cd32-102">可访问性级别的使用限制（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="4cd32-102">Restrictions on Using Accessibility Levels (C# Reference)</span></span>
<span data-ttu-id="4cd32-103">在声明中指定类型时，检查类型的可访问性级别是否依赖于成员或其他类型的可访问性级别。</span><span class="sxs-lookup"><span data-stu-id="4cd32-103">When you specify a type in a declaration, check whether the accessibility level of the type is dependent on the accessibility level of a member or of another type.</span></span> <span data-ttu-id="4cd32-104">例如，直接基类必须至少具有与派生类相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4cd32-104">For example, the direct base class must be at least as accessible as the derived class.</span></span> <span data-ttu-id="4cd32-105">以下声明会导致编译器错误，因为基类 `BaseClass` 的可访问性低于 `MyClass`：</span><span class="sxs-lookup"><span data-stu-id="4cd32-105">The following declarations cause a compiler error because the base class `BaseClass` is less accessible than `MyClass`:</span></span>  
  
```  
class BaseClass {...}  
public class MyClass: BaseClass {...} // Error  
```  
  
 <span data-ttu-id="4cd32-106">下表汇总了对已声明可访问性级别的限制。</span><span class="sxs-lookup"><span data-stu-id="4cd32-106">The following table summarizes the restrictions on declared accessibility levels.</span></span>  
  
|<span data-ttu-id="4cd32-107">上下文</span><span class="sxs-lookup"><span data-stu-id="4cd32-107">Context</span></span>|<span data-ttu-id="4cd32-108">备注</span><span class="sxs-lookup"><span data-stu-id="4cd32-108">Remarks</span></span>|  
|-------------|-------------|  
|[<span data-ttu-id="4cd32-109">类</span><span class="sxs-lookup"><span data-stu-id="4cd32-109">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)|<span data-ttu-id="4cd32-110">类类型的直接基类必须至少具有与类类型本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4cd32-110">The direct base class of a class type must be at least as accessible as the class type itself.</span></span>|  
|[<span data-ttu-id="4cd32-111">接口</span><span class="sxs-lookup"><span data-stu-id="4cd32-111">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)|<span data-ttu-id="4cd32-112">接口类型的显式基接口必须至少具有与接口类型本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4cd32-112">The explicit base interfaces of an interface type must be at least as accessible as the interface type itself.</span></span>|  
|[<span data-ttu-id="4cd32-113">委托</span><span class="sxs-lookup"><span data-stu-id="4cd32-113">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)|<span data-ttu-id="4cd32-114">委托类型的返回类型和参数类型必须至少具有与委托类型本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4cd32-114">The return type and parameter types of a delegate type must be at least as accessible as the delegate type itself.</span></span>|  
|[<span data-ttu-id="4cd32-115">常量</span><span class="sxs-lookup"><span data-stu-id="4cd32-115">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="4cd32-116">常量的类型必须至少具有与常量本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4cd32-116">The type of a constant must be at least as accessible as the constant itself.</span></span>|  
|[<span data-ttu-id="4cd32-117">字段</span><span class="sxs-lookup"><span data-stu-id="4cd32-117">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="4cd32-118">字段的类型必须至少具有与字段本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4cd32-118">The type of a field must be at least as accessible as the field itself.</span></span>|  
|[<span data-ttu-id="4cd32-119">方法</span><span class="sxs-lookup"><span data-stu-id="4cd32-119">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="4cd32-120">方法的返回类型和参数类型必须至少具有与方法本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4cd32-120">The return type and parameter types of a method must be at least as accessible as the method itself.</span></span>|  
|[<span data-ttu-id="4cd32-121">属性</span><span class="sxs-lookup"><span data-stu-id="4cd32-121">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="4cd32-122">属性的类型必须至少具有与属性本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4cd32-122">The type of a property must be at least as accessible as the property itself.</span></span>|  
|[<span data-ttu-id="4cd32-123">事件</span><span class="sxs-lookup"><span data-stu-id="4cd32-123">Events</span></span>](../../../csharp/programming-guide/events/index.md)|<span data-ttu-id="4cd32-124">事件的类型必须至少具有与事件本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4cd32-124">The type of an event must be at least as accessible as the event itself.</span></span>|  
|[<span data-ttu-id="4cd32-125">索引器</span><span class="sxs-lookup"><span data-stu-id="4cd32-125">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)|<span data-ttu-id="4cd32-126">索引器的类型和参数类型必须至少具有与索引器本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4cd32-126">The type and parameter types of an indexer must be at least as accessible as the indexer itself.</span></span>|  
|[<span data-ttu-id="4cd32-127">运算符</span><span class="sxs-lookup"><span data-stu-id="4cd32-127">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)|<span data-ttu-id="4cd32-128">运算符的类型和参数类型必须至少具有与运算符本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4cd32-128">The return type and parameter types of an operator must be at least as accessible as the operator itself.</span></span>|  
|[<span data-ttu-id="4cd32-129">构造函数</span><span class="sxs-lookup"><span data-stu-id="4cd32-129">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="4cd32-130">构造函数的参数类型必须至少具有与构造函数本身相同的可访问性。</span><span class="sxs-lookup"><span data-stu-id="4cd32-130">The parameter types of a constructor must be at least as accessible as the constructor itself.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4cd32-131">示例</span><span class="sxs-lookup"><span data-stu-id="4cd32-131">Example</span></span>  
 <span data-ttu-id="4cd32-132">下面的示例包含不同类型的错误声明。</span><span class="sxs-lookup"><span data-stu-id="4cd32-132">The following example contains erroneous declarations of different types.</span></span> <span data-ttu-id="4cd32-133">每个声明后的注释指示预期编译器错误。</span><span class="sxs-lookup"><span data-stu-id="4cd32-133">The comment following each declaration indicates the expected compiler error.</span></span>  
  
```  
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
  
## <a name="c-language-specification"></a><span data-ttu-id="4cd32-134">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="4cd32-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4cd32-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cd32-135">See Also</span></span>  
 <span data-ttu-id="4cd32-136">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4cd32-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4cd32-137">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4cd32-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4cd32-138">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4cd32-138">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="4cd32-139">[访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="4cd32-139">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="4cd32-140">[可访问域](../../../csharp/language-reference/keywords/accessibility-domain.md) </span><span class="sxs-lookup"><span data-stu-id="4cd32-140">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md) </span></span>  
 <span data-ttu-id="4cd32-141">[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="4cd32-141">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="4cd32-142">[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="4cd32-142">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="4cd32-143">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="4cd32-143">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="4cd32-144">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="4cd32-144">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="4cd32-145">[protected](../../../csharp/language-reference/keywords/protected.md) </span><span class="sxs-lookup"><span data-stu-id="4cd32-145">[protected](../../../csharp/language-reference/keywords/protected.md) </span></span>  
 [<span data-ttu-id="4cd32-146">内部</span><span class="sxs-lookup"><span data-stu-id="4cd32-146">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)


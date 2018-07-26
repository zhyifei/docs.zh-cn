---
title: 受保护的内部成员（C# 参考）
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 5ba2c811a1a4f095bcee65ed6678a7dc50fe94db
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "39244853"
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="a5c1d-102">受保护的内部成员（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a5c1d-102">protected internal (C# Reference)</span></span>
<span data-ttu-id="a5c1d-103">`protected internal` 关键字组合是一种成员访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="a5c1d-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="a5c1d-104">可从当前程序集或派生自包含类的类型访问受保护的内部成员。</span><span class="sxs-lookup"><span data-stu-id="a5c1d-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="a5c1d-105">有关 `protected internal` 和其他访问修饰符的比较，请参阅[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="a5c1d-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="a5c1d-106">示例</span><span class="sxs-lookup"><span data-stu-id="a5c1d-106">Example</span></span>  
 <span data-ttu-id="a5c1d-107">可从包含程序集内的任何类型访问基类的受保护的内部成员。</span><span class="sxs-lookup"><span data-stu-id="a5c1d-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="a5c1d-108">也可在另一程序集中的派生类中访问它，前提是通过派生类类型的变量进行访问。</span><span class="sxs-lookup"><span data-stu-id="a5c1d-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="a5c1d-109">以下面的代码段为例：</span><span class="sxs-lookup"><span data-stu-id="a5c1d-109">For example, consider the following code segment:</span></span>  

```csharp
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   protected internal int myValue = 0;  
}

class TestAccess 
{
    void Access()
    {
        BaseClass baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}  
```  
  
```csharp  
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass : BaseClass   
{  
    static void Main()
    {
        BaseClass baseObject = new BaseClass();
        DerivedClass derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10; 

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
} 
```  
 <span data-ttu-id="a5c1d-110">此示例包含两个文件，即 `Assembly1.cs` 和 `Assembly2.cs`。</span><span class="sxs-lookup"><span data-stu-id="a5c1d-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="a5c1d-111">第一个文件包含公共基类 `BaseClass` 和另一个类 `TestAccess`。</span><span class="sxs-lookup"><span data-stu-id="a5c1d-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="a5c1d-112">`BaseClass` 拥有受保护的内部成员 `myValue`，由 `TestAccess` 类型访问。</span><span class="sxs-lookup"><span data-stu-id="a5c1d-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span> <span data-ttu-id="a5c1d-113">在第二个文件中，如果尝试通过 `BaseClass` 的实例访问 `myValue` ，会生成错误，但如果尝试通过一个派生类的实例来访问此成员，`DerivedClass` 会成功。</span><span class="sxs-lookup"><span data-stu-id="a5c1d-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span> 

 <span data-ttu-id="a5c1d-114">结构成员不能为 `protected internal`，因为无法继承结构。</span><span class="sxs-lookup"><span data-stu-id="a5c1d-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a5c1d-115">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="a5c1d-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a5c1d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5c1d-116">See Also</span></span>  
 <span data-ttu-id="a5c1d-117">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a5c1d-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a5c1d-118">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a5c1d-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a5c1d-119">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a5c1d-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="a5c1d-120">[访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="a5c1d-120">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="a5c1d-121">[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="a5c1d-121">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="a5c1d-122">[修饰符](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="a5c1d-122">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="a5c1d-123">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="a5c1d-123">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="a5c1d-124">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="a5c1d-124">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="a5c1d-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="a5c1d-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="a5c1d-126">[Internal Virtual 关键字的安全问题](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="a5c1d-126">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>

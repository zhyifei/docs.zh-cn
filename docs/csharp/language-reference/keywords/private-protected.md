---
title: private protected（C# 参考）
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 0d511f55f44511590fbe92a98cef118e0cb482e2
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "37961127"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="5455b-102">private protected（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5455b-102">private protected (C# Reference)</span></span>
<span data-ttu-id="5455b-103">`private protected` 关键字组合是一种成员访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="5455b-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="5455b-104">仅派生自包含类的类型可访问私有受保护成员，但仅能在其包含程序集中访问。</span><span class="sxs-lookup"><span data-stu-id="5455b-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="5455b-105">有关 `private protected` 和其他访问修饰符的比较，请参阅[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="5455b-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="5455b-106">`private protected` 访问修饰符在 C# 版本 7.2 及更高版本中有效。</span><span class="sxs-lookup"><span data-stu-id="5455b-106">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>
   
## <a name="example"></a><span data-ttu-id="5455b-107">示例</span><span class="sxs-lookup"><span data-stu-id="5455b-107">Example</span></span>  
 <span data-ttu-id="5455b-108">仅当变量的静态类型是派生类类型时，可从派生的类型访问基类的私有受保护成员（在其包含程序集中访问）。</span><span class="sxs-lookup"><span data-stu-id="5455b-108">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="5455b-109">以下面的代码段为例：</span><span class="sxs-lookup"><span data-stu-id="5455b-109">For example, consider the following code segment:</span></span>  
  
 ```csharp
 // Assembly1.cs  
 // Compile with: /target:library  
 public class BaseClass
 {
     private protected int myValue = 0;
 }
 
 public class DerivedClass1 : BaseClass
 {
     void Access()
     {
         BaseClass baseObject = new BaseClass();
 
         // Error CS1540, because myValue can only be accessed by
         // classes derived from BaseClass.
         // baseObject.myValue = 5;  
 
         // OK, accessed through the current derived class instance
         myValue = 5;
     }
 }
```  
  
```csharp  
 // Assembly2.cs  
 // Compile with: /reference:Assembly1.dll  
 class DerivedClass2 : BaseClass
 {
     void Access()
     {
         // Error CS0122, because myValue can only be
         // accessed by types in Assembly1
         // myValue = 10;
     }
 }
```  
 <span data-ttu-id="5455b-110">此示例包含两个文件，即 `Assembly1.cs` 和 `Assembly2.cs`。</span><span class="sxs-lookup"><span data-stu-id="5455b-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="5455b-111">第一个文件包含公共基类 `BaseClass` 及其派生的类型 `DerivedClass1`。</span><span class="sxs-lookup"><span data-stu-id="5455b-111">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="5455b-112">`BaseClass` 拥有私有受保护成员 `myValue`，`DerivedClass1` 尝试以两种方式访问该成员。</span><span class="sxs-lookup"><span data-stu-id="5455b-112">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="5455b-113">通过 `BaseClass` 的实例第一次尝试访问 `myValue` 时会产生错误。</span><span class="sxs-lookup"><span data-stu-id="5455b-113">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="5455b-114">但是，如果尝试在 `DerivedClass1` 中将其用作继承的成员，则会成功。</span><span class="sxs-lookup"><span data-stu-id="5455b-114">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="5455b-115">在第二个文件中，如果尝试将 `myValue` 作为 `DerivedClass2` 的继承成员进行访问，会生成错误，因为仅 Assembly1 中的派生类型可以访问它。</span><span class="sxs-lookup"><span data-stu-id="5455b-115">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span> 

 <span data-ttu-id="5455b-116">结构成员不能为 `private protected`，因为无法继承结构。</span><span class="sxs-lookup"><span data-stu-id="5455b-116">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5455b-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5455b-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5455b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="5455b-118">See Also</span></span>  
 <span data-ttu-id="5455b-119">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5455b-119">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5455b-120">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5455b-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5455b-121">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="5455b-121">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="5455b-122">[访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="5455b-122">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="5455b-123">[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="5455b-123">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="5455b-124">[修饰符](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="5455b-124">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="5455b-125">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="5455b-125">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="5455b-126">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="5455b-126">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="5455b-127">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="5455b-127">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="5455b-128">[Internal Virtual 关键字的安全问题](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="5455b-128">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>

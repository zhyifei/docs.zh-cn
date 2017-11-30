---
title: "私有受保护 （C# 参考）"
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: 5f7abd2569d5bad5af64161042e4e5d21e741c8c
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="ab74d-102">私有受保护 （C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ab74d-102">private protected (C# Reference)</span></span>
<span data-ttu-id="ab74d-103">`private protected`关键字组合都是成员访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="ab74d-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="ab74d-104">由派生自包含的类，但仅在其包含的程序集中的类型可进行访问私有受保护的成员。</span><span class="sxs-lookup"><span data-stu-id="ab74d-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="ab74d-105">有关 `private protected` 和其他访问修饰符的比较，请参阅[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="ab74d-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="ab74d-106">示例</span><span class="sxs-lookup"><span data-stu-id="ab74d-106">Example</span></span>  
 <span data-ttu-id="ab74d-107">变量的静态类型是派生的类类型，基类的私有受保护的成员才可从其包含的程序集中的派生类型访问。</span><span class="sxs-lookup"><span data-stu-id="ab74d-107">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="ab74d-108">以下面的代码段为例：</span><span class="sxs-lookup"><span data-stu-id="ab74d-108">For example, consider the following code segment:</span></span>  
  
 ```
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
  
```  
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
 <span data-ttu-id="ab74d-109">此示例包含两个文件，即 `Assembly1.cs` 和 `Assembly2.cs`。</span><span class="sxs-lookup"><span data-stu-id="ab74d-109">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="ab74d-110">第一个文件包含公共的基类， `BaseClass`，和由它派生的类型`DerivedClass1`。</span><span class="sxs-lookup"><span data-stu-id="ab74d-110">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="ab74d-111">`BaseClass`拥有专用的受保护的成员， `myValue`，后者`DerivedClass1`尝试以两种方式访问。</span><span class="sxs-lookup"><span data-stu-id="ab74d-111">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="ab74d-112">首次尝试访问`myValue`的实例通过`BaseClass`将产生错误。</span><span class="sxs-lookup"><span data-stu-id="ab74d-112">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="ab74d-113">但是，尝试将其用作中继承的成员`DerivedClass1`将会成功。</span><span class="sxs-lookup"><span data-stu-id="ab74d-113">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="ab74d-114">在第二个文件中，尝试访问`myValue`的继承的成员作为`DerivedClass2`将产生错误，因为仅由派生类型中 Assembly1 访问它。</span><span class="sxs-lookup"><span data-stu-id="ab74d-114">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span> 

 <span data-ttu-id="ab74d-115">结构成员不能为`private protected`由于结构不能被继承。</span><span class="sxs-lookup"><span data-stu-id="ab74d-115">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ab74d-116">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ab74d-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ab74d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab74d-117">See Also</span></span>  
 <span data-ttu-id="ab74d-118">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ab74d-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ab74d-119">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ab74d-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ab74d-120">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="ab74d-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="ab74d-121">[访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="ab74d-121">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="ab74d-122">[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="ab74d-122">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="ab74d-123">[修饰符](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="ab74d-123">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="ab74d-124">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="ab74d-124">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="ab74d-125">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="ab74d-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="ab74d-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="ab74d-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="ab74d-127">[Internal virtual 关键字的安全问题](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="ab74d-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>

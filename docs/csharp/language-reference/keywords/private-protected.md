---
title: private protected（C# 参考）
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 4a4ee999fe932674e854b1428ab33b33bc71d2ad
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43419529"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="956f4-102">private protected（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="956f4-102">private protected (C# Reference)</span></span>

<span data-ttu-id="956f4-103">`private protected` 关键字组合是一种成员访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="956f4-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="956f4-104">仅派生自包含类的类型可访问私有受保护成员，但仅能在其包含程序集中访问。</span><span class="sxs-lookup"><span data-stu-id="956f4-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="956f4-105">有关 `private protected` 和其他访问修饰符的比较，请参阅[可访问性级别](accessibility-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="956f4-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="956f4-106">`private protected` 访问修饰符在 C# 版本 7.2 及更高版本中有效。</span><span class="sxs-lookup"><span data-stu-id="956f4-106">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="956f4-107">示例</span><span class="sxs-lookup"><span data-stu-id="956f4-107">Example</span></span>

<span data-ttu-id="956f4-108">仅当变量的静态类型是派生类类型时，可从派生的类型访问基类的私有受保护成员（在其包含程序集中访问）。</span><span class="sxs-lookup"><span data-stu-id="956f4-108">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="956f4-109">以下面的代码段为例：</span><span class="sxs-lookup"><span data-stu-id="956f4-109">For example, consider the following code segment:</span></span>  

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

<span data-ttu-id="956f4-110">此示例包含两个文件，即 `Assembly1.cs` 和 `Assembly2.cs`。</span><span class="sxs-lookup"><span data-stu-id="956f4-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="956f4-111">第一个文件包含公共基类 `BaseClass` 及其派生的类型 `DerivedClass1`。</span><span class="sxs-lookup"><span data-stu-id="956f4-111">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="956f4-112">`BaseClass` 拥有私有受保护成员 `myValue`，`DerivedClass1` 尝试以两种方式访问该成员。</span><span class="sxs-lookup"><span data-stu-id="956f4-112">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="956f4-113">通过 `BaseClass` 的实例第一次尝试访问 `myValue` 时会产生错误。</span><span class="sxs-lookup"><span data-stu-id="956f4-113">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="956f4-114">但是，如果尝试在 `DerivedClass1` 中将其用作继承的成员，则会成功。</span><span class="sxs-lookup"><span data-stu-id="956f4-114">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="956f4-115">在第二个文件中，如果尝试将 `myValue` 作为 `DerivedClass2` 的继承成员进行访问，会生成错误，因为仅 Assembly1 中的派生类型可以访问它。</span><span class="sxs-lookup"><span data-stu-id="956f4-115">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="956f4-116">结构成员不能为 `private protected`，因为无法继承结构。</span><span class="sxs-lookup"><span data-stu-id="956f4-116">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="956f4-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="956f4-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="956f4-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="956f4-118">See also</span></span>

- [<span data-ttu-id="956f4-119">C# 参考</span><span class="sxs-lookup"><span data-stu-id="956f4-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="956f4-120">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="956f4-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="956f4-121">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="956f4-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="956f4-122">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="956f4-122">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="956f4-123">可访问性级别</span><span class="sxs-lookup"><span data-stu-id="956f4-123">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="956f4-124">修饰符</span><span class="sxs-lookup"><span data-stu-id="956f4-124">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="956f4-125">public</span><span class="sxs-lookup"><span data-stu-id="956f4-125">public</span></span>](public.md)
- [<span data-ttu-id="956f4-126">private</span><span class="sxs-lookup"><span data-stu-id="956f4-126">private</span></span>](private.md)
- [<span data-ttu-id="956f4-127">internal</span><span class="sxs-lookup"><span data-stu-id="956f4-127">internal</span></span>](internal.md)
- <span data-ttu-id="956f4-128">[Internal Virtual 关键字的安全问题](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="956f4-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
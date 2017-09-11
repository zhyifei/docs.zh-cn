---
title: "重构为纯函数 (C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 2944a0d4-fd33-4e2e-badd-abb0f9be2fcc
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 9bb17207ba72bb22f5d6db55e9d1bd77e3013445
ms.openlocfilehash: 2bce781df80a777203ed8e713bedf83f1c7779a8
ms.contentlocale: zh-cn
ms.lasthandoff: 08/25/2017

---
# <a name="refactoring-into-pure-functions-c"></a><span data-ttu-id="5cf16-102">重构为纯函数 (C#)</span><span class="sxs-lookup"><span data-stu-id="5cf16-102">Refactoring Into Pure Functions (C#)</span></span>

<span data-ttu-id="5cf16-103">纯函数转换的一个重要方面是学习如何使用纯函数重构代码。</span><span class="sxs-lookup"><span data-stu-id="5cf16-103">An important aspect of pure functional transformations is learning how to refactor code using pure functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5cf16-104">函数编程中的常用术语是使用纯函数重构程序。</span><span class="sxs-lookup"><span data-stu-id="5cf16-104">The common nomenclature in functional programming is that you refactor programs using pure functions.</span></span> <span data-ttu-id="5cf16-105">在 Visual Basic 和 C++ 中，这对应于使用相应语言的函数。</span><span class="sxs-lookup"><span data-stu-id="5cf16-105">In Visual Basic and C++, this aligns with the use of functions in the respective languages.</span></span> <span data-ttu-id="5cf16-106">但在 C# 中，函数称为方法。</span><span class="sxs-lookup"><span data-stu-id="5cf16-106">However, in C#, functions are called methods.</span></span> <span data-ttu-id="5cf16-107">出于本文论述的需要，在 C# 中以方法的形式实现了一个纯函数。</span><span class="sxs-lookup"><span data-stu-id="5cf16-107">For the purposes of this discussion, a pure function is implemented as a method in C#.</span></span>  
  
 <span data-ttu-id="5cf16-108">如本节前面所述，纯函数具有两个有用的特性：</span><span class="sxs-lookup"><span data-stu-id="5cf16-108">As noted previously in this section, a pure function has two useful characteristics:</span></span>  
  
-   <span data-ttu-id="5cf16-109">它没有任何副作用。</span><span class="sxs-lookup"><span data-stu-id="5cf16-109">It has no side effects.</span></span> <span data-ttu-id="5cf16-110">函数不会更改函数以外的任何变量或任何类型的数据。</span><span class="sxs-lookup"><span data-stu-id="5cf16-110">The function does not change any variables or the data of any type outside of the function.</span></span>  
  
-   <span data-ttu-id="5cf16-111">它具有一致性。</span><span class="sxs-lookup"><span data-stu-id="5cf16-111">It is consistent.</span></span> <span data-ttu-id="5cf16-112">在提供同一组输入数据的情况下，它将始终返回相同的输出值。</span><span class="sxs-lookup"><span data-stu-id="5cf16-112">Given the same set of input data, it will always return the same output value.</span></span>  
  
 <span data-ttu-id="5cf16-113">转换为函数编程的一种方式是重构现有代码以消除不必要的副作用和外部依赖项。</span><span class="sxs-lookup"><span data-stu-id="5cf16-113">One way of transitioning to functional programming is to refactor existing code to eliminate unnecessary side effects and external dependencies.</span></span> <span data-ttu-id="5cf16-114">这样，您可以创建现有代码的纯函数版本。</span><span class="sxs-lookup"><span data-stu-id="5cf16-114">In this way, you can create pure function versions of existing code.</span></span>  
  
 <span data-ttu-id="5cf16-115">本主题讨论什么是纯函数，什么不是纯函数。</span><span class="sxs-lookup"><span data-stu-id="5cf16-115">This topic discusses what a pure function is and what it is not.</span></span> <span data-ttu-id="5cf16-116">[教程：操作 WordprocessingML 文档中的内容 (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) 教程演示如何操作 WordprocessingML 文档并包括两个有关如何使用纯函数进行重构的示例。</span><span class="sxs-lookup"><span data-stu-id="5cf16-116">The [Tutorial: Manipulating Content in a WordprocessingML Document (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.</span></span>  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a><span data-ttu-id="5cf16-117">消除副作用和外部依赖项</span><span class="sxs-lookup"><span data-stu-id="5cf16-117">Eliminating Side Effects and External Dependencies</span></span>  
 <span data-ttu-id="5cf16-118">下面的示例对比两个非纯函数和一个纯函数。</span><span class="sxs-lookup"><span data-stu-id="5cf16-118">The following examples contrast two non-pure functions and a pure function.</span></span>  
  
### <a name="non-pure-function-that-changes-a-class-member"></a><span data-ttu-id="5cf16-119">可更改类成员的非纯函数</span><span class="sxs-lookup"><span data-stu-id="5cf16-119">Non-Pure Function that Changes a Class Member</span></span>  
 <span data-ttu-id="5cf16-120">在下面的代码中，`HypenatedConcat` 函数不是纯函数，因为它修改了类中的 `aMember` 数据成员：</span><span class="sxs-lookup"><span data-stu-id="5cf16-120">In the following code, the `HypenatedConcat` function is not a pure function, because it modifies the `aMember` data member in the class:</span></span>  
  
```csharp  
public class Program  
{  
    private static string aMember = "StringOne";  
  
    public static void HypenatedConcat(string appendStr)  
    {  
        aMember += '-' + appendStr;  
    }  
  
    public static void Main()  
    {  
        HypenatedConcat("StringTwo");  
        Console.WriteLine(aMember);  
    }  
}  
```  
  
 <span data-ttu-id="5cf16-121">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="5cf16-121">This code produces the following output:</span></span>  
  
```  
StringOne-StringTwo  
```  
  
 <span data-ttu-id="5cf16-122">请注意，它与修改的数据是具有 `public` 还是 `private` 访问权限或者是 `static` 成员还是实例成员均无关。</span><span class="sxs-lookup"><span data-stu-id="5cf16-122">Note that it is irrelevant whether the data being modified has `public` or `private` access, or is a `static` member or an instance member.</span></span> <span data-ttu-id="5cf16-123">纯函数不会更改函数以外的任何数据。</span><span class="sxs-lookup"><span data-stu-id="5cf16-123">A pure function does not change any data outside of the function.</span></span>  
  
### <a name="non-pure-function-that-changes-an-argument"></a><span data-ttu-id="5cf16-124">可更改参数的非纯函数</span><span class="sxs-lookup"><span data-stu-id="5cf16-124">Non-Pure Function that Changes an Argument</span></span>  
 <span data-ttu-id="5cf16-125">此外，此同一个函数的下面版本不是纯函数，因为它修改了其参数 `sb` 的内容。</span><span class="sxs-lookup"><span data-stu-id="5cf16-125">Furthermore, the following version of this same function is not pure because it modifies the contents of its parameter, `sb`.</span></span>  
  
```csharp  
public class Program  
{  
    public static void HypenatedConcat(StringBuilder sb, String appendStr)  
    {  
        sb.Append('-' + appendStr);  
    }  
  
    public static void Main()  
    {  
        StringBuilder sb1 = new StringBuilder("StringOne");  
        HypenatedConcat(sb1, "StringTwo");  
        Console.WriteLine(sb1);  
    }  
}  
```  
  
 <span data-ttu-id="5cf16-126">此版本的程序生成的输出与第一个版本相同，因为 `HypenatedConcat` 函数已通过调用 <xref:System.Text.StringBuilder.Append%2A> 成员函数而更改了其第一个参数的值（状态）。</span><span class="sxs-lookup"><span data-stu-id="5cf16-126">This version of the program produces the same output as the first version, because the `HypenatedConcat` function has changed the value (state) of its first parameter by invoking the <xref:System.Text.StringBuilder.Append%2A> member function.</span></span> <span data-ttu-id="5cf16-127">请注意，即使 `HypenatedConcat` 实际上使用了按值调用参数传递，也会发生此更改。</span><span class="sxs-lookup"><span data-stu-id="5cf16-127">Note that this alteration occurs despite that fact that `HypenatedConcat` uses call-by-value parameter passing.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5cf16-128">对于引用类型，按值传递参数会得到对所传递对象的引用的副本。</span><span class="sxs-lookup"><span data-stu-id="5cf16-128">For reference types, if you pass a parameter by value, it results in a copy of the reference to an object being passed.</span></span> <span data-ttu-id="5cf16-129">此副本与原始引用一样，仍与同一个实例数据关联（除非为引用变量分配新对象）。</span><span class="sxs-lookup"><span data-stu-id="5cf16-129">This copy is still associated with the same instance data as the original reference (until the reference variable is assigned to a new object).</span></span> <span data-ttu-id="5cf16-130">函数修改参数不一定需要按引用调用。</span><span class="sxs-lookup"><span data-stu-id="5cf16-130">Call-by-reference is not necessarily required for a function to modify a parameter.</span></span>  
  
### <a name="pure-function"></a><span data-ttu-id="5cf16-131">纯函数</span><span class="sxs-lookup"><span data-stu-id="5cf16-131">Pure Function</span></span>  
<span data-ttu-id="5cf16-132">下面版本的程序演示如何将 `HypenatedConcat` 函数作为纯函数实现。</span><span class="sxs-lookup"><span data-stu-id="5cf16-132">This next version of the program shows how to implement the `HypenatedConcat` function as a pure function.</span></span>  
  
```csharp  
class Program  
{  
    public static string HyphenatedConcat(string s, string appendStr)  
    {  
        return (s + '-' + appendStr);  
    }  
  
    public static void Main(string[] args)  
    {  
        string s1 = "StringOne";  
        string s2 = HyphenatedConcat(s1, "StringTwo");  
        Console.WriteLine(s2);  
    }  
}  
```  
  
 <span data-ttu-id="5cf16-133">此版本同样生成相同的输出行：`StringOne-StringTwo`。</span><span class="sxs-lookup"><span data-stu-id="5cf16-133">Again, this version produces the same line of output: `StringOne-StringTwo`.</span></span> <span data-ttu-id="5cf16-134">请注意保留串联值，它存储在中间变量 `s2` 中。</span><span class="sxs-lookup"><span data-stu-id="5cf16-134">Note that to retain the concatenated value, it is stored in the intermediate variable `s2`.</span></span>  
  
 <span data-ttu-id="5cf16-135">一种非常实用的方法是编写本地不纯（即声明和修改本地变量）但在全局为纯的函数。</span><span class="sxs-lookup"><span data-stu-id="5cf16-135">One approach that can be very useful is to write functions that are locally impure (that is, they declare and modify local variables) but are globally pure.</span></span> <span data-ttu-id="5cf16-136">这些函数具有许多需要的可组合特性，但舍弃了一些较为繁复的函数编程语法，如在使用简单的循环即可完成同样操作时必须使用递归。</span><span class="sxs-lookup"><span data-stu-id="5cf16-136">Such functions have many of the desirable composability characteristics, but avoid some of the more convoluted functional programming idioms, such as having to use recursion when a simple loop would accomplish the same thing.</span></span>  
  
## <a name="standard-query-operators"></a><span data-ttu-id="5cf16-137">标准查询运算符</span><span class="sxs-lookup"><span data-stu-id="5cf16-137">Standard Query Operators</span></span>  
 <span data-ttu-id="5cf16-138">标准查询运算符的重要特性是它们以纯函数的形式实现。</span><span class="sxs-lookup"><span data-stu-id="5cf16-138">An important characteristic of the standard query operators is that they are implemented as pure functions.</span></span>  
  
 <span data-ttu-id="5cf16-139">有关详细信息，请参阅[标准查询运算符概述 (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5cf16-139">For more information, see [Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cf16-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="5cf16-140">See Also</span></span>  
 <span data-ttu-id="5cf16-141">[纯函数转换简介 (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="5cf16-141">[Introduction to Pure Functional Transformations (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span></span>  
 [<span data-ttu-id="5cf16-142">函数编程与命令式编程 (C#)</span><span class="sxs-lookup"><span data-stu-id="5cf16-142">Functional Programming vs. Imperative Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)


---
title: 泛型接口中的变体 (C#)
ms.date: 07/20/2015
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
ms.openlocfilehash: 11d0c8665412bb513cb68d58203a454b7c97e052
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2018
ms.locfileid: "47399776"
---
# <a name="variance-in-generic-interfaces-c"></a><span data-ttu-id="97e08-102">泛型接口中的变体 (C#)</span><span class="sxs-lookup"><span data-stu-id="97e08-102">Variance in Generic Interfaces (C#)</span></span>
<span data-ttu-id="97e08-103">.NET Framework 4 引入了对多个现有泛型接口的变体支持。</span><span class="sxs-lookup"><span data-stu-id="97e08-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="97e08-104">变体支持允许实现这些接口的类进行隐式转换。</span><span class="sxs-lookup"><span data-stu-id="97e08-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> <span data-ttu-id="97e08-105">下面的接口现在是变体：</span><span class="sxs-lookup"><span data-stu-id="97e08-105">The following interfaces are now variant:</span></span>  
  
-   <span data-ttu-id="97e08-106"><xref:System.Collections.Generic.IEnumerable%601>（T 是协变）</span><span class="sxs-lookup"><span data-stu-id="97e08-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="97e08-107"><xref:System.Collections.Generic.IEnumerator%601>（T 是协变）</span><span class="sxs-lookup"><span data-stu-id="97e08-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="97e08-108"><xref:System.Linq.IQueryable%601>（T 是协变）</span><span class="sxs-lookup"><span data-stu-id="97e08-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="97e08-109"><xref:System.Linq.IGrouping%602>（`TKey` 和 `TElement` 都是协变）</span><span class="sxs-lookup"><span data-stu-id="97e08-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>  
  
-   <span data-ttu-id="97e08-110"><xref:System.Collections.Generic.IComparer%601>（T 是逆变）</span><span class="sxs-lookup"><span data-stu-id="97e08-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="97e08-111"><xref:System.Collections.Generic.IEqualityComparer%601>（T 是逆变）</span><span class="sxs-lookup"><span data-stu-id="97e08-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="97e08-112"><xref:System.IComparable%601>（T 是逆变）</span><span class="sxs-lookup"><span data-stu-id="97e08-112"><xref:System.IComparable%601> (T is contravariant)</span></span>  
  
 <span data-ttu-id="97e08-113">协变允许方法具有的返回类型比接口的泛型类型参数定义的返回类型的派生程度更大。</span><span class="sxs-lookup"><span data-stu-id="97e08-113">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="97e08-114">若要演示协变功能，请考虑以下泛型接口：`IEnumerable<Object>` 和 `IEnumerable<String>`。</span><span class="sxs-lookup"><span data-stu-id="97e08-114">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable<Object>` and `IEnumerable<String>`.</span></span> <span data-ttu-id="97e08-115">`IEnumerable<String>` 接口不继承 `IEnumerable<Object>` 接口。</span><span class="sxs-lookup"><span data-stu-id="97e08-115">The `IEnumerable<String>` interface does not inherit the `IEnumerable<Object>` interface.</span></span> <span data-ttu-id="97e08-116">但是，`String` 类型会继承 `Object` 类型，在某些情况下，建议为这些接口互相指派彼此的对象。</span><span class="sxs-lookup"><span data-stu-id="97e08-116">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="97e08-117">下面的代码示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="97e08-117">This is shown in the following code example.</span></span>  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 <span data-ttu-id="97e08-118">在 .NET Framework 早期版本中，在 `Option Strict On` 条件下，此代码会导致 C# 中出现编译错误。</span><span class="sxs-lookup"><span data-stu-id="97e08-118">In earlier versions of the .NET Framework, this code causes a compilation error in C# with `Option Strict On`.</span></span> <span data-ttu-id="97e08-119">但现在可使用 `strings` 代替 `objects`，如上例所示，因为 <xref:System.Collections.Generic.IEnumerable%601> 接口是协变接口。</span><span class="sxs-lookup"><span data-stu-id="97e08-119">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>  
  
 <span data-ttu-id="97e08-120">逆变允许方法具有的实参类型比接口的泛型形参定义的类型的派生程度更小。</span><span class="sxs-lookup"><span data-stu-id="97e08-120">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="97e08-121">若要演示逆变，假设已创建了 `BaseComparer` 类来比较 `BaseClass` 类的实例。</span><span class="sxs-lookup"><span data-stu-id="97e08-121">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="97e08-122">`BaseComparer` 类实现 `IEqualityComparer<BaseClass>` 接口。</span><span class="sxs-lookup"><span data-stu-id="97e08-122">The `BaseComparer` class implements the `IEqualityComparer<BaseClass>` interface.</span></span> <span data-ttu-id="97e08-123">因为 <xref:System.Collections.Generic.IEqualityComparer%601> 接口现在是逆变接口，因此可使用 `BaseComparer` 比较继承 `BaseClass` 类的类的实例。</span><span class="sxs-lookup"><span data-stu-id="97e08-123">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="97e08-124">下面的代码示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="97e08-124">This is shown in the following code example.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
class BaseClass { }  
class DerivedClass : BaseClass { }  
  
// Comparer class.  
class BaseComparer : IEqualityComparer<BaseClass>   
{  
    public int GetHashCode(BaseClass baseInstance)  
    {  
        return baseInstance.GetHashCode();  
    }  
    public bool Equals(BaseClass x, BaseClass y)  
    {  
        return x == y;  
    }  
}  
class Program  
{  
    static void Test()  
    {  
        IEqualityComparer<BaseClass> baseComparer = new BaseComparer();  
  
        // Implicit conversion of IEqualityComparer<BaseClass> to   
        // IEqualityComparer<DerivedClass>.  
        IEqualityComparer<DerivedClass> childComparer = baseComparer;  
    }  
}  
```  
  
 <span data-ttu-id="97e08-125">有关更多示例，请参阅[在泛型集合的接口中使用变体 (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)。</span><span class="sxs-lookup"><span data-stu-id="97e08-125">For more examples, see [Using Variance in Interfaces for Generic Collections (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>  
  
 <span data-ttu-id="97e08-126">只有引用类型才支持使用泛型接口中的变体。</span><span class="sxs-lookup"><span data-stu-id="97e08-126">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="97e08-127">值类型不支持变体。</span><span class="sxs-lookup"><span data-stu-id="97e08-127">Value types do not support variance.</span></span> <span data-ttu-id="97e08-128">例如，无法将 `IEnumerable<int>` 隐式转换为 `IEnumerable<object>`，因为整数由值类型表示。</span><span class="sxs-lookup"><span data-stu-id="97e08-128">For example, `IEnumerable<int>` cannot be implicitly converted to `IEnumerable<object>`, because integers are represented by a value type.</span></span>  
  
```csharp  
IEnumerable<int> integers = new List<int>();  
// The following statement generates a compiler errror,  
// because int is a value type.  
// IEnumerable<Object> objects = integers;  
```  
  
 <span data-ttu-id="97e08-129">还需记住，实现变体接口的类仍是固定类。</span><span class="sxs-lookup"><span data-stu-id="97e08-129">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="97e08-130">例如，虽然 <xref:System.Collections.Generic.List%601> 实现协变接口 <xref:System.Collections.Generic.IEnumerable%601>，但不能将 `List<Object>` 隐式转换为 `List<String>`。</span><span class="sxs-lookup"><span data-stu-id="97e08-130">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List<Object>` to `List<String>`.</span></span> <span data-ttu-id="97e08-131">以下代码示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="97e08-131">This is illustrated in the following code example.</span></span>  
  
```csharp  
// The following line generates a compiler error  
// because classes are invariant.  
// List<Object> list = new List<String>();  
  
// You can use the interface object instead.  
IEnumerable<Object> listObjects = new List<String>();  
```  
  
## <a name="see-also"></a><span data-ttu-id="97e08-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="97e08-132">See Also</span></span>

- [<span data-ttu-id="97e08-133">在泛型集合的接口中使用变体 (C#)</span><span class="sxs-lookup"><span data-stu-id="97e08-133">Using Variance in Interfaces for Generic Collections (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)  
- [<span data-ttu-id="97e08-134">创建变体泛型接口 (C#)</span><span class="sxs-lookup"><span data-stu-id="97e08-134">Creating Variant Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)  
- [<span data-ttu-id="97e08-135">泛型接口</span><span class="sxs-lookup"><span data-stu-id="97e08-135">Generic Interfaces</span></span>](../../../../standard/generics/interfaces.md)  
- [<span data-ttu-id="97e08-136">委托中的变体 (C#)</span><span class="sxs-lookup"><span data-stu-id="97e08-136">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)

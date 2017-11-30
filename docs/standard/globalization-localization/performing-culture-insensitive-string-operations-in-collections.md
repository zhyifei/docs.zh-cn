---
title: "在集合中执行不区分区域性的字符串操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CaseInsensitiveComparer class, using
- CollectionsUtil.CreateCaseInsensitiveHashtable method
- culture-insensitive string operations, collections
- collections [.NET Framework], culture-insensitive string operations
- CaseInsensitiveHashCodeProvider class, using
- ArrayList.Sort method
- SortedList class, culture-insensitive string operations
- culture parameter
ms.assetid: 5cdc9396-a64b-4615-a1cd-b605db4c5983
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1ecba9c055f8e99d26283c7f37c2430dc17bf31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-string-operations-in-collections"></a><span data-ttu-id="a7807-102">在集合中执行不区分区域性的字符串操作</span><span class="sxs-lookup"><span data-stu-id="a7807-102">Performing Culture-Insensitive String Operations in Collections</span></span>
<span data-ttu-id="a7807-103">有中类和成员<xref:System.Collections>默认情况下提供区分区域性的行为的命名空间。</span><span class="sxs-lookup"><span data-stu-id="a7807-103">There are classes and members in the <xref:System.Collections> namespace that provide culture-sensitive behavior by default.</span></span> <span data-ttu-id="a7807-104">默认构造函数<xref:System.Collections.CaseInsensitiveComparer>和<xref:System.Collections.CaseInsensitiveHashCodeProvider>类初始化新实例使用<xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="a7807-104">The default constructors for the <xref:System.Collections.CaseInsensitiveComparer> and <xref:System.Collections.CaseInsensitiveHashCodeProvider> classes initialize a new instance using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a7807-105">所有重载<xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType>方法创建的新实例<xref:System.Collections.Hashtable>类使用`Thread.CurrentCulture`默认情况下的属性。</span><span class="sxs-lookup"><span data-stu-id="a7807-105">All overloads of the <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> method create a new instance of the <xref:System.Collections.Hashtable> class using the `Thread.CurrentCulture` property by default.</span></span> <span data-ttu-id="a7807-106">重载的<xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType>方法执行区分区域性的排序通过默认使用`Thread.CurrentCulture`。</span><span class="sxs-lookup"><span data-stu-id="a7807-106">Overloads of the <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> method perform culture-sensitive sorts by default using `Thread.CurrentCulture`.</span></span> <span data-ttu-id="a7807-107">排序和中的查找<xref:System.Collections.SortedList>可能会影响`Thread.CurrentCulture`时将字符串用作密钥。</span><span class="sxs-lookup"><span data-stu-id="a7807-107">Sorting and lookup in a <xref:System.Collections.SortedList> can be affected by `Thread.CurrentCulture` when strings are used as the keys.</span></span> <span data-ttu-id="a7807-108">请按本节提供的用法建议，在 `Collections` 命名空间中的这些类和方法中获取不区分区域性的结果。</span><span class="sxs-lookup"><span data-stu-id="a7807-108">Follow the usage recommendations provided in this section to obtain culture-insensitive results from these classes and methods in the `Collections` namespace.</span></span>  
  
 <span data-ttu-id="a7807-109">**请注意**传递<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>与比较方法并执行不区分区域性的比较。</span><span class="sxs-lookup"><span data-stu-id="a7807-109">**Note** Passing <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="a7807-110">但是，这不会导致对文件路径、注册表项、环境变量等进行非语义比较。</span><span class="sxs-lookup"><span data-stu-id="a7807-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="a7807-111">也不支持基于比较结果的安全决策。</span><span class="sxs-lookup"><span data-stu-id="a7807-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="a7807-112">对于非语言比较或结果基于安全决策的支持，应用程序应使用的比较方法，接受<xref:System.StringComparison>值。</span><span class="sxs-lookup"><span data-stu-id="a7807-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="a7807-113">应用程序应传递<xref:System.StringComparison>。</span><span class="sxs-lookup"><span data-stu-id="a7807-113">The application should then pass <xref:System.StringComparison>.</span></span>  
  
## <a name="using-the-caseinsensitivecomparer-and-caseinsensitivehashcodeprovider-classes"></a><span data-ttu-id="a7807-114">使用 CaseInsensitiveComparer 和 CaseInsensitiveHashCodeProvider 类</span><span class="sxs-lookup"><span data-stu-id="a7807-114">Using the CaseInsensitiveComparer and CaseInsensitiveHashCodeProvider Classes</span></span>  
 <span data-ttu-id="a7807-115">`CaseInsensitiveHashCodeProvider` 和 `CaseInsensitiveComparer` 的默认构造函数使用 `Thread.CurrentCulture` 来初始化类的新实例，因而产生区分区域性的行为。</span><span class="sxs-lookup"><span data-stu-id="a7807-115">The default constructors for `CaseInsensitiveHashCodeProvider` and `CaseInsensitiveComparer` initialize a new instance of the class using the `Thread.CurrentCulture`, resulting in culture-sensitive behavior.</span></span> <span data-ttu-id="a7807-116">下面的代码示例演示 `Hashtable` 的构造函数，该构造函数使用 `CaseInsensitiveHashCodeProvider` 和 `CaseInsensitiveComparer` 的默认构造函数，因而区分区域性。</span><span class="sxs-lookup"><span data-stu-id="a7807-116">The following code example demonstrates the constructor for a `Hashtable` that is culture-sensitive because it uses the default constructors for `CaseInsensitiveHashCodeProvider` and `CaseInsensitiveComparer`.</span></span>  
  
```vb  
internalHashtable = New Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default)  
```  
  
```csharp  
internalHashtable = new Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default);  
```  
  
 <span data-ttu-id="a7807-117">如果你想要创建不区分区域性的`Hashtable`使用`CaseInsensitiveComparer`和`CaseInsensitiveHashCodeProvider`类，初始化将接受构造函数使用这些类的新实例`culture`参数。</span><span class="sxs-lookup"><span data-stu-id="a7807-117">If you want to create a culture-insensitive `Hashtable` using the `CaseInsensitiveComparer` and `CaseInsensitiveHashCodeProvider` classes, initialize new instances of these classes using the constructors that accept a `culture` parameter.</span></span> <span data-ttu-id="a7807-118">对于 `culture` 参数，请指定 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a7807-118">For the `culture` parameter, specify <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a7807-119">下面的代码示例演示不区分区域性的 `Hashtable` 的构造函数。</span><span class="sxs-lookup"><span data-stu-id="a7807-119">The following code example demonstrates the constructor for a culture-insensitive `Hashtable`.</span></span>  
  
```vb  
internalHashtable = New Hashtable(New  
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),  
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))  
```  
  
```csharp  
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider  
    (CultureInfo.InvariantCulture),   
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));  
```  
  
## <a name="using-the-collectionsutilcreatecaseinsensitivehashtable-method"></a><span data-ttu-id="a7807-120">使用 CollectionsUtil.CreateCaseInsensitiveHashTable 方法</span><span class="sxs-lookup"><span data-stu-id="a7807-120">Using the CollectionsUtil.CreateCaseInsensitiveHashTable Method</span></span>  
 <span data-ttu-id="a7807-121">若要为 `Hashtable` 类创建一个忽略字符串大小写的新实例，`CollectionsUtil.CreateCaseInsensitiveHashTable` 方法是一种十分有用的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="a7807-121">The `CollectionsUtil.CreateCaseInsensitiveHashTable` method is a useful shortcut for creating a new instance of the `Hashtable` class that ignores the case of strings.</span></span> <span data-ttu-id="a7807-122">但是，`CollectionsUtil.CreateCaseInsensitiveHashTable` 方法的所有重载都区分区域性，因为这些重载使用 `Thread.CurrentCulture` 属性。</span><span class="sxs-lookup"><span data-stu-id="a7807-122">However, all overloads of the `CollectionsUtil.CreateCaseInsensitiveHashTable` method are culture-sensitive because they use the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="a7807-123">不能使用此方法创建不区分区域性的 `Hashtable`。</span><span class="sxs-lookup"><span data-stu-id="a7807-123">You cannot create a culture-insensitive `Hashtable` using this method.</span></span> <span data-ttu-id="a7807-124">若要创建不区分区域性的 `Hashtable`，请使用接受 `culture` 参数的 `Hashtable` 构造函数。</span><span class="sxs-lookup"><span data-stu-id="a7807-124">To create a culture-insensitive `Hashtable`, use the `Hashtable` constructor that accepts a `culture` parameter.</span></span> <span data-ttu-id="a7807-125">对于 `culture` 参数，请指定 `CultureInfo.InvariantCulture`。</span><span class="sxs-lookup"><span data-stu-id="a7807-125">For the `culture` parameter, specify `CultureInfo.InvariantCulture`.</span></span> <span data-ttu-id="a7807-126">下面的代码示例演示不区分区域性的 `Hashtable` 的构造函数。</span><span class="sxs-lookup"><span data-stu-id="a7807-126">The following code example demonstrates the constructor for a culture-insensitive `Hashtable`.</span></span>  
  
```vb  
internalHashtable = New Hashtable(New  
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),  
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))  
```  
  
```csharp  
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider  
    (CultureInfo.InvariantCulture),   
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));  
```  
  
<a name="cpconperformingculture-insensitivestringoperationsincollectionsanchor1"></a>   
## <a name="using-the-sortedlist-class"></a><span data-ttu-id="a7807-127">使用 SortedList 类</span><span class="sxs-lookup"><span data-stu-id="a7807-127">Using the SortedList Class</span></span>  
 <span data-ttu-id="a7807-128">`SortedList` 表示键值对的集合，这些键值对按键排序，并可按照键和索引进行访问。</span><span class="sxs-lookup"><span data-stu-id="a7807-128">A `SortedList` represents a collection of key-and-value pairs that are sorted by the keys and are accessible by key and by index.</span></span> <span data-ttu-id="a7807-129">在使用以字符串作为键的 `SortedList` 时，排序和查找会受 `Thread.CurrentCulture` 属性的影响。</span><span class="sxs-lookup"><span data-stu-id="a7807-129">When you use a `SortedList` where strings are the keys, the sorting and lookup can be affected by the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="a7807-130">若要从 `SortedList` 获取不区分区域性的行为，请使用一个接受 `comparer` 参数的构造函数来创建 `SortedList`。</span><span class="sxs-lookup"><span data-stu-id="a7807-130">To obtain culture-insensitive behavior from a `SortedList`, create a `SortedList` using one of the constructors that accepts a `comparer` parameter.</span></span> <span data-ttu-id="a7807-131">`comparer`参数指定<xref:System.Collections.IComparer>实现对键进行比较时使用。</span><span class="sxs-lookup"><span data-stu-id="a7807-131">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing keys.</span></span> <span data-ttu-id="a7807-132">对于该参数，请指定使用 `CultureInfo.InvariantCulture` 来比较键的自定义比较器类。</span><span class="sxs-lookup"><span data-stu-id="a7807-132">For the parameter, specify a custom comparer class that uses `CultureInfo.InvariantCulture` to compare keys.</span></span> <span data-ttu-id="a7807-133">下面的示例说明一个不区分区域性的自定义比较器类，可将该比较器类指定为 `SortedList` 构造函数的 `comparer` 参数。</span><span class="sxs-lookup"><span data-stu-id="a7807-133">The following example illustrates a custom culture-insensitive comparer class that you can specify as the `comparer` parameter to a `SortedList` constructor.</span></span>  
  
```vb  
Imports System  
Imports System.Collections  
Imports System.Globalization  
  
Friend Class InvariantComparer  
    Implements IComparer   
    Private m_compareInfo As CompareInfo  
    Friend Shared [Default] As New InvariantComparer()  
  
    Friend Sub New()  
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo  
    End Sub     
  
    Public Function Compare(a As Object, b As Object) As Integer _  
            Implements IComparer.Compare  
        Dim sa As String = CType(a, String)  
        Dim sb As String = CType(b, String)  
        If Not (sa Is Nothing) And Not (sb Is Nothing) Then  
            Return m_compareInfo.Compare(sa, sb)  
        Else  
            Return Comparer.Default.Compare(a, b)  
        End If  
    End Function  
End Class  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Globalization;  
  
internal class InvariantComparer : IComparer   
{  
    private CompareInfo m_compareInfo;  
    internal static readonly InvariantComparer Default = new  
        InvariantComparer();  
  
    internal InvariantComparer()   
    {  
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo;  
    }  
  
    public int Compare(Object a, Object b)  
    {  
        String sa = a as String;  
        String sb = b as String;  
        if (sa != null && sb != null)  
            return m_compareInfo.Compare(sa, sb);  
        else  
            return Comparer.Default.Compare(a,b);  
    }  
}  
```  
  
 <span data-ttu-id="a7807-134">一般而言，如果对字符串使用 `SortedList` 而不指定自定义固定比较器，填充列表后，更改 `Thread.CurrentCulture` 会使列表失效。</span><span class="sxs-lookup"><span data-stu-id="a7807-134">In general, if you use a `SortedList` on strings without specifying a custom invariant comparer, a change to `Thread.CurrentCulture` after the list has been populated can invalidate the list.</span></span>  
  
## <a name="using-the-arraylistsort-method"></a><span data-ttu-id="a7807-135">使用 ArrayList.Sort 方法</span><span class="sxs-lookup"><span data-stu-id="a7807-135">Using the ArrayList.Sort Method</span></span>  
 <span data-ttu-id="a7807-136">默认情况下，`ArrayList.Sort` 方法的重载使用 `Thread.CurrentCulture` 属性来执行区分区域性的排序。</span><span class="sxs-lookup"><span data-stu-id="a7807-136">Overloads of the `ArrayList.Sort` method perform culture-sensitive sorts by default using the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="a7807-137">由于排序顺序不同，结果可能会因区域性而异。</span><span class="sxs-lookup"><span data-stu-id="a7807-137">Results can vary by culture due to different sort orders.</span></span> <span data-ttu-id="a7807-138">若要消除区分区域性的行为，请使用接受 `IComparer` 实现的此方法的重载。</span><span class="sxs-lookup"><span data-stu-id="a7807-138">To eliminate culture-sensitive behavior, use the overloads of this method that accept an `IComparer` implementation.</span></span> <span data-ttu-id="a7807-139">对于 `comparer` 参数，请指定使用 `CultureInfo.InvariantCulture` 的自定义固定比较器类。</span><span class="sxs-lookup"><span data-stu-id="a7807-139">For the `comparer` parameter, specify a custom invariant comparer class that uses `CultureInfo.InvariantCulture`.</span></span> <span data-ttu-id="a7807-140">[使用 SortedList 类](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1)主题中提供了自定义固定比较器类的示例。</span><span class="sxs-lookup"><span data-stu-id="a7807-140">An example of a custom invariant comparer class is provided in the [Using the SortedList Class](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7807-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7807-141">See Also</span></span>  
 <xref:System.Collections.CaseInsensitiveComparer>  
 <xref:System.Collections.CaseInsensitiveHashCodeProvider>  
 <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Collections.SortedList>  
 <xref:System.Collections.Hashtable>  
 <xref:System.Collections.IComparer>  
 [<span data-ttu-id="a7807-142">执行不区分区域性的字符串操作</span><span class="sxs-lookup"><span data-stu-id="a7807-142">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)  
 <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType>

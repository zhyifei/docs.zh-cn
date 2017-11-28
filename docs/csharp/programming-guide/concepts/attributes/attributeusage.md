---
title: AttributeUsage (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 22c45568-9a6a-4c2f-8480-f38c1caa0a99
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 81e7440279a2d7dfa801394ee0e9af6181da3c13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="attributeusage-c"></a><span data-ttu-id="37856-102">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="37856-102">AttributeUsage (C#)</span></span>
<span data-ttu-id="37856-103">确定如何使用自定义特性类。</span><span class="sxs-lookup"><span data-stu-id="37856-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="37856-104">`AttributeUsage` 是一个特性，可应用于自定义特性定义，以控制如何应用新特性。</span><span class="sxs-lookup"><span data-stu-id="37856-104">`AttributeUsage` is an attribute that can be applied to custom attribute definitions to control how the new attribute can be applied.</span></span> <span data-ttu-id="37856-105">在显式应用时的默认设置如下：</span><span class="sxs-lookup"><span data-stu-id="37856-105">The default settings look like this when applied explicitly:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All,  
                   AllowMultiple = false,  
                   Inherited = true)]  
class NewAttribute : System.Attribute { }  
```  
  
 <span data-ttu-id="37856-106">在此示例中，`NewAttribute` 类可应用于任何特性的代码实体，但只能对每个实体应用一次。</span><span class="sxs-lookup"><span data-stu-id="37856-106">In this example, the `NewAttribute` class can be applied to any attribute-able code entity, but can be applied only once to each entity.</span></span> <span data-ttu-id="37856-107">当应用于基类时，它由派生类继承。</span><span class="sxs-lookup"><span data-stu-id="37856-107">It is inherited by derived classes when applied to a base class.</span></span>  
  
 <span data-ttu-id="37856-108">`AllowMultiple` 和 `Inherited` 参数是可选的，因而此代码具有相同的效果：</span><span class="sxs-lookup"><span data-stu-id="37856-108">The `AllowMultiple` and `Inherited` arguments are optional, so this code has the same effect:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All)]  
class NewAttribute : System.Attribute { }  
```  
  
 <span data-ttu-id="37856-109">第一个 `AttributeUsage` 参数必须是 <xref:System.AttributeTargets> 枚举的一个或多个元素。</span><span class="sxs-lookup"><span data-stu-id="37856-109">The first `AttributeUsage` argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="37856-110">可将多个目标类型与 OR 运算符链接在一起，如下所示：</span><span class="sxs-lookup"><span data-stu-id="37856-110">Multiple target types can be linked together with the OR operator, like this:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Property | AttributeTargets.Field)]  
class NewPropertyOrFieldAttribute : Attribute { }  
```  
  
 <span data-ttu-id="37856-111">如果 `AllowMultiple` 参数设置为 `true`，则结果特性可多次应用于单个实体，如下所示：</span><span class="sxs-lookup"><span data-stu-id="37856-111">If the `AllowMultiple` argument is set to `true`, then the resulting attribute can be applied more than once to a single entity, like this:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]  
class MultiUseAttr : Attribute { }  
  
[MultiUseAttr]  
[MultiUseAttr]  
class Class1 { }  
  
[MultiUseAttr, MultiUseAttr]  
class Class2 { }  
```  
  
 <span data-ttu-id="37856-112">在本例中，`MultiUseAttr` 可重复应用，因为 `AllowMultiple` 设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="37856-112">In this case `MultiUseAttr` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="37856-113">所显示的两种用于应用多个特性的格式均有效。</span><span class="sxs-lookup"><span data-stu-id="37856-113">Both formats shown for applying multiple attributes are valid.</span></span>  
  
 <span data-ttu-id="37856-114">如果 `Inherited` 设置为 `false`，那么特性不会由派生自已特性化的类的类继承。</span><span class="sxs-lookup"><span data-stu-id="37856-114">If `Inherited` is set to `false`, then the attribute is not inherited by classes that are derived from a class that is attributed.</span></span> <span data-ttu-id="37856-115">例如: </span><span class="sxs-lookup"><span data-stu-id="37856-115">For example:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, Inherited = false)]  
class Attr1 : Attribute { }  
  
[Attr1]  
class BClass { }  
  
class DClass : BClass { }  
```  
  
 <span data-ttu-id="37856-116">在本例中，`Attr1` 不会通过继承应用于 `DClass`。</span><span class="sxs-lookup"><span data-stu-id="37856-116">In this case `Attr1` is not applied to `DClass` via inheritance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37856-117">备注</span><span class="sxs-lookup"><span data-stu-id="37856-117">Remarks</span></span>  
 <span data-ttu-id="37856-118">`AttributeUsage` 特性是单次使用的特性 -- 它无法应用于同一个类超过一次。</span><span class="sxs-lookup"><span data-stu-id="37856-118">The `AttributeUsage` attribute is a single-use attribute--it cannot be applied more than once to the same class.</span></span> <span data-ttu-id="37856-119">`AttributeUsage` 是 <xref:System.AttributeUsageAttribute> 的别名。</span><span class="sxs-lookup"><span data-stu-id="37856-119">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="37856-120">有关详细信息，请参阅[使用反射访问特性 (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)。</span><span class="sxs-lookup"><span data-stu-id="37856-120">For more information, see [Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37856-121">示例</span><span class="sxs-lookup"><span data-stu-id="37856-121">Example</span></span>  
 <span data-ttu-id="37856-122">以下示例演示 `Inherited` 和 `AllowMultiple` 参数对 `AttributeUsage` 特性的影响，以及如何枚举应用于类的自定义特性。</span><span class="sxs-lookup"><span data-stu-id="37856-122">The following example demonstrates the effect of the `Inherited` and `AllowMultiple` arguments to the `AttributeUsage` attribute, and how the custom attributes applied to a class can be enumerated.</span></span>  
  
```csharp  
using System;  

// Create some custom attributes:  
[AttributeUsage(System.AttributeTargets.Class, Inherited = false)]  
class A1 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class)]  
class A2 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class, AllowMultiple = true)]  
class A3 : System.Attribute { }  
  
// Apply custom attributes to classes:  
[A1, A2]  
class BaseClass { }  
  
[A3, A3]  
class DerivedClass : BaseClass { }  
  
public class TestAttributeUsage  
{  
    static void Main()  
    {  
        BaseClass b = new BaseClass();  
        DerivedClass d = new DerivedClass();  
  
        // Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:");  
        object[] attrs = b.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
  
        Console.WriteLine("Attributes on Derived Class:");  
        attrs = d.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
    }  
}  
```  
  
## <a name="sample-output"></a><span data-ttu-id="37856-123">示例输出</span><span class="sxs-lookup"><span data-stu-id="37856-123">Sample Output</span></span>  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a><span data-ttu-id="37856-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37856-124">See Also</span></span>  
 <xref:System.Attribute>  
 <xref:System.Reflection>  
 [<span data-ttu-id="37856-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="37856-125">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="37856-126">特性</span><span class="sxs-lookup"><span data-stu-id="37856-126">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)  
 [<span data-ttu-id="37856-127">反射 (C#)</span><span class="sxs-lookup"><span data-stu-id="37856-127">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="37856-128">特性</span><span class="sxs-lookup"><span data-stu-id="37856-128">Attributes</span></span>](../../../../csharp/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="37856-129">创建自定义特性 (C#)</span><span class="sxs-lookup"><span data-stu-id="37856-129">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="37856-130">使用反射访问特性 (C#)</span><span class="sxs-lookup"><span data-stu-id="37856-130">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)

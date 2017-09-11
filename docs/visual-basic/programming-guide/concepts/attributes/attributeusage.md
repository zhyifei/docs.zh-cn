---
title: "AttributeUsage (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c91f2686a03d2590e1aaf166d27c49744bb13c9b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="attributeusage-visual-basic"></a><span data-ttu-id="a4746-102">AttributeUsage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4746-102">AttributeUsage (Visual Basic)</span></span>
<span data-ttu-id="a4746-103">确定如何使用自定义特性类。</span><span class="sxs-lookup"><span data-stu-id="a4746-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="a4746-104">`AttributeUsage`是可以应用于自定义特性定义来控制如何将应用新的属性的属性。</span><span class="sxs-lookup"><span data-stu-id="a4746-104">`AttributeUsage` is an attribute that can be applied to custom attribute definitions to control how the new attribute can be applied.</span></span> <span data-ttu-id="a4746-105">当显式应用默认设置如下所示︰</span><span class="sxs-lookup"><span data-stu-id="a4746-105">The default settings look like this when applied explicitly:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All,   
                   AllowMultiple:=False,   
                   Inherited:=True)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 <span data-ttu-id="a4746-106">在此示例中，`NewAttribute`类可以是应用于任何特性的代码的实体，但可以一次只能应用于每个实体。</span><span class="sxs-lookup"><span data-stu-id="a4746-106">In this example, the `NewAttribute` class can be applied to any attribute-able code entity, but can be applied only once to each entity.</span></span> <span data-ttu-id="a4746-107">它由派生类时应用于基类继承。</span><span class="sxs-lookup"><span data-stu-id="a4746-107">It is inherited by derived classes when applied to a base class.</span></span>  
  
 <span data-ttu-id="a4746-108">`AllowMultiple`和`Inherited`参数是可选的所以此代码具有相同的效果︰</span><span class="sxs-lookup"><span data-stu-id="a4746-108">The `AllowMultiple` and `Inherited` arguments are optional, so this code has the same effect:</span></span>  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 <span data-ttu-id="a4746-109">第一个`AttributeUsage`参数必须是一个或多个元素的<xref:System.AttributeTargets>枚举。</xref:System.AttributeTargets></span><span class="sxs-lookup"><span data-stu-id="a4746-109">The first `AttributeUsage` argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="a4746-110">多个目标类型可以被链接在一起的或运算符如下︰</span><span class="sxs-lookup"><span data-stu-id="a4746-110">Multiple target types can be linked together with the OR operator, like this:</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>   
Class NewPropertyOrFieldAttribute  
    Inherits Attribute  
End Class  
```  
  
 <span data-ttu-id="a4746-111">如果`AllowMultiple`参数设置为`true`，则生成的属性可以多次应用于单个实体，如下︰</span><span class="sxs-lookup"><span data-stu-id="a4746-111">If the `AllowMultiple` argument is set to `true`, then the resulting attribute can be applied more than once to a single entity, like this:</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=True)>   
Class MultiUseAttr  
    Inherits Attribute  
End Class  
  
<MultiUseAttr(), MultiUseAttr()>   
Class Class1  
End Class  
```  
  
 <span data-ttu-id="a4746-112">在这种情况下`MultiUseAttr`可以重复应用，因为`AllowMultiple`设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="a4746-112">In this case `MultiUseAttr` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="a4746-113">这两种格式所示的应用多个属性均有效。</span><span class="sxs-lookup"><span data-stu-id="a4746-113">Both formats shown for applying multiple attributes are valid.</span></span>  
  
 <span data-ttu-id="a4746-114">如果`Inherited`设置为`false`，则该属性不会由从特性化的类派生的类继承。</span><span class="sxs-lookup"><span data-stu-id="a4746-114">If `Inherited` is set to `false`, then the attribute is not inherited by classes that are derived from a class that is attributed.</span></span> <span data-ttu-id="a4746-115">例如: </span><span class="sxs-lookup"><span data-stu-id="a4746-115">For example:</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, Inherited:=False)>   
Class Attr1  
    Inherits Attribute  
End Class  
  
<Attr1()>   
Class BClass  
  
End Class    
  
Class DClass  
    Inherits BClass  
End Class  
```  
  
 <span data-ttu-id="a4746-116">在这种情况下`Attr1`不应用于`DClass`通过继承。</span><span class="sxs-lookup"><span data-stu-id="a4746-116">In this case `Attr1` is not applied to `DClass` via inheritance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4746-117">备注</span><span class="sxs-lookup"><span data-stu-id="a4746-117">Remarks</span></span>  
 <span data-ttu-id="a4746-118">`AttributeUsage`属性是一个单用途属性 — 不能为同一个类不止一次应用。</span><span class="sxs-lookup"><span data-stu-id="a4746-118">The `AttributeUsage` attribute is a single-use attribute--it cannot be applied more than once to the same class.</span></span> <span data-ttu-id="a4746-119">`AttributeUsage`是<xref:System.AttributeUsageAttribute>。</xref:System.AttributeUsageAttribute>的别名</span><span class="sxs-lookup"><span data-stu-id="a4746-119">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="a4746-120">有关详细信息，请参阅[访问通过使用反射 (Visual Basic 中) 的属性](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)。</span><span class="sxs-lookup"><span data-stu-id="a4746-120">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4746-121">示例</span><span class="sxs-lookup"><span data-stu-id="a4746-121">Example</span></span>  
 <span data-ttu-id="a4746-122">下面的示例演示的效果`Inherited`和`AllowMultiple`参数`AttributeUsage`属性和要如何枚举应用于类的自定义特性。</span><span class="sxs-lookup"><span data-stu-id="a4746-122">The following example demonstrates the effect of the `Inherited` and `AllowMultiple` arguments to the `AttributeUsage` attribute, and how the custom attributes applied to a class can be enumerated.</span></span>  
  
```vb  
Imports System  
```  
  
```vb  
' Create some custom attributes:  
<AttributeUsage(System.AttributeTargets.Class, Inherited:=False)>   
Class A1  
    Inherits System.Attribute  
End Class  
  
<AttributeUsage(System.AttributeTargets.Class)>   
Class A2  
    Inherits System.Attribute  
End Class      
  
<AttributeUsage(System.AttributeTargets.Class, AllowMultiple:=True)>   
Class A3  
    Inherits System.Attribute  
End Class  
  
' Apply custom attributes to classes:  
<A1(), A2()>   
Class BaseClass  
  
End Class  
  
<A3(), A3()>   
Class DerivedClass  
    Inherits BaseClass  
End Class  
  
Public Class TestAttributeUsage  
    Sub Main()  
        Dim b As New BaseClass  
        Dim d As New DerivedClass  
        ' Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:")  
        Dim attrs() As Object = b.GetType().GetCustomAttributes(True)  
  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next  
  
        Console.WriteLine("Attributes on Derived Class:")  
        attrs = d.GetType().GetCustomAttributes(True)  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next              
    End Sub  
End Class  
```  
  
## <a name="sample-output"></a><span data-ttu-id="a4746-123">示例输出</span><span class="sxs-lookup"><span data-stu-id="a4746-123">Sample Output</span></span>  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4746-124">请参见</span><span class="sxs-lookup"><span data-stu-id="a4746-124">See Also</span></span>  
 <span data-ttu-id="a4746-125"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="a4746-125"><xref:System.Attribute></span></span>   
 <span data-ttu-id="a4746-126"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="a4746-126"><xref:System.Reflection></span></span>   
<span data-ttu-id="a4746-127"> [Visual Basic 编程指南](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a4746-127"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="a4746-128"> [属性](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="a4746-128"> [Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
<span data-ttu-id="a4746-129"> [反射 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="a4746-129"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="a4746-130"> [特性 (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span><span class="sxs-lookup"><span data-stu-id="a4746-130"> [Attributes (Visual Basic)](../../../../visual-basic/language-reference/attributes.md) </span></span>  
<span data-ttu-id="a4746-131"> [创建自定义特性 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="a4746-131"> [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) </span></span>  
<span data-ttu-id="a4746-132"> [使用反射 (Visual Basic 中) 访问特性](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="a4746-132"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>

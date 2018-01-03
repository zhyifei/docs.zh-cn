---
title: "如何： 创建 C-c + + 联合使用属性 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 51d04c573e91a351c48edefebdb3d32fce1d306f
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a><span data-ttu-id="b1392-102">如何： 创建 C/c + + 联合使用属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1392-102">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>
<span data-ttu-id="b1392-103">通过使用特性，可自定义结构在内存中的布局方式。</span><span class="sxs-lookup"><span data-stu-id="b1392-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="b1392-104">例如，可使用 `StructLayout(LayoutKind.Explicit)` 和 `FieldOffset` 特性在 C/C++ 中创建所谓的联合。</span><span class="sxs-lookup"><span data-stu-id="b1392-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1392-105">示例</span><span class="sxs-lookup"><span data-stu-id="b1392-105">Example</span></span>  
 <span data-ttu-id="b1392-106">在此代码段中，`TestUnion` 的所有字段均从内存中的同一位置开始。</span><span class="sxs-lookup"><span data-stu-id="b1392-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
<System.Runtime.InteropServices.StructLayout(   
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestUnion  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public i As Integer  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public d As Double  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public c As Char  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public b As Byte  
End Structure  
```  
  
## <a name="example"></a><span data-ttu-id="b1392-107">示例</span><span class="sxs-lookup"><span data-stu-id="b1392-107">Example</span></span>  
 <span data-ttu-id="b1392-108">下面是另一个示例，其中的字段从不同的显式设置位置开始。</span><span class="sxs-lookup"><span data-stu-id="b1392-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
 <System.Runtime.InteropServices.StructLayout(  
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestExplicit  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public lg As Long  
  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public i1 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(4)>   
     Public i2 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(8)>   
     Public d As Double  
  
     <System.Runtime.InteropServices.FieldOffset(12)>   
     Public c As Char  
  
     <System.Runtime.InteropServices.FieldOffset(14)>   
     Public b As Byte  
 End Structure  
```  
  
 <span data-ttu-id="b1392-109">两个整数字段 `i1` 和 `i2` 共享与 `lg` 相同的内存位置。</span><span class="sxs-lookup"><span data-stu-id="b1392-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="b1392-110">使用平台调用时，这种对结构布局的控制很有用。</span><span class="sxs-lookup"><span data-stu-id="b1392-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1392-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1392-111">See Also</span></span>  
 <xref:System.Reflection>  
 <xref:System.Attribute>  
 [<span data-ttu-id="b1392-112">Visual Basic 编程指南</span><span class="sxs-lookup"><span data-stu-id="b1392-112">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)  
 [<span data-ttu-id="b1392-113">特性</span><span class="sxs-lookup"><span data-stu-id="b1392-113">Attributes</span></span>](../../../../standard/attributes/index.md)  
 [<span data-ttu-id="b1392-114">反射 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1392-114">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="b1392-115">属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1392-115">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)  
 [<span data-ttu-id="b1392-116">创建自定义特性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1392-116">Creating Custom Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="b1392-117">使用反射访问特性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1392-117">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)

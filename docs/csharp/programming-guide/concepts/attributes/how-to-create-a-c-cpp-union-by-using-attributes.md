---
title: "如何：使用特性创建 C-C++ 联合 (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e9274b585c2fecf53b94d94f9bdfdaf4a47f1041
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a><span data-ttu-id="651c7-102">如何：使用特性创建 C/C++ 联合 (C#)</span><span class="sxs-lookup"><span data-stu-id="651c7-102">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>
<span data-ttu-id="651c7-103">通过使用特性，可自定义结构在内存中的布局方式。</span><span class="sxs-lookup"><span data-stu-id="651c7-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="651c7-104">例如，可使用 `StructLayout(LayoutKind.Explicit)` 和 `FieldOffset` 特性在 C/C++ 中创建所谓的联合。</span><span class="sxs-lookup"><span data-stu-id="651c7-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="651c7-105">示例</span><span class="sxs-lookup"><span data-stu-id="651c7-105">Example</span></span>  
 <span data-ttu-id="651c7-106">在此代码段中，`TestUnion` 的所有字段均从内存中的同一位置开始。</span><span class="sxs-lookup"><span data-stu-id="651c7-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestUnion  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public byte b;  
       }  
```  
  
## <a name="example"></a><span data-ttu-id="651c7-107">示例</span><span class="sxs-lookup"><span data-stu-id="651c7-107">Example</span></span>  
 <span data-ttu-id="651c7-108">下面是另一个示例，其中的字段从不同的显式设置位置开始。</span><span class="sxs-lookup"><span data-stu-id="651c7-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestExplicit  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public long lg;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i1;  
  
           [System.Runtime.InteropServices.FieldOffset(4)]  
           public int i2;  
  
           [System.Runtime.InteropServices.FieldOffset(8)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(12)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(14)]  
           public byte b;  
       }  
```  
  
 <span data-ttu-id="651c7-109">两个整数字段 `i1` 和 `i2` 共享与 `lg` 相同的内存位置。</span><span class="sxs-lookup"><span data-stu-id="651c7-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="651c7-110">使用平台调用时，这种对结构布局的控制很有用。</span><span class="sxs-lookup"><span data-stu-id="651c7-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="651c7-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="651c7-111">See Also</span></span>  
 <xref:System.Reflection>  
 <xref:System.Attribute>  
 [<span data-ttu-id="651c7-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="651c7-112">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="651c7-113">特性</span><span class="sxs-lookup"><span data-stu-id="651c7-113">Attributes</span></span>](../../../../../docs/standard/attributes/index.md)  
 [<span data-ttu-id="651c7-114">反射 (C#)</span><span class="sxs-lookup"><span data-stu-id="651c7-114">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="651c7-115">特性 (C#)</span><span class="sxs-lookup"><span data-stu-id="651c7-115">Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="651c7-116">创建自定义特性 (C#)</span><span class="sxs-lookup"><span data-stu-id="651c7-116">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="651c7-117">使用反射访问特性 (C#)</span><span class="sxs-lookup"><span data-stu-id="651c7-117">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)

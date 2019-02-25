---
title: 编译器警告 CS3024
ms.date: 07/20/2015
f1_keywords:
- CS3024
helpviewer_keywords:
- CS3024
ms.assetid: fef9db31-9a7f-42d5-ad37-3e7faf661f95
ms.openlocfilehash: e49c131328f132ae6372167818d084df51ef6c78
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "56797352"
---
# <a name="compiler-warning-cs3024"></a><span data-ttu-id="4d64b-102">编译器警告 CS3024</span><span class="sxs-lookup"><span data-stu-id="4d64b-102">Compiler Warning CS3024</span></span>
<span data-ttu-id="4d64b-103">约束类型“'type”不符合 CLS。</span><span class="sxs-lookup"><span data-stu-id="4d64b-103">Constraint type 'type' is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="4d64b-104">编译器发出此警告是因为：将不符合 CLS 的类型用作泛型类型约束会导致用某些语言编写的代码无法使用泛型类。</span><span class="sxs-lookup"><span data-stu-id="4d64b-104">The compiler issues this warning because the use of a non-CLS-compliant type as a generic type constraint could make it impossible for code written in some languages to consume your generic class.</span></span>  
  
### <a name="to-eliminate-this-warning"></a><span data-ttu-id="4d64b-105">消除此警告</span><span class="sxs-lookup"><span data-stu-id="4d64b-105">To eliminate this warning</span></span>  
  
1.  <span data-ttu-id="4d64b-106">对类型约束使用符合 CLS 的类型。</span><span class="sxs-lookup"><span data-stu-id="4d64b-106">Use a CLS-compliant type for the type constraint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d64b-107">示例</span><span class="sxs-lookup"><span data-stu-id="4d64b-107">Example</span></span>  
 <span data-ttu-id="4d64b-108">下面的示例在几个位置生成 CS3024：</span><span class="sxs-lookup"><span data-stu-id="4d64b-108">The following example generates CS3024 in several locations:</span></span>  
  
```csharp  
// cs3024.cs  
// Compile with: /target:library  
 [assembly: System.CLSCompliant(true)]  
  
[type: System.CLSCompliant(false)]  
public class TestClass // CS3024  
{  
    public ushort us;  
}  
[type: System.CLSCompliant(false)]  
public interface ITest // CS3024  
{}  
public interface I<T> where T : TestClass  
{}  
public class TestClass_2<T> where T : ITest  
{}  
public class TestClass_3<T> : I<T> where T : TestClass  
{}  
public class TestClass_4<T> : TestClass_2<T> where T : ITest  
{}  
public class Test  
{  
    public static int Main()  
    {  
        return 0;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d64b-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d64b-109">See also</span></span>

- [<span data-ttu-id="4d64b-110">类型参数的约束</span><span class="sxs-lookup"><span data-stu-id="4d64b-110">Constraints on Type Parameters</span></span>](../../csharp/programming-guide/generics/constraints-on-type-parameters.md)

---
title: 后期绑定重载决策不能应用于“<procedurename>”，因为访问实例是一个接口类型
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: 7215be3f454f4a799124620fb5db520282988035
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272626"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="14ef0-102">后期绑定重载决策不能应用于\<过程名称 > 因为访问实例是一个接口类型</span><span class="sxs-lookup"><span data-stu-id="14ef0-102">Latebound overload resolution cannot be applied to '\<procedurename>' because the accessing instance is an interface type</span></span>
<span data-ttu-id="14ef0-103">编译器尝试解析对重载的属性或过程中，但引用失败，因为参数的类型`Object`和引用对象具有一个接口的数据类型。</span><span class="sxs-lookup"><span data-stu-id="14ef0-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="14ef0-104">`Object`参数强制编译器将引用解析为后期绑定。</span><span class="sxs-lookup"><span data-stu-id="14ef0-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>  
  
 <span data-ttu-id="14ef0-105">在这些情况下，编译器将通过实现类而不是通过基础接口的重载解析。</span><span class="sxs-lookup"><span data-stu-id="14ef0-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="14ef0-106">如果类重命名其中一个重载版本，则编译器将不考虑该版本是重载方法，因为其名称不同。</span><span class="sxs-lookup"><span data-stu-id="14ef0-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="14ef0-107">这反过来会导致编译器忽略重命名的版本时可能已正确的选择来解析引用。</span><span class="sxs-lookup"><span data-stu-id="14ef0-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>  
  
 <span data-ttu-id="14ef0-108">**错误 ID:** BC30933</span><span class="sxs-lookup"><span data-stu-id="14ef0-108">**Error ID:** BC30933</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="14ef0-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="14ef0-109">To correct this error</span></span>  
  
-   <span data-ttu-id="14ef0-110">使用`CType`强制转换的参数从`Object`到你想要调用的重载的签名由指定的类型。</span><span class="sxs-lookup"><span data-stu-id="14ef0-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>  
  
     <span data-ttu-id="14ef0-111">请注意，它无法帮助转换到基础接口的引用对象。</span><span class="sxs-lookup"><span data-stu-id="14ef0-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="14ef0-112">您必须强制转换来避免此错误的参数。</span><span class="sxs-lookup"><span data-stu-id="14ef0-112">You must cast the argument to avoid this error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14ef0-113">示例</span><span class="sxs-lookup"><span data-stu-id="14ef0-113">Example</span></span>  
 <span data-ttu-id="14ef0-114">下面的示例演示如何调用一个已重载的`Sub`会在编译时导致此错误的过程。</span><span class="sxs-lookup"><span data-stu-id="14ef0-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>  
  
```  
Module m1  
    Interface i1  
        Sub s1(ByVal p1 As Integer)  
        Sub s1(ByVal p1 As Double)  
    End Interface  
    Class c1  
        Implements i1  
        Public Overloads Sub s1(ByVal p1 As Integer) Implements i1.s1  
        End Sub  
        Public Overloads Sub s2(ByVal p1 As Double) Implements i1.s1  
        End Sub  
    End Class  
    Sub Main()  
        Dim refer As i1 = New c1  
        Dim o1 As Object = 3.1415  
        ' The following reference is INVALID and causes a compiler error.  
        refer.s1(o1)   
    End Sub  
End Module  
```  
  
 <span data-ttu-id="14ef0-115">在前面的示例中，如果编译器允许在调用`s1`分辨率一样编写的将会通过类发生`c1`而不是接口`i1`。</span><span class="sxs-lookup"><span data-stu-id="14ef0-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="14ef0-116">这就意味着编译器不会考虑`s2`因为其名称为在不同`c1`，即使它是正确的选择，因为由定义`i1`。</span><span class="sxs-lookup"><span data-stu-id="14ef0-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>  
  
 <span data-ttu-id="14ef0-117">可以通过更改为以下代码行的任何一调用来纠正此错误：</span><span class="sxs-lookup"><span data-stu-id="14ef0-117">You can correct the error by changing the call to either of the following lines of code:</span></span>  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 <span data-ttu-id="14ef0-118">每个前面几行代码显式强制转换`Object`变量`o1`的重载定义的参数类型之一。</span><span class="sxs-lookup"><span data-stu-id="14ef0-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14ef0-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="14ef0-119">See also</span></span>
- [<span data-ttu-id="14ef0-120">过程重载</span><span class="sxs-lookup"><span data-stu-id="14ef0-120">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="14ef0-121">重载决策</span><span class="sxs-lookup"><span data-stu-id="14ef0-121">Overload Resolution</span></span>](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)
- [<span data-ttu-id="14ef0-122">CType 函数</span><span class="sxs-lookup"><span data-stu-id="14ef0-122">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)

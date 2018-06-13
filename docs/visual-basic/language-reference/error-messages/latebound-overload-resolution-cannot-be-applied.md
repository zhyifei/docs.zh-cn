---
title: 后期绑定重载解决方法不能应用于&#39;&lt;过程名称&gt;&#39;因为访问实例是一个接口类型
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: e41cbf30f06547ef39553e31542e4e8b6df49a3b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589875"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-39ltprocedurenamegt39-because-the-accessing-instance-is-an-interface-type"></a><span data-ttu-id="e0e1b-102">后期绑定重载解决方法不能应用于&#39;&lt;过程名称&gt;&#39;因为访问实例是一个接口类型</span><span class="sxs-lookup"><span data-stu-id="e0e1b-102">Latebound overload resolution cannot be applied to &#39;&lt;procedurename&gt;&#39; because the accessing instance is an interface type</span></span>
<span data-ttu-id="e0e1b-103">编译器正在尝试解析的引用的重载的属性或过程，但引用失败，因为自变量的类型`Object`和引用的对象具有接口的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e0e1b-103">The compiler is attempting to resolve a reference to an overloaded property or procedure, but the reference fails because an argument is of type `Object` and the referring object has the data type of an interface.</span></span> <span data-ttu-id="e0e1b-104">`Object`参数强制编译器将引用解析为后期绑定。</span><span class="sxs-lookup"><span data-stu-id="e0e1b-104">The `Object` argument forces the compiler to resolve the reference as late-bound.</span></span>  
  
 <span data-ttu-id="e0e1b-105">在这些情况下，编译器将解析通过实现类而不是通过基础接口的重载。</span><span class="sxs-lookup"><span data-stu-id="e0e1b-105">In these circumstances, the compiler resolves the overload through the implementing class instead of through the underlying interface.</span></span> <span data-ttu-id="e0e1b-106">如果类重命名其中一个重载版本，则编译器不考虑该版本为重载，因为其名称不同。</span><span class="sxs-lookup"><span data-stu-id="e0e1b-106">If the class renames one of the overloaded versions, the compiler does not consider that version to be an overload because its name is different.</span></span> <span data-ttu-id="e0e1b-107">这反过来会使编译器忽略重命名的版本时可能已正确的选择来解析引用。</span><span class="sxs-lookup"><span data-stu-id="e0e1b-107">This in turn causes the compiler to ignore the renamed version when it might have been the correct choice to resolve the reference.</span></span>  
  
 <span data-ttu-id="e0e1b-108">**错误 ID:** BC30933</span><span class="sxs-lookup"><span data-stu-id="e0e1b-108">**Error ID:** BC30933</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e0e1b-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="e0e1b-109">To correct this error</span></span>  
  
-   <span data-ttu-id="e0e1b-110">使用`CType`转换从参数`Object`到你想要调用的重载的签名由指定的类型。</span><span class="sxs-lookup"><span data-stu-id="e0e1b-110">Use `CType` to cast the argument from `Object` to the type specified by the signature of the overload you want to call.</span></span>  
  
     <span data-ttu-id="e0e1b-111">请注意，它没有任何帮助引用将对象转换为基础的接口。</span><span class="sxs-lookup"><span data-stu-id="e0e1b-111">Note that it does not help to cast the referring object to the underlying interface.</span></span> <span data-ttu-id="e0e1b-112">您必须强制转换的自变量，若要避免此错误。</span><span class="sxs-lookup"><span data-stu-id="e0e1b-112">You must cast the argument to avoid this error.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0e1b-113">示例</span><span class="sxs-lookup"><span data-stu-id="e0e1b-113">Example</span></span>  
 <span data-ttu-id="e0e1b-114">下面的示例演示对重载的调用`Sub`会在编译时导致此错误的过程。</span><span class="sxs-lookup"><span data-stu-id="e0e1b-114">The following example shows a call to an overloaded `Sub` procedure that causes this error at compile time.</span></span>  
  
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
  
 <span data-ttu-id="e0e1b-115">在前面的示例中，如果编译器允许调用`s1`顾名思义，解析将通过类`c1`而不是接口`i1`。</span><span class="sxs-lookup"><span data-stu-id="e0e1b-115">In the preceding example, if the compiler allowed the call to `s1` as written, the resolution would take place through the class `c1` instead of the interface `i1`.</span></span> <span data-ttu-id="e0e1b-116">这就意味着编译器不会考虑`s2`因为其名称中不同`c1`，即使它是正确的选择，因为由定义`i1`。</span><span class="sxs-lookup"><span data-stu-id="e0e1b-116">This would mean that the compiler would not consider `s2` because its name is different in `c1`, even though it is the correct choice as defined by `i1`.</span></span>  
  
 <span data-ttu-id="e0e1b-117">可以通过更改为以下代码行的任何一调用来更正该错误：</span><span class="sxs-lookup"><span data-stu-id="e0e1b-117">You can correct the error by changing the call to either of the following lines of code:</span></span>  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 <span data-ttu-id="e0e1b-118">每个前面几行代码显式强制转换`Object`变量`o1`为重载定义的参数类型之一。</span><span class="sxs-lookup"><span data-stu-id="e0e1b-118">Each of the preceding lines of code explicitly casts the `Object` variable `o1` to one of the parameter types defined for the overloads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e1b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0e1b-119">See Also</span></span>  
 [<span data-ttu-id="e0e1b-120">过程重载</span><span class="sxs-lookup"><span data-stu-id="e0e1b-120">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [<span data-ttu-id="e0e1b-121">重载决策</span><span class="sxs-lookup"><span data-stu-id="e0e1b-121">Overload Resolution</span></span>](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)  
 [<span data-ttu-id="e0e1b-122">CType 函数</span><span class="sxs-lookup"><span data-stu-id="e0e1b-122">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)

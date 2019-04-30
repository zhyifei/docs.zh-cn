---
title: 无法推断出变量“<variablename>”的类型，因为它绑定到封闭范围中的某个字段
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: bcd142785d8ee736c6a1b41950fae80e4d26fa18
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013642"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="87bb3-102">变量的类型\<变量名 >' 绑定到封闭范围中的字段，因此将不会推断</span><span class="sxs-lookup"><span data-stu-id="87bb3-102">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope</span></span>
<span data-ttu-id="87bb3-103">变量的类型\<变量名 >' 绑定到封闭范围中的字段，因此将不会推断。</span><span class="sxs-lookup"><span data-stu-id="87bb3-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="87bb3-104">请更改名称\<变量名 >，或使用完全限定的名称 （例如，Me.variablename 或 MyBase.variablename）。</span><span class="sxs-lookup"><span data-stu-id="87bb3-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>  
  
 <span data-ttu-id="87bb3-105">在代码中的循环控制变量与类或其他封闭范围内的字段具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="87bb3-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="87bb3-106">因为控制变量用在无需`As`子句，它绑定到封闭范围中的字段和编译器不为其创建一个新的变量或推断出类型。</span><span class="sxs-lookup"><span data-stu-id="87bb3-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>  
  
 <span data-ttu-id="87bb3-107">在以下示例中，`Index`中的控制变量`For`语句中，绑定到`Index`字段中`Customer`类。</span><span class="sxs-lookup"><span data-stu-id="87bb3-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="87bb3-108">编译器不会创建新的变量控制变量`Index`或推断其类型。</span><span class="sxs-lookup"><span data-stu-id="87bb3-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="87bb3-109">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="87bb3-109">By default, this message is a warning.</span></span> <span data-ttu-id="87bb3-110">有关如何隐藏警告或如何将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="87bb3-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="87bb3-111">**错误 ID:** BC42110</span><span class="sxs-lookup"><span data-stu-id="87bb3-111">**Error ID:** BC42110</span></span>  
  
### <a name="to-address-this-warning"></a><span data-ttu-id="87bb3-112">解决此警告</span><span class="sxs-lookup"><span data-stu-id="87bb3-112">To address this warning</span></span>  
  
- <span data-ttu-id="87bb3-113">通过其名称更改为标识符，也不是类的字段的名称使本地循环控制变量。</span><span class="sxs-lookup"><span data-stu-id="87bb3-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>  
  
    ```  
    For I = 1 To 10  
    ```  
  
- <span data-ttu-id="87bb3-114">阐明循环控制变量绑定到类字段，通过前缀来`Me.`向变量名称。</span><span class="sxs-lookup"><span data-stu-id="87bb3-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
- <span data-ttu-id="87bb3-115">使用而不是依赖于本地类型推断，`As`子句来指定 for 循环控制变量的类型。</span><span class="sxs-lookup"><span data-stu-id="87bb3-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a><span data-ttu-id="87bb3-116">示例</span><span class="sxs-lookup"><span data-stu-id="87bb3-116">Example</span></span>  
 <span data-ttu-id="87bb3-117">下面的代码演示在位置中的第一个更正与前面的示例。</span><span class="sxs-lookup"><span data-stu-id="87bb3-117">The following code shows the earlier example with the first correction in place.</span></span>  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="87bb3-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="87bb3-118">See also</span></span>

- [<span data-ttu-id="87bb3-119">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="87bb3-119">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="87bb3-120">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="87bb3-120">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="87bb3-121">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="87bb3-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="87bb3-122">如何：引用对象的当前实例</span><span class="sxs-lookup"><span data-stu-id="87bb3-122">How to: Refer to the Current Instance of an Object</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="87bb3-123">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="87bb3-123">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="87bb3-124">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="87bb3-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)

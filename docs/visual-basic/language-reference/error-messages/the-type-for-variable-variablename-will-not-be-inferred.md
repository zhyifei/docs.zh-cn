---
title: 无法推断出变量“<variablename>”的类型，因为它绑定到封闭范围中的某个字段
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: e56529919945558df178e18a83a895a79bfe4919
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512727"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="783ea-102">不会推断变量 "\<variablename >" 的类型, 因为它绑定到封闭范围中的某个字段</span><span class="sxs-lookup"><span data-stu-id="783ea-102">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope</span></span>

<span data-ttu-id="783ea-103">不会推断变量 "\<variablename >" 的类型, 因为它绑定到封闭范围中的某个字段。</span><span class="sxs-lookup"><span data-stu-id="783ea-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="783ea-104">请更改 "\<variablename >" 的名称, 或使用完全限定的名称 (例如, "variablename" 或 "variablename")。</span><span class="sxs-lookup"><span data-stu-id="783ea-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>

<span data-ttu-id="783ea-105">代码中的循环控制变量与类的字段或其他封闭范围的名称相同。</span><span class="sxs-lookup"><span data-stu-id="783ea-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="783ea-106">因为在没有`As`子句的情况下使用控制变量, 它将绑定到封闭范围中的字段, 并且编译器不会为其创建新的变量, 也不会推断其类型。</span><span class="sxs-lookup"><span data-stu-id="783ea-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>

<span data-ttu-id="783ea-107">在`Index`下面的示例中, `For`语句中的控制变量绑定`Customer`到类中的`Index`字段。</span><span class="sxs-lookup"><span data-stu-id="783ea-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="783ea-108">编译器不会为控件变量`Index`创建新的变量, 也不会推断其类型。</span><span class="sxs-lookup"><span data-stu-id="783ea-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>

```vb
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

<span data-ttu-id="783ea-109">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="783ea-109">By default, this message is a warning.</span></span> <span data-ttu-id="783ea-110">有关如何隐藏警告或如何将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="783ea-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

<span data-ttu-id="783ea-111">**错误 ID:** BC42110</span><span class="sxs-lookup"><span data-stu-id="783ea-111">**Error ID:** BC42110</span></span>

### <a name="to-address-this-warning"></a><span data-ttu-id="783ea-112">解决此警告</span><span class="sxs-lookup"><span data-stu-id="783ea-112">To address this warning</span></span>

- <span data-ttu-id="783ea-113">将循环控制变量的名称更改为不属于类的字段名称的标识符, 使该循环控制变量成为局部变量。</span><span class="sxs-lookup"><span data-stu-id="783ea-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>

  ```vb
  For I = 1 To 10
  ```

- <span data-ttu-id="783ea-114">阐明循环控制变量是通过在变量名称的前面加上`Me.`前缀来绑定到类字段。</span><span class="sxs-lookup"><span data-stu-id="783ea-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>

  ```vb
  For Me.Index = 1 To 10
  ```

- <span data-ttu-id="783ea-115">使用`As`子句来指定循环控制变量的类型, 而不是依赖于局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="783ea-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>

  ```vb
  For Index As Integer = 1 To 10
  ```

## <a name="example"></a><span data-ttu-id="783ea-116">示例</span><span class="sxs-lookup"><span data-stu-id="783ea-116">Example</span></span>
 <span data-ttu-id="783ea-117">下面的代码显示了前面的示例, 其中的第一个更正是就地的。</span><span class="sxs-lookup"><span data-stu-id="783ea-117">The following code shows the earlier example with the first correction in place.</span></span>

```vb
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

## <a name="see-also"></a><span data-ttu-id="783ea-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="783ea-118">See also</span></span>

- [<span data-ttu-id="783ea-119">Option Infer 语句</span><span class="sxs-lookup"><span data-stu-id="783ea-119">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="783ea-120">For Each...Next 语句</span><span class="sxs-lookup"><span data-stu-id="783ea-120">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="783ea-121">For...Next 语句</span><span class="sxs-lookup"><span data-stu-id="783ea-121">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="783ea-122">如何：引用对象的当前实例</span><span class="sxs-lookup"><span data-stu-id="783ea-122">How to: Refer to the Current Instance of an Object</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="783ea-123">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="783ea-123">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="783ea-124">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="783ea-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)

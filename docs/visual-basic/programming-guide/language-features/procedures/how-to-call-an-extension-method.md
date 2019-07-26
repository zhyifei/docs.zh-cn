---
title: 如何：调用扩展方法 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: f2058162ab939d2619d7255c884d88c35ee63715
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512676"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="9e9f6-102">如何：调用扩展方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e9f6-102">How to: Call an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="9e9f6-103">扩展方法使你能够向现有类添加方法。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="9e9f6-104">在扩展方法被声明并引入作用域后, 可以像它所扩展的类型的实例方法一样调用它。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="9e9f6-105">有关如何编写扩展方法的详细信息, 请参阅[如何:编写扩展方法](./how-to-write-an-extension-method.md)。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>

 <span data-ttu-id="9e9f6-106">下面的说明引用 extension 方法, `PrintAndPunctuate`该方法将显示调用它的字符串实例, 然后在中为第二个`punc`参数发送任何值。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>

```vb
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub

End Module
```

<span data-ttu-id="9e9f6-107">调用方法时, 该方法必须在范围内。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-107">The method must be in scope when it is called.</span></span>

### <a name="to-call-an-extension-method"></a><span data-ttu-id="9e9f6-108">调用扩展方法</span><span class="sxs-lookup"><span data-stu-id="9e9f6-108">To call an extension method</span></span>

1. <span data-ttu-id="9e9f6-109">声明一个变量, 该变量的数据类型为扩展方法的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="9e9f6-110">对于`PrintAndPunctuate`, 需要一个<xref:System.String>变量:</span><span class="sxs-lookup"><span data-stu-id="9e9f6-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>

    ```vb
    Dim example = "Ready"
    ```

2. <span data-ttu-id="9e9f6-111">该变量将调用扩展方法, 并且其值绑定到第一个参数`aString`。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="9e9f6-112">将显示`Ready?`下面的调用语句。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-112">The following calling statement will display `Ready?`.</span></span>

    ```vb
    example.PrintAndPunctuate("?")
    ```

     <span data-ttu-id="9e9f6-113">请注意, 对此扩展方法的调用看起来就像调用需要一个参数的<xref:System.String>任何一个实例方法:</span><span class="sxs-lookup"><span data-stu-id="9e9f6-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>

    ```vb
    example.EndsWith("dy")
    example.IndexOf("R")
    ```

3. <span data-ttu-id="9e9f6-114">声明另一个字符串变量并再次调用方法, 以查看它是否适用于任何字符串。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-114">Declare another string variable and call the method again to see that it works with any string.</span></span>

    ```vb
    Dim example2 = " or not"
    example2.PrintAndPunctuate("!!!")
    ```

     <span data-ttu-id="9e9f6-115">此时间的结果为: `or not!!!`。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-115">The result this time is: `or not!!!`.</span></span>

## <a name="example"></a><span data-ttu-id="9e9f6-116">示例</span><span class="sxs-lookup"><span data-stu-id="9e9f6-116">Example</span></span>
 <span data-ttu-id="9e9f6-117">下面的代码是创建和使用简单扩展方法的完整示例。</span><span class="sxs-lookup"><span data-stu-id="9e9f6-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>

```vb
Imports System.Runtime.CompilerServices
Imports ConsoleApplication1.StringExtensions

Module Module1

    Sub Main()

        Dim example = "Hello"
        example.PrintAndPunctuate(".")
        example.PrintAndPunctuate("!!!!")

        Dim example2 = "Goodbye"
        example2.PrintAndPunctuate("?")
    End Sub

    <Extension()>
    Public Sub PrintAndPunctuate(ByVal aString As String,
                                 ByVal punc As String)
        Console.WriteLine(aString & punc)
    End Sub
End Module

' Output:
' Hello.
' Hello!!!!
' Goodbye?
```

## <a name="see-also"></a><span data-ttu-id="9e9f6-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e9f6-118">See also</span></span>

- [<span data-ttu-id="9e9f6-119">如何：编写扩展方法</span><span class="sxs-lookup"><span data-stu-id="9e9f6-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)
- [<span data-ttu-id="9e9f6-120">扩展方法</span><span class="sxs-lookup"><span data-stu-id="9e9f6-120">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="9e9f6-121">范围 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e9f6-121">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)

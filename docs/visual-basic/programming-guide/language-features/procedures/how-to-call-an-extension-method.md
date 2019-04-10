---
title: 如何：调用扩展方法 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: 5cb0684637a716dfec947740ba345c62eaabddd7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59313796"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="af768-102">如何：调用扩展方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af768-102">How to: Call an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="af768-103">扩展方法，可将方法添加到现有类。</span><span class="sxs-lookup"><span data-stu-id="af768-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="af768-104">声明的扩展方法并将其引入到范围后，可以调用它类似于它所扩展的类型的实例方法。</span><span class="sxs-lookup"><span data-stu-id="af768-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="af768-105">有关如何编写扩展方法的详细信息，请参阅[如何：编写扩展方法](./how-to-write-an-extension-method.md)。</span><span class="sxs-lookup"><span data-stu-id="af768-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>  
  
 <span data-ttu-id="af768-106">以下说明，请参阅扩展方法`PrintAndPunctuate`，随后会显示调用它的任何值后跟的字符串实例中发送的第二个参数， `punc`。</span><span class="sxs-lookup"><span data-stu-id="af768-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>  
  
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
  
 <span data-ttu-id="af768-107">该方法必须在范围内，被调用时。</span><span class="sxs-lookup"><span data-stu-id="af768-107">The method must be in scope when it is called.</span></span>  
  
### <a name="to-call-an-extension-method"></a><span data-ttu-id="af768-108">若要调用扩展方法</span><span class="sxs-lookup"><span data-stu-id="af768-108">To call an extension method</span></span>  
  
1. <span data-ttu-id="af768-109">声明具有扩展方法的第一个参数的数据类型的变量。</span><span class="sxs-lookup"><span data-stu-id="af768-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="af768-110">有关`PrintAndPunctuate`，你需要<xref:System.String>变量：</span><span class="sxs-lookup"><span data-stu-id="af768-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2. <span data-ttu-id="af768-111">变量将调用扩展方法，和它的值绑定到的第一个参数， `aString`。</span><span class="sxs-lookup"><span data-stu-id="af768-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="af768-112">将显示以下调用语句`Ready?`。</span><span class="sxs-lookup"><span data-stu-id="af768-112">The following calling statement will display `Ready?`.</span></span>  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     <span data-ttu-id="af768-113">请注意，对此扩展方法的调用看起来就像对任何一个调用<xref:System.String>实例需要一个参数的方法：</span><span class="sxs-lookup"><span data-stu-id="af768-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3. <span data-ttu-id="af768-114">声明另一个字符串变量，并再次调用方法以查看其工作与任何字符串。</span><span class="sxs-lookup"><span data-stu-id="af768-114">Declare another string variable and call the method again to see that it works with any string.</span></span>  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     <span data-ttu-id="af768-115">结果这一次是： `or not!!!`。</span><span class="sxs-lookup"><span data-stu-id="af768-115">The result this time is: `or not!!!`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af768-116">示例</span><span class="sxs-lookup"><span data-stu-id="af768-116">Example</span></span>  
 <span data-ttu-id="af768-117">下面的代码是创建的一个完整的示例和使用简单的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="af768-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="af768-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="af768-118">See also</span></span>

- [<span data-ttu-id="af768-119">如何：编写扩展方法</span><span class="sxs-lookup"><span data-stu-id="af768-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)
- [<span data-ttu-id="af768-120">扩展方法</span><span class="sxs-lookup"><span data-stu-id="af768-120">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="af768-121">Visual Basic 中的范围</span><span class="sxs-lookup"><span data-stu-id="af768-121">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)

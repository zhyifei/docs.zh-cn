---
title: "如何：调用扩展方法 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 25b5a86af15694e6f64f96a5d5d645a01f8f1f12
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="a39de-102">如何：调用扩展方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a39de-102">How to: Call an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="a39de-103">扩展方法使你能够向现有类添加方法。</span><span class="sxs-lookup"><span data-stu-id="a39de-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="a39de-104">声明数据并扩展方法置于范围后，你可以调用它类似于它所扩展的类型的实例方法。</span><span class="sxs-lookup"><span data-stu-id="a39de-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="a39de-105">有关如何编写扩展方法的详细信息，请参阅[如何： 编写扩展方法](./how-to-write-an-extension-method.md)。</span><span class="sxs-lookup"><span data-stu-id="a39de-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>  
  
 <span data-ttu-id="a39de-106">下面的说明，请参阅对扩展方法`PrintAndPunctuate`，这将显示调用它，并且后跟任意值的字符串实例发送第二个参数，用于`punc`。</span><span class="sxs-lookup"><span data-stu-id="a39de-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>  
  
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
  
 <span data-ttu-id="a39de-107">该方法必须在范围内，被调用时。</span><span class="sxs-lookup"><span data-stu-id="a39de-107">The method must be in scope when it is called.</span></span>  
  
### <a name="to-call-an-extension-method"></a><span data-ttu-id="a39de-108">若要调用扩展方法</span><span class="sxs-lookup"><span data-stu-id="a39de-108">To call an extension method</span></span>  
  
1.  <span data-ttu-id="a39de-109">声明具有扩展方法的第一个参数的数据类型的变量。</span><span class="sxs-lookup"><span data-stu-id="a39de-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="a39de-110">有关`PrintAndPunctuate`，你需要<xref:System.String>变量：</span><span class="sxs-lookup"><span data-stu-id="a39de-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2.  <span data-ttu-id="a39de-111">变量将调用扩展方法，并且其值将绑定到的第一个参数， `aString`。</span><span class="sxs-lookup"><span data-stu-id="a39de-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="a39de-112">将显示以下调用语句`Ready?`。</span><span class="sxs-lookup"><span data-stu-id="a39de-112">The following calling statement will display `Ready?`.</span></span>  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     <span data-ttu-id="a39de-113">请注意，对此扩展方法的调用看起来就像对任何之一的调用<xref:System.String>实例需要一个参数的方法：</span><span class="sxs-lookup"><span data-stu-id="a39de-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3.  <span data-ttu-id="a39de-114">声明另一个字符串变量，并再次调用方法以查看其工作与任何字符串。</span><span class="sxs-lookup"><span data-stu-id="a39de-114">Declare another string variable and call the method again to see that it works with any string.</span></span>  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     <span data-ttu-id="a39de-115">结果此时是： `or not!!!`。</span><span class="sxs-lookup"><span data-stu-id="a39de-115">The result this time is: `or not!!!`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a39de-116">示例</span><span class="sxs-lookup"><span data-stu-id="a39de-116">Example</span></span>  
 <span data-ttu-id="a39de-117">下面的代码是创建的完整示例和使用简单的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="a39de-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a39de-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a39de-118">See Also</span></span>  
 [<span data-ttu-id="a39de-119">如何：编写扩展方法</span><span class="sxs-lookup"><span data-stu-id="a39de-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)  
 [<span data-ttu-id="a39de-120">扩展方法</span><span class="sxs-lookup"><span data-stu-id="a39de-120">Extension Methods</span></span>](./extension-methods.md)  
 [<span data-ttu-id="a39de-121">在 Visual Basic 中的作用域</span><span class="sxs-lookup"><span data-stu-id="a39de-121">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)

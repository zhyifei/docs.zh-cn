---
title: 如何：编写扩展方法 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: e220a025c39757b492be033caeb8924523515804
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648728"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="a012b-102">如何：编写扩展方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a012b-102">How to: Write an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="a012b-103">扩展方法使你能够向现有类添加方法。</span><span class="sxs-lookup"><span data-stu-id="a012b-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="a012b-104">可以调用扩展方法，就像它是该类的实例。</span><span class="sxs-lookup"><span data-stu-id="a012b-104">The extension method can be called as if it were an instance of that class.</span></span>  
  
### <a name="to-define-an-extension-method"></a><span data-ttu-id="a012b-105">若要定义的扩展方法</span><span class="sxs-lookup"><span data-stu-id="a012b-105">To define an extension method</span></span>  
  
1.  <span data-ttu-id="a012b-106">在 Visual Studio 中打开新的或现有 Visual Basic 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a012b-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="a012b-107">在你要在其中定义的扩展方法的文件的顶部，包括以下 import 语句：</span><span class="sxs-lookup"><span data-stu-id="a012b-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  <span data-ttu-id="a012b-108">新的或现有应用程序中的模块内, 开始使用扩展属性的方法定义：</span><span class="sxs-lookup"><span data-stu-id="a012b-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>  
  
    ```  
    <Extension()>  
    ```  
  
4.  <span data-ttu-id="a012b-109">你的方法声明的方式声明普通，只不过的第一个参数的类型必须是你想要扩展的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a012b-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a><span data-ttu-id="a012b-110">示例</span><span class="sxs-lookup"><span data-stu-id="a012b-110">Example</span></span>  
 <span data-ttu-id="a012b-111">下面的示例声明模块中的扩展方法`StringExtensions`。</span><span class="sxs-lookup"><span data-stu-id="a012b-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="a012b-112">第二个模块， `Module1`，导入`StringExtensions`和调用的方法。</span><span class="sxs-lookup"><span data-stu-id="a012b-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="a012b-113">扩展方法必须在范围内，被调用时。</span><span class="sxs-lookup"><span data-stu-id="a012b-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="a012b-114">扩展方法`PrintAndPunctuate`扩展<xref:System.String>的显示字符串实例的方法的类后, 跟作为一个参数发送的标点符号的字符串。</span><span class="sxs-lookup"><span data-stu-id="a012b-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>  
  
```vb  
' Declarations will typically be in a separate module.  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
```vb  
' Import the module that holds the extension method you want to use,   
' and call it.  
  
Imports ConsoleApplication2.StringExtensions  
  
Module Module1  
  
    Sub Main()  
        Dim example = "Hello"  
        example.PrintAndPunctuate("?")  
        example.PrintAndPunctuate("!!!!")  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="a012b-115">请注意，方法是使用两个参数定义的只使用一个调用。</span><span class="sxs-lookup"><span data-stu-id="a012b-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="a012b-116">第一个参数， `aString`，方法中定义绑定到`example`，实例`String`调用的方法。</span><span class="sxs-lookup"><span data-stu-id="a012b-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="a012b-117">该示例输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="a012b-117">The output of the example is as follows:</span></span>  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a><span data-ttu-id="a012b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a012b-118">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>  
 [<span data-ttu-id="a012b-119">扩展方法</span><span class="sxs-lookup"><span data-stu-id="a012b-119">Extension Methods</span></span>](./extension-methods.md)  
 [<span data-ttu-id="a012b-120">Module 语句</span><span class="sxs-lookup"><span data-stu-id="a012b-120">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [<span data-ttu-id="a012b-121">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="a012b-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="a012b-122">在 Visual Basic 中的作用域</span><span class="sxs-lookup"><span data-stu-id="a012b-122">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)

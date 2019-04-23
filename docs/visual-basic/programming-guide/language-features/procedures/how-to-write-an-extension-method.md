---
title: 如何：编写扩展方法 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 00d62d275f7afc06e066a375dc1ffcd74b23c9ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313757"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="0bb8e-102">如何：编写扩展方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0bb8e-102">How to: Write an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="0bb8e-103">扩展方法，可将方法添加到现有类。</span><span class="sxs-lookup"><span data-stu-id="0bb8e-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="0bb8e-104">可以调用扩展方法，就像该类的实例。</span><span class="sxs-lookup"><span data-stu-id="0bb8e-104">The extension method can be called as if it were an instance of that class.</span></span>  
  
### <a name="to-define-an-extension-method"></a><span data-ttu-id="0bb8e-105">若要定义的扩展方法</span><span class="sxs-lookup"><span data-stu-id="0bb8e-105">To define an extension method</span></span>  
  
1. <span data-ttu-id="0bb8e-106">在 Visual Studio 中打开新的或现有 Visual Basic 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0bb8e-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>  
  
2. <span data-ttu-id="0bb8e-107">在您要在其中定义扩展方法，该文件的顶部，包括以下 import 语句：</span><span class="sxs-lookup"><span data-stu-id="0bb8e-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3. <span data-ttu-id="0bb8e-108">在新的或现有应用程序中的模块内, 开始使用扩展属性的方法定义：</span><span class="sxs-lookup"><span data-stu-id="0bb8e-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>  
  
    ```  
    <Extension()>  
    ```  
  
4. <span data-ttu-id="0bb8e-109">以普通方式声明你的方法，只不过的第一个参数的类型必须是你想要扩展的数据类型。</span><span class="sxs-lookup"><span data-stu-id="0bb8e-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a><span data-ttu-id="0bb8e-110">示例</span><span class="sxs-lookup"><span data-stu-id="0bb8e-110">Example</span></span>  
 <span data-ttu-id="0bb8e-111">下面的示例声明模块中的扩展方法`StringExtensions`。</span><span class="sxs-lookup"><span data-stu-id="0bb8e-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="0bb8e-112">第二个模块， `Module1`，将导入`StringExtensions`和调用的方法。</span><span class="sxs-lookup"><span data-stu-id="0bb8e-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="0bb8e-113">扩展方法必须在范围内，被调用时。</span><span class="sxs-lookup"><span data-stu-id="0bb8e-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="0bb8e-114">扩展方法`PrintAndPunctuate`扩展了<xref:System.String>类显示的字符串实例的方法后, 跟标点符号中发送作为参数的字符串。</span><span class="sxs-lookup"><span data-stu-id="0bb8e-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>  
  
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
  
 <span data-ttu-id="0bb8e-115">请注意，方法是使用两个参数定义，仅有一个调用。</span><span class="sxs-lookup"><span data-stu-id="0bb8e-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="0bb8e-116">第一个参数， `aString`，在方法中定义绑定到`example`，实例`String`调用的方法。</span><span class="sxs-lookup"><span data-stu-id="0bb8e-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="0bb8e-117">示例输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="0bb8e-117">The output of the example is as follows:</span></span>  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a><span data-ttu-id="0bb8e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="0bb8e-118">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="0bb8e-119">扩展方法</span><span class="sxs-lookup"><span data-stu-id="0bb8e-119">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="0bb8e-120">Module 语句</span><span class="sxs-lookup"><span data-stu-id="0bb8e-120">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="0bb8e-121">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="0bb8e-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="0bb8e-122">在 Visual Basic 中的作用域</span><span class="sxs-lookup"><span data-stu-id="0bb8e-122">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)

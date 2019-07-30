---
title: 如何：编写扩展方法 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 7a7a9d16d9f69071e9d1dacb0558f7ca92e1d21e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631035"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="659bd-102">如何：编写扩展方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="659bd-102">How to: Write an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="659bd-103">扩展方法使你能够向现有类添加方法。</span><span class="sxs-lookup"><span data-stu-id="659bd-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="659bd-104">可以调用扩展方法, 就像它是该类的实例一样。</span><span class="sxs-lookup"><span data-stu-id="659bd-104">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="659bd-105">定义扩展方法</span><span class="sxs-lookup"><span data-stu-id="659bd-105">To define an extension method</span></span>

1. <span data-ttu-id="659bd-106">在 Visual Studio 中打开新的或现有的 Visual Basic 应用程序。</span><span class="sxs-lookup"><span data-stu-id="659bd-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="659bd-107">在要在其中定义扩展方法的文件的顶部, 请包含以下 import 语句:</span><span class="sxs-lookup"><span data-stu-id="659bd-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="659bd-108">在新应用程序或现有应用程序的模块中, 使用扩展属性开始方法定义:</span><span class="sxs-lookup"><span data-stu-id="659bd-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>

    ```vb
    <Extension()>
    ```

4. <span data-ttu-id="659bd-109">用普通方法声明方法, 但第一个参数的类型必须是要扩展的数据类型。</span><span class="sxs-lookup"><span data-stu-id="659bd-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName (ByVal para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="659bd-110">示例</span><span class="sxs-lookup"><span data-stu-id="659bd-110">Example</span></span>
 <span data-ttu-id="659bd-111">下面的示例声明了模块`StringExtensions`中的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="659bd-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="659bd-112">第二个模块`Module1`导入`StringExtensions`并调用方法。</span><span class="sxs-lookup"><span data-stu-id="659bd-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="659bd-113">在调用扩展方法时, 该方法必须在范围内。</span><span class="sxs-lookup"><span data-stu-id="659bd-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="659bd-114">扩展方法`PrintAndPunctuate`使用一个<xref:System.String>方法来扩展类, 该方法将后跟以参数形式发送的标点符号字符串作为参数。</span><span class="sxs-lookup"><span data-stu-id="659bd-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>
  
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
  
 <span data-ttu-id="659bd-115">请注意, 方法是用两个参数定义的, 并且只能用一个参数调用。</span><span class="sxs-lookup"><span data-stu-id="659bd-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="659bd-116">方法定义中的`aString`第一个参数绑定到`example`调用方法的实例`String` 。</span><span class="sxs-lookup"><span data-stu-id="659bd-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="659bd-117">示例输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="659bd-117">The output of the example is as follows:</span></span>
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a><span data-ttu-id="659bd-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="659bd-118">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="659bd-119">扩展方法</span><span class="sxs-lookup"><span data-stu-id="659bd-119">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="659bd-120">Module 语句</span><span class="sxs-lookup"><span data-stu-id="659bd-120">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="659bd-121">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="659bd-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="659bd-122">范围 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="659bd-122">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)

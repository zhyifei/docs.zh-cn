---
title: 如何：编写扩展方法 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 4671728330614f0f3da23fd90f5e635ddcf46578
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581154"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="864cf-102">如何：编写扩展方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="864cf-102">How to: Write an Extension Method (Visual Basic)</span></span>

<span data-ttu-id="864cf-103">扩展方法使你能够向现有类添加方法。</span><span class="sxs-lookup"><span data-stu-id="864cf-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="864cf-104">可以调用扩展方法，就像它是该类的实例一样。</span><span class="sxs-lookup"><span data-stu-id="864cf-104">The extension method can be called as if it were an instance of that class.</span></span>

### <a name="to-define-an-extension-method"></a><span data-ttu-id="864cf-105">定义扩展方法</span><span class="sxs-lookup"><span data-stu-id="864cf-105">To define an extension method</span></span>

1. <span data-ttu-id="864cf-106">在 Visual Studio 中打开新的或现有的 Visual Basic 应用程序。</span><span class="sxs-lookup"><span data-stu-id="864cf-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>

2. <span data-ttu-id="864cf-107">在要在其中定义扩展方法的文件的顶部，请包含以下 import 语句：</span><span class="sxs-lookup"><span data-stu-id="864cf-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. <span data-ttu-id="864cf-108">在新应用程序或现有应用程序的模块中，使用[`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute)特性开始方法定义：</span><span class="sxs-lookup"><span data-stu-id="864cf-108">Within a module in your new or existing application, begin the method definition with the [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) attribute:</span></span>

    ```vb
    <Extension()>
    ```

    <span data-ttu-id="864cf-109">请注意，`Extension` 属性只能应用于 Visual Basic[模块](../../../language-reference/statements/module-statement.md)中的方法（`Sub` 或 `Function` 过程）。</span><span class="sxs-lookup"><span data-stu-id="864cf-109">Note that the `Extension` attribute can only be applied to a method (a `Sub` or `Function` procedure) in a Visual Basic [Module](../../../language-reference/statements/module-statement.md).</span></span> <span data-ttu-id="864cf-110">如果将它应用于 `Class` 或 `Structure` 中的方法，则 Visual Basic 编译器将生成错误[BC36551](../../../misc/bc36551.md)，"只能在模块中定义扩展方法。"</span><span class="sxs-lookup"><span data-stu-id="864cf-110">If you apply it to a method in a `Class` or a `Structure`, the Visual Basic compiler generates error [BC36551](../../../misc/bc36551.md), "Extension methods can be defined only in modules."</span></span>

4. <span data-ttu-id="864cf-111">用普通方法声明方法，但第一个参数的类型必须是要扩展的数据类型。</span><span class="sxs-lookup"><span data-stu-id="864cf-111">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a><span data-ttu-id="864cf-112">示例</span><span class="sxs-lookup"><span data-stu-id="864cf-112">Example</span></span>

<span data-ttu-id="864cf-113">下面的示例在模块 `StringExtensions` 中声明了扩展方法。</span><span class="sxs-lookup"><span data-stu-id="864cf-113">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="864cf-114">第二个模块 `Module1`，`StringExtensions` 导入并调用方法。</span><span class="sxs-lookup"><span data-stu-id="864cf-114">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="864cf-115">在调用扩展方法时，该方法必须在范围内。</span><span class="sxs-lookup"><span data-stu-id="864cf-115">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="864cf-116">扩展方法 `PrintAndPunctuate` 使用一个方法来扩展 <xref:System.String> 类，该方法将后跟以参数形式发送的标点符号字符串作为参数。</span><span class="sxs-lookup"><span data-stu-id="864cf-116">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>

```vb
' Declarations will typically be in a separate module.
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
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

<span data-ttu-id="864cf-117">请注意，方法是用两个参数定义的，并且只能用一个参数调用。</span><span class="sxs-lookup"><span data-stu-id="864cf-117">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="864cf-118">方法定义中的第一个参数 `aString` 绑定到 `example`，后者调用方法的 `String` 的实例。</span><span class="sxs-lookup"><span data-stu-id="864cf-118">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="864cf-119">示例输出如下所示：</span><span class="sxs-lookup"><span data-stu-id="864cf-119">The output of the example is as follows:</span></span>

```console
Hello?
Hello!!!!
```

## <a name="see-also"></a><span data-ttu-id="864cf-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="864cf-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="864cf-121">扩展方法</span><span class="sxs-lookup"><span data-stu-id="864cf-121">Extension Methods</span></span>](extension-methods.md)
- [<span data-ttu-id="864cf-122">Module 语句</span><span class="sxs-lookup"><span data-stu-id="864cf-122">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="864cf-123">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="864cf-123">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="864cf-124">范围 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="864cf-124">Scope in Visual Basic</span></span>](../declared-elements/scope.md)

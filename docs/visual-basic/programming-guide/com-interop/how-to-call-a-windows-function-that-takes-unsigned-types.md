---
title: "如何︰ 调用采用无符号的类型 (Visual Basic 中) 的 Windows 函数 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Windows functions, calling
- unsigned data types
- UShort data type, using
- functions [Visual Basic], calling Windows functions
- ULong data type, using
- UInteger data type, using
- data types [Visual Basic], using
- unsigned types
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types, using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7b6b1d46b6ccab0ec8d63fb8b7d8722b518b81b4
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a><span data-ttu-id="9e58a-102">如何：调用采用无符号类型的 Windows 函数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e58a-102">How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)</span></span>
<span data-ttu-id="9e58a-103">如果您正在使用类、 模块或具有无符号的整数类型的成员的结构，您可以访问这些成员与[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9e58a-103">If you are consuming a class, module, or structure that has members of unsigned integer types, you can access these members with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a><span data-ttu-id="9e58a-104">若要调用采用无符号的类型的 Windows 函数</span><span class="sxs-lookup"><span data-stu-id="9e58a-104">To call a Windows function that takes an unsigned type</span></span>  
  
1.  <span data-ttu-id="9e58a-105">使用[声明语句](../../../visual-basic/language-reference/statements/declare-statement.md)告诉[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]的库包含函数、 什么其名称是在库中、 其调用的顺序是什么，和如何将字符串转换调用时。</span><span class="sxs-lookup"><span data-stu-id="9e58a-105">Use a [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) to tell [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] which library holds the function, what its name is in that library, what its calling sequence is, and how to convert strings when calling it.</span></span>  
  
2.  <span data-ttu-id="9e58a-106">在`Declare`语句中，使用`UInteger`， `ULong`， `UShort`，或`Byte`为适合于无符号类型的每个参数。</span><span class="sxs-lookup"><span data-stu-id="9e58a-106">In the `Declare` statement, use `UInteger`, `ULong`, `UShort`, or `Byte` as appropriate for each parameter with an unsigned type.</span></span>  
  
3.  <span data-ttu-id="9e58a-107">查阅文档以获取要调用要查找的名称和值的常量，它使用的 Windows 函数。</span><span class="sxs-lookup"><span data-stu-id="9e58a-107">Consult the documentation for the Windows function you are calling to find the names and values of the constants it uses.</span></span> <span data-ttu-id="9e58a-108">其中许多 WinUser.h 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="9e58a-108">Many of these are defined in the WinUser.h file.</span></span>  
  
4.  <span data-ttu-id="9e58a-109">声明在代码中必要的常数。</span><span class="sxs-lookup"><span data-stu-id="9e58a-109">Declare the necessary constants in your code.</span></span> <span data-ttu-id="9e58a-110">许多 Windows 常量是 32 位无符号的值，并应将这些声明`As``UInteger`。</span><span class="sxs-lookup"><span data-stu-id="9e58a-110">Many Windows constants are 32-bit unsigned values, and you should declare these `As``UInteger`.</span></span>  
  
5.  <span data-ttu-id="9e58a-111">以正常方式调用函数。</span><span class="sxs-lookup"><span data-stu-id="9e58a-111">Call the function in the normal way.</span></span> <span data-ttu-id="9e58a-112">下面的示例调用 Windows 函数`MessageBox`，它将采用一个无符号的整数参数。</span><span class="sxs-lookup"><span data-stu-id="9e58a-112">The following example calls the Windows function `MessageBox`, which takes an unsigned integer argument.</span></span>  
  
    ```  
    Public Class windowsMessage  
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (  
            ByVal hWnd As Integer,   
            ByVal lpText As String,   
            ByVal lpCaption As String,   
            ByVal uType As UInteger) As Integer  
        Private Const MB_OK As UInteger = 0  
        Private Const MB_ICONEXCLAMATION As UInteger = &H30  
        Private Const IDOK As UInteger = 1  
        Private Const IDCLOSE As UInteger = 8  
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION  
        Public Function messageThroughWindows() As String  
            Dim r As Integer = mb(0, "Click OK if you see this!",   
                "Windows API call", c)  
            Dim s As String = "Windows API MessageBox returned " &  
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &  
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"  
            Return s  
        End Function  
    End Class  
    ```  
  
     <span data-ttu-id="9e58a-113">您可以测试该函数`messageThroughWindows`替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="9e58a-113">You can test the function `messageThroughWindows` with the following code.</span></span>  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="9e58a-114">`UInteger`， `ULong`， `UShort`，和`SByte`数据类型不属于[语言独立性和与语言无关的组件](https://msdn.microsoft.com/library/12a7a7h3)(CLS)，因此符合 cls 的代码不能使用它们使用的组件。</span><span class="sxs-lookup"><span data-stu-id="9e58a-114">The `UInteger`, `ULong`, `UShort`, and `SByte` data types are not part of the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), so CLS-compliant code cannot consume a component that uses them.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9e58a-115">Windows 应用程序编程接口 (API)，如在非托管代码调用公开您的代码与潜在的安全风险。</span><span class="sxs-lookup"><span data-stu-id="9e58a-115">Making a call to unmanaged code, such as the Windows application programming interface (API), exposes your code to potential security risks.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9e58a-116">调用 Windows API 要求非托管的代码的权限，这可能会影响它在部分信任的情况下执行。</span><span class="sxs-lookup"><span data-stu-id="9e58a-116">Calling the Windows API requires unmanaged code permission, which might affect its execution in partial-trust situations.</span></span> <span data-ttu-id="9e58a-117">有关详细信息，请参阅<xref:System.Security.Permissions.SecurityPermission>和[代码访问权限](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675)。</xref:System.Security.Permissions.SecurityPermission></span><span class="sxs-lookup"><span data-stu-id="9e58a-117">For more information, see <xref:System.Security.Permissions.SecurityPermission> and [Code Access Permissions](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e58a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e58a-118">See Also</span></span>  
 <span data-ttu-id="9e58a-119">[数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="9e58a-119">[Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="9e58a-120"> [整数数据类型](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="9e58a-120"> [Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span></span>  
<span data-ttu-id="9e58a-121"> [UInteger 数据类型](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="9e58a-121"> [UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) </span></span>  
<span data-ttu-id="9e58a-122"> [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="9e58a-122"> [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) </span></span>  
<span data-ttu-id="9e58a-123"> [演练：调用 Windows API](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)</span><span class="sxs-lookup"><span data-stu-id="9e58a-123"> [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)</span></span>

---
title: "如何：调用采用无符号类型的 Windows 函数 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1d59c29a83ede97d90926c8e499788676e2c235
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a><span data-ttu-id="ff4fe-102">如何：调用采用无符号类型的 Windows 函数 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff4fe-102">How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)</span></span>
<span data-ttu-id="ff4fe-103">如果你使用的类、 模块或结构，它具有无符号的整数类型的成员，则可以访问与这些成员[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ff4fe-103">If you are consuming a class, module, or structure that has members of unsigned integer types, you can access these members with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a><span data-ttu-id="ff4fe-104">若要调用采用无符号的类型的 Windows 函数</span><span class="sxs-lookup"><span data-stu-id="ff4fe-104">To call a Windows function that takes an unsigned type</span></span>  
  
1.  <span data-ttu-id="ff4fe-105">使用[声明语句](../../../visual-basic/language-reference/statements/declare-statement.md)告诉[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]哪些库包含函数、 什么其名称是在库中，其调用的序列是什么，和如何将字符串转换调用它时。</span><span class="sxs-lookup"><span data-stu-id="ff4fe-105">Use a [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) to tell [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] which library holds the function, what its name is in that library, what its calling sequence is, and how to convert strings when calling it.</span></span>  
  
2.  <span data-ttu-id="ff4fe-106">在`Declare`语句，使用`UInteger`， `ULong`， `UShort`，或`Byte`为适合于与无符号类型的每个参数。</span><span class="sxs-lookup"><span data-stu-id="ff4fe-106">In the `Declare` statement, use `UInteger`, `ULong`, `UShort`, or `Byte` as appropriate for each parameter with an unsigned type.</span></span>  
  
3.  <span data-ttu-id="ff4fe-107">查阅文档以获取要调用若要查找的名称和它所使用的常量值的 Windows 函数。</span><span class="sxs-lookup"><span data-stu-id="ff4fe-107">Consult the documentation for the Windows function you are calling to find the names and values of the constants it uses.</span></span> <span data-ttu-id="ff4fe-108">其中许多参见 WinUser.h 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="ff4fe-108">Many of these are defined in the WinUser.h file.</span></span>  
  
4.  <span data-ttu-id="ff4fe-109">声明在代码中的必要常量。</span><span class="sxs-lookup"><span data-stu-id="ff4fe-109">Declare the necessary constants in your code.</span></span> <span data-ttu-id="ff4fe-110">许多 Windows 常量是 32 位无符号的值，并应将这些声明`As``UInteger`。</span><span class="sxs-lookup"><span data-stu-id="ff4fe-110">Many Windows constants are 32-bit unsigned values, and you should declare these `As``UInteger`.</span></span>  
  
5.  <span data-ttu-id="ff4fe-111">以常规方式调用函数。</span><span class="sxs-lookup"><span data-stu-id="ff4fe-111">Call the function in the normal way.</span></span> <span data-ttu-id="ff4fe-112">下面的示例调用 Windows 函数`MessageBox`，它将采用一个无符号的整数自变量。</span><span class="sxs-lookup"><span data-stu-id="ff4fe-112">The following example calls the Windows function `MessageBox`, which takes an unsigned integer argument.</span></span>  
  
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
  
     <span data-ttu-id="ff4fe-113">你可以测试函数`messageThroughWindows`替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="ff4fe-113">You can test the function `messageThroughWindows` with the following code.</span></span>  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="ff4fe-114">`UInteger`， `ULong`， `UShort`，和`SByte`数据类型不属于[语言独立性和独立于语言的组件](https://msdn.microsoft.com/library/12a7a7h3)(CLS)，因此符合 cls 的代码不能使用的组件，使用它们。</span><span class="sxs-lookup"><span data-stu-id="ff4fe-114">The `UInteger`, `ULong`, `UShort`, and `SByte` data types are not part of the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), so CLS-compliant code cannot consume a component that uses them.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ff4fe-115">Windows 应用程序编程接口 (API)，例如在调用非托管代码，公开将代码移植到潜在的安全风险。</span><span class="sxs-lookup"><span data-stu-id="ff4fe-115">Making a call to unmanaged code, such as the Windows application programming interface (API), exposes your code to potential security risks.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ff4fe-116">调用 Windows API 需要非托管的代码的权限，这可能会影响在部分信任情况下其执行。</span><span class="sxs-lookup"><span data-stu-id="ff4fe-116">Calling the Windows API requires unmanaged code permission, which might affect its execution in partial-trust situations.</span></span> <span data-ttu-id="ff4fe-117">有关详细信息，请参阅<xref:System.Security.Permissions.SecurityPermission>和[代码访问权限](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675)。</span><span class="sxs-lookup"><span data-stu-id="ff4fe-117">For more information, see <xref:System.Security.Permissions.SecurityPermission> and [Code Access Permissions](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff4fe-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff4fe-118">See Also</span></span>  
 [<span data-ttu-id="ff4fe-119">数据类型</span><span class="sxs-lookup"><span data-stu-id="ff4fe-119">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="ff4fe-120">Integer 数据类型</span><span class="sxs-lookup"><span data-stu-id="ff4fe-120">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="ff4fe-121">UInteger 数据类型</span><span class="sxs-lookup"><span data-stu-id="ff4fe-121">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
 [<span data-ttu-id="ff4fe-122">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="ff4fe-122">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="ff4fe-123">演练：调用 Windows API</span><span class="sxs-lookup"><span data-stu-id="ff4fe-123">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)

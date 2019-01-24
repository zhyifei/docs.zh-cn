---
title: Visual Basic 中的 Main 过程
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: b84bf20acaaa912e47102973b0484d635f1aa244
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54679417"
---
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="2e231-102">Visual Basic 中的 Main 过程</span><span class="sxs-lookup"><span data-stu-id="2e231-102">Main Procedure in Visual Basic</span></span>
<span data-ttu-id="2e231-103">每个 Visual Basic 应用程序必须包含被调用的过程`Main`。</span><span class="sxs-lookup"><span data-stu-id="2e231-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="2e231-104">此过程可用作起始点并为应用程序的总体控制。</span><span class="sxs-lookup"><span data-stu-id="2e231-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="2e231-105">.NET Framework 调用你`Main`时它已加载你的应用程序并已准备好将控制传递给它的过程。</span><span class="sxs-lookup"><span data-stu-id="2e231-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="2e231-106">除非要创建 Windows 窗体应用程序，必须编写`Main`运行其自己的应用程序的过程。</span><span class="sxs-lookup"><span data-stu-id="2e231-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>  
  
 <span data-ttu-id="2e231-107">`Main` 包含先运行的代码。</span><span class="sxs-lookup"><span data-stu-id="2e231-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="2e231-108">在`Main`，可以确定在程序启动时首先加载哪个窗体，找出在系统上是否已在运行应用程序的副本，为应用程序建立了一组变量或打开应用程序所需的数据库。</span><span class="sxs-lookup"><span data-stu-id="2e231-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>  
  
## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="2e231-109">主要过程的要求</span><span class="sxs-lookup"><span data-stu-id="2e231-109">Requirements for the Main Procedure</span></span>  
 <span data-ttu-id="2e231-110">在运行其自身 （通常使用扩展名为.exe) 文件必须包含`Main`过程。</span><span class="sxs-lookup"><span data-stu-id="2e231-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="2e231-111">（例如使用扩展名为.dll) 的库不会运行其自己并不需要`Main`过程。</span><span class="sxs-lookup"><span data-stu-id="2e231-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="2e231-112">您可以创建不同类型的项目的要求如下所示：</span><span class="sxs-lookup"><span data-stu-id="2e231-112">The requirements for the different types of projects you can create are as follows:</span></span>  
  
-   <span data-ttu-id="2e231-113">控制台应用程序可以独立运行，并且必须提供至少一个`Main`过程。</span><span class="sxs-lookup"><span data-stu-id="2e231-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span> <span data-ttu-id="2e231-114">.</span><span class="sxs-lookup"><span data-stu-id="2e231-114">.</span></span>  
  
-   <span data-ttu-id="2e231-115">Windows 窗体应用程序上运行其自己。</span><span class="sxs-lookup"><span data-stu-id="2e231-115">Windows Forms applications run on their own.</span></span> <span data-ttu-id="2e231-116">但是，Visual Basic 编译器会自动生成`Main`过程在此类应用程序，并且您无需编写一个。</span><span class="sxs-lookup"><span data-stu-id="2e231-116">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>  
  
-   <span data-ttu-id="2e231-117">不需要类库`Main`过程。</span><span class="sxs-lookup"><span data-stu-id="2e231-117">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="2e231-118">其中包括 Windows 控件库和 Web 控件库。</span><span class="sxs-lookup"><span data-stu-id="2e231-118">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="2e231-119">Web 应用程序部署为类库。</span><span class="sxs-lookup"><span data-stu-id="2e231-119">Web applications are deployed as class libraries.</span></span>  
  
## <a name="declaring-the-main-procedure"></a><span data-ttu-id="2e231-120">声明的主要过程</span><span class="sxs-lookup"><span data-stu-id="2e231-120">Declaring the Main Procedure</span></span>  
 <span data-ttu-id="2e231-121">有四种方法来声明`Main`过程。</span><span class="sxs-lookup"><span data-stu-id="2e231-121">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="2e231-122">它可以采用自变量和其可以或不返回值。</span><span class="sxs-lookup"><span data-stu-id="2e231-122">It can take arguments or not, and it can return a value or not.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e231-123">如果声明`Main`在类中，必须使用`Shared`关键字。</span><span class="sxs-lookup"><span data-stu-id="2e231-123">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="2e231-124">在模块中，`Main`不需要为`Shared`。</span><span class="sxs-lookup"><span data-stu-id="2e231-124">In a module, `Main` does not need to be `Shared`.</span></span>  
  
-   <span data-ttu-id="2e231-125">最简单方法是声明`Sub`不采用自变量或返回值的过程。</span><span class="sxs-lookup"><span data-stu-id="2e231-125">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   <span data-ttu-id="2e231-126">`Main` 此外可以返回`Integer`值，操作系统的退出代码为使用您的计划。</span><span class="sxs-lookup"><span data-stu-id="2e231-126">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="2e231-127">其他程序可以测试此代码通过检查 Windows ERRORLEVEL 值。</span><span class="sxs-lookup"><span data-stu-id="2e231-127">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="2e231-128">若要返回的退出代码，必须声明`Main`作为`Function`而不是过程`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="2e231-128">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>  
  
    ```  
    Module mainModule  
        Function Main() As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' Insert call to appropriate starting place in your code.  
            ' On return, assign appropriate value to returnValue.  
            ' 0 usually means successful completion.  
            MsgBox("The application is terminating with error level " &  
                 CStr(returnValue) & ".")  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
-   <span data-ttu-id="2e231-129">`Main` 也可以采用`String`数组作为参数。</span><span class="sxs-lookup"><span data-stu-id="2e231-129">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="2e231-130">每个字符串数组中的包含一个用于调用程序的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="2e231-130">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="2e231-131">您可以采取不同操作，具体取决于它们的值。</span><span class="sxs-lookup"><span data-stu-id="2e231-131">You can take different actions depending on their values.</span></span>  
  
    ```  
    Module mainModule  
        Function Main(ByVal cmdArgs() As String) As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            ' On return, assign appropriate value to returnValue.  
            ' 0 usually means successful completion.  
            MsgBox("The application is terminating with error level " &  
                 CStr(returnValue) & ".")  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
-   <span data-ttu-id="2e231-132">您可以声明`Main`来检查命令行参数而不是会返回退出代码，按如下所示。</span><span class="sxs-lookup"><span data-stu-id="2e231-132">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>  
  
    ```  
    Module mainModule  
        Sub Main(ByVal cmdArgs() As String)  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2e231-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e231-133">See also</span></span>
- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="2e231-134">Visual Basic 程序的结构</span><span class="sxs-lookup"><span data-stu-id="2e231-134">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="2e231-135">/main</span><span class="sxs-lookup"><span data-stu-id="2e231-135">/main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)
- [<span data-ttu-id="2e231-136">Shared</span><span class="sxs-lookup"><span data-stu-id="2e231-136">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="2e231-137">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="2e231-137">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="2e231-138">Function 语句</span><span class="sxs-lookup"><span data-stu-id="2e231-138">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="2e231-139">Integer 数据类型</span><span class="sxs-lookup"><span data-stu-id="2e231-139">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="2e231-140">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="2e231-140">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)

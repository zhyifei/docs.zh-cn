---
title: 如何：创建和使用程序集使用命令行 (Visual Basic)
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
ms.openlocfilehash: eecd644a7b91492f0a78cf969cfa71ae927609ab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819393"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a><span data-ttu-id="6dbbd-102">如何：创建和使用程序集使用命令行 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6dbbd-102">How to: Create and Use Assemblies Using the Command Line (Visual Basic)</span></span>
<span data-ttu-id="6dbbd-103">程序集或动态链接库 (DLL) 会在运行时链接到程序。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="6dbbd-104">为了演示如何生成和使用 DLL，请考虑以下方案：</span><span class="sxs-lookup"><span data-stu-id="6dbbd-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="6dbbd-105">`MathLibrary.DLL`：包含要在运行时调用的方法的库文件。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="6dbbd-106">在此示例中，DLL 包含两个方法，即 `Add` 和 `Multiply`。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="6dbbd-107">`Add`：包含方法 `Add` 的源文件。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="6dbbd-108">它返回其参数的总和。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="6dbbd-109">包含方法 `Add` 的类 `AddClass` 是命名空间 `UtilityMethods` 的成员。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="6dbbd-110">`Mult`：包含方法 `Multiply` 的源代码。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="6dbbd-111">它返回其参数的乘积。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-111">It returns the product of its parameters.</span></span> <span data-ttu-id="6dbbd-112">包含方法 `Multiply` 的类 `MultiplyClass` 也是命名空间 `UtilityMethods` 的成员。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="6dbbd-113">`TestCode`：包含 `Main` 方法的文件。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="6dbbd-114">它使用 DLL 文件中的方法计算运行时参数的总和与乘积。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6dbbd-115">示例</span><span class="sxs-lookup"><span data-stu-id="6dbbd-115">Example</span></span>  
  
```vb  
' File: Add.vb   
Namespace UtilityMethods  
    Public Class AddClass  
        Public Shared Function Add(ByVal i As Long, ByVal j As Long) As Long  
            Return i + j  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: Mult.vb  
Namespace UtilityMethods  
    Public Class MultiplyClass  
        Public Shared Function Multiply(ByVal x As Long, ByVal y As Long) As Long  
            Return x * y  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: TestCode.vb  
  
Imports UtilityMethods  
  
Module Test  
  
    Sub Main(ByVal args As String())  
  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:")  
  
        If args.Length <> 2 Then  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>")  
            Return  
        End If  
  
        Dim num1 As Long = Long.Parse(args(0))  
        Dim num2 As Long = Long.Parse(args(1))  
  
        Dim sum As Long = AddClass.Add(num1, num2)  
        Dim product As Long = MultiplyClass.Multiply(num1, num2)  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum)  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product)  
  
    End Sub  
  
End Module  
  
' Output (assuming 1234 and 5678 are entered as command-line arguments):  
' Calling methods from MathLibrary.DLL:  
' 1234 + 5678 = 6912  
' 1234 * 5678 = 7006652  
```  
  
 <span data-ttu-id="6dbbd-116">此文件包含使用 DLL 方法 `Add` 和 `Multiply` 的算法。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="6dbbd-117">它首先分析从命令行输入的参数 `num1` 和 `num2`。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="6dbbd-118">然后通过对 `AddClass` 类使用 `Add` 方法来计算总和，并通过对 `MultiplyClass` 类使用 `Multiply` 方法来计算乘积。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="6dbbd-119">请注意，`Imports`文件的开头的语句，可使用非限定的类名来引用 DLL 方法在编译时，按如下所示：</span><span class="sxs-lookup"><span data-stu-id="6dbbd-119">Notice that the  `Imports` statement at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 <span data-ttu-id="6dbbd-120">否则，你必须使用完全限定的名称，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6dbbd-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a><span data-ttu-id="6dbbd-121">执行</span><span class="sxs-lookup"><span data-stu-id="6dbbd-121">Execution</span></span>  
 <span data-ttu-id="6dbbd-122">若要运行程序，请输入 EXE 文件的名称，后跟两个数字，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6dbbd-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6dbbd-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="6dbbd-123">Compiling the Code</span></span>  
 <span data-ttu-id="6dbbd-124">若要生成文件 `MathLibrary.DLL`，请使用以下命令行编译两个文件 `Add` 和 `Mult`。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```console  
vbc -target:library -out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 <span data-ttu-id="6dbbd-125">[-目标 (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md)编译器选项告知编译器输出 DLL 而不是 EXE 文件。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-125">The [-target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="6dbbd-126">[-Out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md)跟文件名称的编译器选项用于指定 DLL 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-126">The [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="6dbbd-127">否则，编译器使用第一个文件 (`Add.vb`) 作为 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-127">Otherwise, the compiler uses the first file (`Add.vb`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="6dbbd-128">若要生成可执行文件 `TestCode.exe`，请使用以下命令行：</span><span class="sxs-lookup"><span data-stu-id="6dbbd-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```console  
vbc -out:TestCode.exe -reference:MathLibrary.DLL TestCode.vb  
```  
  
 <span data-ttu-id="6dbbd-129">**-Out**编译器选项告知编译器输出 EXE 文件，并指定输出文件的名称 (`TestCode.exe`)。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-129">The **-out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="6dbbd-130">此编译器选项是可选的。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-130">This compiler option is optional.</span></span> <span data-ttu-id="6dbbd-131">[的引用 (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md)编译器选项指定此程序使用的 DLL 文件。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-131">The [-reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) compiler option specifies the DLL file or files that this program uses.</span></span>  
  
 <span data-ttu-id="6dbbd-132">有关从命令行生成的详细信息，请参阅并[从命令行生成](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="6dbbd-132">For more information about building from the command line, see  and [Building from the Command Line](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dbbd-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="6dbbd-133">See also</span></span>

- [<span data-ttu-id="6dbbd-134">编程概念</span><span class="sxs-lookup"><span data-stu-id="6dbbd-134">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="6dbbd-135">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="6dbbd-135">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="6dbbd-136">创建用于容纳 DLL 函数的类</span><span class="sxs-lookup"><span data-stu-id="6dbbd-136">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)

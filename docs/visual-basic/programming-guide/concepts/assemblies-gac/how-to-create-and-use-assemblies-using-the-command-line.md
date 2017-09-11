---
title: "如何︰ 创建和使用程序集使用命令行 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 69e9cab9dda1fefe8bee3dc46b541313d1d80e58
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a><span data-ttu-id="20031-102">如何︰ 创建和使用程序集使用命令行 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20031-102">How to: Create and Use Assemblies Using the Command Line (Visual Basic)</span></span>
<span data-ttu-id="20031-103">在运行时，程序集或动态链接库 (DLL) 到您的程序链接。</span><span class="sxs-lookup"><span data-stu-id="20031-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="20031-104">为了说明如何生成和使用 DLL，请考虑以下方案︰</span><span class="sxs-lookup"><span data-stu-id="20031-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="20031-105">`MathLibrary.DLL`︰ 包含要在运行时调用的方法的库文件。</span><span class="sxs-lookup"><span data-stu-id="20031-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="20031-106">在此示例中，该 DLL 包含两个方法，`Add`和`Multiply`。</span><span class="sxs-lookup"><span data-stu-id="20031-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="20031-107">`Add`︰ 包含的方法在源文件`Add`。</span><span class="sxs-lookup"><span data-stu-id="20031-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="20031-108">它返回其参数的总和。</span><span class="sxs-lookup"><span data-stu-id="20031-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="20031-109">此类`AddClass`，其中包含该方法`Add`是命名空间的成员`UtilityMethods`。</span><span class="sxs-lookup"><span data-stu-id="20031-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="20031-110">`Mult`︰ 包含的方法源代码`Multiply`。</span><span class="sxs-lookup"><span data-stu-id="20031-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="20031-111">它返回其参数的乘积。</span><span class="sxs-lookup"><span data-stu-id="20031-111">It returns the product of its parameters.</span></span> <span data-ttu-id="20031-112">此类`MultiplyClass`，其中包含该方法`Multiply`也是命名空间的成员`UtilityMethods`。</span><span class="sxs-lookup"><span data-stu-id="20031-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="20031-113">`TestCode`︰ 该文件包含`Main`方法。</span><span class="sxs-lookup"><span data-stu-id="20031-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="20031-114">它使用 DLL 文件中的方法来计算 sum 和运行时参数的乘积。</span><span class="sxs-lookup"><span data-stu-id="20031-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20031-115">示例</span><span class="sxs-lookup"><span data-stu-id="20031-115">Example</span></span>  
  
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
  
 <span data-ttu-id="20031-116">此文件包含使用 DLL 的方法，该算法`Add`和`Multiply`。</span><span class="sxs-lookup"><span data-stu-id="20031-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="20031-117">它首先分析命令行中输入的参数`num1`和`num2`。</span><span class="sxs-lookup"><span data-stu-id="20031-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="20031-118">然后它通过使用计算总和`Add`方法`AddClass`类，并且通过使用产品`Multiply`方法`MultiplyClass`类。</span><span class="sxs-lookup"><span data-stu-id="20031-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="20031-119">请注意，`Imports`语句开头的文件使您能够使用非限定的类名来引用 DLL 方法在编译时，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="20031-119">Notice that the  `Imports` statement at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 <span data-ttu-id="20031-120">否则，您必须使用完全限定的名，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="20031-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a><span data-ttu-id="20031-121">执行</span><span class="sxs-lookup"><span data-stu-id="20031-121">Execution</span></span>  
 <span data-ttu-id="20031-122">若要运行该程序，请输入跟两个数字，如下所示的 EXE 文件的名称︰</span><span class="sxs-lookup"><span data-stu-id="20031-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="20031-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="20031-123">Compiling the Code</span></span>  
 <span data-ttu-id="20031-124">若要生成文件`MathLibrary.DLL`，编译两个文件`Add`和`Mult`通过使用下面的命令行。</span><span class="sxs-lookup"><span data-stu-id="20031-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```vb  
vbc /target:library /out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 <span data-ttu-id="20031-125">[/Target (Visual Basic 中)](../../../../visual-basic/reference/command-line-compiler/target.md)编译器选项指示编译器将输出 DLL 而不是 EXE 文件。</span><span class="sxs-lookup"><span data-stu-id="20031-125">The [/target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="20031-126">[/输出 (Visual Basic 中)](../../../../visual-basic/reference/command-line-compiler/out.md)跟文件的名称的编译器选项用于指定 DLL 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="20031-126">The [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="20031-127">否则，编译器将使用第一个文件 (`Add.vb`) 作为 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="20031-127">Otherwise, the compiler uses the first file (`Add.vb`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="20031-128">若要生成可执行文件， `TestCode.exe`，使用下面的命令行︰</span><span class="sxs-lookup"><span data-stu-id="20031-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```vb  
vbc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.vb  
```  
  
 <span data-ttu-id="20031-129">**/Out**编译器选项会告知编译器输出的 EXE 文件，并指定输出文件的名称 (`TestCode.exe`)。</span><span class="sxs-lookup"><span data-stu-id="20031-129">The **/out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="20031-130">此编译器选项是可选的。</span><span class="sxs-lookup"><span data-stu-id="20031-130">This compiler option is optional.</span></span> <span data-ttu-id="20031-131">[/Reference (Visual Basic 中)](../../../../visual-basic/reference/command-line-compiler/reference.md)编译器选项指定的 DLL 文件或该程序使用的文件。</span><span class="sxs-lookup"><span data-stu-id="20031-131">The [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) compiler option specifies the DLL file or files that this program uses.</span></span>  
  
 <span data-ttu-id="20031-132">有关从命令行生成的详细信息，请参阅和[从命令行生成](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="20031-132">For more information about building from the command line, see  and [Building from the Command Line](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20031-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20031-133">See Also</span></span>  
 <span data-ttu-id="20031-134">[编程概念](../../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="20031-134">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="20031-135"> [程序集和全局程序集缓存 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="20031-135"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="20031-136"> [创建用于容纳 DLL 函数的类](http://msdn.microsoft.com/library/e08e4c34-0223-45f7-aa55-a3d8dd979b0f)</span><span class="sxs-lookup"><span data-stu-id="20031-136"> [Creating a Class to Hold DLL Functions](http://msdn.microsoft.com/library/e08e4c34-0223-45f7-aa55-a3d8dd979b0f)</span></span>

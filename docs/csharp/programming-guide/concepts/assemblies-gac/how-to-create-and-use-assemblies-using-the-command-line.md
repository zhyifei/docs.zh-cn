---
title: 如何：使用命令行创建和使用程序集 (C#)
ms.date: 07/20/2015
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
ms.openlocfilehash: 0cb964991cdbcdb3fa528ac96a0e883a37439099
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514550"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a><span data-ttu-id="a5ae2-102">如何：使用命令行创建和使用程序集 (C#)</span><span class="sxs-lookup"><span data-stu-id="a5ae2-102">How to: Create and Use Assemblies Using the Command Line (C#)</span></span>
<span data-ttu-id="a5ae2-103">程序集或动态链接库 (DLL) 会在运行时链接到程序。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="a5ae2-104">为了演示如何生成和使用 DLL，请考虑以下方案：</span><span class="sxs-lookup"><span data-stu-id="a5ae2-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="a5ae2-105">`MathLibrary.DLL`：包含要在运行时调用的方法的库文件。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="a5ae2-106">在此示例中，DLL 包含两个方法，即 `Add` 和 `Multiply`。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="a5ae2-107">`Add`：包含方法 `Add` 的源文件。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="a5ae2-108">它返回其参数的总和。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="a5ae2-109">包含方法 `Add` 的类 `AddClass` 是命名空间 `UtilityMethods` 的成员。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="a5ae2-110">`Mult`：包含方法 `Multiply` 的源代码。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="a5ae2-111">它返回其参数的乘积。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-111">It returns the product of its parameters.</span></span> <span data-ttu-id="a5ae2-112">包含方法 `Multiply` 的类 `MultiplyClass` 也是命名空间 `UtilityMethods` 的成员。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="a5ae2-113">`TestCode`：包含 `Main` 方法的文件。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="a5ae2-114">它使用 DLL 文件中的方法计算运行时参数的总和与乘积。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5ae2-115">示例</span><span class="sxs-lookup"><span data-stu-id="a5ae2-115">Example</span></span>  
  
```csharp  
// File: Add.cs   
namespace UtilityMethods  
{  
    public class AddClass   
    {  
        public static long Add(long i, long j)   
        {   
            return (i + j);  
        }  
    }  
}  
```  
  
```csharp  
// File: Mult.cs  
namespace UtilityMethods   
{  
    public class MultiplyClass  
    {  
        public static long Multiply(long x, long y)   
        {  
            return (x * y);   
        }  
    }  
}  
```  
  
```csharp  
// File: TestCode.cs  
  
using UtilityMethods;  
  
class TestCode  
{  
    static void Main(string[] args)   
    {  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:");  
  
        if (args.Length != 2)  
        {  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>");  
            return;  
        }  
  
        long num1 = long.Parse(args[0]);  
        long num2 = long.Parse(args[1]);  
  
        long sum = AddClass.Add(num1, num2);  
        long product = MultiplyClass.Multiply(num1, num2);  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum);  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product);  
    }  
}  
/* Output (assuming 1234 and 5678 are entered as command-line arguments):  
    Calling methods from MathLibrary.DLL:  
    1234 + 5678 = 6912  
    1234 * 5678 = 7006652          
*/  
```  
  
 <span data-ttu-id="a5ae2-116">此文件包含使用 DLL 方法 `Add` 和 `Multiply` 的算法。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="a5ae2-117">它首先分析从命令行输入的参数 `num1` 和 `num2`。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="a5ae2-118">然后通过对 `AddClass` 类使用 `Add` 方法来计算总和，并通过对 `MultiplyClass` 类使用 `Multiply` 方法来计算乘积。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="a5ae2-119">请注意，文件开头的 `using` 指令使你可以使用非限定类名在编译时引用 DLL 方法，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5ae2-119">Notice that the `using` directive at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 <span data-ttu-id="a5ae2-120">否则，你必须使用完全限定的名称，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5ae2-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a><span data-ttu-id="a5ae2-121">执行</span><span class="sxs-lookup"><span data-stu-id="a5ae2-121">Execution</span></span>  
 <span data-ttu-id="a5ae2-122">若要运行程序，请输入 EXE 文件的名称，后跟两个数字，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a5ae2-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a5ae2-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="a5ae2-123">Compiling the Code</span></span>  
 <span data-ttu-id="a5ae2-124">若要生成文件 `MathLibrary.DLL`，请使用以下命令行编译两个文件 `Add` 和 `Mult`。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```csharp  
csc /target:library /out:MathLibrary.DLL Add.cs Mult.cs  
```  
  
 <span data-ttu-id="a5ae2-125">[/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) 编译器选项告知编译器输出 DLL 而不是 EXE 文件。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-125">The [/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="a5ae2-126">后跟文件名的 [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) 编译器选项用于指定 DLL 文件名。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-126">The [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="a5ae2-127">否则，编译器使用第一个文件 (`Add.cs`) 作为 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-127">Otherwise, the compiler uses the first file (`Add.cs`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="a5ae2-128">若要生成可执行文件 `TestCode.exe`，请使用以下命令行：</span><span class="sxs-lookup"><span data-stu-id="a5ae2-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```csharp  
csc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.cs  
```  
  
 <span data-ttu-id="a5ae2-129">**/out** 编译器选项告知编译器输出 EXE 文件并指定输出文件的名称 (`TestCode.exe`)。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-129">The **/out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="a5ae2-130">此编译器选项是可选的。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-130">This compiler option is optional.</span></span> <span data-ttu-id="a5ae2-131">[/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) 编译器选项指定此程序使用的 DLL 文件。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-131">The [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) compiler option specifies the DLL file or files that this program uses.</span></span> <span data-ttu-id="a5ae2-132">有关详细信息，请参阅 [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-132">For more information, see [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="a5ae2-133">有关从命令行进行生成的详细信息，请参阅[在命令行上使用 csc.exe 生成](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="a5ae2-133">For more information about building from the command line, see [Command-line Building With csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5ae2-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5ae2-134">See Also</span></span>

- [<span data-ttu-id="a5ae2-135">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a5ae2-135">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a5ae2-136">程序集和全局程序集缓存 (C#)</span><span class="sxs-lookup"><span data-stu-id="a5ae2-136">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
- [<span data-ttu-id="a5ae2-137">创建用于容纳 DLL 函数的类</span><span class="sxs-lookup"><span data-stu-id="a5ae2-137">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)

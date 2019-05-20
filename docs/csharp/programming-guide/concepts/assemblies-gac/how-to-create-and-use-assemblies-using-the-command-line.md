---
title: 如何：使用命令行创建和使用程序集 (C#)
ms.date: 07/20/2015
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
ms.openlocfilehash: 12d23816b740816bd357c3c2ac57583f31bf3cb3
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586033"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a><span data-ttu-id="b6235-102">如何：使用命令行创建和使用程序集 (C#)</span><span class="sxs-lookup"><span data-stu-id="b6235-102">How to: Create and Use Assemblies Using the Command Line (C#)</span></span>
<span data-ttu-id="b6235-103">程序集或动态链接库 (DLL) 会在运行时链接到程序。</span><span class="sxs-lookup"><span data-stu-id="b6235-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="b6235-104">为了演示如何生成和使用 DLL，请考虑以下方案：</span><span class="sxs-lookup"><span data-stu-id="b6235-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
- <span data-ttu-id="b6235-105">`MathLibrary.DLL`：包含要在运行时调用的方法的库文件。</span><span class="sxs-lookup"><span data-stu-id="b6235-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="b6235-106">在此示例中，DLL 包含两个方法，即 `Add` 和 `Multiply`。</span><span class="sxs-lookup"><span data-stu-id="b6235-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
- <span data-ttu-id="b6235-107">`Add`：包含方法 `Add` 的源文件。</span><span class="sxs-lookup"><span data-stu-id="b6235-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="b6235-108">它返回其参数的总和。</span><span class="sxs-lookup"><span data-stu-id="b6235-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="b6235-109">包含方法 `Add` 的类 `AddClass` 是命名空间 `UtilityMethods` 的成员。</span><span class="sxs-lookup"><span data-stu-id="b6235-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="b6235-110">`Mult`：包含方法 `Multiply` 的源代码。</span><span class="sxs-lookup"><span data-stu-id="b6235-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="b6235-111">它返回其参数的乘积。</span><span class="sxs-lookup"><span data-stu-id="b6235-111">It returns the product of its parameters.</span></span> <span data-ttu-id="b6235-112">包含方法 `Multiply` 的类 `MultiplyClass` 也是命名空间 `UtilityMethods` 的成员。</span><span class="sxs-lookup"><span data-stu-id="b6235-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="b6235-113">`TestCode`：包含 `Main` 方法的文件。</span><span class="sxs-lookup"><span data-stu-id="b6235-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="b6235-114">它使用 DLL 文件中的方法计算运行时参数的总和与乘积。</span><span class="sxs-lookup"><span data-stu-id="b6235-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6235-115">示例</span><span class="sxs-lookup"><span data-stu-id="b6235-115">Example</span></span>  
  
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
  
 <span data-ttu-id="b6235-116">此文件包含使用 DLL 方法 `Add` 和 `Multiply` 的算法。</span><span class="sxs-lookup"><span data-stu-id="b6235-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="b6235-117">它首先分析从命令行输入的参数 `num1` 和 `num2`。</span><span class="sxs-lookup"><span data-stu-id="b6235-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="b6235-118">然后通过对 `AddClass` 类使用 `Add` 方法来计算总和，并通过对 `MultiplyClass` 类使用 `Multiply` 方法来计算乘积。</span><span class="sxs-lookup"><span data-stu-id="b6235-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="b6235-119">请注意，文件开头的 `using` 指令使你可以使用非限定类名在编译时引用 DLL 方法，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6235-119">Notice that the `using` directive at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 <span data-ttu-id="b6235-120">否则，你必须使用完全限定的名称，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6235-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a><span data-ttu-id="b6235-121">执行</span><span class="sxs-lookup"><span data-stu-id="b6235-121">Execution</span></span>  
 <span data-ttu-id="b6235-122">若要运行程序，请输入 EXE 文件的名称，后跟两个数字，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6235-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="see-also"></a><span data-ttu-id="b6235-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6235-123">See also</span></span>

- [<span data-ttu-id="b6235-124">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b6235-124">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="b6235-125">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="b6235-125">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="b6235-126">创建用于容纳 DLL 函数的类</span><span class="sxs-lookup"><span data-stu-id="b6235-126">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)

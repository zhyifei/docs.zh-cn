---
title: "#<a name=\"line-c-reference\"></a>line（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#line'
helpviewer_keywords: '#line directive [C#]'
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d2f42915d214349eebff40949482d7f603c0c2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="line-c-reference"></a><span data-ttu-id="b96b8-102">#line（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b96b8-102">#line (C# Reference)</span></span>
<span data-ttu-id="b96b8-103">`#line` 可修改编译器的行号及（可选）用于错误和警告的文件名输出。</span><span class="sxs-lookup"><span data-stu-id="b96b8-103">`#line` lets you modify the compiler's line number and (optionally) the file name output for errors and warnings.</span></span> <span data-ttu-id="b96b8-104">此示例演示如何报告与行号相关联的两个警告。</span><span class="sxs-lookup"><span data-stu-id="b96b8-104">This example shows how to report two warnings associated with line numbers.</span></span> <span data-ttu-id="b96b8-105">`#line 200` 指令将行号强制设为 200（尽管默认值为 #7），直到下一个 #line 指令前，文件名都将报告为“特殊”。</span><span class="sxs-lookup"><span data-stu-id="b96b8-105">The `#line 200` directive forces the line number to be 200 (although the default is #7) and until the next #line directive, the filename will be reported as "Special".</span></span> <span data-ttu-id="b96b8-106">#line 默认指令将行号返回至其默认行号，默认行号对由上个指令重新编号的行进行计数。</span><span class="sxs-lookup"><span data-stu-id="b96b8-106">The #line default directive returns the line numbering to its default numbering, which counts the lines that were renumbered by the previous directive.</span></span>  
  
```csharp
class MainClass  
{  
    static void Main()  
    {  
#line 200 "Special"  
        int i;    // CS0168 on line 200  
        int j;    // CS0168 on line 201  
#line default  
        char c;   // CS0168 on line 9  
        float f;  // CS0168 on line 10  
#line hidden // numbering not affected  
        string s;   
        double d; // CS0168 on line 13  
    }  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="b96b8-107">备注</span><span class="sxs-lookup"><span data-stu-id="b96b8-107">Remarks</span></span>  
 <span data-ttu-id="b96b8-108">可在生成过程的自动、中间步骤中使用 `#line` 指令。</span><span class="sxs-lookup"><span data-stu-id="b96b8-108">The `#line` directive might be used in an automated, intermediate step in the build process.</span></span> <span data-ttu-id="b96b8-109">例如，如果已从原始源代码文件中删除行，但仍希望编译器基于文件中的原始行号生成输出，可在删除行后，使用 `#line` 来模拟原始行号。</span><span class="sxs-lookup"><span data-stu-id="b96b8-109">For example, if lines were removed from the original source code file, but you still wanted the compiler to generate output based on the original line numbering in the file, you could remove lines and then simulate the original line numbering with `#line`.</span></span>  
  
 <span data-ttu-id="b96b8-110">`#line hidden` 指令能对调试程序隐藏连续行，当开发者逐行执行代码时，介于 `#line hidden` 和下一 `#line` 指令（假设它不是其他 `#line hidden` 指令）间的任何行都将被跳过。</span><span class="sxs-lookup"><span data-stu-id="b96b8-110">The `#line hidden` directive hides the successive lines from the debugger, such that when the developer steps through the code, any lines between a `#line hidden` and the next `#line` directive (assuming that it is not another `#line hidden` directive) will be stepped over.</span></span> <span data-ttu-id="b96b8-111">还可通过此选项允许 ASP.NET 区分用户定义和计算机生成的代码。</span><span class="sxs-lookup"><span data-stu-id="b96b8-111">This option can also be used to allow ASP.NET to differentiate between user-defined and machine-generated code.</span></span> <span data-ttu-id="b96b8-112">虽然此功能主要用于 ASP.NET，但可能更多的源生成器会利用此功能。</span><span class="sxs-lookup"><span data-stu-id="b96b8-112">Although ASP.NET is the primary consumer of this feature, it is likely that more source generators will make use of it.</span></span>  
  
 <span data-ttu-id="b96b8-113">`#line hidden` 指令不影响错误报告中的文件名或行号。</span><span class="sxs-lookup"><span data-stu-id="b96b8-113">A `#line hidden` directive does not affect file names or line numbers in error reporting.</span></span> <span data-ttu-id="b96b8-114">也就是说，如果在隐藏块中遇到错误，编译器将报告错误的当前文件名和行号。</span><span class="sxs-lookup"><span data-stu-id="b96b8-114">That is, if an error is encountered in a hidden block, the compiler will report the current file name and line number of the error.</span></span>  
  
 <span data-ttu-id="b96b8-115">`#line filename` 指令可指定要在编译器输出中显示的文件名。</span><span class="sxs-lookup"><span data-stu-id="b96b8-115">The `#line filename` directive specifies the file name you want to appear in the compiler output.</span></span> <span data-ttu-id="b96b8-116">默认情况下，将使用源代码文件的实际名称。</span><span class="sxs-lookup"><span data-stu-id="b96b8-116">By default, the actual name of the source code file is used.</span></span> <span data-ttu-id="b96b8-117">该文件名必须以双引号 ("") 引起来，且必须位于行号之后。</span><span class="sxs-lookup"><span data-stu-id="b96b8-117">The file name must be in double quotation marks ("") and must be preceded by a line number.</span></span>  
  
 <span data-ttu-id="b96b8-118">源代码文件中可包含任意数目的 `#line` 指令。</span><span class="sxs-lookup"><span data-stu-id="b96b8-118">A source code file can have any number of `#line` directives.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="b96b8-119">示例 1</span><span class="sxs-lookup"><span data-stu-id="b96b8-119">Example 1</span></span>  
 <span data-ttu-id="b96b8-120">下列示例演示调试程序如何忽略代码中的隐藏行。</span><span class="sxs-lookup"><span data-stu-id="b96b8-120">The following example shows how the debugger ignores the hidden lines in the code.</span></span> <span data-ttu-id="b96b8-121">运行示例时，它将显示三行文本。</span><span class="sxs-lookup"><span data-stu-id="b96b8-121">When you run the example, it will display three lines of text.</span></span> <span data-ttu-id="b96b8-122">但是，如果按照示例所示设置断点、并按 F10 逐行执行代码，可观察到调试程序忽略隐藏行。</span><span class="sxs-lookup"><span data-stu-id="b96b8-122">However, when you set a break point, as shown in the example, and hit F10 to step through the code, you will notice that the debugger ignores the hidden line.</span></span> <span data-ttu-id="b96b8-123">另请注意，即使在隐藏行设置断点，调试程序仍将忽略它。</span><span class="sxs-lookup"><span data-stu-id="b96b8-123">Notice also that even if you set a break point at the hidden line, the debugger will still ignore it.</span></span>  
  
```csharp
// preprocessor_linehidden.cs  
using System;  
class MainClass   
{  
    static void Main()   
    {  
        Console.WriteLine("Normal line #1."); // Set break point here.  
#line hidden  
        Console.WriteLine("Hidden line.");  
#line default  
        Console.WriteLine("Normal line #2.");  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b96b8-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b96b8-124">See Also</span></span>  
 [<span data-ttu-id="b96b8-125">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b96b8-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b96b8-126">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b96b8-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b96b8-127">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="b96b8-127">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

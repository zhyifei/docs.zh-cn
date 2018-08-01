---
title: '#define（C# 参考）'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: f40c32a89641256e4f8fe30cd24f523b898139d5
ms.sourcegitcommit: dc02d7d95f1e3efcc7166eaf431b0ec0dc9d8dca
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2018
ms.locfileid: "37143474"
---
# <a name="define-c-reference"></a><span data-ttu-id="f1c44-102">#define（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="f1c44-102">#define (C# Reference)</span></span>
<span data-ttu-id="f1c44-103">使用 `#define` 来定义符号。</span><span class="sxs-lookup"><span data-stu-id="f1c44-103">You use `#define` to define a symbol.</span></span> <span data-ttu-id="f1c44-104">将符号用作传递给 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 指令的表达式时，该表达式的计算结果为 `true`，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="f1c44-104">When you use the symbol as the expression that's passed to the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  
 
 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a><span data-ttu-id="f1c44-105">备注</span><span class="sxs-lookup"><span data-stu-id="f1c44-105">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1c44-106">`#define` 指令不能用于声明常量值，这与 C 和 C++ 中的通常做法一样。</span><span class="sxs-lookup"><span data-stu-id="f1c44-106">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="f1c44-107">C# 中的常量最好定义为类或结构的静态成员。</span><span class="sxs-lookup"><span data-stu-id="f1c44-107">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="f1c44-108">如果具有多个此类常量，请考虑创建一个单独的“常量”类来容纳它们。</span><span class="sxs-lookup"><span data-stu-id="f1c44-108">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="f1c44-109">符号可用于指定编译的条件。</span><span class="sxs-lookup"><span data-stu-id="f1c44-109">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="f1c44-110">可通过 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 或 [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) 测试符号。</span><span class="sxs-lookup"><span data-stu-id="f1c44-110">You can test for the symbol with either [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).</span></span> <span data-ttu-id="f1c44-111">还可以使用 `conditional` 属性来执行条件编译。</span><span class="sxs-lookup"><span data-stu-id="f1c44-111">You can also use the `conditional` attribute to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="f1c44-112">可以定义一个符号，但不能向符号分配值。</span><span class="sxs-lookup"><span data-stu-id="f1c44-112">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="f1c44-113">文件中必须先出现 `#define` 指令，才能使用并非同时也是预处理器指令的任何指示。</span><span class="sxs-lookup"><span data-stu-id="f1c44-113">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="f1c44-114">还可以通过 [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 编译器选项来定义符号。</span><span class="sxs-lookup"><span data-stu-id="f1c44-114">You can also define a symbol with the [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="f1c44-115">可以通过 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) 取消定义符号。</span><span class="sxs-lookup"><span data-stu-id="f1c44-115">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="f1c44-116">使用 `-define` 或 `#define` 定义的符号与具有相同名称的变量不冲突。</span><span class="sxs-lookup"><span data-stu-id="f1c44-116">A symbol that you define with `-define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="f1c44-117">也就是说，变量名称不应传递给预处理器指令，且符号仅能由预处理器指令评估。</span><span class="sxs-lookup"><span data-stu-id="f1c44-117">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="f1c44-118">使用 `#define` 创建的符号的作用域是在其中定义该符号的文件。</span><span class="sxs-lookup"><span data-stu-id="f1c44-118">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="f1c44-119">如以下示例所示，必须将 `#define` 指令放在文件顶部。</span><span class="sxs-lookup"><span data-stu-id="f1c44-119">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 <span data-ttu-id="f1c44-120">有关如何取消对符号进行定义的示例，请参阅 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)。</span><span class="sxs-lookup"><span data-stu-id="f1c44-120">For an example of how to undefine a symbol, see [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c44-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1c44-121">See Also</span></span>  
 [<span data-ttu-id="f1c44-122">C# 参考</span><span class="sxs-lookup"><span data-stu-id="f1c44-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f1c44-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f1c44-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f1c44-124">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="f1c44-124">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
 [<span data-ttu-id="f1c44-125">const</span><span class="sxs-lookup"><span data-stu-id="f1c44-125">const</span></span>](../../../csharp/language-reference/keywords/const.md)  
 [<span data-ttu-id="f1c44-126">如何：使用跟踪和调试进行条件编译</span><span class="sxs-lookup"><span data-stu-id="f1c44-126">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)  
 [<span data-ttu-id="f1c44-127">#undef</span><span class="sxs-lookup"><span data-stu-id="f1c44-127">#undef</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)  
 [<span data-ttu-id="f1c44-128">#if</span><span class="sxs-lookup"><span data-stu-id="f1c44-128">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)

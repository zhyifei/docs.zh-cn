---
title: Main() 和命令行参数（C# 编程指南）
ms.date: 08/02/2017
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
ms.openlocfilehash: 03d6e7185a0a16589fb612724be52ce51e813173
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="ce2d0-102">Main() 和命令行参数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="ce2d0-102">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="ce2d0-103">`Main` 方法是 C# 应用程序的入口点。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-103">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="ce2d0-104">（库和服务不要求使用 `Main` 方法作为入口点）。`Main` 方法是应用程序启动后调用的第一个方法。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-104">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

 <span data-ttu-id="ce2d0-105">C# 程序中只能有一个入口点。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-105">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="ce2d0-106">如果多个类包含 `Main` 方法，必须使用 **/main** 编译器选项来编译程序，以指定将哪个 `Main` 方法用作入口点。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-106">If you have more than one class that has a `Main` method, you must compile your program with the **/main** compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="ce2d0-107">有关详细信息，请参阅 [/main（C# 编译器选项）](../../../csharp/language-reference/compiler-options/main-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-107">For more information, see [/main (C# Compiler Options)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span></span>

 [!code-csharp[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]

## <a name="overview"></a><span data-ttu-id="ce2d0-108">概述</span><span class="sxs-lookup"><span data-stu-id="ce2d0-108">Overview</span></span>

- <span data-ttu-id="ce2d0-109">`Main` 方法是可执行程序的入口点，也是程序控制开始和结束的位置。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-109">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="ce2d0-110">`Main` 在类或结构中声明。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-110">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="ce2d0-111">`Main` 必须是[静态](../../../csharp/language-reference/keywords/static.md)方法，不得为[公共](../../../csharp/language-reference/keywords/public.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-111">`Main` must be [static](../../../csharp/language-reference/keywords/static.md) and it need not be [public](../../../csharp/language-reference/keywords/public.md).</span></span> <span data-ttu-id="ce2d0-112">（在前面的示例中，它获得的是[私有](../../../csharp/language-reference/keywords/private.md)成员的默认访问权限）。封闭类或结构不一定要是静态的。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-112">(In the earlier example, it receives the default access of [private](../../../csharp/language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="ce2d0-113">`Main` 可以具有 `void`、`int`，或者以 C# 7.1、`Task` 或 `Task<int>` 返回类型开头。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-113">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="ce2d0-114">当且仅当 `Main` 返回 `Task` 或 `Task<int>` 时，`Main` 的声明可包括 [`async`](../../language-reference/keywords/async.md) 修饰符。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-114">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="ce2d0-115">请注意，该操作可明确排除 `async void Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-115">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="ce2d0-116">使用或不使用包含命令行自变量的 `string[]` 参数声明 `Main` 方法都行。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-116">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="ce2d0-117">使用 Visual Studio 创建 Windows 应用程序时，可以手动添加此形参，也可以使用 <xref:System.Environment> 类来获取命令行实参。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-117">When using Visual Studio to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment> class to obtain the command-line arguments.</span></span> <span data-ttu-id="ce2d0-118">参数被读取为从零开始编制索引的命令行自变量。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-118">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="ce2d0-119">与 C 和 C++ 不同，程序的名称不被视为第一个命令行自变量。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-119">Unlike C and C++, the name of the program is not treated as the first command-line argument.</span></span>

<span data-ttu-id="ce2d0-120">添加 `async`、`Task` 和 `Task<int>` 返回类型可简化控制台应用程序需要启动时的程序代码，以及 `Main` 中的 `await` 异步操作。</span><span class="sxs-lookup"><span data-stu-id="ce2d0-120">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ce2d0-121">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ce2d0-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ce2d0-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce2d0-122">See also</span></span>
[<span data-ttu-id="ce2d0-123">在命令行上使用 csc.exe 生成</span><span class="sxs-lookup"><span data-stu-id="ce2d0-123">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
[<span data-ttu-id="ce2d0-124">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ce2d0-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="ce2d0-125">方法</span><span class="sxs-lookup"><span data-stu-id="ce2d0-125">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
[<span data-ttu-id="ce2d0-126">在 C# 程序内部</span><span class="sxs-lookup"><span data-stu-id="ce2d0-126">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)  

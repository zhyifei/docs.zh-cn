---
title: Main() 和命令行参数 - C# 编程指南
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
ms.openlocfilehash: 0571ec6dbc42f103ec922a6b2b13a52510640a78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "75700596"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="ac278-102">Main() 和命令行参数（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="ac278-102">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="ac278-103">`Main` 方法是 C# 应用程序的入口点。</span><span class="sxs-lookup"><span data-stu-id="ac278-103">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="ac278-104">（库和服务不要求使用 `Main` 方法作为入口点）。`Main` 方法是应用程序启动后调用的第一个方法。</span><span class="sxs-lookup"><span data-stu-id="ac278-104">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

 <span data-ttu-id="ac278-105">C# 程序中只能有一个入口点。</span><span class="sxs-lookup"><span data-stu-id="ac278-105">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="ac278-106">如果多个类包含 `Main` 方法，必须使用 **/main** 编译器选项来编译程序，以指定将哪个 `Main` 方法用作入口点。</span><span class="sxs-lookup"><span data-stu-id="ac278-106">If you have more than one class that has a `Main` method, you must compile your program with the **/main** compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="ac278-107">有关详细信息，请参阅 [-main（C# 编译器选项）](../../language-reference/compiler-options/main-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="ac278-107">For more information, see [-main (C# Compiler Options)](../../language-reference/compiler-options/main-compiler-option.md).</span></span>

[!code-csharp[csProgGuideMain#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#17)]

## <a name="overview"></a><span data-ttu-id="ac278-108">概述</span><span class="sxs-lookup"><span data-stu-id="ac278-108">Overview</span></span>

- <span data-ttu-id="ac278-109">`Main` 方法是可执行程序的入口点，也是程序控制开始和结束的位置。</span><span class="sxs-lookup"><span data-stu-id="ac278-109">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="ac278-110">`Main` 在类或结构中声明。</span><span class="sxs-lookup"><span data-stu-id="ac278-110">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="ac278-111">`Main` 必须是[静态](../../language-reference/keywords/static.md)方法，不得为[公共](../../language-reference/keywords/public.md)方法。</span><span class="sxs-lookup"><span data-stu-id="ac278-111">`Main` must be [static](../../language-reference/keywords/static.md) and it need not be [public](../../language-reference/keywords/public.md).</span></span> <span data-ttu-id="ac278-112">（在前面的示例中，它获得的是[私有](../../language-reference/keywords/private.md)成员的默认访问权限）。封闭类或结构不一定要是静态的。</span><span class="sxs-lookup"><span data-stu-id="ac278-112">(In the earlier example, it receives the default access of [private](../../language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="ac278-113">`Main` 可以具有 `void`、`int`，或者以 C# 7.1、`Task` 或 `Task<int>` 返回类型开头。</span><span class="sxs-lookup"><span data-stu-id="ac278-113">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="ac278-114">当且仅当 `Main` 返回 `Task` 或 `Task<int>` 时，`Main` 的声明可包括 [`async`](../../language-reference/keywords/async.md) 修饰符。</span><span class="sxs-lookup"><span data-stu-id="ac278-114">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="ac278-115">请注意，该操作可明确排除 `async void Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="ac278-115">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="ac278-116">使用或不使用包含命令行自变量的 `string[]` 参数声明 `Main` 方法都行。</span><span class="sxs-lookup"><span data-stu-id="ac278-116">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="ac278-117">使用 Visual Studio 创建 Windows 应用程序时，可以手动添加此形参，也可以使用 <xref:System.Environment.GetCommandLineArgs> 方法来获取[命令行实参](command-line-arguments.md)。</span><span class="sxs-lookup"><span data-stu-id="ac278-117">When using Visual Studio to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment.GetCommandLineArgs> method to obtain the [command-line arguments](command-line-arguments.md).</span></span> <span data-ttu-id="ac278-118">参数被读取为从零开始编制索引的命令行自变量。</span><span class="sxs-lookup"><span data-stu-id="ac278-118">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="ac278-119">与 C 和 C++ 不同，程序的名称不被视为 `args` 数组中的第一个命令行实参，但它是 <xref:System.Environment.GetCommandLineArgs> 方法中的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="ac278-119">Unlike C and C++, the name of the program is not treated as the first command-line argument in the `args` array, but it is the first element of the <xref:System.Environment.GetCommandLineArgs> method.</span></span>

<span data-ttu-id="ac278-120">以下是有效 `Main` 签名的列表：</span><span class="sxs-lookup"><span data-stu-id="ac278-120">The following is a list of valid `Main` signatures:</span></span>

```csharp
public static void Main() { }
public static int Main() { }
public static void Main(string[] args) { }
public static int Main(string[] args) { }
public static async Task Main() { }
public static async Task<int> Main() { }
public static async Task Main(string[] args) { }
public static async Task<int> Main(string[] args) { }
```

<span data-ttu-id="ac278-121">添加 `async`、`Task` 和 `Task<int>` 返回类型可简化控制台应用程序需要启动时的程序代码，以及 `Main` 中的 `await` 异步操作。</span><span class="sxs-lookup"><span data-stu-id="ac278-121">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ac278-122">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ac278-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ac278-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac278-123">See also</span></span>

- [<span data-ttu-id="ac278-124">在命令行上使用 csc.exe 生成</span><span class="sxs-lookup"><span data-stu-id="ac278-124">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="ac278-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ac278-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ac278-126">方法</span><span class="sxs-lookup"><span data-stu-id="ac278-126">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="ac278-127">在 C# 程序内部</span><span class="sxs-lookup"><span data-stu-id="ac278-127">Inside a C# Program</span></span>](../inside-a-program/index.md)

---
title: C# 7.1 中的新增功能
description: C# 7.1 中的新增功能概述。
ms.date: 04/09/2019
ms.openlocfilehash: c79c8576f9cbbd921ebf30bd84ee5a817d6dc6e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59480958"
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="6b873-103">C# 7.1 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="6b873-103">What's new in C# 7.1</span></span>

<span data-ttu-id="6b873-104">C# 7.1 是 C# 语言的第一个点版本（更新版本）。</span><span class="sxs-lookup"><span data-stu-id="6b873-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="6b873-105">它标志着该语言发布节奏的加速。</span><span class="sxs-lookup"><span data-stu-id="6b873-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="6b873-106">理想情况下，可以在每个新功能准备就绪时更快推出新功能。</span><span class="sxs-lookup"><span data-stu-id="6b873-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="6b873-107">C# 7.1 增加了将编译器配置为匹配特定语言版本的功能。</span><span class="sxs-lookup"><span data-stu-id="6b873-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="6b873-108">从而可以分别制定有关升级语言版本的决策和有关升级工具的决策。</span><span class="sxs-lookup"><span data-stu-id="6b873-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="6b873-109">C# 7.1 增加了[语言版本选择](../language-reference/configure-language-version.md)配置元素、三个新的语言功能和新的编译器行为。</span><span class="sxs-lookup"><span data-stu-id="6b873-109">C# 7.1 adds the [language version selection](../language-reference/configure-language-version.md) configuration element, three new language features, and new compiler behavior.</span></span>

<span data-ttu-id="6b873-110">此版本中新增的语言功能包括：</span><span class="sxs-lookup"><span data-stu-id="6b873-110">The new language features in this release are:</span></span>

* [<span data-ttu-id="6b873-111">`async` `Main` 方法</span><span class="sxs-lookup"><span data-stu-id="6b873-111">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="6b873-112">应用程序的入口点可以含有 `async` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="6b873-112">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="6b873-113">`default` 文本表达式</span><span class="sxs-lookup"><span data-stu-id="6b873-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="6b873-114">在可以推断目标类型的情况下，可在默认值表达式中使用默认文本表达式。</span><span class="sxs-lookup"><span data-stu-id="6b873-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="6b873-115">推断元组元素名称</span><span class="sxs-lookup"><span data-stu-id="6b873-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="6b873-116">在许多情况下，可通过元组初始化来推断元组元素的名称。</span><span class="sxs-lookup"><span data-stu-id="6b873-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>
* [<span data-ttu-id="6b873-117">泛型类型参数的模式匹配</span><span class="sxs-lookup"><span data-stu-id="6b873-117">Pattern matching on generic type parameters</span></span>](#pattern-matching-on-generic-type-parameters)
  - <span data-ttu-id="6b873-118">可以对类型为泛型类型参数的变量使用模式匹配表达式。</span><span class="sxs-lookup"><span data-stu-id="6b873-118">You can use pattern match expressions on variables whose type is a generic type parameter.</span></span>

<span data-ttu-id="6b873-119">最后，编译器有 `/refout` 和 `/refonly` 两个选项，可用于控制[引用程序集生成](#reference-assembly-generation)。</span><span class="sxs-lookup"><span data-stu-id="6b873-119">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

<span data-ttu-id="6b873-120">若要使用单点版本中的最新功能，需要[配置编译器语言版本](../language-reference/configure-language-version.md)并选择版本。</span><span class="sxs-lookup"><span data-stu-id="6b873-120">To use the latest features in a point release, you need to [configure the compiler language version](../language-reference/configure-language-version.md) and select the version.</span></span>

## <a name="async-main"></a><span data-ttu-id="6b873-121">异步 `main` 方法</span><span class="sxs-lookup"><span data-stu-id="6b873-121">Async main</span></span>

<span data-ttu-id="6b873-122">*异步 Main* 方法使你能够在 `Main` 方法中使用 `await` 关键字。</span><span class="sxs-lookup"><span data-stu-id="6b873-122">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="6b873-123">在过去，需要编写：</span><span class="sxs-lookup"><span data-stu-id="6b873-123">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="6b873-124">现在，您可以编写：</span><span class="sxs-lookup"><span data-stu-id="6b873-124">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="6b873-125">如果程序不返回退出代码，可以声明返回 <xref:System.Threading.Tasks.Task> 的 `Main` 方法:</span><span class="sxs-lookup"><span data-stu-id="6b873-125">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="6b873-126">如需了解更多详情，可以阅读编程指南中的[异步 Main](../programming-guide/main-and-command-args/index.md) 一文。</span><span class="sxs-lookup"><span data-stu-id="6b873-126">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) article in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="6b873-127">默认文本表达式</span><span class="sxs-lookup"><span data-stu-id="6b873-127">Default literal expressions</span></span>

<span data-ttu-id="6b873-128">默认文本表达式是针对默认值表达式的一项增强功能。</span><span class="sxs-lookup"><span data-stu-id="6b873-128">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="6b873-129">这些表达式将变量初始化为默认值。</span><span class="sxs-lookup"><span data-stu-id="6b873-129">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="6b873-130">过去会这么编写：</span><span class="sxs-lookup"><span data-stu-id="6b873-130">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="6b873-131">现在，可以省略掉初始化右侧的类型：</span><span class="sxs-lookup"><span data-stu-id="6b873-131">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="6b873-132">若要详细了解此增强功能，可以参阅 C# 编程指南中的[默认值表达式](../programming-guide/statements-expressions-operators/default-value-expressions.md)一文。</span><span class="sxs-lookup"><span data-stu-id="6b873-132">You can learn more about this enhancement in the C# Programming Guide article on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="6b873-133">此增强功能也会更改某些[default 关键字](../language-reference/keywords/default.md) 的分析规则。</span><span class="sxs-lookup"><span data-stu-id="6b873-133">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="6b873-134">推断元组元素名称</span><span class="sxs-lookup"><span data-stu-id="6b873-134">Inferred tuple element names</span></span>

<span data-ttu-id="6b873-135">此功能是对 C# 7.0 中引入的元组功能一次小型增强。</span><span class="sxs-lookup"><span data-stu-id="6b873-135">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="6b873-136">在初始化元组时，许多时候，赋值操作右侧的变量名与用于元组元素的名称相同：</span><span class="sxs-lookup"><span data-stu-id="6b873-136">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="6b873-137">元组元素的名称可通过在 C# 7.1 中初始化元组时使用的变量进行推断：</span><span class="sxs-lookup"><span data-stu-id="6b873-137">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="6b873-138">若要详细了解此功能，可以参阅[元组](../tuples.md)一文。</span><span class="sxs-lookup"><span data-stu-id="6b873-138">You can learn more about this feature in the [Tuples](../tuples.md) article.</span></span>

## <a name="pattern-matching-on-generic-type-parameters"></a><span data-ttu-id="6b873-139">泛型类型参数的模式匹配</span><span class="sxs-lookup"><span data-stu-id="6b873-139">Pattern matching on generic type parameters</span></span>

<span data-ttu-id="6b873-140">自 C# 7.1 起，`is` 和 `switch` 类型模式的模式表达式的类型可能为泛型类型参数。</span><span class="sxs-lookup"><span data-stu-id="6b873-140">Beginning with C# 7.1, the pattern expression for `is` and the `switch` type pattern may have the type of a generic type parameter.</span></span> <span data-ttu-id="6b873-141">这可能在检查 `struct` 或 `class` 类型且要避免装箱时最有用。</span><span class="sxs-lookup"><span data-stu-id="6b873-141">This can be most useful when checking types that may be either `struct` or `class` types, and you want to avoid boxing.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="6b873-142">引用程序集生成</span><span class="sxs-lookup"><span data-stu-id="6b873-142">Reference assembly generation</span></span>

<span data-ttu-id="6b873-143">有两个新的编译器选项会生成“仅引用”程序集：[/refout](../language-reference/compiler-options/refout-compiler-option.md) 和 [/refonly](../language-reference/compiler-options/refonly-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="6b873-143">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="6b873-144">链接的文章详细介绍了这些选项和引用程序集。</span><span class="sxs-lookup"><span data-stu-id="6b873-144">The linked articles explain these options and reference assemblies in more detail.</span></span>

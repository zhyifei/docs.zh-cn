---
title: C# 7.1 中的新增功能
description: C# 7.1 中的新增功能概述。
ms.date: 08/16/2017
ms.openlocfilehash: 00baec45d7582d3ac12c7b0865241f5cd8159246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="8170c-103">C# 7.1 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="8170c-103">What's new in C# 7.1</span></span>

<span data-ttu-id="8170c-104">C# 7.1 是 C# 语言的第一个点版本（更新版本）。</span><span class="sxs-lookup"><span data-stu-id="8170c-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="8170c-105">它标志着该语言发布节奏的加速。</span><span class="sxs-lookup"><span data-stu-id="8170c-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="8170c-106">理想情况下，可以在每个新功能准备就绪时更快推出新功能。</span><span class="sxs-lookup"><span data-stu-id="8170c-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="8170c-107">C# 7.1 增加了将编译器配置为匹配特定语言版本的功能。</span><span class="sxs-lookup"><span data-stu-id="8170c-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="8170c-108">从而可以分别制定有关升级语言版本的决策和有关升级工具的决策。</span><span class="sxs-lookup"><span data-stu-id="8170c-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="8170c-109">C# 7.1 增加了[语言版本选择](#language-version-selection)配置元素、三个新的语言功能和新的编译器行为。</span><span class="sxs-lookup"><span data-stu-id="8170c-109">C# 7.1 adds the [language version selection](#language-version-selection) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="8170c-110">此版本中新增的语言功能包括：</span><span class="sxs-lookup"><span data-stu-id="8170c-110">The new language features in this release are:</span></span>

* [<span data-ttu-id="8170c-111">`async` `Main` 方法</span><span class="sxs-lookup"><span data-stu-id="8170c-111">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="8170c-112">应用程序的入口点可以含有 `async` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="8170c-112">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="8170c-113">`default` 文本表达式</span><span class="sxs-lookup"><span data-stu-id="8170c-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="8170c-114">在可以推断目标类型的情况下，可在默认值表达式中使用默认文本表达式。</span><span class="sxs-lookup"><span data-stu-id="8170c-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="8170c-115">推断元组元素名称</span><span class="sxs-lookup"><span data-stu-id="8170c-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="8170c-116">在许多情况下，可通过元组初始化来推断元组元素的名称。</span><span class="sxs-lookup"><span data-stu-id="8170c-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="8170c-117">最后，编译器有 `/refout` 和 `/refonly` 两个选项，可用于控制[引用程序集生成](#reference-assembly-generation)。</span><span class="sxs-lookup"><span data-stu-id="8170c-117">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

## <a name="language-version-selection"></a><span data-ttu-id="8170c-118">语言版本选择</span><span class="sxs-lookup"><span data-stu-id="8170c-118">Language version selection</span></span>

<span data-ttu-id="8170c-119">自 Visual Studio 2017 版本 15.3 或 .NET Core SDK 2.0 起，C# 编译器支持 C# 7.1。</span><span class="sxs-lookup"><span data-stu-id="8170c-119">The C# compiler supports C# 7.1 starting with Visual Studio 2017 version 15.3, or the .NET Core SDK 2.0.</span></span> <span data-ttu-id="8170c-120">但会默认关闭 7.1 功能。</span><span class="sxs-lookup"><span data-stu-id="8170c-120">However, the 7.1 features are turned off by default.</span></span> <span data-ttu-id="8170c-121">若要启用 7.1 功能，需要更改项目的语言版本设置。</span><span class="sxs-lookup"><span data-stu-id="8170c-121">To enable the 7.1 features, you need to change the language version setting for your project.</span></span>

<span data-ttu-id="8170c-122">在 Visual Studio 中，右键单击解决方案资源管理器中的项目节点，然后选择**属性**。 </span><span class="sxs-lookup"><span data-stu-id="8170c-122">In Visual Studio, right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="8170c-123">选择**生成**选项卡并选择**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="8170c-123">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="8170c-124">如下图所示，在下拉列表中，选择 **C# 最新次要版本(最新)**，或具体版本 **C# 7.1**。</span><span class="sxs-lookup"><span data-stu-id="8170c-124">In the dropdown, select **C# latest minor version (latest)**, or the specific version **C# 7.1** as shown in the image following.</span></span> <span data-ttu-id="8170c-125">`latest` 值表示你想要在当前计算机上使用最新次版本。</span><span class="sxs-lookup"><span data-stu-id="8170c-125">The `latest` value means you want to use the latest minor version on the current machine.</span></span> <span data-ttu-id="8170c-126">`C# 7.1` 意味着你想要使用 C# 7.1，甚至在更新的次要版本发布之后。</span><span class="sxs-lookup"><span data-stu-id="8170c-126">The `C# 7.1` means that you want to use C# 7.1, even after newer minor versions are released.</span></span>

![设置语言版本](./media/csharp-7-1/advanced-build-settings.png)

<span data-ttu-id="8170c-128">或者，您可以编辑 "csproj" 文件，添加或修改以下行：</span><span class="sxs-lookup"><span data-stu-id="8170c-128">Alternatively, you can edit the "csproj" file and add or modify the following lines:</span></span>

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="8170c-129">如果使用 Visual Studio IDE 来更新 csproj 文件，IDE 将为每个生成配置创建单独的节点。</span><span class="sxs-lookup"><span data-stu-id="8170c-129">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="8170c-130">通常在所有生成配置中都设置相同的值，但你需要为每个生成配置显式地设置值，或在修改此设置时选择"所有配置"。</span><span class="sxs-lookup"><span data-stu-id="8170c-130">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="8170c-131">在 csproj 文件中，你可以看到如下内容：</span><span class="sxs-lookup"><span data-stu-id="8170c-131">You'll see the following in your csproj file:</span></span>

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="8170c-132">`LangVersion` 元素的有效设置选项：</span><span class="sxs-lookup"><span data-stu-id="8170c-132">Valid settings for the `LangVersion` element are:</span></span>

* `ISO-1`
* `ISO-2`
* `3`
* `4`
* `5`
* `6`
* `7`
* `7.1`
* `default`
* `latest`

<span data-ttu-id="8170c-133">特殊字符串 `default` 和 `latest` 分别解析为生成计算机上安装的最新主要和次要语言版本。</span><span class="sxs-lookup"><span data-stu-id="8170c-133">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

<span data-ttu-id="8170c-134">采用此设置后，在开发环境中安装新版本的 SDK 和工具时，不必选择在项目中引入新的语言功能。</span><span class="sxs-lookup"><span data-stu-id="8170c-134">This setting decouples installing new versions of the SDK and tools in your development environment from choosing to incorporate new language features in a project.</span></span> <span data-ttu-id="8170c-135">可以在生成计算机上安装最新的 SDK 和工具。</span><span class="sxs-lookup"><span data-stu-id="8170c-135">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="8170c-136">每个项目可以配置为对其生成使用该语言的特定版本。</span><span class="sxs-lookup"><span data-stu-id="8170c-136">Each project can be configured to use a specific version of the language for its build.</span></span>

## <a name="async-main"></a><span data-ttu-id="8170c-137">异步 `main` 方法
</span><span class="sxs-lookup"><span data-stu-id="8170c-137">Async main</span></span>

<span data-ttu-id="8170c-138">*异步 Main* 方法使你能够在 `Main` 方法中使用 `await` 关键字。</span><span class="sxs-lookup"><span data-stu-id="8170c-138">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="8170c-139">在过去，需要编写：</span><span class="sxs-lookup"><span data-stu-id="8170c-139">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="8170c-140">现在，您可以编写：</span><span class="sxs-lookup"><span data-stu-id="8170c-140">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="8170c-141">如果程序不返回退出代码，可以声明返回 <xref:System.Threading.Tasks.Task> 的 `Main` 方法:
</span><span class="sxs-lookup"><span data-stu-id="8170c-141">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="8170c-142">你可以在编程指南的[异步 Main 方法](../programming-guide/main-and-command-args/index.md)主题中阅读更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="8170c-142">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="8170c-143">默认文本表达式</span><span class="sxs-lookup"><span data-stu-id="8170c-143">Default literal expressions</span></span>

<span data-ttu-id="8170c-144">默认文本表达式是针对默认值表达式的一项增强功能。</span><span class="sxs-lookup"><span data-stu-id="8170c-144">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="8170c-145">这些表达式将变量初始化为默认值。</span><span class="sxs-lookup"><span data-stu-id="8170c-145">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="8170c-146">过去会这么编写：</span><span class="sxs-lookup"><span data-stu-id="8170c-146">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="8170c-147">现在，可以省略掉初始化右侧的类型：</span><span class="sxs-lookup"><span data-stu-id="8170c-147">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="8170c-148">你可以通过 C# 编程指南的[默认值表达式](../programming-guide/statements-expressions-operators/default-value-expressions.md) 主题了解有关此增强功能的详细信息。
</span><span class="sxs-lookup"><span data-stu-id="8170c-148">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="8170c-149">此增强功能也会更改某些[default 关键字](../language-reference/keywords/default.md) 的分析规则。</span><span class="sxs-lookup"><span data-stu-id="8170c-149">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="8170c-150">推断元组元素名称</span><span class="sxs-lookup"><span data-stu-id="8170c-150">Inferred tuple element names</span></span>

<span data-ttu-id="8170c-151">此功能是对 C# 7.0 中引入的元组功能一次小型增强。</span><span class="sxs-lookup"><span data-stu-id="8170c-151">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="8170c-152">在初始化元组时，许多时候，赋值操作右侧的变量名与用于元组元素的名称相同：</span><span class="sxs-lookup"><span data-stu-id="8170c-152">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="8170c-153">元组元素的名称可通过在 C# 7.1 中初始化元组时使用的变量进行推断：</span><span class="sxs-lookup"><span data-stu-id="8170c-153">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="8170c-154">可以在[元组](../tuples.md)主题中了解有关此功能的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8170c-154">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="8170c-155">引用程序集生成</span><span class="sxs-lookup"><span data-stu-id="8170c-155">Reference assembly generation</span></span>

<span data-ttu-id="8170c-156">有两个新的编译器选项会生成“仅引用”程序集：[/refout](../language-reference/compiler-options/refout-compiler-option.md) 和 [/refonly](../language-reference/compiler-options/refonly-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="8170c-156">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="8170c-157">链接的主题详细介绍了这些选项和引用程序集。</span><span class="sxs-lookup"><span data-stu-id="8170c-157">The linked topics explain these options and reference assemblies in more detail.</span></span>

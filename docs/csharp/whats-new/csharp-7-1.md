---
title: "什么是 C# 7.1 中的新增功能"
description: "C# 7.1 中的新增功能概述。"
keywords: "C# 语言设计，7.1，Visual Studio 2017，"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 02f1f8fc8f0a3221e00e2a3c43ce06423ca43672
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="83c31-104">什么是 C# 7.1 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="83c31-104">What's new in C# 7.1</span></span>

<span data-ttu-id="83c31-105">C# 7.1 是 C# 语言的第一个点版本。</span><span class="sxs-lookup"><span data-stu-id="83c31-105">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="83c31-106">会将标记的语言增加的发布节奏。</span><span class="sxs-lookup"><span data-stu-id="83c31-106">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="83c31-107">你可以使用新的功能更快，理想情况下准备每个新功能时。</span><span class="sxs-lookup"><span data-stu-id="83c31-107">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="83c31-108">C# 7.1 添加了配置以匹配的指定的版本的语言编译器的功能。</span><span class="sxs-lookup"><span data-stu-id="83c31-108">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="83c31-109">它使你可以将分隔从判定升级语言版本升级工具的决策。</span><span class="sxs-lookup"><span data-stu-id="83c31-109">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="83c31-110">C# 7.1 添加[语言版本选择](#language-version-selection)配置元素、 三个新的语言功能和新的编译器行为。</span><span class="sxs-lookup"><span data-stu-id="83c31-110">C# 7.1 adds the [language version selection](#language-version-selection) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="83c31-111">在此版本中的新语言功能包括：</span><span class="sxs-lookup"><span data-stu-id="83c31-111">The new language features in this release are:</span></span>

* [<span data-ttu-id="83c31-112">`async` `Main`方法</span><span class="sxs-lookup"><span data-stu-id="83c31-112">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="83c31-113">应用程序的入口点可以具有`async`修饰符。</span><span class="sxs-lookup"><span data-stu-id="83c31-113">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="83c31-114">`default`文本表达式</span><span class="sxs-lookup"><span data-stu-id="83c31-114">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="83c31-115">可以推断的目标类型时，可以在默认值表达式中使用默认文本表达式。</span><span class="sxs-lookup"><span data-stu-id="83c31-115">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="83c31-116">推断元组元素名称</span><span class="sxs-lookup"><span data-stu-id="83c31-116">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="83c31-117">可以从在许多情况下的元组初始化推断的元组元素的名称。</span><span class="sxs-lookup"><span data-stu-id="83c31-117">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="83c31-118">最后，编译器具有两个选项`/refout`和`/refonly`该控件[引用程序集生成](#reference-assembly-generation)。</span><span class="sxs-lookup"><span data-stu-id="83c31-118">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

## <a name="language-version-selection"></a><span data-ttu-id="83c31-119">语言版本选择</span><span class="sxs-lookup"><span data-stu-id="83c31-119">Language version selection</span></span>

<span data-ttu-id="83c31-120">C# 编译器支持 C# 7.1 从 Visual Studio 2017 版本 15.3 或.NET 核心 SDK 2.0。</span><span class="sxs-lookup"><span data-stu-id="83c31-120">The C# compiler supports C# 7.1 starting with Visual Studio 2017 version 15.3, or the .NET Core SDK 2.0.</span></span> <span data-ttu-id="83c31-121">但是，7.1 功能将关闭默认情况下。</span><span class="sxs-lookup"><span data-stu-id="83c31-121">However, the 7.1 features are turned off by default.</span></span> <span data-ttu-id="83c31-122">若要启用的 7.1 功能，你需要更改你的项目的语言版本设置。</span><span class="sxs-lookup"><span data-stu-id="83c31-122">To enable the 7.1 features, you need to change the language version setting for your project.</span></span>

<span data-ttu-id="83c31-123">在 Visual Studio 中，右键单击解决方案资源管理器中的项目节点，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="83c31-123">In Visual Studio, right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="83c31-124">选择**生成**选项卡并选择**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="83c31-124">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="83c31-125">在下拉列表中，选择**C# 最新次要版本 （最新）**，或特定版本**C# 7.1**在映像下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="83c31-125">In the dropdown, select **C# latest minor version (latest)**, or the specific version **C# 7.1** as shown in the image following.</span></span> <span data-ttu-id="83c31-126">`latest`值表示你想要在当前计算机上使用的最新次版本。</span><span class="sxs-lookup"><span data-stu-id="83c31-126">The `latest` value means you want to use the latest minor version on the current machine.</span></span> <span data-ttu-id="83c31-127">`C# 7.1`意味着你想要使用 C# 7.1、，甚至在较新的次要版本发布之后。</span><span class="sxs-lookup"><span data-stu-id="83c31-127">The `C# 7.1` means that you want to use C# 7.1, even after newer minor versions are released.</span></span>

![设置的语言版本](./media/csharp-7-1/advanced-build-settings.png)

<span data-ttu-id="83c31-129">或者，你可以编辑"csproj"文件和添加或修改以下行：</span><span class="sxs-lookup"><span data-stu-id="83c31-129">Alternatively, you can edit the "csproj" file and add or modify the following lines:</span></span>

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="83c31-130">如果使用 Visual Studio IDE 来更新 csproj 文件，IDE 将创建单独的节点，每个生成配置。</span><span class="sxs-lookup"><span data-stu-id="83c31-130">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="83c31-131">你将通常设置的值相同在所有生成配置，但你需要将其显式设置每个生成配置，或修改此设置时选择"所有配置"。</span><span class="sxs-lookup"><span data-stu-id="83c31-131">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="83c31-132">在 csproj 文件中，你将看到以下：</span><span class="sxs-lookup"><span data-stu-id="83c31-132">You'll see the following in your csproj file:</span></span>

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="83c31-133">有效设置`LangVersion`元素：</span><span class="sxs-lookup"><span data-stu-id="83c31-133">Valid settings for the `LangVersion` element are:</span></span>

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

<span data-ttu-id="83c31-134">特殊字符串`default`和`latest`解析为分别在生成计算机上安装的最新主要和次要语言版本。</span><span class="sxs-lookup"><span data-stu-id="83c31-134">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

<span data-ttu-id="83c31-135">此设置将分离选择以包含在项目中的新语言功能的开发环境中安装新版本的 SDK 和工具。</span><span class="sxs-lookup"><span data-stu-id="83c31-135">This setting decouples installing new versions of the SDK and tools in your development environment from choosing to incorporate new language features in a project.</span></span> <span data-ttu-id="83c31-136">你可以在生成计算机上安装的最新的 SDK 和工具。</span><span class="sxs-lookup"><span data-stu-id="83c31-136">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="83c31-137">每个项目可以配置要用于其生成的特定版本的语言。</span><span class="sxs-lookup"><span data-stu-id="83c31-137">Each project can be configured to use a specific version of the language for its build.</span></span>

## <a name="async-main"></a><span data-ttu-id="83c31-138">异步主要</span><span class="sxs-lookup"><span data-stu-id="83c31-138">Async main</span></span>

<span data-ttu-id="83c31-139">*异步主要*方法使您能够使用`await`中你`Main`方法。</span><span class="sxs-lookup"><span data-stu-id="83c31-139">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="83c31-140">以前，你需要编写：</span><span class="sxs-lookup"><span data-stu-id="83c31-140">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="83c31-141">您现在可以编写：</span><span class="sxs-lookup"><span data-stu-id="83c31-141">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="83c31-142">如果你的程序不返回退出代码，你可以声明`Main`返回方法<xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="83c31-142">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="83c31-143">你可以阅读更多有关中的详细信息[异步主要](../programming-guide/main-and-command-args/index.md)编程指南中的主题。</span><span class="sxs-lookup"><span data-stu-id="83c31-143">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="83c31-144">默认文本表达式</span><span class="sxs-lookup"><span data-stu-id="83c31-144">Default literal expressions</span></span>

<span data-ttu-id="83c31-145">默认文本表达式是一项增强功能的默认值表达式。</span><span class="sxs-lookup"><span data-stu-id="83c31-145">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="83c31-146">这些表达式初始化为默认值的变量。</span><span class="sxs-lookup"><span data-stu-id="83c31-146">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="83c31-147">其中以前编写：</span><span class="sxs-lookup"><span data-stu-id="83c31-147">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="83c31-148">现在，则可以省略的初始化的右侧类型：</span><span class="sxs-lookup"><span data-stu-id="83c31-148">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="83c31-149">你可以了解有关 C# 编程指南主题中的此增强功能的详细信息上[默认值表达式](../programming-guide/statements-expressions-operators/default-value-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="83c31-149">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="83c31-150">此增强功能也会更改某些的分析规则[default 关键字](../language-reference/keywords/default.md)。</span><span class="sxs-lookup"><span data-stu-id="83c31-150">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="83c31-151">推断元组元素名称</span><span class="sxs-lookup"><span data-stu-id="83c31-151">Inferred tuple element names</span></span>

<span data-ttu-id="83c31-152">此功能是在 C# 7.0 中引入的元组功能小增强功能。</span><span class="sxs-lookup"><span data-stu-id="83c31-152">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="83c31-153">很多时候时初始化元组，使用分配的左右两边的变量是你想要为元组元素的名称相同：</span><span class="sxs-lookup"><span data-stu-id="83c31-153">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="83c31-154">用于初始化的元组 7.1 C# 中的变量中推断的元组元素的名称：</span><span class="sxs-lookup"><span data-stu-id="83c31-154">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="83c31-155">你可以了解有关此功能的详细[元组](../tuples.md)主题。</span><span class="sxs-lookup"><span data-stu-id="83c31-155">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="83c31-156">引用程序集生成</span><span class="sxs-lookup"><span data-stu-id="83c31-156">Reference assembly generation</span></span>

<span data-ttu-id="83c31-157">有两个新的编译器选项生成*仅引用程序集*: [/refout](../language-reference/compiler-options/refout-compiler-option.md)和[/refonly](../language-reference/compiler-options/refonly-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="83c31-157">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="83c31-158">链接的主题介绍了这些选项以及更多详细信息中的引用程序集。</span><span class="sxs-lookup"><span data-stu-id="83c31-158">The linked topics explain these options and reference assemblies in more detail.</span></span>

---
title: "C# 7.1 中的新增功能"
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
# <a name="whats-new-in-c-71"></a>C# 7.1 中的新增功能

C# 7.1 是 C# 语言的第一个点版本。 它标志着该语言的发布节奏的增加。 您可以更早地使用新功能（理想情况下，在每个新功能完成准备时）。 C# 7.1 新增了能够配置编译器来匹配特定的语言版本的功能。 这使您可以将是否升级语言版本的决定和是否升级工具的决定分离开来。

C# 7.1 添加[语言版本选择](#language-version-selection)配置元素、 三个新的语言功能和新的编译器行为。

在此版本中的新语言功能包括：

* [`async` `Main`方法](#async-main)
  - 应用程序的入口点可以具有`async`修饰符。
* [`default`文本表达式](#default-literal-expressions)
  - 目标类型可推断时，可以在默认值表达式中使用默认文本表达式。
* [推断元组元素名称](#inferred-tuple-element-names)
  - 在许多情况下，可以从元组初始化中推断出元组元素的名称。

最后，编译器有两个用于控制[引用程序集生成](#reference-assembly-generation) 的选项`/refout`和``/refonly`。

## <a name="language-version-selection"></a>语言版本选择

C# 编译器从 Visual Studio 2017 版本 15.3 或.NET 核心 SDK 2.0 开始支持 C# 7.1 的功能。 但在默认情况下，C# 7.1 的功能是关闭的。 若要启用 C# 7.1 的功能，您需要更改您的项目的语言版本设置。


在 Visual Studio 中，右键单击解决方案资源管理器中的项目节点，然后选择**属性**。  选择**生成**选项卡并选择**高级**按钮。 如下图所示，在下拉列表中，选择 **C# 最新次要版本(最新)**，或具体版本 **C# 7.1**。 `latest` 值表示你想要在当前计算机上使用最新次版本。 `C# 7.1` 意味着你想要使用 C# 7.1，甚至在更新的次要版本发布之后。

![设置的语言版本](./media/csharp-7-1/advanced-build-settings.png)

或者，您可以编辑 "csproj" 文件，添加或修改以下行：

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> 如果使用 Visual Studio IDE 来更新 csproj 文件，IDE 将创建单独的节点，每个生成配置。 你将通常设置的值相同在所有生成配置，但你需要将其显式设置每个生成配置，或修改此设置时选择"所有配置"。 在 csproj 文件中，你将看到以下：

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

`LangVersion` 元素的有效设置选项：

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

特殊字符串`default`和`latest`解析为分别在生成计算机上安装的最新主要和次要语言版本。

采用此设置后，在开发环境中安装新版本的 SDK 和工具时，不必选择在项目中引入新的语言功能。 可以在生成计算机上安装最新的 SDK 和工具。 每个项目可以配置为对其生成使用该语言的特定版本。

## <a name="async-main"></a>异步 `main` 方法


*异步 Main* 方法使你能够在 `Main` 方法中使用 `await` 关键字。
以前，你需要编写：

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

现在，您可以编写：

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

如果程序不返回退出代码，可以声明返回 <xref:System.Threading.Tasks.Task> 的 `Main` 方法:


```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

你可以在编程指南的[异步 Main 方法](../programming-guide/main-and-command-args/index.md)主题中阅读更多详细信息。

## <a name="default-literal-expressions"></a>默认文本表达式

默认文本表达式是一项增强功能的默认值表达式。
这些表达式将变量初始化为默认值。 比如以前这样编写：

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

现在，可以省略掉初始化右侧的类型：

```csharp
Func<string, bool> whereClause = default;
```

你可以通过 C# 编程指南的[默认值表达式](../programming-guide/statements-expressions-operators/default-value-expressions.md) 主题了解有关此增强功能的详细信息。


此增强功能也会更改某些[default 关键字](../language-reference/keywords/default.md) 的分析规则。

## <a name="inferred-tuple-element-names"></a>推断元组元素名称

此功能是在 C# 7.0 中引入的元组功能的小增强功能。 很多时候，在初始化元组时，分配式右侧使用的变量与你想要给元组元素分配的名称相同：

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

在 C# 7.1 中，可以通过用于初始化元组的变量来推断出元组元素的名称：

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

你可以在[元组](../tuples.md)主题中了解有关此功能的详细信息。

## <a name="reference-assembly-generation"></a>引用程序集生成

有两个新的编译器选项生成*仅引用程序集*: [/refout](../language-reference/compiler-options/refout-compiler-option.md)和[/refonly](../language-reference/compiler-options/refonly-compiler-option.md)。
链接的主题介绍了这些选项以及更多详细信息中的引用程序集。

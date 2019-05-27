---
title: C# 7.1 中的新增功能
description: C# 7.1 中的新增功能概述。
ms.date: 04/09/2019
ms.openlocfilehash: 4b7bd96e428f990b2db91a4cfd45da01dc133aac
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881556"
---
# <a name="whats-new-in-c-71"></a>C# 7.1 中的新增功能

C# 7.1 是 C# 语言的第一个点版本（更新版本）。 它标志着该语言发布节奏的加速。 理想情况下，可以在每个新功能准备就绪时更快推出新功能。 C# 7.1 增加了将编译器配置为匹配特定语言版本的功能。 从而可以分别制定有关升级语言版本的决策和有关升级工具的决策。

C# 7.1 增加了[语言版本选择](../language-reference/configure-language-version.md)配置元素、三个新的语言功能和新的编译器行为。

此版本中新增的语言功能包括：

* [`async` `Main` 方法](#async-main)
  - 应用程序的入口点可以含有 `async` 修饰符。
* [`default` 文本表达式](#default-literal-expressions)
  - 在可以推断目标类型的情况下，可在默认值表达式中使用默认文本表达式。
* [推断元组元素名称](#inferred-tuple-element-names)
  - 在许多情况下，可通过元组初始化来推断元组元素的名称。
* [泛型类型参数的模式匹配](#pattern-matching-on-generic-type-parameters)
  - 可以对类型为泛型类型参数的变量使用模式匹配表达式。

最后，编译器有 `-refout` 和 `-refonly` 两个选项，可用于控制[引用程序集生成](#reference-assembly-generation)。

若要使用单点版本中的最新功能，需要[配置编译器语言版本](../language-reference/configure-language-version.md)并选择版本。

## <a name="async-main"></a>异步 `main` 方法

*异步 Main* 方法使你能够在 `Main` 方法中使用 `await` 关键字。
在过去，需要编写：

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

如需了解更多详情，可以阅读编程指南中的[异步 Main](../programming-guide/main-and-command-args/index.md) 一文。

## <a name="default-literal-expressions"></a>默认文本表达式

默认文本表达式是针对默认值表达式的一项增强功能。
这些表达式将变量初始化为默认值。 过去会这么编写：

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

现在，可以省略掉初始化右侧的类型：

```csharp
Func<string, bool> whereClause = default;
```

若要详细了解此增强功能，可以参阅 C# 编程指南中的[默认值表达式](../programming-guide/statements-expressions-operators/default-value-expressions.md)一文。

此增强功能也会更改某些[default 关键字](../language-reference/keywords/default.md) 的分析规则。

## <a name="inferred-tuple-element-names"></a>推断元组元素名称

此功能是对 C# 7.0 中引入的元组功能一次小型增强。 在初始化元组时，许多时候，赋值操作右侧的变量名与用于元组元素的名称相同：

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

元组元素的名称可通过在 C# 7.1 中初始化元组时使用的变量进行推断：

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

若要详细了解此功能，可以参阅[元组](../tuples.md)一文。

## <a name="pattern-matching-on-generic-type-parameters"></a>泛型类型参数的模式匹配

自 C# 7.1 起，`is` 和 `switch` 类型模式的模式表达式的类型可能为泛型类型参数。 这可能在检查 `struct` 或 `class` 类型且要避免装箱时最有用。

## <a name="reference-assembly-generation"></a>引用程序集生成

有两个新编译器选项可生成仅引用程序集：[-refout](../language-reference/compiler-options/refout-compiler-option.md) 和 [-refonly](../language-reference/compiler-options/refonly-compiler-option.md)。
链接的文章详细介绍了这些选项和引用程序集。

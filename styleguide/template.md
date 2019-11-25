---
title:
- 文章标题
description: ''
author:
- GITHUB USERNAME
ms.author:
- MICROSOFT ALIAS OF INTERNAL OWNER
ms.date:
- CREATION/UPDATE DATE - MM/dd/yyyy
ms.topic:
- TOPIC TYPE
ms.prod:
- PRODUCT VALUE
helpviewer_keywords:
- OFFLINE BOOK INDEX ENTRIES
ms.openlocfilehash: ed9fd55fd84606d2083e0576581391331769a1e6
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089280"
---
# <a name="metadata-and-markdown-template"></a>元数据和 Markdown 模板

此 dotnet/文档模板包含 Markdown 语法的示例以及有关设置元数据的指南。 若要充分利用该模板，则必须查看[原始 Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) 和[呈现的视图](https://github.com/dotnet/docs/blob/master/styleguide/template.md)。

创建 Markdown 文件时，应将此模板复制到新文件中，按下面的指定填写元数据，将上面的 H1 标题设置为本文的标题，并删除内容。

## <a name="metadata"></a>元数据

完整的元数据块如上所示（在[原始 Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) 文件中），分为必填字段和可选字段。 一些重要说明：

- 元数据元素的冒号 (:) 和值之间**必须**有空格。
- 如果可选的元数据元素没有值，请使用 # 注释掉该元素或将其删除（请勿将其留空或使用“na”）。 如果要向已被注释掉的元素添加值，请务必删除 #。
- 值（例如标题）中的冒号会中断元数据解析器。 在此情况下，使用双引号将标题括起来（例如， `title: "Writing .NET Core console apps: An advanced step-by-step guide"`）。
- **title**：出现在搜索引擎结果中。 此标题不应与 H1 标题相同，并且包含的字符数不超过 60 个。
- **描述**：概括文章内容。 它通常显示在搜索结果页中，但不用于搜索排名。 其长度应为 115-145 个字符，包括空格。
- “作者”和“ ms.author”   ：“作者”字段应包含作者的“GitHub 用户名”，而不是其别名  。  另一方面，“ms.author”字段应包含 Microsoft 别名，并指示负责维护该文章的人员  。
- **ms.topic**：主题类型。 最常见的值为 `conceptual` 并且在全局级别进行设置。 使用的其他常用值为 `tutorial`、`overview` 和 `reference`。
- “dev_langs”  定义主题显示的语言筛选器。 可以在[支持的语言](#supported-languages)部分中查看受支持的值列表。 仅当主题涵盖了多个编程语言时才需要设置。 通常，只在内容中使用 `csharp`、`vb`、`fsharp` 和 `cpp` 作为值。
- **ms-chap**：用于 BI 目的的产品标识。 它们通常在全局级别进行设置，因此通常不会出现在每篇文章的元数据块中。
- **ms.technology**：其他 BI 分类。 一些受支持的值是：适用于 C# 主题的 `devlang-csharp`、适用于 F# 主题的 `devlang-fsharp` 和适用于 VB 主题的 `devlang-visual-basic`。 对于其他指南，值将有所不同，因此请让团队成员提供指导。
- **ms.date**：采用 MM/dd/yyyy 格式的日期。 显示在“已发布”页面上，表明刚对文章进行了重大编辑或保证是“最新”的（即项目已查看并被视为最新）。
- **helpviewer_keywords**：条目用于脱机图书索引（Visual Studio 中的功能）。
- **f1_keywords**：将文章连接到 F1 键（Visual Studio 中的功能）。

## <a name="basic-markdown-gfm-and-special-characters"></a>基本 Markdown、 GFM 和特殊字符

支持所有基本 Markdown 和 GitHub Flavored Markdown (GFM)。 有关这些主题的更多信息，请参阅：

- [Markdown 基本语法](https://daringfireball.net/projects/markdown/syntax)
- [GFM 文档](https://guides.github.com/features/mastering-markdown)

Markdown 使用特殊字符如 \*、\` 和 \# 进行格式化。 如果要在内容中包括一个特殊字符，必须执行以下两个操作之一：

- 在特殊字符前面放置一个反斜杠来“转义”它（例如，将 \* 写为 `\*`）
- 对字符使用 [HTML 实体代码](https://www.ascii.cl/htmlcodes.htm)（例如，将 &#42; 写为 `&#42;`）。

## <a name="file-name"></a>文件名

文件名使用以下规则：

- 只包含小写字母、数字和连字符。
- 不包括空格或标点字符。 在文件名中使用连字符分隔单词和数字。
- 使用具体的动作动词，例如 develop、buy、build、troubleshoot。 不使用带 -ing 的单词。
- 不使用小单词 - 不包含 a、and、the、in、or 等。
- 必须为 Markdown 格式，使用 .md 文件扩展名。
- 保持文件名简短。 它们是文章 URL 的一部分。

## <a name="headings"></a>标题

使用句式单词首字母大写。 将标题、专有名词的第一个单词的第一个字母和冒号后的第一个字母大写（例如，“Tutorial:Predict prices using regression with ML.NET”）。

请勿在“How to”之后添加冒号（例如，“How to sort an array”而不是“How to:Sort an array”）。

标题使用 atx 样式，即在行的开头使用 1-6 个哈希字符 (#) 来表示标题，对应于 HTML 标题级别 H1 到 H6。 上面使用的是第一和第二级别标题示例。

主题中**必须**只有一个第一级别标题 (H1)，此标题显示为页面上的标题。

如果标题以 `#` 字符结尾，则需要对其进行转义以正确呈现标题。 例如 `# Async programming in F\#`。

第二级标题生成页面 TOC，显示在“In this article”部分的页面标题下方。

### <a name="third-level-heading"></a>第三级标题
#### <a name="fourth-level-heading"></a>第四级标题
##### <a name="fifth-level-heading"></a>第五级标题
###### <a name="sixth-level-heading"></a>第六级标题

## <a name="text-styling"></a>文本样式

斜体：用于文件、文件夹、路径（对于较长的项，将其拆分到各自行）和新术语  。

**粗体**用于 UI 元素。

`Code`：用于内联代码、语言关键字、NuGet 包名称、命令行命令、数据库表和列名称，以及不希望其变为可单击的 URL。

## <a name="links"></a>链接

### <a name="internal-links"></a>内部链接

若要链接到同一 Markdown 文件中的标题（也称为定位链接），需要找出想要链接到的标题的 ID。 若要确认 ID，请查看呈现的文章的源，以查找 ID（例如， `id="blockquote"`），并使用 # + ID 进行链接（例如， `#blockquote`）。
ID 是基于标头文本自动生成的。 因此，例如，如果某个唯一部分名称为 `## Step 2`，则 ID 应类似于 `id="step-2"`。

- 示例：`[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` 生成[使用语言标识符声明内联块](#inline-code-blocks-with-language-identifier)。

若要链接到同一个存储库中的 Markdown 文件，请使用[相对链接](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2)，文件名末尾包含“.md”。

- 示例：`[Readme file](../README.md)` 生成[自述文件](../README.md)。 （请注意，链接区分大小写。）
- 示例：`[Welcome to .NET](../docs/welcome.md)` 生成[欢迎使用 .NET](../docs/welcome.md)。

若要链接到同一个存储库中的 Markdown 文件中的标头，请使用相对链接 + 哈希标记进行链接。

- 示例：`[.NET Community](../docs/welcome.md#open-source)` 生成[.NET 社区](../docs/welcome.md#open-source)。

大多数情况下，我们使用相对链接，阻止在链接中使用 `~/`，因为在 GitHub 上的源中解析相对链接。 但是，当我们链接到依赖存储库中的文件时，我们将使用 `~/` 字符来提供路径。 由于依赖存储库中的文件位于 GitHub 中的不同位置，因此无论链接的编写方式如何，都无法使用相对链接正确解析这些链接。

C# 语言规范和 Visual Basic 语言规范通过包含语言存储库中的源，都包含在 .NET 文档中。 Markdown 源在 [csharplang](https://github.com/dotnet/csharplang) 和 [visual basic](https://github.com/dotnet/vblang) 存储库中进行管理。

指向规范的链接必须指向包含这些规范的源目录。 对于 C#，它是“~/_csharplang/spec”，对于 VB，它是“~/_vblang/spec”   。

- 示例：`[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` 生成 [C# 查询表达式](~/_csharplang/spec/expressions.md#query-expressions)。

### <a name="external-links"></a>外部链接

若要链接到外部文件，请使用完整的 URL 作为链接。

- 示例：`[GitHub](https://www.github.com)` 生成 [GitHub](https://www.github.com)。

如果在 Markdown 文件中显示一个 URL，此 URL 将转换为可单击的链接。

- 示例：`<https://www.github.com>` 生成 <https://www.github.com>。

外部链接首选 `https` 协议。 仅为不支持 `https` 的站点使用 `http` 链接。

### <a name="links-to-apis"></a>链接到 API

生成系统具有一些扩展功能，使我们能够链接到 .NET API，而无需使用外部链接。
链接到 API 时，可以使用从源代码自动生成的 API 的唯一标识符 (UID)。

UID 等同于完全限定的类型和成员名称。

如果在 UID 后面添加 \*（或 %2A），则该链接将表示重载页，而不是特定的 API。 例如，如果希望使用通用方法而不是特定重载（比如 [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_)）链接到 [List\<T>.BinarySearch 方法](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch)页，可以使用该类型。 当成员未重载时，还可以使用 \* 链接到成员页；这样可以避免在 UID 中包含参数列表。

若要链接到特定的方法重载，必须包括该方法每个参数的完全限定类型名称。 例如，\<xref:System.DateTime.ToString> 链接到无参数的 [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) 方法，而 \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> 链接到 [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) 方法。 可以从 <https://xref.docs.microsoft.com/autocomplete> 中查找特定重载成员的 UID。 查询字符串“?text==\<type-member-name>”标识要查看其 UID 的类型或成员  。 例如，<https://xref.docs.microsoft.com/autocomplete?text=string.format> 检索 [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) 重载。

若要链接到泛型类型（如 [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1)），请在泛型类型参数后面使用 \` (%60) 字符。 例如，\<xref:System.Nullable%601> 链接到 [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) 类型，而 \<xref:System.Func%602> 链接到 [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) 委托。

可以使用以下任一种语法：

1. 自动链接：`<xref:UID>` 或 `<xref:UID?displayProperty=nameWithType>`

   `displayProperty` 查询参数生成完全限定的链接文本。 默认情况下，链接文本仅显示成员或类型名称。

2. Markdown 链接：`[link text](xref:UID)`

   需要自定义显示的链接文本时使用。

示例：

- `<xref:System.String>` 呈现为 [String](https://docs.microsoft.com/dotnet/api/system.string)
- `<xref:System.String?displayProperty=nameWithType>` 呈现为 [System.String](https://docs.microsoft.com/dotnet/api/system.string)
- `[String class](xref:System.String)` 呈现为 [String 类](https://docs.microsoft.com/dotnet/api/system.string)

有关使用这一表示法的详细信息，请参阅 [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference)（使用交叉引用）。

有两种方法可以查找 UID：

- 查看要链接到的 API 页面的源，并找到 assetid 值。 请注意，各个重载值不会显示在源中。
- 使用以下工具搜索 UID：<https://xref.docs.microsoft.com/autocomplete?text=tostring>（将 tostring 替换为尝试查找的部分 API 名称）。 该工具在 UID 的任何部分中搜索提供的 `text` 查询参数。 例如，可以搜索成员名称 (ToString)、部分成员名称 (ToStri)、类型和成员名称 (Double.ToString) 等。

如果 UID 包含特殊字符 \`、\# 或 \*，则 UID 值需要分别使用 HTML 编码为 `%60`、`%23` 和 `%2A`。 有时会看到对括号进行编码，但这并不是必需的。

示例：

- System.Threading.Tasks.Task\`1 生成 `System.Threading.Tasks.Task%601`
- System.Exception.\#ctor 生成 `System.Exception.%23ctor`
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) 生成 `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`

## <a name="lists"></a>列表

### <a name="ordered-lists"></a>有序列表

1. 这
1. 是
1. 一个
1. Ordered
1. 列表

#### <a name="ordered-list-with-an-embedded-list"></a>包含嵌套列表的有序列表

1. Here
1. comes
1. 一个
1. embedded
    1. Miss Scarlett
    1. Professor Plum
1. ordered
1. list

### <a name="unordered-lists"></a>无序列表

- 这
- is
- a
- 无序
- list

#### <a name="unordered-list-with-an-embedded-list"></a>包含嵌套列表的无序列表

- 这
- 无序
- list
  - Mrs. Peacock
  - Mr. Green
- 包含
- 其他
  1. Colonel Mustard
  1. Mrs. White
- 列表

## <a name="horizontal-rule"></a>水平标尺

---

## <a name="tables"></a>表

| 表        | 很           | 酷  |
| ------------- |:-------------:| -----:|
| 第 3 列是      | 右对齐 | $1600 |
| 第 2 列是      | 居中对齐      |   $12 |
| 第 1 列为默认对齐方式 | 左对齐     |    $1 |

可以使用 [Markdown 表生成器工具](https://www.tablesgenerator.com/markdown_tables)来更轻松地创建它们。

## <a name="code"></a>代码

包含代码的最好方法是包含工作示例中的代码片段。 按照[参与指南](../CONTRIBUTING.md#contributing-to-samples)中的说明创建示例。

可以使用以下语法来包含代码：

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

- `-<language>`（可选但建议这样做）  
  - 引用的代码片段的语言。 有关支持的值列表，请参阅[支持的语言](#supported-languages)。

- `<name>`（可选） 
  - 代码片段的名称。 它不会对输出 HTML 产生任何影响，但可以使用它来提高 Markdown 源的可读性。

- `<pathToFile>`（强制） 
  - 文件系统中的相对路径指示要引用的代码片段文件。

- `<queryoption>` 和 `<queryoptionvalue>`（可选） 
  - 一起使用可以指定从文件中检索代码的方式：
    - `#`：`#L{startlinenumber}-L{endlinenumber}`（行范围）或 `#{tagname}`（标记名称）  。
    不建议使用行号，因为它们容易出错。 标记名称是引用代码片段的首选方法。
    - `range`：`?range=1,3-5` 行范围。 此示例包括第 1、第 3、第 4 和第 5 行。
    - `dedent`：`?dedent=8` 用若干空格取消缩进行 - 此事例中为第 8 行。 这可以与 `range` 和其他查询选项结合使用，这些选项用于选择文件中行的子集。
    - `outdent`：`?outdent=8` 用若干空格减少缩进行 - 此事例中为第 8 行。 这可以与 `range` 和其他查询选项结合使用，这些选项用于选择文件中行的子集。

建议尽可能使用标记名称选项。 标记名称是区域的名称或代码注释的名称，其格式为源代码中的 `Snippettagname` 格式。 下面的示例演示如何引用标记名称 `1`：

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

可在[此源文件](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs)中了解片段标记的结构。 有关代码片段源文件中的标记名称表示形式（按语言）的详细信息，请参阅 [DocFX 指南](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file)。

包括完整程序中的代码片段可以确保在整个持续集成 (CI) 系统中运行所有代码。 但是，如果需要显示导致编译时或运行时错误的一些内容，则可以使用内联代码块。

### <a name="inline-code-blocks-with-language-identifier"></a>具有语言标识符的内联代码块

使用三个反撇号 (\`\`\`) + 语言 ID，将特定于语言的颜色编码应用到代码块。 下面是支持的语言列表，显示了每个语言 ID 的 markdown 标签。

#### <a name="supported-languages"></a>支持的语言

|name|Markdown 标签|
|-----|-------|
|.NET 控制台|dotnetcli|
|ASP.NET (C#)|aspx-csharp|
|ASP.NET (VB)|aspx-vb|
|Azure CLI|azurecli|
|AzCopy|azcopy|
|Azure PowerShell|azurepowershell|
|Bash|bash|
|C++|cpp|
|C++/CX|cppcx|
|C++/WinRT|cppwinrt|
|C#|csharp|
|浏览器中的 C#|csharp-interactive|
|控制台|控制台|
|CSHTML|cshtml|
|DAX|dax|
|Dockerfile|dockerfile|
|F#|fsharp|
|Go|go|
|HTML|html|
|HTTP|http|
|Java|java|
|JavaScript|javascript|
|JSON|json|
|Kusto 查询语言|kusto|
|Markdown|md|
|NodeJS|nodejs|
|Objective-C|objc|
|OData|odata|
|PHP|php|
|protobuf|protobuf|
|PowerApps（小数点分隔符）|powerapps-dot|
|PowerApps（逗号分隔符）|powerapps-comma|
|PowerShell|powershell|
|Python|Python|
|Q#|qsharp|
|R|r|
|Ruby|ruby|
|SQL|sql|
|Swift|swift|
|TypeScript|typescript|
|Visual Basic|vb|
|VBScript|vbscript|
|XAML|xaml|
|XML|xml|
|yml|yml|

`csharp-interactive` 名称指定 C# 语言，以及从浏览器中运行示例的能力。 这些代码片段在 Docker 容器中进行编译和执行，并且该程序执行的结果在用户浏览器窗口中显示。

以下是使用 C# (\`\`\`csharp)、Python (\`\`\`python) 和 PowerShell (\`\`\`powershell) 的语言 ID 的代码块示例。

##### <a name="c"></a>C\#

```csharp
using System;
namespace HelloWorld
{
    class Hello
    {
        static void Main()
        {
            Console.WriteLine("Hello World!");

            // Keep the console window open in debug mode.
            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

#### <a name="python"></a>Python

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a>PowerShell

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a>通用代码块

将三个反撇号 (&#96;&#96;&#96;) 用于通用代码块编码。

> 建议的方法是使用具有上一节中所述的语言标识符的代码块，以便确保在文档站点中突出显示正确的语法。 仅在需要时使用通用代码块。

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a>块引用

> 干旱至今已持续了一千万年，可怕的蜥蜴的统治早已结束。 在位于赤道的这片陆地上（某天会把这里当成非洲），生存竞争已经达到新高潮，而胜利者尚未出现。 在这片贫瘠而干旱的土地上，只有那些渺小或者敏捷或者凶残的生物才能茁壮成长，亦或是有希望生存下去。

## <a name="images"></a>图像

### <a name="static-image-or-animated-gif"></a>静态图像或动态 gif

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![这是替换文字](../images/Logo_DotNet.png)

### <a name="linked-image"></a>链接的图像

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

[![链接的图像的替换文字](../images/Logo_DotNet.png)](https://dot.net)

## <a name="videos"></a>视频

目前，可以通过以下语法嵌入第 9 频道和 YouTube 视频：

### <a name="channel-9"></a>第 9 频道

```markdown
> [!VIDEO <channel9_video_link>]
```

若要获取视频的正确 URL，请选择视频帧下面的“嵌入”选项卡，然后从`<iframe>` 元素复制 URL  。 例如:

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a>YouTube

若要获取视频的正确 URL，请右键单击视频，选择“复制嵌入代码”，然后从 `<iframe>` 元素复制 URL  。

```markdown
> [!VIDEO <youtube_video_link>]
```

例如:

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a>docs.microsoft 扩展

docs.microsoft 为 GitHub Flavored Markdown 提供了其他一些扩展。

### <a name="alerts"></a>警报

请务必使用以下警报格式，以便在文档站点中以正确格式呈现警报。 但是，GitHub 上的呈现引擎无法区分它们。

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

这些警报呈现如下：![警报样式](../images/alerts.png)

### <a name="includes"></a>包括

可以使用 include 将一个文件的 Markdown 嵌入到另一个文件中。

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a>选中的列表

可以在列表中使用自定义样式。 可以呈现带有绿色复选标记的列表。

> [!div class="checklist"]
>
> - 如何创建 .NET Core 应用
> - 如何向 Microsoft.XmlSerializer.Generator 包中添加引用
> - 如何编辑 MyApp.csproj 以添加依赖项
> - 如何添加类和 XmlSerializer
> - 如何生成并运行应用程序

可在 [.NET Core 文档](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator)的操作中查看列表示例。

### <a name="buttons"></a>按钮

> [!div class="button"]
> [按钮链接](../docs/core/index.md)

可在 [Visual Studio 文档](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio)中查看按钮操作示例。

### <a name="selectors"></a>选择器

> [!div class="op_single_selector"]
>
> - [macOS](../docs/core/tutorials/using-on-macos.md)
> - [Windows](../docs/core/tutorials/with-visual-studio.md)

可在 [Azure 文档](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic)中查看有效的选择器示例。

### <a name="step-by-steps"></a>按步执行

>[!div class="step-by-step"]
>[上一页](../docs/csharp/expression-trees-interpreting.md)
>[下一页](../docs/csharp/expression-trees-translating.md)

可在 [C# 指南 ](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure)中查看逐步操作的示例。

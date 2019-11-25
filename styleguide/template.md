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
# <a name="metadata-and-markdown-template"></a><span data-ttu-id="c1e5f-102">元数据和 Markdown 模板</span><span class="sxs-lookup"><span data-stu-id="c1e5f-102">Metadata and Markdown Template</span></span>

<span data-ttu-id="c1e5f-103">此 dotnet/文档模板包含 Markdown 语法的示例以及有关设置元数据的指南。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-103">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span> <span data-ttu-id="c1e5f-104">若要充分利用该模板，则必须查看[原始 Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) 和[呈现的视图](https://github.com/dotnet/docs/blob/master/styleguide/template.md)。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-104">To get the most of it, you must view both the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) and the [rendered view](https://github.com/dotnet/docs/blob/master/styleguide/template.md).</span></span>

<span data-ttu-id="c1e5f-105">创建 Markdown 文件时，应将此模板复制到新文件中，按下面的指定填写元数据，将上面的 H1 标题设置为本文的标题，并删除内容。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-105">When creating a Markdown file, you should copy this template to a new file, fill out the metadata as specified below, set the H1 heading above to the title of the article, and delete the content.</span></span>

## <a name="metadata"></a><span data-ttu-id="c1e5f-106">元数据</span><span class="sxs-lookup"><span data-stu-id="c1e5f-106">Metadata</span></span>

<span data-ttu-id="c1e5f-107">完整的元数据块如上所示（在[原始 Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md) 文件中），分为必填字段和可选字段。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-107">The full metadata block is above (in the [raw Markdown](https://raw.githubusercontent.com/dotnet/docs/master/styleguide/template.md)), divided into required fields and optional fields.</span></span> <span data-ttu-id="c1e5f-108">一些重要说明：</span><span class="sxs-lookup"><span data-stu-id="c1e5f-108">Some key notes:</span></span>

- <span data-ttu-id="c1e5f-109">元数据元素的冒号 (:) 和值之间**必须**有空格。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-109">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="c1e5f-110">如果可选的元数据元素没有值，请使用 # 注释掉该元素或将其删除（请勿将其留空或使用“na”）。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-110">If an optional metadata element doesn't have a value, comment out the element with a # or remove it (don't leave it blank or use "na").</span></span> <span data-ttu-id="c1e5f-111">如果要向已被注释掉的元素添加值，请务必删除 #。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-111">If you're adding a value to an element that was commented out, be sure to remove the #.</span></span>
- <span data-ttu-id="c1e5f-112">值（例如标题）中的冒号会中断元数据解析器。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-112">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="c1e5f-113">在此情况下，使用双引号将标题括起来（例如， `title: "Writing .NET Core console apps: An advanced step-by-step guide"`）。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-113">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="c1e5f-114">**title**：出现在搜索引擎结果中。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-114">**title**: Appears in search engine results.</span></span> <span data-ttu-id="c1e5f-115">此标题不应与 H1 标题相同，并且包含的字符数不超过 60 个。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-115">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="c1e5f-116">**描述**：概括文章内容。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-116">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="c1e5f-117">它通常显示在搜索结果页中，但不用于搜索排名。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-117">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="c1e5f-118">其长度应为 115-145 个字符，包括空格。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-118">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="c1e5f-119">“作者”和“ ms.author”   ：“作者”字段应包含作者的“GitHub 用户名”，而不是其别名  。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-119">**author** and **ms.author**: The author field should contain the **GitHub username** of the author, not his/her alias.</span></span>  <span data-ttu-id="c1e5f-120">另一方面，“ms.author”字段应包含 Microsoft 别名，并指示负责维护该文章的人员  。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-120">The **ms.author** field, on the other hand, should contain a Microsoft alias and indicates the person responsible for maintaining the article.</span></span>
- <span data-ttu-id="c1e5f-121">**ms.topic**：主题类型。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-121">**ms.topic**: The topic type.</span></span> <span data-ttu-id="c1e5f-122">最常见的值为 `conceptual` 并且在全局级别进行设置。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-122">The most common value is `conceptual` and is set at a global level.</span></span> <span data-ttu-id="c1e5f-123">使用的其他常用值为 `tutorial`、`overview` 和 `reference`。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-123">Other common values used are `tutorial`, `overview`, and `reference`.</span></span>
- <span data-ttu-id="c1e5f-124">“dev_langs”  定义主题显示的语言筛选器。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-124">**dev_langs** defines the language filter displayed for the topic.</span></span> <span data-ttu-id="c1e5f-125">可以在[支持的语言](#supported-languages)部分中查看受支持的值列表。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-125">You can see a list of the supported values in the [Supported languages](#supported-languages) section.</span></span> <span data-ttu-id="c1e5f-126">仅当主题涵盖了多个编程语言时才需要设置。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-126">Only needs to be set when there's more than one programming language covered in the topic.</span></span> <span data-ttu-id="c1e5f-127">通常，只在内容中使用 `csharp`、`vb`、`fsharp` 和 `cpp` 作为值。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-127">Typically, we only use `csharp`, `vb`, `fsharp`, and `cpp` for this value in our content.</span></span>
- <span data-ttu-id="c1e5f-128">**ms-chap**：用于 BI 目的的产品标识。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-128">**ms.prod**: Product identification used for BI purposes.</span></span> <span data-ttu-id="c1e5f-129">它们通常在全局级别进行设置，因此通常不会出现在每篇文章的元数据块中。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-129">They're usually set at a global level, so they don't usually appear in the metadata block of each article.</span></span>
- <span data-ttu-id="c1e5f-130">**ms.technology**：其他 BI 分类。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-130">**ms.technology**: Additional BI classification.</span></span> <span data-ttu-id="c1e5f-131">一些受支持的值是：适用于 C# 主题的 `devlang-csharp`、适用于 F# 主题的 `devlang-fsharp` 和适用于 VB 主题的 `devlang-visual-basic`。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-131">Some of the supported values are: `devlang-csharp` for C# topics, `devlang-fsharp` for F# topics, and `devlang-visual-basic` for VB topics.</span></span> <span data-ttu-id="c1e5f-132">对于其他指南，值将有所不同，因此请让团队成员提供指导。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-132">For other guides, the values will vary, so ask a member of the team for guidance.</span></span>
- <span data-ttu-id="c1e5f-133">**ms.date**：采用 MM/dd/yyyy 格式的日期。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-133">**ms.date**: A date in the format MM/dd/yyyy.</span></span> <span data-ttu-id="c1e5f-134">显示在“已发布”页面上，表明刚对文章进行了重大编辑或保证是“最新”的（即项目已查看并被视为最新）。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-134">Displayed on the published page to indicate the last time the article was substantially edited or guaranteed "fresh" (that is, the article was reviewed and considered up-to-date).</span></span>
- <span data-ttu-id="c1e5f-135">**helpviewer_keywords**：条目用于脱机图书索引（Visual Studio 中的功能）。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-135">**helpviewer_keywords**: Entries are used for the offline books index (functionality in Visual Studio).</span></span>
- <span data-ttu-id="c1e5f-136">**f1_keywords**：将文章连接到 F1 键（Visual Studio 中的功能）。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-136">**f1_keywords**: Connects the article to the F1 key (functionality in Visual Studio).</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="c1e5f-137">基本 Markdown、 GFM 和特殊字符</span><span class="sxs-lookup"><span data-stu-id="c1e5f-137">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="c1e5f-138">支持所有基本 Markdown 和 GitHub Flavored Markdown (GFM)。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-138">All basic and GitHub Flavored Markdown (GFM) is supported.</span></span> <span data-ttu-id="c1e5f-139">有关这些主题的更多信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="c1e5f-139">For more information on these, see:</span></span>

- [<span data-ttu-id="c1e5f-140">Markdown 基本语法</span><span class="sxs-lookup"><span data-stu-id="c1e5f-140">Baseline Markdown syntax</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="c1e5f-141">GFM 文档</span><span class="sxs-lookup"><span data-stu-id="c1e5f-141">GFM documentation</span></span>](https://guides.github.com/features/mastering-markdown)

<span data-ttu-id="c1e5f-142">Markdown 使用特殊字符如 \*、\` 和 \# 进行格式化。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-142">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="c1e5f-143">如果要在内容中包括一个特殊字符，必须执行以下两个操作之一：</span><span class="sxs-lookup"><span data-stu-id="c1e5f-143">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="c1e5f-144">在特殊字符前面放置一个反斜杠来“转义”它（例如，将 \* 写为 `\*`）</span><span class="sxs-lookup"><span data-stu-id="c1e5f-144">Put a backslash before the special character to "escape" it (for example, `\*` for an \*)</span></span>
- <span data-ttu-id="c1e5f-145">对字符使用 [HTML 实体代码](https://www.ascii.cl/htmlcodes.htm)（例如，将 &#42; 写为 `&#42;`）。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-145">Use the [HTML entity code](https://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for an &#42;).</span></span>

## <a name="file-name"></a><span data-ttu-id="c1e5f-146">文件名</span><span class="sxs-lookup"><span data-stu-id="c1e5f-146">File name</span></span>

<span data-ttu-id="c1e5f-147">文件名使用以下规则：</span><span class="sxs-lookup"><span data-stu-id="c1e5f-147">File names use the following rules:</span></span>

- <span data-ttu-id="c1e5f-148">只包含小写字母、数字和连字符。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-148">Contain only lowercase letters, numbers, and hyphens.</span></span>
- <span data-ttu-id="c1e5f-149">不包括空格或标点字符。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-149">No spaces or punctuation characters.</span></span> <span data-ttu-id="c1e5f-150">在文件名中使用连字符分隔单词和数字。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-150">Use the hyphens to separate words and numbers in the file name.</span></span>
- <span data-ttu-id="c1e5f-151">使用具体的动作动词，例如 develop、buy、build、troubleshoot。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-151">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="c1e5f-152">不使用带 -ing 的单词。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-152">No -ing words.</span></span>
- <span data-ttu-id="c1e5f-153">不使用小单词 - 不包含 a、and、the、in、or 等。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-153">No small words - don't include a, and, the, in, or, etc.</span></span>
- <span data-ttu-id="c1e5f-154">必须为 Markdown 格式，使用 .md 文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-154">Must be in Markdown and use the .md file extension.</span></span>
- <span data-ttu-id="c1e5f-155">保持文件名简短。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-155">Keep file names reasonably short.</span></span> <span data-ttu-id="c1e5f-156">它们是文章 URL 的一部分。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-156">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="c1e5f-157">标题</span><span class="sxs-lookup"><span data-stu-id="c1e5f-157">Headings</span></span>

<span data-ttu-id="c1e5f-158">使用句式单词首字母大写。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-158">Use sentence-style capitalization.</span></span> <span data-ttu-id="c1e5f-159">将标题、专有名词的第一个单词的第一个字母和冒号后的第一个字母大写（例如，“Tutorial:Predict prices using regression with ML.NET”）。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-159">Capitalize the first letter of the first word of a heading, proper nouns, and the first letter following a colon (for example, "Tutorial: Predict prices using regression with ML.NET").</span></span>

<span data-ttu-id="c1e5f-160">请勿在“How to”之后添加冒号（例如，“How to sort an array”而不是“How to:Sort an array”）。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-160">Don't add a colon after "How to" (for example, "How to sort an array" and not "How to: Sort an array").</span></span>

<span data-ttu-id="c1e5f-161">标题使用 atx 样式，即在行的开头使用 1-6 个哈希字符 (#) 来表示标题，对应于 HTML 标题级别 H1 到 H6。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-161">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="c1e5f-162">上面使用的是第一和第二级别标题示例。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-162">Examples of first- and second-level headers are used above.</span></span>

<span data-ttu-id="c1e5f-163">主题中**必须**只有一个第一级别标题 (H1)，此标题显示为页面上的标题。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-163">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="c1e5f-164">如果标题以 `#` 字符结尾，则需要对其进行转义以正确呈现标题。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-164">If your heading ends in a `#` character, you need to escape it for the title to render correctly.</span></span> <span data-ttu-id="c1e5f-165">例如 `# Async programming in F\#`。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-165">For example, `# Async programming in F\#`.</span></span>

<span data-ttu-id="c1e5f-166">第二级标题生成页面 TOC，显示在“In this article”部分的页面标题下方。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-166">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="third-level-heading"></a><span data-ttu-id="c1e5f-167">第三级标题</span><span class="sxs-lookup"><span data-stu-id="c1e5f-167">Third-level heading</span></span>
#### <a name="fourth-level-heading"></a><span data-ttu-id="c1e5f-168">第四级标题</span><span class="sxs-lookup"><span data-stu-id="c1e5f-168">Fourth-level heading</span></span>
##### <a name="fifth-level-heading"></a><span data-ttu-id="c1e5f-169">第五级标题</span><span class="sxs-lookup"><span data-stu-id="c1e5f-169">Fifth level heading</span></span>
###### <a name="sixth-level-heading"></a><span data-ttu-id="c1e5f-170">第六级标题</span><span class="sxs-lookup"><span data-stu-id="c1e5f-170">Sixth-level heading</span></span>

## <a name="text-styling"></a><span data-ttu-id="c1e5f-171">文本样式</span><span class="sxs-lookup"><span data-stu-id="c1e5f-171">Text styling</span></span>

<span data-ttu-id="c1e5f-172">斜体：用于文件、文件夹、路径（对于较长的项，将其拆分到各自行）和新术语  。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-172">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="c1e5f-173">**粗体**用于 UI 元素。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-173">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="c1e5f-174">`Code`：用于内联代码、语言关键字、NuGet 包名称、命令行命令、数据库表和列名称，以及不希望其变为可单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-174">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="c1e5f-175">链接</span><span class="sxs-lookup"><span data-stu-id="c1e5f-175">Links</span></span>

### <a name="internal-links"></a><span data-ttu-id="c1e5f-176">内部链接</span><span class="sxs-lookup"><span data-stu-id="c1e5f-176">Internal Links</span></span>

<span data-ttu-id="c1e5f-177">若要链接到同一 Markdown 文件中的标题（也称为定位链接），需要找出想要链接到的标题的 ID。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-177">To link to a header in the same Markdown file (also known as anchor links), you'll need to find out the id of the header you're trying to link to.</span></span> <span data-ttu-id="c1e5f-178">若要确认 ID，请查看呈现的文章的源，以查找 ID（例如， `id="blockquote"`），并使用 # + ID 进行链接（例如， `#blockquote`）。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-178">To confirm the ID, view the source of the rendered article, find the id of the header (for example, `id="blockquote"`), and link using # + id (for example, `#blockquote`).</span></span>
<span data-ttu-id="c1e5f-179">ID 是基于标头文本自动生成的。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-179">The id is auto-generated based on the header text.</span></span> <span data-ttu-id="c1e5f-180">因此，例如，如果某个唯一部分名称为 `## Step 2`，则 ID 应类似于 `id="step-2"`。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-180">So, for example, given a unique section named `## Step 2`, the id would look like this `id="step-2"`.</span></span>

- <span data-ttu-id="c1e5f-181">示例：`[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` 生成[使用语言标识符声明内联块](#inline-code-blocks-with-language-identifier)。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-181">Example: `[Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier)` produces [Declare inline blocks with a language identifier](#inline-code-blocks-with-language-identifier).</span></span>

<span data-ttu-id="c1e5f-182">若要链接到同一个存储库中的 Markdown 文件，请使用[相对链接](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2)，文件名末尾包含“.md”。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-182">To link to a Markdown file in the same repo, use [relative links](https://www.w3.org/TR/WD-html40-970917/htmlweb.html#h-5.1.2), including the ".md" at the end of the filename.</span></span>

- <span data-ttu-id="c1e5f-183">示例：`[Readme file](../README.md)` 生成[自述文件](../README.md)。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-183">Example: `[Readme file](../README.md)` produces [Readme file](../README.md).</span></span> <span data-ttu-id="c1e5f-184">（请注意，链接区分大小写。）</span><span class="sxs-lookup"><span data-stu-id="c1e5f-184">(Note that links are case-sensitive.)</span></span>
- <span data-ttu-id="c1e5f-185">示例：`[Welcome to .NET](../docs/welcome.md)` 生成[欢迎使用 .NET](../docs/welcome.md)。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-185">Example: `[Welcome to .NET](../docs/welcome.md)` produces [Welcome to .NET](../docs/welcome.md).</span></span>

<span data-ttu-id="c1e5f-186">若要链接到同一个存储库中的 Markdown 文件中的标头，请使用相对链接 + 哈希标记进行链接。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-186">To link to a header in a Markdown file in the same repo, use relative linking + hashtag linking.</span></span>

- <span data-ttu-id="c1e5f-187">示例：`[.NET Community](../docs/welcome.md#open-source)` 生成[.NET 社区](../docs/welcome.md#open-source)。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-187">Example: `[.NET Community](../docs/welcome.md#open-source)` produces [.NET Community](../docs/welcome.md#open-source).</span></span>

<span data-ttu-id="c1e5f-188">大多数情况下，我们使用相对链接，阻止在链接中使用 `~/`，因为在 GitHub 上的源中解析相对链接。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-188">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="c1e5f-189">但是，当我们链接到依赖存储库中的文件时，我们将使用 `~/` 字符来提供路径。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-189">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="c1e5f-190">由于依赖存储库中的文件位于 GitHub 中的不同位置，因此无论链接的编写方式如何，都无法使用相对链接正确解析这些链接。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-190">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>

<span data-ttu-id="c1e5f-191">C# 语言规范和 Visual Basic 语言规范通过包含语言存储库中的源，都包含在 .NET 文档中。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-191">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="c1e5f-192">Markdown 源在 [csharplang](https://github.com/dotnet/csharplang) 和 [visual basic](https://github.com/dotnet/vblang) 存储库中进行管理。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-192">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [visual basic](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="c1e5f-193">指向规范的链接必须指向包含这些规范的源目录。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-193">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="c1e5f-194">对于 C#，它是“~/_csharplang/spec”，对于 VB，它是“~/_vblang/spec”   。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-194">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**.</span></span>

- <span data-ttu-id="c1e5f-195">示例：`[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` 生成 [C# 查询表达式](~/_csharplang/spec/expressions.md#query-expressions)。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-195">Example: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)` produces [C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions).</span></span>

### <a name="external-links"></a><span data-ttu-id="c1e5f-196">外部链接</span><span class="sxs-lookup"><span data-stu-id="c1e5f-196">External Links</span></span>

<span data-ttu-id="c1e5f-197">若要链接到外部文件，请使用完整的 URL 作为链接。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-197">To link to an external file, use the full URL as the link.</span></span>

- <span data-ttu-id="c1e5f-198">示例：`[GitHub](https://www.github.com)` 生成 [GitHub](https://www.github.com)。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-198">Example: `[GitHub](https://www.github.com)` produces [GitHub](https://www.github.com).</span></span>

<span data-ttu-id="c1e5f-199">如果在 Markdown 文件中显示一个 URL，此 URL 将转换为可单击的链接。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-199">If a URL appears in a Markdown file, it will be transformed into a clickable link.</span></span>

- <span data-ttu-id="c1e5f-200">示例：`<https://www.github.com>` 生成 <https://www.github.com>。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-200">Example: `<https://www.github.com>` produces <https://www.github.com>.</span></span>

<span data-ttu-id="c1e5f-201">外部链接首选 `https` 协议。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-201">Prefer the `https` protocol for external links.</span></span> <span data-ttu-id="c1e5f-202">仅为不支持 `https` 的站点使用 `http` 链接。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-202">Only use `http` links for sites that do not support `https`.</span></span>

### <a name="links-to-apis"></a><span data-ttu-id="c1e5f-203">链接到 API</span><span class="sxs-lookup"><span data-stu-id="c1e5f-203">Links to APIs</span></span>

<span data-ttu-id="c1e5f-204">生成系统具有一些扩展功能，使我们能够链接到 .NET API，而无需使用外部链接。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-204">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span>
<span data-ttu-id="c1e5f-205">链接到 API 时，可以使用从源代码自动生成的 API 的唯一标识符 (UID)。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-205">When linking to an API, you can use its unique identifier (UID) that is auto-generated from the source code.</span></span>

<span data-ttu-id="c1e5f-206">UID 等同于完全限定的类型和成员名称。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-206">The UID equates to the fully qualified type and member name.</span></span>

<span data-ttu-id="c1e5f-207">如果在 UID 后面添加 \*（或 %2A），则该链接将表示重载页，而不是特定的 API。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-207">If you add a \* (or %2A) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="c1e5f-208">例如，如果希望使用通用方法而不是特定重载（比如 [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_)）链接到 [List\<T>.BinarySearch 方法](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch)页，可以使用该类型。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-208">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="c1e5f-209">当成员未重载时，还可以使用 \* 链接到成员页；这样可以避免在 UID 中包含参数列表。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-209">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="c1e5f-210">若要链接到特定的方法重载，必须包括该方法每个参数的完全限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-210">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="c1e5f-211">例如，\<xref:System.DateTime.ToString> 链接到无参数的 [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) 方法，而 \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> 链接到 [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) 方法。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-211">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span> <span data-ttu-id="c1e5f-212">可以从 <https://xref.docs.microsoft.com/autocomplete> 中查找特定重载成员的 UID。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-212">You can find the UIDs of a particular overloaded member from <https://xref.docs.microsoft.com/autocomplete>.</span></span> <span data-ttu-id="c1e5f-213">查询字符串“?text==\<type-member-name>”标识要查看其 UID 的类型或成员  。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-213">The query string "?text=*\<type-member-name>*" identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="c1e5f-214">例如，<https://xref.docs.microsoft.com/autocomplete?text=string.format> 检索 [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) 重载。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-214">For example, <https://xref.docs.microsoft.com/autocomplete?text=string.format> retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span>

<span data-ttu-id="c1e5f-215">若要链接到泛型类型（如 [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1)），请在泛型类型参数后面使用 \` (%60) 字符。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-215">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (%60) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="c1e5f-216">例如，\<xref:System.Nullable%601> 链接到 [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) 类型，而 \<xref:System.Func%602> 链接到 [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) 委托。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-216">For example, \<xref:System.Nullable%601> links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while \<xref:System.Func%602> links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

<span data-ttu-id="c1e5f-217">可以使用以下任一种语法：</span><span class="sxs-lookup"><span data-stu-id="c1e5f-217">You can use one of the following syntax:</span></span>

1. <span data-ttu-id="c1e5f-218">自动链接：`<xref:UID>` 或 `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="c1e5f-218">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="c1e5f-219">`displayProperty` 查询参数生成完全限定的链接文本。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-219">The `displayProperty` query    parameter produces a fully qualified link text.</span></span> <span data-ttu-id="c1e5f-220">默认情况下，链接文本仅显示成员或类型名称。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-220">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="c1e5f-221">Markdown 链接：`[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="c1e5f-221">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="c1e5f-222">需要自定义显示的链接文本时使用。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-222">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="c1e5f-223">示例：</span><span class="sxs-lookup"><span data-stu-id="c1e5f-223">Examples:</span></span>

- <span data-ttu-id="c1e5f-224">`<xref:System.String>` 呈现为 [String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="c1e5f-224">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="c1e5f-225">`<xref:System.String?displayProperty=nameWithType>` 呈现为 [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="c1e5f-225">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="c1e5f-226">`[String class](xref:System.String)` 呈现为 [String 类](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="c1e5f-226">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="c1e5f-227">有关使用这一表示法的详细信息，请参阅 [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference)（使用交叉引用）。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-227">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="c1e5f-228">有两种方法可以查找 UID：</span><span class="sxs-lookup"><span data-stu-id="c1e5f-228">There are two ways to find the UID:</span></span>

- <span data-ttu-id="c1e5f-229">查看要链接到的 API 页面的源，并找到 assetid 值。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-229">View the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="c1e5f-230">请注意，各个重载值不会显示在源中。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-230">Note that individual overload values are not shown in the source.</span></span>
- <span data-ttu-id="c1e5f-231">使用以下工具搜索 UID：<https://xref.docs.microsoft.com/autocomplete?text=tostring>（将 tostring 替换为尝试查找的部分 API 名称）。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-231">Use the following tool to search for UIDs: <https://xref.docs.microsoft.com/autocomplete?text=tostring> (replace tostring with parts of the API name you're trying to find).</span></span> <span data-ttu-id="c1e5f-232">该工具在 UID 的任何部分中搜索提供的 `text` 查询参数。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-232">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="c1e5f-233">例如，可以搜索成员名称 (ToString)、部分成员名称 (ToStri)、类型和成员名称 (Double.ToString) 等。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-233">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="c1e5f-234">如果 UID 包含特殊字符 \`、\# 或 \*，则 UID 值需要分别使用 HTML 编码为 `%60`、`%23` 和 `%2A`。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-234">When the UID contains the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="c1e5f-235">有时会看到对括号进行编码，但这并不是必需的。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-235">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="c1e5f-236">示例：</span><span class="sxs-lookup"><span data-stu-id="c1e5f-236">Examples:</span></span>

- <span data-ttu-id="c1e5f-237">System.Threading.Tasks.Task\`1 生成 `System.Threading.Tasks.Task%601`</span><span class="sxs-lookup"><span data-stu-id="c1e5f-237">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="c1e5f-238">System.Exception.\#ctor 生成 `System.Exception.%23ctor`</span><span class="sxs-lookup"><span data-stu-id="c1e5f-238">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="c1e5f-239">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) 生成 `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span><span class="sxs-lookup"><span data-stu-id="c1e5f-239">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

## <a name="lists"></a><span data-ttu-id="c1e5f-240">列表</span><span class="sxs-lookup"><span data-stu-id="c1e5f-240">Lists</span></span>

### <a name="ordered-lists"></a><span data-ttu-id="c1e5f-241">有序列表</span><span class="sxs-lookup"><span data-stu-id="c1e5f-241">Ordered lists</span></span>

1. <span data-ttu-id="c1e5f-242">这</span><span class="sxs-lookup"><span data-stu-id="c1e5f-242">This</span></span>
1. <span data-ttu-id="c1e5f-243">是</span><span class="sxs-lookup"><span data-stu-id="c1e5f-243">Is</span></span>
1. <span data-ttu-id="c1e5f-244">一个</span><span class="sxs-lookup"><span data-stu-id="c1e5f-244">An</span></span>
1. <span data-ttu-id="c1e5f-245">Ordered</span><span class="sxs-lookup"><span data-stu-id="c1e5f-245">Ordered</span></span>
1. <span data-ttu-id="c1e5f-246">列表</span><span class="sxs-lookup"><span data-stu-id="c1e5f-246">List</span></span>

#### <a name="ordered-list-with-an-embedded-list"></a><span data-ttu-id="c1e5f-247">包含嵌套列表的有序列表</span><span class="sxs-lookup"><span data-stu-id="c1e5f-247">Ordered list with an embedded list</span></span>

1. <span data-ttu-id="c1e5f-248">Here</span><span class="sxs-lookup"><span data-stu-id="c1e5f-248">Here</span></span>
1. <span data-ttu-id="c1e5f-249">comes</span><span class="sxs-lookup"><span data-stu-id="c1e5f-249">comes</span></span>
1. <span data-ttu-id="c1e5f-250">一个</span><span class="sxs-lookup"><span data-stu-id="c1e5f-250">an</span></span>
1. <span data-ttu-id="c1e5f-251">embedded</span><span class="sxs-lookup"><span data-stu-id="c1e5f-251">embedded</span></span>
    1. <span data-ttu-id="c1e5f-252">Miss Scarlett</span><span class="sxs-lookup"><span data-stu-id="c1e5f-252">Miss Scarlett</span></span>
    1. <span data-ttu-id="c1e5f-253">Professor Plum</span><span class="sxs-lookup"><span data-stu-id="c1e5f-253">Professor Plum</span></span>
1. <span data-ttu-id="c1e5f-254">ordered</span><span class="sxs-lookup"><span data-stu-id="c1e5f-254">ordered</span></span>
1. <span data-ttu-id="c1e5f-255">list</span><span class="sxs-lookup"><span data-stu-id="c1e5f-255">list</span></span>

### <a name="unordered-lists"></a><span data-ttu-id="c1e5f-256">无序列表</span><span class="sxs-lookup"><span data-stu-id="c1e5f-256">Unordered Lists</span></span>

- <span data-ttu-id="c1e5f-257">这</span><span class="sxs-lookup"><span data-stu-id="c1e5f-257">This</span></span>
- <span data-ttu-id="c1e5f-258">is</span><span class="sxs-lookup"><span data-stu-id="c1e5f-258">is</span></span>
- <span data-ttu-id="c1e5f-259">a</span><span class="sxs-lookup"><span data-stu-id="c1e5f-259">a</span></span>
- <span data-ttu-id="c1e5f-260">无序</span><span class="sxs-lookup"><span data-stu-id="c1e5f-260">bulleted</span></span>
- <span data-ttu-id="c1e5f-261">list</span><span class="sxs-lookup"><span data-stu-id="c1e5f-261">list</span></span>

#### <a name="unordered-list-with-an-embedded-list"></a><span data-ttu-id="c1e5f-262">包含嵌套列表的无序列表</span><span class="sxs-lookup"><span data-stu-id="c1e5f-262">Unordered list with an embedded list</span></span>

- <span data-ttu-id="c1e5f-263">这</span><span class="sxs-lookup"><span data-stu-id="c1e5f-263">This</span></span>
- <span data-ttu-id="c1e5f-264">无序</span><span class="sxs-lookup"><span data-stu-id="c1e5f-264">bulleted</span></span>
- <span data-ttu-id="c1e5f-265">list</span><span class="sxs-lookup"><span data-stu-id="c1e5f-265">list</span></span>
  - <span data-ttu-id="c1e5f-266">Mrs. Peacock</span><span class="sxs-lookup"><span data-stu-id="c1e5f-266">Mrs. Peacock</span></span>
  - <span data-ttu-id="c1e5f-267">Mr. Green</span><span class="sxs-lookup"><span data-stu-id="c1e5f-267">Mr. Green</span></span>
- <span data-ttu-id="c1e5f-268">包含</span><span class="sxs-lookup"><span data-stu-id="c1e5f-268">contains</span></span>
- <span data-ttu-id="c1e5f-269">其他</span><span class="sxs-lookup"><span data-stu-id="c1e5f-269">other</span></span>
  1. <span data-ttu-id="c1e5f-270">Colonel Mustard</span><span class="sxs-lookup"><span data-stu-id="c1e5f-270">Colonel Mustard</span></span>
  1. <span data-ttu-id="c1e5f-271">Mrs. White</span><span class="sxs-lookup"><span data-stu-id="c1e5f-271">Mrs. White</span></span>
- <span data-ttu-id="c1e5f-272">列表</span><span class="sxs-lookup"><span data-stu-id="c1e5f-272">lists</span></span>

## <a name="horizontal-rule"></a><span data-ttu-id="c1e5f-273">水平标尺</span><span class="sxs-lookup"><span data-stu-id="c1e5f-273">Horizontal rule</span></span>

---

## <a name="tables"></a><span data-ttu-id="c1e5f-274">表</span><span class="sxs-lookup"><span data-stu-id="c1e5f-274">Tables</span></span>

| <span data-ttu-id="c1e5f-275">表</span><span class="sxs-lookup"><span data-stu-id="c1e5f-275">Tables</span></span>        | <span data-ttu-id="c1e5f-276">很</span><span class="sxs-lookup"><span data-stu-id="c1e5f-276">Are</span></span>           | <span data-ttu-id="c1e5f-277">酷</span><span class="sxs-lookup"><span data-stu-id="c1e5f-277">Cool</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="c1e5f-278">第 3 列是</span><span class="sxs-lookup"><span data-stu-id="c1e5f-278">col 3 is</span></span>      | <span data-ttu-id="c1e5f-279">右对齐</span><span class="sxs-lookup"><span data-stu-id="c1e5f-279">right-aligned</span></span> | <span data-ttu-id="c1e5f-280">$1600</span><span class="sxs-lookup"><span data-stu-id="c1e5f-280">$1600</span></span> |
| <span data-ttu-id="c1e5f-281">第 2 列是</span><span class="sxs-lookup"><span data-stu-id="c1e5f-281">col 2 is</span></span>      | <span data-ttu-id="c1e5f-282">居中对齐</span><span class="sxs-lookup"><span data-stu-id="c1e5f-282">centered</span></span>      |   <span data-ttu-id="c1e5f-283">$12</span><span class="sxs-lookup"><span data-stu-id="c1e5f-283">$12</span></span> |
| <span data-ttu-id="c1e5f-284">第 1 列为默认对齐方式</span><span class="sxs-lookup"><span data-stu-id="c1e5f-284">col 1 is default</span></span> | <span data-ttu-id="c1e5f-285">左对齐</span><span class="sxs-lookup"><span data-stu-id="c1e5f-285">left-aligned</span></span>     |    <span data-ttu-id="c1e5f-286">$1</span><span class="sxs-lookup"><span data-stu-id="c1e5f-286">$1</span></span> |

<span data-ttu-id="c1e5f-287">可以使用 [Markdown 表生成器工具](https://www.tablesgenerator.com/markdown_tables)来更轻松地创建它们。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-287">You can use a [Markdown table generator tool](https://www.tablesgenerator.com/markdown_tables) to help creating them more easily.</span></span>

## <a name="code"></a><span data-ttu-id="c1e5f-288">代码</span><span class="sxs-lookup"><span data-stu-id="c1e5f-288">Code</span></span>

<span data-ttu-id="c1e5f-289">包含代码的最好方法是包含工作示例中的代码片段。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-289">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="c1e5f-290">按照[参与指南](../CONTRIBUTING.md#contributing-to-samples)中的说明创建示例。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-290">Create your sample following the instructions in the [contributing guide](../CONTRIBUTING.md#contributing-to-samples).</span></span>

<span data-ttu-id="c1e5f-291">可以使用以下语法来包含代码：</span><span class="sxs-lookup"><span data-stu-id="c1e5f-291">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

- <span data-ttu-id="c1e5f-292">`-<language>`（可选但建议这样做）  </span><span class="sxs-lookup"><span data-stu-id="c1e5f-292">`-<language>` (*optional* but *recommended*)</span></span>
  - <span data-ttu-id="c1e5f-293">引用的代码片段的语言。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-293">Language of the code snippet being referenced.</span></span> <span data-ttu-id="c1e5f-294">有关支持的值列表，请参阅[支持的语言](#supported-languages)。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-294">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

- <span data-ttu-id="c1e5f-295">`<name>`（可选） </span><span class="sxs-lookup"><span data-stu-id="c1e5f-295">`<name>` (*optional*)</span></span>
  - <span data-ttu-id="c1e5f-296">代码片段的名称。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-296">Name for the code snippet.</span></span> <span data-ttu-id="c1e5f-297">它不会对输出 HTML 产生任何影响，但可以使用它来提高 Markdown 源的可读性。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-297">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

- <span data-ttu-id="c1e5f-298">`<pathToFile>`（强制） </span><span class="sxs-lookup"><span data-stu-id="c1e5f-298">`<pathToFile>` (*mandatory*)</span></span>
  - <span data-ttu-id="c1e5f-299">文件系统中的相对路径指示要引用的代码片段文件。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-299">Relative path in the file system that indicates the code snippet file to reference.</span></span>

- <span data-ttu-id="c1e5f-300">`<queryoption>` 和 `<queryoptionvalue>`（可选） </span><span class="sxs-lookup"><span data-stu-id="c1e5f-300">`<queryoption>` and `<queryoptionvalue>` (*optional*)</span></span>
  - <span data-ttu-id="c1e5f-301">一起使用可以指定从文件中检索代码的方式：</span><span class="sxs-lookup"><span data-stu-id="c1e5f-301">Used together to specify how the code should be retrieved from the file:</span></span>
    - <span data-ttu-id="c1e5f-302">`#`：`#L{startlinenumber}-L{endlinenumber}`（行范围）或 `#{tagname}`（标记名称）  。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-302">`#`:  `#L{startlinenumber}-L{endlinenumber}` (line range) *or* `#{tagname}` (tag name).</span></span>
    <span data-ttu-id="c1e5f-303">不建议使用行号，因为它们容易出错。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-303">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="c1e5f-304">标记名称是引用代码片段的首选方法。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-304">Tag name is the preferred way of referencing code snippets.</span></span>
    - <span data-ttu-id="c1e5f-305">`range`：`?range=1,3-5` 行范围。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-305">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="c1e5f-306">此示例包括第 1、第 3、第 4 和第 5 行。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-306">This example includes lines 1, 3, 4, and 5.</span></span>
    - <span data-ttu-id="c1e5f-307">`dedent`：`?dedent=8` 用若干空格取消缩进行 - 此事例中为第 8 行。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-307">`dedent`: `?dedent=8` Dedents the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="c1e5f-308">这可以与 `range` 和其他查询选项结合使用，这些选项用于选择文件中行的子集。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-308">This can be combined with the `range` and other query options that select a subset of the lines of a file.</span></span>
    - <span data-ttu-id="c1e5f-309">`outdent`：`?outdent=8` 用若干空格减少缩进行 - 此事例中为第 8 行。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-309">`outdent`: `?outdent=8` Reverses the indent of the lines by a number of spaces--in this case, 8.</span></span> <span data-ttu-id="c1e5f-310">这可以与 `range` 和其他查询选项结合使用，这些选项用于选择文件中行的子集。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-310">This can be combined with `range` and other query options that select a subset of the lines of a file.</span></span>

<span data-ttu-id="c1e5f-311">建议尽可能使用标记名称选项。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-311">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="c1e5f-312">标记名称是区域的名称或代码注释的名称，其格式为源代码中的 `Snippettagname` 格式。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-312">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="c1e5f-313">下面的示例演示如何引用标记名称 `1`：</span><span class="sxs-lookup"><span data-stu-id="c1e5f-313">The following example shows how to refer to the tag name `1`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]
```

<span data-ttu-id="c1e5f-314">可在[此源文件](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs)中了解片段标记的结构。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-314">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/keywords/throw/throw-1.cs).</span></span> <span data-ttu-id="c1e5f-315">有关代码片段源文件中的标记名称表示形式（按语言）的详细信息，请参阅 [DocFX 指南](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file)。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-315">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="c1e5f-316">包括完整程序中的代码片段可以确保在整个持续集成 (CI) 系统中运行所有代码。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-316">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="c1e5f-317">但是，如果需要显示导致编译时或运行时错误的一些内容，则可以使用内联代码块。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-317">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

### <a name="inline-code-blocks-with-language-identifier"></a><span data-ttu-id="c1e5f-318">具有语言标识符的内联代码块</span><span class="sxs-lookup"><span data-stu-id="c1e5f-318">Inline code blocks with language identifier</span></span>

<span data-ttu-id="c1e5f-319">使用三个反撇号 (\`\`\`) + 语言 ID，将特定于语言的颜色编码应用到代码块。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-319">Use three backticks (\`\`\`) + a language ID to apply language-specific color coding to a code block.</span></span> <span data-ttu-id="c1e5f-320">下面是支持的语言列表，显示了每个语言 ID 的 markdown 标签。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-320">Here is the list of supported languages showing the markdown label for each language ID.</span></span>

#### <a name="supported-languages"></a><span data-ttu-id="c1e5f-321">支持的语言</span><span class="sxs-lookup"><span data-stu-id="c1e5f-321">Supported languages</span></span>

|<span data-ttu-id="c1e5f-322">name</span><span class="sxs-lookup"><span data-stu-id="c1e5f-322">Name</span></span>|<span data-ttu-id="c1e5f-323">Markdown 标签</span><span class="sxs-lookup"><span data-stu-id="c1e5f-323">Markdown label</span></span>|
|-----|-------|
|<span data-ttu-id="c1e5f-324">.NET 控制台</span><span class="sxs-lookup"><span data-stu-id="c1e5f-324">.NET Console</span></span>|<span data-ttu-id="c1e5f-325">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="c1e5f-325">dotnetcli</span></span>|
|<span data-ttu-id="c1e5f-326">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="c1e5f-326">ASP.NET (C#)</span></span>|<span data-ttu-id="c1e5f-327">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="c1e5f-327">aspx-csharp</span></span>|
|<span data-ttu-id="c1e5f-328">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="c1e5f-328">ASP.NET (VB)</span></span>|<span data-ttu-id="c1e5f-329">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="c1e5f-329">aspx-vb</span></span>|
|<span data-ttu-id="c1e5f-330">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="c1e5f-330">Azure CLI</span></span>|<span data-ttu-id="c1e5f-331">azurecli</span><span class="sxs-lookup"><span data-stu-id="c1e5f-331">azurecli</span></span>|
|<span data-ttu-id="c1e5f-332">AzCopy</span><span class="sxs-lookup"><span data-stu-id="c1e5f-332">AzCopy</span></span>|<span data-ttu-id="c1e5f-333">azcopy</span><span class="sxs-lookup"><span data-stu-id="c1e5f-333">azcopy</span></span>|
|<span data-ttu-id="c1e5f-334">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1e5f-334">Azure PowerShell</span></span>|<span data-ttu-id="c1e5f-335">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="c1e5f-335">azurepowershell</span></span>|
|<span data-ttu-id="c1e5f-336">Bash</span><span class="sxs-lookup"><span data-stu-id="c1e5f-336">Bash</span></span>|<span data-ttu-id="c1e5f-337">bash</span><span class="sxs-lookup"><span data-stu-id="c1e5f-337">bash</span></span>|
|<span data-ttu-id="c1e5f-338">C++</span><span class="sxs-lookup"><span data-stu-id="c1e5f-338">C++</span></span>|<span data-ttu-id="c1e5f-339">cpp</span><span class="sxs-lookup"><span data-stu-id="c1e5f-339">cpp</span></span>|
|<span data-ttu-id="c1e5f-340">C++/CX</span><span class="sxs-lookup"><span data-stu-id="c1e5f-340">C++/CX</span></span>|<span data-ttu-id="c1e5f-341">cppcx</span><span class="sxs-lookup"><span data-stu-id="c1e5f-341">cppcx</span></span>|
|<span data-ttu-id="c1e5f-342">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="c1e5f-342">C++/WinRT</span></span>|<span data-ttu-id="c1e5f-343">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="c1e5f-343">cppwinrt</span></span>|
|<span data-ttu-id="c1e5f-344">C#</span><span class="sxs-lookup"><span data-stu-id="c1e5f-344">C#</span></span>|<span data-ttu-id="c1e5f-345">csharp</span><span class="sxs-lookup"><span data-stu-id="c1e5f-345">csharp</span></span>|
|<span data-ttu-id="c1e5f-346">浏览器中的 C#</span><span class="sxs-lookup"><span data-stu-id="c1e5f-346">C# in browser</span></span>|<span data-ttu-id="c1e5f-347">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="c1e5f-347">csharp-interactive</span></span>|
|<span data-ttu-id="c1e5f-348">控制台</span><span class="sxs-lookup"><span data-stu-id="c1e5f-348">Console</span></span>|<span data-ttu-id="c1e5f-349">控制台</span><span class="sxs-lookup"><span data-stu-id="c1e5f-349">console</span></span>|
|<span data-ttu-id="c1e5f-350">CSHTML</span><span class="sxs-lookup"><span data-stu-id="c1e5f-350">CSHTML</span></span>|<span data-ttu-id="c1e5f-351">cshtml</span><span class="sxs-lookup"><span data-stu-id="c1e5f-351">cshtml</span></span>|
|<span data-ttu-id="c1e5f-352">DAX</span><span class="sxs-lookup"><span data-stu-id="c1e5f-352">DAX</span></span>|<span data-ttu-id="c1e5f-353">dax</span><span class="sxs-lookup"><span data-stu-id="c1e5f-353">dax</span></span>|
|<span data-ttu-id="c1e5f-354">Dockerfile</span><span class="sxs-lookup"><span data-stu-id="c1e5f-354">Dockerfile</span></span>|<span data-ttu-id="c1e5f-355">dockerfile</span><span class="sxs-lookup"><span data-stu-id="c1e5f-355">dockerfile</span></span>|
|<span data-ttu-id="c1e5f-356">F#</span><span class="sxs-lookup"><span data-stu-id="c1e5f-356">F#</span></span>|<span data-ttu-id="c1e5f-357">fsharp</span><span class="sxs-lookup"><span data-stu-id="c1e5f-357">fsharp</span></span>|
|<span data-ttu-id="c1e5f-358">Go</span><span class="sxs-lookup"><span data-stu-id="c1e5f-358">Go</span></span>|<span data-ttu-id="c1e5f-359">go</span><span class="sxs-lookup"><span data-stu-id="c1e5f-359">go</span></span>|
|<span data-ttu-id="c1e5f-360">HTML</span><span class="sxs-lookup"><span data-stu-id="c1e5f-360">HTML</span></span>|<span data-ttu-id="c1e5f-361">html</span><span class="sxs-lookup"><span data-stu-id="c1e5f-361">html</span></span>|
|<span data-ttu-id="c1e5f-362">HTTP</span><span class="sxs-lookup"><span data-stu-id="c1e5f-362">HTTP</span></span>|<span data-ttu-id="c1e5f-363">http</span><span class="sxs-lookup"><span data-stu-id="c1e5f-363">http</span></span>|
|<span data-ttu-id="c1e5f-364">Java</span><span class="sxs-lookup"><span data-stu-id="c1e5f-364">Java</span></span>|<span data-ttu-id="c1e5f-365">java</span><span class="sxs-lookup"><span data-stu-id="c1e5f-365">java</span></span>|
|<span data-ttu-id="c1e5f-366">JavaScript</span><span class="sxs-lookup"><span data-stu-id="c1e5f-366">JavaScript</span></span>|<span data-ttu-id="c1e5f-367">javascript</span><span class="sxs-lookup"><span data-stu-id="c1e5f-367">javascript</span></span>|
|<span data-ttu-id="c1e5f-368">JSON</span><span class="sxs-lookup"><span data-stu-id="c1e5f-368">JSON</span></span>|<span data-ttu-id="c1e5f-369">json</span><span class="sxs-lookup"><span data-stu-id="c1e5f-369">json</span></span>|
|<span data-ttu-id="c1e5f-370">Kusto 查询语言</span><span class="sxs-lookup"><span data-stu-id="c1e5f-370">Kusto Query Language</span></span>|<span data-ttu-id="c1e5f-371">kusto</span><span class="sxs-lookup"><span data-stu-id="c1e5f-371">kusto</span></span>|
|<span data-ttu-id="c1e5f-372">Markdown</span><span class="sxs-lookup"><span data-stu-id="c1e5f-372">Markdown</span></span>|<span data-ttu-id="c1e5f-373">md</span><span class="sxs-lookup"><span data-stu-id="c1e5f-373">md</span></span>|
|<span data-ttu-id="c1e5f-374">NodeJS</span><span class="sxs-lookup"><span data-stu-id="c1e5f-374">NodeJS</span></span>|<span data-ttu-id="c1e5f-375">nodejs</span><span class="sxs-lookup"><span data-stu-id="c1e5f-375">nodejs</span></span>|
|<span data-ttu-id="c1e5f-376">Objective-C</span><span class="sxs-lookup"><span data-stu-id="c1e5f-376">Objective-C</span></span>|<span data-ttu-id="c1e5f-377">objc</span><span class="sxs-lookup"><span data-stu-id="c1e5f-377">objc</span></span>|
|<span data-ttu-id="c1e5f-378">OData</span><span class="sxs-lookup"><span data-stu-id="c1e5f-378">OData</span></span>|<span data-ttu-id="c1e5f-379">odata</span><span class="sxs-lookup"><span data-stu-id="c1e5f-379">odata</span></span>|
|<span data-ttu-id="c1e5f-380">PHP</span><span class="sxs-lookup"><span data-stu-id="c1e5f-380">PHP</span></span>|<span data-ttu-id="c1e5f-381">php</span><span class="sxs-lookup"><span data-stu-id="c1e5f-381">php</span></span>|
|<span data-ttu-id="c1e5f-382">protobuf</span><span class="sxs-lookup"><span data-stu-id="c1e5f-382">protobuf</span></span>|<span data-ttu-id="c1e5f-383">protobuf</span><span class="sxs-lookup"><span data-stu-id="c1e5f-383">protobuf</span></span>|
|<span data-ttu-id="c1e5f-384">PowerApps（小数点分隔符）</span><span class="sxs-lookup"><span data-stu-id="c1e5f-384">PowerApps (dot decimal separator)</span></span>|<span data-ttu-id="c1e5f-385">powerapps-dot</span><span class="sxs-lookup"><span data-stu-id="c1e5f-385">powerapps-dot</span></span>|
|<span data-ttu-id="c1e5f-386">PowerApps（逗号分隔符）</span><span class="sxs-lookup"><span data-stu-id="c1e5f-386">PowerApps (comma decimal separator)</span></span>|<span data-ttu-id="c1e5f-387">powerapps-comma</span><span class="sxs-lookup"><span data-stu-id="c1e5f-387">powerapps-comma</span></span>|
|<span data-ttu-id="c1e5f-388">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1e5f-388">PowerShell</span></span>|<span data-ttu-id="c1e5f-389">powershell</span><span class="sxs-lookup"><span data-stu-id="c1e5f-389">powershell</span></span>|
|<span data-ttu-id="c1e5f-390">Python</span><span class="sxs-lookup"><span data-stu-id="c1e5f-390">Python</span></span>|<span data-ttu-id="c1e5f-391">Python</span><span class="sxs-lookup"><span data-stu-id="c1e5f-391">python</span></span>|
|<span data-ttu-id="c1e5f-392">Q#</span><span class="sxs-lookup"><span data-stu-id="c1e5f-392">Q#</span></span>|<span data-ttu-id="c1e5f-393">qsharp</span><span class="sxs-lookup"><span data-stu-id="c1e5f-393">qsharp</span></span>|
|<span data-ttu-id="c1e5f-394">R</span><span class="sxs-lookup"><span data-stu-id="c1e5f-394">R</span></span>|<span data-ttu-id="c1e5f-395">r</span><span class="sxs-lookup"><span data-stu-id="c1e5f-395">r</span></span>|
|<span data-ttu-id="c1e5f-396">Ruby</span><span class="sxs-lookup"><span data-stu-id="c1e5f-396">Ruby</span></span>|<span data-ttu-id="c1e5f-397">ruby</span><span class="sxs-lookup"><span data-stu-id="c1e5f-397">ruby</span></span>|
|<span data-ttu-id="c1e5f-398">SQL</span><span class="sxs-lookup"><span data-stu-id="c1e5f-398">SQL</span></span>|<span data-ttu-id="c1e5f-399">sql</span><span class="sxs-lookup"><span data-stu-id="c1e5f-399">sql</span></span>|
|<span data-ttu-id="c1e5f-400">Swift</span><span class="sxs-lookup"><span data-stu-id="c1e5f-400">Swift</span></span>|<span data-ttu-id="c1e5f-401">swift</span><span class="sxs-lookup"><span data-stu-id="c1e5f-401">swift</span></span>|
|<span data-ttu-id="c1e5f-402">TypeScript</span><span class="sxs-lookup"><span data-stu-id="c1e5f-402">TypeScript</span></span>|<span data-ttu-id="c1e5f-403">typescript</span><span class="sxs-lookup"><span data-stu-id="c1e5f-403">typescript</span></span>|
|<span data-ttu-id="c1e5f-404">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1e5f-404">Visual Basic</span></span>|<span data-ttu-id="c1e5f-405">vb</span><span class="sxs-lookup"><span data-stu-id="c1e5f-405">vb</span></span>|
|<span data-ttu-id="c1e5f-406">VBScript</span><span class="sxs-lookup"><span data-stu-id="c1e5f-406">VBScript</span></span>|<span data-ttu-id="c1e5f-407">vbscript</span><span class="sxs-lookup"><span data-stu-id="c1e5f-407">vbscript</span></span>|
|<span data-ttu-id="c1e5f-408">XAML</span><span class="sxs-lookup"><span data-stu-id="c1e5f-408">XAML</span></span>|<span data-ttu-id="c1e5f-409">xaml</span><span class="sxs-lookup"><span data-stu-id="c1e5f-409">xaml</span></span>|
|<span data-ttu-id="c1e5f-410">XML</span><span class="sxs-lookup"><span data-stu-id="c1e5f-410">XML</span></span>|<span data-ttu-id="c1e5f-411">xml</span><span class="sxs-lookup"><span data-stu-id="c1e5f-411">xml</span></span>|
|<span data-ttu-id="c1e5f-412">yml</span><span class="sxs-lookup"><span data-stu-id="c1e5f-412">yml</span></span>|<span data-ttu-id="c1e5f-413">yml</span><span class="sxs-lookup"><span data-stu-id="c1e5f-413">yml</span></span>|

<span data-ttu-id="c1e5f-414">`csharp-interactive` 名称指定 C# 语言，以及从浏览器中运行示例的能力。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-414">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="c1e5f-415">这些代码片段在 Docker 容器中进行编译和执行，并且该程序执行的结果在用户浏览器窗口中显示。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-415">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

<span data-ttu-id="c1e5f-416">以下是使用 C# (\`\`\`csharp)、Python (\`\`\`python) 和 PowerShell (\`\`\`powershell) 的语言 ID 的代码块示例。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-416">The following are examples of code blocks using the language IDs for C# (\`\`\`csharp), Python (\`\`\`python), and PowerShell (\`\`\`powershell).</span></span>

##### <a name="c"></a><span data-ttu-id="c1e5f-417">C\#</span><span class="sxs-lookup"><span data-stu-id="c1e5f-417">C\#</span></span>

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

#### <a name="python"></a><span data-ttu-id="c1e5f-418">Python</span><span class="sxs-lookup"><span data-stu-id="c1e5f-418">Python</span></span>

```python
friends = ['john', 'pat', 'gary', 'michael']
for i, name in enumerate(friends):
    print "iteration {iteration} is {name}".format(iteration=i, name=name)
```

#### <a name="powershell"></a><span data-ttu-id="c1e5f-419">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1e5f-419">PowerShell</span></span>

```powershell
Clear-Host
$Directory = "C:\Windows\"
$Files = Get-Childitem $Directory -recurse -Include *.log `
-ErrorAction SilentlyContinue
```

### <a name="generic-code-block"></a><span data-ttu-id="c1e5f-420">通用代码块</span><span class="sxs-lookup"><span data-stu-id="c1e5f-420">Generic code block</span></span>

<span data-ttu-id="c1e5f-421">将三个反撇号 (&#96;&#96;&#96;) 用于通用代码块编码。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-421">Use three backticks (&#96;&#96;&#96;) for generic code block coding.</span></span>

> <span data-ttu-id="c1e5f-422">建议的方法是使用具有上一节中所述的语言标识符的代码块，以便确保在文档站点中突出显示正确的语法。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-422">The recommended approach is to use code blocks with language identifiers as explained in the previous section to ensure the proper syntax highlighting in the documentation site.</span></span> <span data-ttu-id="c1e5f-423">仅在需要时使用通用代码块。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-423">Use generic code blocks only when necessary.</span></span>

```
function fancyAlert(arg) {
    if(arg) {
        $.docs({div:'#foo'})
    }
}
```

## <a name="blockquotes"></a><span data-ttu-id="c1e5f-424">块引用</span><span class="sxs-lookup"><span data-stu-id="c1e5f-424">Blockquotes</span></span>

> <span data-ttu-id="c1e5f-425">干旱至今已持续了一千万年，可怕的蜥蜴的统治早已结束。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-425">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="c1e5f-426">在位于赤道的这片陆地上（某天会把这里当成非洲），生存竞争已经达到新高潮，而胜利者尚未出现。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-426">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="c1e5f-427">在这片贫瘠而干旱的土地上，只有那些渺小或者敏捷或者凶残的生物才能茁壮成长，亦或是有希望生存下去。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-427">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

## <a name="images"></a><span data-ttu-id="c1e5f-428">图像</span><span class="sxs-lookup"><span data-stu-id="c1e5f-428">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="c1e5f-429">静态图像或动态 gif</span><span class="sxs-lookup"><span data-stu-id="c1e5f-429">Static Image or Animated gif</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

![这是替换文字](../images/Logo_DotNet.png)

### <a name="linked-image"></a><span data-ttu-id="c1e5f-431">链接的图像</span><span class="sxs-lookup"><span data-stu-id="c1e5f-431">Linked Image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

<span data-ttu-id="c1e5f-432">[![链接的图像的替换文字](../images/Logo_DotNet.png)](https://dot.net)</span><span class="sxs-lookup"><span data-stu-id="c1e5f-432">[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)</span></span>

## <a name="videos"></a><span data-ttu-id="c1e5f-433">视频</span><span class="sxs-lookup"><span data-stu-id="c1e5f-433">Videos</span></span>

<span data-ttu-id="c1e5f-434">目前，可以通过以下语法嵌入第 9 频道和 YouTube 视频：</span><span class="sxs-lookup"><span data-stu-id="c1e5f-434">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="c1e5f-435">第 9 频道</span><span class="sxs-lookup"><span data-stu-id="c1e5f-435">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="c1e5f-436">若要获取视频的正确 URL，请选择视频帧下面的“嵌入”选项卡，然后从`<iframe>` 元素复制 URL  。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-436">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="c1e5f-437">例如:</span><span class="sxs-lookup"><span data-stu-id="c1e5f-437">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="c1e5f-438">YouTube</span><span class="sxs-lookup"><span data-stu-id="c1e5f-438">YouTube</span></span>

<span data-ttu-id="c1e5f-439">若要获取视频的正确 URL，请右键单击视频，选择“复制嵌入代码”，然后从 `<iframe>` 元素复制 URL  。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-439">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="c1e5f-440">例如:</span><span class="sxs-lookup"><span data-stu-id="c1e5f-440">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="c1e5f-441">docs.microsoft 扩展</span><span class="sxs-lookup"><span data-stu-id="c1e5f-441">docs.microsoft extensions</span></span>

<span data-ttu-id="c1e5f-442">docs.microsoft 为 GitHub Flavored Markdown 提供了其他一些扩展。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-442">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="alerts"></a><span data-ttu-id="c1e5f-443">警报</span><span class="sxs-lookup"><span data-stu-id="c1e5f-443">Alerts</span></span>

<span data-ttu-id="c1e5f-444">请务必使用以下警报格式，以便在文档站点中以正确格式呈现警报。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-444">It's important to use the following alert styles so they render with the proper style in the documentation site.</span></span> <span data-ttu-id="c1e5f-445">但是，GitHub 上的呈现引擎无法区分它们。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-445">However, the rendering engine on GitHub doesn't differentiate them.</span></span>

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

<span data-ttu-id="c1e5f-446">这些警报呈现如下：![警报样式](../images/alerts.png)</span><span class="sxs-lookup"><span data-stu-id="c1e5f-446">And they'll render like this: ![Alert styles](../images/alerts.png)</span></span>

### <a name="includes"></a><span data-ttu-id="c1e5f-447">包括</span><span class="sxs-lookup"><span data-stu-id="c1e5f-447">Includes</span></span>

<span data-ttu-id="c1e5f-448">可以使用 include 将一个文件的 Markdown 嵌入到另一个文件中。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-448">You can embed the Markdown of one file into another using an include.</span></span>

[!INCLUDE[sample include file](../includes/sampleinclude.md)]

### <a name="checked-lists"></a><span data-ttu-id="c1e5f-449">选中的列表</span><span class="sxs-lookup"><span data-stu-id="c1e5f-449">Checked lists</span></span>

<span data-ttu-id="c1e5f-450">可以在列表中使用自定义样式。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-450">A custom style is available for lists.</span></span> <span data-ttu-id="c1e5f-451">可以呈现带有绿色复选标记的列表。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-451">You can render lists with green check marks.</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="c1e5f-452">如何创建 .NET Core 应用</span><span class="sxs-lookup"><span data-stu-id="c1e5f-452">How to create a .NET Core app</span></span>
> - <span data-ttu-id="c1e5f-453">如何向 Microsoft.XmlSerializer.Generator 包中添加引用</span><span class="sxs-lookup"><span data-stu-id="c1e5f-453">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> - <span data-ttu-id="c1e5f-454">如何编辑 MyApp.csproj 以添加依赖项</span><span class="sxs-lookup"><span data-stu-id="c1e5f-454">How to edit your MyApp.csproj to add dependencies</span></span>
> - <span data-ttu-id="c1e5f-455">如何添加类和 XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="c1e5f-455">How to add a class and an XmlSerializer</span></span>
> - <span data-ttu-id="c1e5f-456">如何生成并运行应用程序</span><span class="sxs-lookup"><span data-stu-id="c1e5f-456">How to build and run the application</span></span>

<span data-ttu-id="c1e5f-457">可在 [.NET Core 文档](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator)的操作中查看列表示例。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-457">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="c1e5f-458">按钮</span><span class="sxs-lookup"><span data-stu-id="c1e5f-458">Buttons</span></span>

> [!div class="button"]
> [<span data-ttu-id="c1e5f-459">按钮链接</span><span class="sxs-lookup"><span data-stu-id="c1e5f-459">button links</span></span>](../docs/core/index.md)

<span data-ttu-id="c1e5f-460">可在 [Visual Studio 文档](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio)中查看按钮操作示例。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-460">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="selectors"></a><span data-ttu-id="c1e5f-461">选择器</span><span class="sxs-lookup"><span data-stu-id="c1e5f-461">Selectors</span></span>

> [!div class="op_single_selector"]
>
> - [macOS](../docs/core/tutorials/using-on-macos.md)
> - [Windows](../docs/core/tutorials/with-visual-studio.md)

<span data-ttu-id="c1e5f-464">可在 [Azure 文档](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic)中查看有效的选择器示例。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-464">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="c1e5f-465">按步执行</span><span class="sxs-lookup"><span data-stu-id="c1e5f-465">Step-By-Steps</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c1e5f-466">[上一页](../docs/csharp/expression-trees-interpreting.md)
>[下一页](../docs/csharp/expression-trees-translating.md)</span><span class="sxs-lookup"><span data-stu-id="c1e5f-466">[Previous](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)</span></span>

<span data-ttu-id="c1e5f-467">可在 [C# 指南 ](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure)中查看逐步操作的示例。</span><span class="sxs-lookup"><span data-stu-id="c1e5f-467">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>

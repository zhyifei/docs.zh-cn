---
title: "使用 XML 注释来记录代码"
description: "了解如何使用 XML 文档注释来记录代码和在编译时生成 XML 文档文件。"
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 02/14/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 8e75e317-4a55-45f2-a866-e76124171838
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0cb5725a70d94173c8596f818dcaa6eb2de13bcc
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---

# <a name="documenting-your-code-with-xml-comments"></a><span data-ttu-id="9a508-104">使用 XML 注释来记录代码</span><span class="sxs-lookup"><span data-stu-id="9a508-104">Documenting your code with XML comments</span></span>

<span data-ttu-id="9a508-105">XML 文档注释是一种特殊注释，添加在任何用户定义的类型或成员的定义上方。</span><span class="sxs-lookup"><span data-stu-id="9a508-105">XML documentation comments are a special kind of comment, added above the definition of any user-defined type or member.</span></span> <span data-ttu-id="9a508-106">其特殊之处在于其可由编译器处理，由此在编译时生成 XML 文档文件。</span><span class="sxs-lookup"><span data-stu-id="9a508-106">They are special because they can be processed by the compiler to generate an XML documentation file at compile time.</span></span>
<span data-ttu-id="9a508-107">编译器生成的 XML 文件可以与 .NET 程序集一起分发，以便 Visual Studio 和其他 IDE 可使用 IntelliSense 显示关于类型或成员的快速信息。</span><span class="sxs-lookup"><span data-stu-id="9a508-107">The compiler generated XML file can be distributed alongside your .NET assembly so that Visual Studio and other IDEs can use IntelliSense to show quick information about types or members.</span></span> <span data-ttu-id="9a508-108">此外，可以通过 [DocFX](https://dotnet.github.io/docfx/) 和 [Sandcastle](https://github.com/EWSoftware/SHFB) 等工具运行 XML 文件，由此生成 API 引用网站。</span><span class="sxs-lookup"><span data-stu-id="9a508-108">Additionally, the XML file can be run through tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to generate API reference websites.</span></span>

<span data-ttu-id="9a508-109">编译器会忽略 XML 文档注释，与对待其他注释一样。</span><span class="sxs-lookup"><span data-stu-id="9a508-109">XML documentation comments, like all other comments, are ignored by the compiler.</span></span>

<span data-ttu-id="9a508-110">可通过执行下列操作之一在编译时生成 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="9a508-110">You can generate the XML file at compile time by doing one of the following:</span></span>

- <span data-ttu-id="9a508-111">如果要使用 .NET Core 从命令行开发应用程序，可以将 [DocumentationFile 元素](http://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties)添加到 .csproj 项目文件的 `<PropertyGroup>` 部分。</span><span class="sxs-lookup"><span data-stu-id="9a508-111">If you are developing an application with .NET Core from the command line, you can add a [DocumentationFile element](http://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-properties) to the `<PropertyGroup>` section of your .csproj project file.</span></span> <span data-ttu-id="9a508-112">下面的示例使用与项目相同的根文件夹名在项目目录中生成 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="9a508-112">The following example generates an XML file in the project directory with the same root filename as the project:</span></span>

   ```xml
   <DocumentationFile>$(MSBuildProjectName).xml</DocumentationFile>
   ```

   <span data-ttu-id="9a508-113">还可以精确指定 XML 文件的绝对或相对路径及名称。</span><span class="sxs-lookup"><span data-stu-id="9a508-113">You can also specify the exact absolute or relative path and name of the XML file.</span></span> <span data-ttu-id="9a508-114">下面的示例在与调试版本的应用程序相同的目录中生成 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="9a508-114">The following example generates the XML file in the same directory as the debug version of an application:</span></span>

    ```xml
   <DocumentationFile>bin\Debug\netcoreapp1.0\App.xml</DocumentationFile>
   ```

- <span data-ttu-id="9a508-115">如果使用 Visual Studio 开发应用程序，右键单击项目并选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="9a508-115">If you are developing an application using Visual Studio, right-click on the project and select **Properties**.</span></span> <span data-ttu-id="9a508-116">在属性对话框中，选择“生成”选项卡，然后选中“XML 文档文件”。</span><span class="sxs-lookup"><span data-stu-id="9a508-116">In the properties dialog, select the **Build** tab, and check **XML documentation file**.</span></span> <span data-ttu-id="9a508-117">还可以更改编译器写入文件的位置。</span><span class="sxs-lookup"><span data-stu-id="9a508-117">You can also change the location to which the compiler writes the file.</span></span> 

- <span data-ttu-id="9a508-118">如果是从命令行编译 .NET Framework 应用程序，编译时请添加 [/doc 编译器选项](language-reference/compiler-options/doc-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="9a508-118">If you are compiling a .NET Framework application from the command line, add the [/doc compiler option](language-reference/compiler-options/doc-compiler-option.md) when compiling.</span></span>  

<span data-ttu-id="9a508-119">XML 文档注释使用三个正斜杠 (`///`) 和 XML 格式的注释正文。</span><span class="sxs-lookup"><span data-stu-id="9a508-119">XML documentation comments use triple forward slashes (`///`) and an XML formatted comment body.</span></span> <span data-ttu-id="9a508-120">例如：</span><span class="sxs-lookup"><span data-stu-id="9a508-120">For example:</span></span>

<span data-ttu-id="9a508-121">[!code-csharpXML 文档注释[](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-121">[!code-csharp[XML Documentation Comment](../../samples/snippets/csharp/concepts/codedoc/xml-comment.cs)]</span></span>

## <a name="walkthrough"></a><span data-ttu-id="9a508-122">演练</span><span class="sxs-lookup"><span data-stu-id="9a508-122">Walkthrough</span></span>

<span data-ttu-id="9a508-123">现在来演练针对一个十分基本的数学库进行文档编制，以使新手开发人员能够容易地理解/参与，以及使第三方开发人员能够轻松使用。</span><span class="sxs-lookup"><span data-stu-id="9a508-123">Let's walk through documenting a very basic math library to make it easy for new developers to understand/contribute and for third party developers to use.</span></span>

<span data-ttu-id="9a508-124">下面是简单数学库的代码：</span><span class="sxs-lookup"><span data-stu-id="9a508-124">Here's code for the simple math library:</span></span>

<span data-ttu-id="9a508-125">[!code-csharp[示例库](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-125">[!code-csharp[Sample Library](../../samples/snippets/csharp/concepts/codedoc/sample-library.cs)]</span></span>

<span data-ttu-id="9a508-126">示例库支持 `int` 和 `double` 数据类型的四种主要算术运算：`add`、`subtract`、`multiply` 和 `divide`。</span><span class="sxs-lookup"><span data-stu-id="9a508-126">The sample library supports four major arithmetic operations `add`, `subtract`, `multiply` and `divide` on `int` and `double` data types.</span></span>

<span data-ttu-id="9a508-127">现在，希望能够从代码中为使用库但无源代码访问权限的第三方开发人员创建 API 引用文档。</span><span class="sxs-lookup"><span data-stu-id="9a508-127">Now you want to be able to create an API reference document from your code for third party developers who use your library but don't have access to the source code.</span></span>
<span data-ttu-id="9a508-128">如之前提到的，可使用 XML 文档标记实现此目的，现在介绍 C# 编译器支持的标准 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="9a508-128">As mentioned earlier XML documentation tags can be used to achieve this, You will now be introduced to the standard XML tags the C# compiler supports.</span></span>

### <a name="ltsummarygt"></a><span data-ttu-id="9a508-129">&lt;summary&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-129">&lt;summary&gt;</span></span>

<span data-ttu-id="9a508-130">`<summary>` 标记可添加关于类型或成员的信息摘要。</span><span class="sxs-lookup"><span data-stu-id="9a508-130">The `<summary>` tag adds brief information about a type or member.</span></span>
<span data-ttu-id="9a508-131">这里通过将其添加到 `Math` 类定义和第一个 `Add` 方法来演示其用法。</span><span class="sxs-lookup"><span data-stu-id="9a508-131">I'll demonstrate its use by adding it to the `Math` class definition and the first `Add` method.</span></span> <span data-ttu-id="9a508-132">可随意将其应用于代码的其余部分。</span><span class="sxs-lookup"><span data-stu-id="9a508-132">Feel free to apply it to the rest of your code.</span></span>

<span data-ttu-id="9a508-133">[!code-csharp[摘要标记](../../samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-133">[!code-csharp[Summary Tag](../../samples/snippets/csharp/concepts/codedoc/summary-tag.cs)]</span></span>

<span data-ttu-id="9a508-134">`<summary>` 标记非常重要，建议包含，因为其内容是 IntelliSense 或 API 参考文档中的类型或成员信息的主要来源。</span><span class="sxs-lookup"><span data-stu-id="9a508-134">The `<summary>` tag is very important, and we recommend that you include it because its content is the primary source of type or member information in IntelliSense or an API reference document.</span></span>

### <a name="ltremarksgt"></a><span data-ttu-id="9a508-135">&lt;remarks&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-135">&lt;remarks&gt;</span></span>

<span data-ttu-id="9a508-136">`<remarks>`标记可补充关于 `<summary>` 标记提供的类型或成员的信息。</span><span class="sxs-lookup"><span data-stu-id="9a508-136">The `<remarks>` tag supplements the information about types or members that the `<summary>` tag provides.</span></span> <span data-ttu-id="9a508-137">在此示例中，只需将其添加到类。</span><span class="sxs-lookup"><span data-stu-id="9a508-137">In this example, you'll just add it to the class.</span></span>

<span data-ttu-id="9a508-138">[!code-csharp[Remarks 标记](../../samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-138">[!code-csharp[Remarks Tag](../../samples/snippets/csharp/concepts/codedoc/remarks-tag.cs)]</span></span>

### <a name="ltreturnsgt"></a><span data-ttu-id="9a508-139">&lt;returns&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-139">&lt;returns&gt;</span></span>

<span data-ttu-id="9a508-140">`<returns>` 标记描述方法声明的返回值。</span><span class="sxs-lookup"><span data-stu-id="9a508-140">The `<returns>` tag describes the return value of a method declaration.</span></span>
<span data-ttu-id="9a508-141">与以前一样，下面的示例展示第一个 `Add` 方法上的 `<returns>` 标记。</span><span class="sxs-lookup"><span data-stu-id="9a508-141">As before, the following example illustrates the `<returns>` tag on the first `Add` method.</span></span> <span data-ttu-id="9a508-142">可以对其他方法执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="9a508-142">You can do the same on other methods.</span></span>

<span data-ttu-id="9a508-143">[!code-csharp[Returns 标记](../../samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-143">[!code-csharp[Returns Tag](../../samples/snippets/csharp/concepts/codedoc/returns-tag.cs)]</span></span>

### <a name="ltvaluegt"></a><span data-ttu-id="9a508-144">&lt;值&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-144">&lt;value&gt;</span></span>

<span data-ttu-id="9a508-145">`<value>` 标记类似于 `<returns>` 标记，只不过前者用于属性。</span><span class="sxs-lookup"><span data-stu-id="9a508-145">The `<value>` tag is similar to the `<returns>` tag, except that you use it for properties.</span></span>
<span data-ttu-id="9a508-146">假设 `Math` 库有一个名为 `PI` 的静态属性，下面是此标记的用法：</span><span class="sxs-lookup"><span data-stu-id="9a508-146">Assuming your `Math` library had a static property called `PI`, here's how you'd use this tag:</span></span>

<span data-ttu-id="9a508-147">[!code-csharp[Value 标记](../../samples/snippets/csharp/concepts/codedoc/value-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-147">[!code-csharp[Value Tag](../../samples/snippets/csharp/concepts/codedoc/value-tag.cs)]</span></span>

### <a name="ltexamplegt"></a><span data-ttu-id="9a508-148">&lt;example&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-148">&lt;example&gt;</span></span>

<span data-ttu-id="9a508-149">使用 `<example>` 标记可在 XML 文档中包含一个示例。</span><span class="sxs-lookup"><span data-stu-id="9a508-149">You use the `<example>` tag to include an example in your XML documentation.</span></span>
<span data-ttu-id="9a508-150">此操作包括使用子 `<code>` 标记。</span><span class="sxs-lookup"><span data-stu-id="9a508-150">This involves using the child `<code>` tag.</span></span>

<span data-ttu-id="9a508-151">[!code-csharp[Example 标记](../../samples/snippets/csharp/concepts/codedoc/example-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-151">[!code-csharp[Example Tag](../../samples/snippets/csharp/concepts/codedoc/example-tag.cs)]</span></span>

<span data-ttu-id="9a508-152">`code` 标记保留较长示例的换行符和缩进。</span><span class="sxs-lookup"><span data-stu-id="9a508-152">The `code` tag preserves line breaks and indentation for longer examples.</span></span>

### <a name="ltparagt"></a><span data-ttu-id="9a508-153">&lt;para&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-153">&lt;para&gt;</span></span>

<span data-ttu-id="9a508-154">`<para>` 标记可用于设置其父标记内的内容的格式。</span><span class="sxs-lookup"><span data-stu-id="9a508-154">You use the `<para>` tag to format the content within its parent tag.</span></span> <span data-ttu-id="9a508-155">`<para>` 通常在标记内使用，如 `<remarks>` 或 `<returns>`，作用是将文本分成段落。</span><span class="sxs-lookup"><span data-stu-id="9a508-155">`<para>` is usually used inside a tag, such as `<remarks>` or `<returns>`, to divide text into paragraphs.</span></span>
<span data-ttu-id="9a508-156">可以为类定义设置 `<remarks>` 标记的内容的格式。</span><span class="sxs-lookup"><span data-stu-id="9a508-156">You can format the contents of the `<remarks>` tag for your class definition.</span></span>

<span data-ttu-id="9a508-157">[!code-csharp[Para 标记](../../samples/snippets/csharp/concepts/codedoc/para-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-157">[!code-csharp[Para Tag](../../samples/snippets/csharp/concepts/codedoc/para-tag.cs)]</span></span>

### <a name="ltcgt"></a><span data-ttu-id="9a508-158">&lt;c&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-158">&lt;c&gt;</span></span>

<span data-ttu-id="9a508-159">还是关于格式设置，使用 `<c>` 标记可将部分文本标记为代码。</span><span class="sxs-lookup"><span data-stu-id="9a508-159">Still on the topic of formatting, you use the `<c>` tag for marking part of text as code.</span></span>
<span data-ttu-id="9a508-160">与 `<code>` 标记类似，但是内联的。</span><span class="sxs-lookup"><span data-stu-id="9a508-160">It's like the `<code>` tag but inline.</span></span> <span data-ttu-id="9a508-161">想要显示快速代码示例并将其作为标记内容一部分时，这很有帮助。</span><span class="sxs-lookup"><span data-stu-id="9a508-161">It's useful when you want to show a quick code example as part of a tag's content.</span></span>
<span data-ttu-id="9a508-162">现在来更新 `Math` 类的文档。</span><span class="sxs-lookup"><span data-stu-id="9a508-162">Let's update the documentation for the `Math` class.</span></span>

<span data-ttu-id="9a508-163">[!code-csharp[C 标记](../../samples/snippets/csharp/concepts/codedoc/c-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-163">[!code-csharp[C Tag](../../samples/snippets/csharp/concepts/codedoc/c-tag.cs)]</span></span>

### <a name="ltexceptiongt"></a><span data-ttu-id="9a508-164">&lt;exception&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-164">&lt;exception&gt;</span></span>

<span data-ttu-id="9a508-165">通过使用 `<exception>` 标记，可以让开发人员了解到，方法有可能引发特定异常。</span><span class="sxs-lookup"><span data-stu-id="9a508-165">By using the `<exception>` tag, you let your developers know that a method can throw specific exceptions.</span></span>
<span data-ttu-id="9a508-166">查看 `Math` 库，可以看到，如果满足特定条件，两个 `Add` 方法都会引发异常。</span><span class="sxs-lookup"><span data-stu-id="9a508-166">Looking at your `Math` library, you can see that both `Add` methods throw an exception if a certain condition is met.</span></span> <span data-ttu-id="9a508-167">如果 `b` 参数为零，则 `Divide` 方法也会引发异常，尽管不是很常见。</span><span class="sxs-lookup"><span data-stu-id="9a508-167">Not so obvious, though, is that integer `Divide` method throws as well if the `b` parameter is zero.</span></span> <span data-ttu-id="9a508-168">现在将异常文档添加到此方法。</span><span class="sxs-lookup"><span data-stu-id="9a508-168">Now add exception documentation to this method.</span></span>

<span data-ttu-id="9a508-169">[!code-csharp[Exception 标记](../../samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-169">[!code-csharp[Exception Tag](../../samples/snippets/csharp/concepts/codedoc/exception-tag.cs)]</span></span>

<span data-ttu-id="9a508-170">`cref` 属性表示可从当前编译环境中实现的异常引用。</span><span class="sxs-lookup"><span data-stu-id="9a508-170">The `cref` attribute represents a reference to an exception that is available from the current compilation environment.</span></span>
<span data-ttu-id="9a508-171">其类型可为项目中或引用的程序集中定义的任何类型。</span><span class="sxs-lookup"><span data-stu-id="9a508-171">This can be any type defined in the project or a referenced assembly.</span></span> <span data-ttu-id="9a508-172">如果无法解析编译器的值，则该编译器将发出一条警告。</span><span class="sxs-lookup"><span data-stu-id="9a508-172">The compiler will issue a warning if its value cannot be resolved.</span></span>

### <a name="ltseegt"></a><span data-ttu-id="9a508-173">&lt;see&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-173">&lt;see&gt;</span></span>

<span data-ttu-id="9a508-174">使用 `<see>` 标记，可以创建可单击的链接，指向另一个代码元素的文档页面。</span><span class="sxs-lookup"><span data-stu-id="9a508-174">The `<see>` tag lets you create a clickable link to a documentation page for another code element.</span></span> <span data-ttu-id="9a508-175">在下一个示例中，将创建两个 `Add` 方法之间的可单击的链接。</span><span class="sxs-lookup"><span data-stu-id="9a508-175">In our next example, we'll create a clickable link between the two `Add` methods.</span></span>

<span data-ttu-id="9a508-176">[!code-csharp[See 标记](../../samples/snippets/csharp/concepts/codedoc/see-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-176">[!code-csharp[See Tag](../../samples/snippets/csharp/concepts/codedoc/see-tag.cs)]</span></span>

<span data-ttu-id="9a508-177">`cref` 是表示可从当前编译环境引用的类型或其成员的**必需**属性。</span><span class="sxs-lookup"><span data-stu-id="9a508-177">The `cref` is a **required** attribute that represents a reference to a type or its member that is available from the current compilation environment.</span></span> <span data-ttu-id="9a508-178">其类型可为项目中或引用的程序集中定义的任何类型。</span><span class="sxs-lookup"><span data-stu-id="9a508-178">This can be any type defined in the project or a referenced assembly.</span></span>

### <a name="ltseealsogt"></a><span data-ttu-id="9a508-179">&lt;seealso&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-179">&lt;seealso&gt;</span></span>

<span data-ttu-id="9a508-180">可以通过使用 `<see>` 标记的方式使用 `<seealso>`标记。</span><span class="sxs-lookup"><span data-stu-id="9a508-180">You use the `<seealso>` tag in the same way you do the `<see>` tag.</span></span> <span data-ttu-id="9a508-181">唯一的区别是其内容通常位于“另请参见”部分。</span><span class="sxs-lookup"><span data-stu-id="9a508-181">The only difference is that its content is typically placed in a "See Also" section.</span></span> <span data-ttu-id="9a508-182">以下将在整数 `Add` 方法上添加 `seealso` 标记，从而在接受整数参数的类中引用其他方法：</span><span class="sxs-lookup"><span data-stu-id="9a508-182">Here we'll add a `seealso` tag on the integer `Add` method to reference other methods in the class that accept integer parameters:</span></span>

<span data-ttu-id="9a508-183">[!code-csharp[Seealso 标记](../../samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-183">[!code-csharp[Seealso Tag](../../samples/snippets/csharp/concepts/codedoc/seealso-tag.cs)]</span></span>

<span data-ttu-id="9a508-184">`cref` 属性表示可从当前编译环境进行的对类型或其成员的引用。</span><span class="sxs-lookup"><span data-stu-id="9a508-184">The `cref` attribute represents a reference to a type or its member that is available from the current compilation environment.</span></span>
<span data-ttu-id="9a508-185">其类型可为项目中或引用的程序集中定义的任何类型。</span><span class="sxs-lookup"><span data-stu-id="9a508-185">This can be any type defined in the project or a referenced assembly.</span></span>

### <a name="ltparamgt"></a><span data-ttu-id="9a508-186">&lt;param&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-186">&lt;param&gt;</span></span>

<span data-ttu-id="9a508-187">使用 `<param>` 标记来描述方法的参数。</span><span class="sxs-lookup"><span data-stu-id="9a508-187">You use the `<param>` tag to describe a method's parameters.</span></span> <span data-ttu-id="9a508-188">下面是关于双 `Add` 方法的示例：标记所描述的参数在**必需**的 `name` 属性中指定。</span><span class="sxs-lookup"><span data-stu-id="9a508-188">Here's an example on the double `Add` method: The parameter the tag describes is specified in the **required** `name` attribute.</span></span>

<span data-ttu-id="9a508-189">[!code-csharp[Param 标记](../../samples/snippets/csharp/concepts/codedoc/param-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-189">[!code-csharp[Param Tag](../../samples/snippets/csharp/concepts/codedoc/param-tag.cs)]</span></span>

### <a name="lttypeparamgt"></a><span data-ttu-id="9a508-190">&lt;typeparam&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-190">&lt;typeparam&gt;</span></span>

<span data-ttu-id="9a508-191">`<typeparam>` 标记的用法与 `<param>` 标记一样，但前者由泛型类型或方法声明用来描述泛型参数。</span><span class="sxs-lookup"><span data-stu-id="9a508-191">You use `<typeparam>` tag just like the `<param>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="9a508-192">将快速泛型方法添加到 `Math` 类，以检查某个数量是否大于另一个数量。</span><span class="sxs-lookup"><span data-stu-id="9a508-192">Add a quick generic method to your `Math` class to check if one quantity is greater than another.</span></span>

<span data-ttu-id="9a508-193">[!code-csharp[Typeparam 标记](../../samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-193">[!code-csharp[Typeparam Tag](../../samples/snippets/csharp/concepts/codedoc/typeparam-tag.cs)]</span></span>

### <a name="ltparamrefgt"></a><span data-ttu-id="9a508-194">&lt;paramref&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-194">&lt;paramref&gt;</span></span>

<span data-ttu-id="9a508-195">有时可能正在通过一个 `<summary>` 标记描述一个方法的作用，并且想要引用一个参数。</span><span class="sxs-lookup"><span data-stu-id="9a508-195">Sometimes you might be in the middle of describing what a method does in what could be a `<summary>` tag, and you might want to make a reference to a parameter.</span></span> <span data-ttu-id="9a508-196">这时 `<paramref>` 标记就很适合用来实现这一目的。</span><span class="sxs-lookup"><span data-stu-id="9a508-196">The `<paramref>` tag is great for just this.</span></span> <span data-ttu-id="9a508-197">现在来更新双基 `Add` 方法的摘要。</span><span class="sxs-lookup"><span data-stu-id="9a508-197">Let's update the summary of our double based `Add` method.</span></span> <span data-ttu-id="9a508-198">与 `<param>` 标记一样，参数名称在**必需**的 `name` 属性中指定。</span><span class="sxs-lookup"><span data-stu-id="9a508-198">Like the `<param>` tag the parameter name is specified in the **required** `name` attribute.</span></span>

<span data-ttu-id="9a508-199">[!code-csharp[Paramref 标记](../../samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-199">[!code-csharp[Paramref Tag](../../samples/snippets/csharp/concepts/codedoc/paramref-tag.cs)]</span></span>

### <a name="lttypeparamrefgt"></a><span data-ttu-id="9a508-200">&lt;typeparamref&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-200">&lt;typeparamref&gt;</span></span>

<span data-ttu-id="9a508-201">`<typeparamref>` 标记的用法与 `<paramref>` 标记一样，但前者由泛型类型或方法声明用来描述泛型参数。</span><span class="sxs-lookup"><span data-stu-id="9a508-201">You use `<typeparamref>` tag just like the `<paramref>` tag but for generic type or method declarations to describe a generic parameter.</span></span>
<span data-ttu-id="9a508-202">可以使用之前创建的那个泛型方法。</span><span class="sxs-lookup"><span data-stu-id="9a508-202">You can use the same generic method you previously created.</span></span>

<span data-ttu-id="9a508-203">[!code-csharp[Typeparamref 标记](../../samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-203">[!code-csharp[Typeparamref Tag](../../samples/snippets/csharp/concepts/codedoc/typeparamref-tag.cs)]</span></span>

### <a name="ltlistgt"></a><span data-ttu-id="9a508-204">&lt;list&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-204">&lt;list&gt;</span></span>

<span data-ttu-id="9a508-205">使用 `<list>` 标记可将文档信息格式化为有序列表、无序列表或表格。</span><span class="sxs-lookup"><span data-stu-id="9a508-205">You use the `<list>` tag to format documentation information as an ordered list, unordered list or table.</span></span>
<span data-ttu-id="9a508-206">制作 `Math` 库支持的所有数学操作的无序列表。</span><span class="sxs-lookup"><span data-stu-id="9a508-206">Make an unordered list of every math operation your `Math` library supports.</span></span>

<span data-ttu-id="9a508-207">[!code-csharp[List 标记](../../samples/snippets/csharp/concepts/codedoc/list-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-207">[!code-csharp[List Tag](../../samples/snippets/csharp/concepts/codedoc/list-tag.cs)]</span></span>

<span data-ttu-id="9a508-208">可以通过将 `type` 属性分别改为 `number` 或 `table` 来制作有序列表或表格。</span><span class="sxs-lookup"><span data-stu-id="9a508-208">You can make an ordered list or table by changing the `type` attribute to `number` or `table`, respectively.</span></span>

### <a name="putting-it-all-together"></a><span data-ttu-id="9a508-209">配合使用</span><span class="sxs-lookup"><span data-stu-id="9a508-209">Putting it all together</span></span>

<span data-ttu-id="9a508-210">如果已按照本教程的操作方法将标记应用于代码中的所需位置，则代码现应如下所示：</span><span class="sxs-lookup"><span data-stu-id="9a508-210">If you've followed this tutorial and applied the tags to your code where necessary, your code should now look similar to the following:</span></span>

<span data-ttu-id="9a508-211">[!code-csharp[标记的库](../../samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-211">[!code-csharp[Tagged Library](../../samples/snippets/csharp/concepts/codedoc/tagged-library.cs)]</span></span>

<span data-ttu-id="9a508-212">可从代码中生成包括可单击的交叉引用的详细文档网站。</span><span class="sxs-lookup"><span data-stu-id="9a508-212">From your code, you can generate a detailed documentation website complete with clickable cross-references.</span></span> <span data-ttu-id="9a508-213">但将面临另一问题：代码变得难以阅读。</span><span class="sxs-lookup"><span data-stu-id="9a508-213">But you're faced with another problem: your code has become hard to read.</span></span>
<span data-ttu-id="9a508-214">需要筛查的信息浩如烟海，这对任何要参与此代码编写的开发人员都是噩梦。</span><span class="sxs-lookup"><span data-stu-id="9a508-214">There's so much information to sift through that this is going to be a nightmare for any developer who wants to contribute to this code.</span></span> <span data-ttu-id="9a508-215">幸好有一个 XML 标记，可帮助解决这个问题：</span><span class="sxs-lookup"><span data-stu-id="9a508-215">Thankfully there's an XML tag that can help you deal with this:</span></span>

### <a name="ltincludegt"></a><span data-ttu-id="9a508-216">&lt;include&gt;</span><span class="sxs-lookup"><span data-stu-id="9a508-216">&lt;include&gt;</span></span>

<span data-ttu-id="9a508-217">使用 `<include>` 标记，可以引用单独的 XML 文件中的注释（该文件描述源代码中的类型和成员），而不是将文档注释直接放入源代码文件中。</span><span class="sxs-lookup"><span data-stu-id="9a508-217">The `<include>` tag lets you refer to comments in a separate XML file that describe the types and members in your source code, as opposed to placing documentation comments directly in your source code file.</span></span>

<span data-ttu-id="9a508-218">现在，要将所有 XML 标记移到名为 `docs.xml` 的单独的 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="9a508-218">Now you're going to move all your XML tags into a separate XML file named `docs.xml`.</span></span> <span data-ttu-id="9a508-219">可随时重新命名该文件。</span><span class="sxs-lookup"><span data-stu-id="9a508-219">Feel free to name the file whatever you want.</span></span>

<span data-ttu-id="9a508-220">[!code-xml[示例 XML](../../samples/snippets/csharp/concepts/codedoc/include.xml)]</span><span class="sxs-lookup"><span data-stu-id="9a508-220">[!code-xml[Sample XML](../../samples/snippets/csharp/concepts/codedoc/include.xml)]</span></span>

<span data-ttu-id="9a508-221">在上面的 XML 中，每个成员的文档注释将直接显示在按其作用命名的标记中。</span><span class="sxs-lookup"><span data-stu-id="9a508-221">In the above XML, each member's documentation comments appear directly inside a tag named after what they do.</span></span> <span data-ttu-id="9a508-222">可选择自己的策略。</span><span class="sxs-lookup"><span data-stu-id="9a508-222">You can choose your own strategy.</span></span> <span data-ttu-id="9a508-223">现在一个单独的文件中已具有 XML 注释，接下来来看看如何通过使用 `<include>` 标记使代码更易于阅读：</span><span class="sxs-lookup"><span data-stu-id="9a508-223">Now that you have your XML comments in a separate file, let's see how your code can be made more readable by using the `<include>` tag:</span></span>

<span data-ttu-id="9a508-224">[!code-csharp[Include 标记](../../samples/snippets/csharp/concepts/codedoc/include-tag.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a508-224">[!code-csharp[Include Tag](../../samples/snippets/csharp/concepts/codedoc/include-tag.cs)]</span></span>

<span data-ttu-id="9a508-225">现在好了，代码又变得可读了，并且未丢失任何文档信息。</span><span class="sxs-lookup"><span data-stu-id="9a508-225">And there you have it: our code is back to being readable, and no documentation information has been lost.</span></span> 

<span data-ttu-id="9a508-226">`filename` 属性表示包含文档的 XML 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="9a508-226">The `filename` attribute represents the name of the XML file containing the documentation.</span></span>

<span data-ttu-id="9a508-227">`path` 属性表示一个 [XPath](https://msdn.microsoft.com/library/ms256115.aspx) 查询，该查询的对象为指定的 `filename` 中的 `tag name`。</span><span class="sxs-lookup"><span data-stu-id="9a508-227">The `path` attribute represents an [XPath](https://msdn.microsoft.com/library/ms256115.aspx) query to the `tag name` present in the specified `filename`.</span></span>

<span data-ttu-id="9a508-228">`name` 属性表示位于注释前的标记中的名称说明符。</span><span class="sxs-lookup"><span data-stu-id="9a508-228">The `name` attribute represents the name specifier in the tag that precedes the comments.</span></span>

<span data-ttu-id="9a508-229">可用于替换 `name` 的 `id` 属性表示位于注释前的标记的 ID。</span><span class="sxs-lookup"><span data-stu-id="9a508-229">The `id` attribute which can be used in place of `name` represents the ID for the tag that precedes the comments.</span></span>

### <a name="user-defined-tags"></a><span data-ttu-id="9a508-230">用户定义的标记</span><span class="sxs-lookup"><span data-stu-id="9a508-230">User Defined Tags</span></span>

<span data-ttu-id="9a508-231">上述所有标记均表示由 C# 编译器识别的标记。</span><span class="sxs-lookup"><span data-stu-id="9a508-231">All the tags outlined above represent those that are recognized by the C# compiler.</span></span> <span data-ttu-id="9a508-232">但用户可随意定义自己的标记。</span><span class="sxs-lookup"><span data-stu-id="9a508-232">However, a user is free to define their own tags.</span></span>
<span data-ttu-id="9a508-233">Sandcastle 等工具支持其他标记，如 [`<event>`](http://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm)、 [`<note>`](http://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm)，甚至支持[编制命名空间文档](http://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm)。</span><span class="sxs-lookup"><span data-stu-id="9a508-233">Tools like Sandcastle bring support for extra tags like [`<event>`](http://ewsoftware.github.io/XMLCommentsGuide/html/81bf7ad3-45dc-452f-90d5-87ce2494a182.htm), [`<note>`](http://ewsoftware.github.io/XMLCommentsGuide/html/4302a60f-e4f4-4b8d-a451-5f453c4ebd46.htm) and even support [documenting namespaces](http://ewsoftware.github.io/XMLCommentsGuide/html/BD91FAD4-188D-4697-A654-7C07FD47EF31.htm).</span></span>
<span data-ttu-id="9a508-234">自定义或内部文档生成工具也可与标准标记配合使用，并支持 HTML 到 PDF 等多种输出格式。</span><span class="sxs-lookup"><span data-stu-id="9a508-234">Custom or in-house documentation generation tools can also be used with the standard tags and multiple output formats from HTML to PDF can be supported.</span></span>

## <a name="recommendations"></a><span data-ttu-id="9a508-235">建议</span><span class="sxs-lookup"><span data-stu-id="9a508-235">Recommendations</span></span>

<span data-ttu-id="9a508-236">出于多种原因，建议编制代码文档。</span><span class="sxs-lookup"><span data-stu-id="9a508-236">Documenting code is recommended for many reasons.</span></span> <span data-ttu-id="9a508-237">接下来将介绍一些最佳做法、常规使用方案，以及在 C# 代码中使用 XML 文档标记时的需知内容。</span><span class="sxs-lookup"><span data-stu-id="9a508-237">What follows are some best practices, general use case scenarios, and things that you should know when using XML documentation tags in your C# code.</span></span>

* <span data-ttu-id="9a508-238">为保持一致性，应编制所有公共可见类型及其成员的文档。</span><span class="sxs-lookup"><span data-stu-id="9a508-238">For the sake of consistency, all publicly visible types and their members should be documented.</span></span> <span data-ttu-id="9a508-239">如果必须这么做，请完整全面地完成这一操作。</span><span class="sxs-lookup"><span data-stu-id="9a508-239">If you must do it, do it all.</span></span>
* <span data-ttu-id="9a508-240">还可使用 XML 注释编制私有成员的文档。</span><span class="sxs-lookup"><span data-stu-id="9a508-240">Private members can also be documented using XML comments.</span></span> <span data-ttu-id="9a508-241">但这会公开库的内部（很可能是机密的）运作情况。</span><span class="sxs-lookup"><span data-stu-id="9a508-241">However, this exposes the inner (potentially confidential) workings of your library.</span></span>
* <span data-ttu-id="9a508-242">但至少类型及其成员应具有 `<summary>` 标记，因为其内容是 IntelliSense 所需要的。</span><span class="sxs-lookup"><span data-stu-id="9a508-242">At a bare minimum, types and their members should have a `<summary>` tag because its content is needed for IntelliSense.</span></span>
* <span data-ttu-id="9a508-243">应使用句号结尾的完整句子编写文档文本。</span><span class="sxs-lookup"><span data-stu-id="9a508-243">Documentation text should be written using complete sentences ending with full stops.</span></span>
* <span data-ttu-id="9a508-244">完全支持部分类，并且该类型的文档信息将串联为单个条目。</span><span class="sxs-lookup"><span data-stu-id="9a508-244">Partial classes are fully supported, and documentation information will be concatenated into a single entry for that type.</span></span>
* <span data-ttu-id="9a508-245">编译器验证 `<exception>`、`<include>`、`<param>`、`<see>`、`<seealso>` 和 `<typeparam>` 标记的语法。</span><span class="sxs-lookup"><span data-stu-id="9a508-245">The compiler verifies the syntax of the `<exception>`, `<include>`, `<param>`, `<see>`, `<seealso>` and `<typeparam>` tags.</span></span>
- <span data-ttu-id="9a508-246">编译器验证某些参数，这些参数包含文件路径和对代码其余部分的引用。</span><span class="sxs-lookup"><span data-stu-id="9a508-246">The compiler validates the parameters that contain file paths and references to other parts of the code.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a508-247">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a508-247">See also</span></span>
[<span data-ttu-id="9a508-248">XML 文档注释（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="9a508-248">XML Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/xml-documentation-comments.md)

[<span data-ttu-id="9a508-249">建议的文档注释标记（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="9a508-249">Recommended Tags for Documentation Comments (C# Programming Guide)</span></span>](programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

